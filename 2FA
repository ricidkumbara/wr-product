# 2FA Authentication

### Get 2FA QR Code
`GET /auth/setting-2fa/qrcode`

Response Body
```json
{
  "statusCode": 200,
  "base64_code": "data:/image, base64xxxxx"
}
```

### Validate 2FA
`GET /auth/setting-2fa/validate`

Request Body
```json
{
  "token": "secret"
}
```

Response Body
```json
{
  "statusCode": 200,
  "message": "OK"
}
```

### Login with 2FA
`GET /auth/validate-2fa`

Request Body
```json
{
  "username": "secret",
  "password": "secret",
  "capcha": "secret",
  "token": "secret",
}
```

Response Body
```json
{
  "statusCode": 200,
  "message": "OK"
}
```
