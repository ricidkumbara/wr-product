
# 2FA Authentication

### Get 2FA QR Code
`GET /auth/setting-2fa/qrcode`

Header
```yaml
Authorization: Bearer xxxxx
```

Response Body
```json
{
  "statusCode": 200,
  "data": {
    "qr_code": "data:image/png;base64,xxxxx"
  }
}
```

### Enable 2FA
`GET /auth/setting-2fa/enable`

Header
```yaml
Authorization: Bearer xxxxx
```

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
  "message": "2FA Authenticator Successfully Enabled"
}
```

### Disable 2FA
`GET /auth/setting-2fa/disable`

Header
```yaml
Authorization: Bearer xxxxx
```

Response Body
```json
{
  "statusCode": 200,
  "message": "2FA Authenticator Successfully Disabled"
}
```

### Get 2FA Status
`GET /auth/setting-2fa/status`

Header
```yaml
Authorization: Bearer xxxxx
```

Response Body
```json
{
  "statusCode": 200,
  "data": {
    "status": "enabled" // enabled, disabled
  }
}
```

### Login with 2FA
- This API used at 2nd step after login using username & password
- Captcha should be regenerated

`GET /auth/login`

Request Body
```json
{
  "email": "secret",
  "password": "secret",
  "gRecaptchaToken": "regenerated_secret", // should re-generate new captcha
  "twoFactorAuthToken": "secret",
}

// Request body should encryted in data
// Example
// {
//   "data": "d29827a7da677b8594a5f22a2d197e04c3c6c0579f1b7ae4b00fd28f629a8ed61a1c066da39791c7a10b65a33dd0a37dd92d5adea2e84bdf3b6c41921c36acb584e59b5f82ff1f1f441671c7edae7d68965fb6cfe3c60fd650c35b85d2d94500162de559a23ee1"
// }
```

Response Body
```json
{
  "statusCode": 200,
  "data": "encrypted_payload"
}
```
