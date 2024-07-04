# Forgot Password

### Forgot Password
`POST /auth/forgot-password`

Header: 
```yaml
Content-Type: application/json
X-Referer: http://localhost:3000 # ambil current url dari FE (tanpa path)
```

Request Body
```json
{
  "email": "ricidkumbara@gmail.com",
  "gRecaptchaToken": "secret"
}
```

Response Body - OK
```json
{
  "statusCode": 200,
  "message": "OK"
}
```

Response Body - Error
```json
{
  "statusCode": 404,
  "error": {
    "message": "Email Not Found"
  }
}
```

<hr>

### Validate Link
`GET /auth/forgot-password/{token}/validate-link`

Response Body - OK
```json
{
  "statusCode": 200,
  "message": "OK"
}
```

Response Body - Error
```json
{
  "statusCode": 400,
  "error": {
    "code": "ERR-001",
    "message": "Link Expired"
  }
}
```

Error Code List:
- ERR-001: Link Expired 
- ERR-002: Link has been Confirmed 
- ERR-003: Link Not Found

<hr>

### Reset Password
`PUT /auth/forgot-password/{token}/reset`

Request Body
```json
{
  "password": "secret",
  "confirm_password": "secret",
}
```

Response Body - OK
```json
{
  "statusCode": 200,
  "message": "OK"
}
```


Response Body - Error
```json
{
  "statusCode": 400,
  "error": {
    "code": "ERR-004",
    "message": "Cannot use same password within 3 period back history"
  }
}
```

Error Code List:
- ERR-004: Cannot use same password within 3 period back history 
- ERR-005: Password Requirement Not Match 
- ERR-003: Passsword and Confirm Password Not Match