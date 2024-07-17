# Tab

### Get Tab
`GET /master/tab-form/tab`

Query Param (optional), default value with retrieve all list
```yaml
# avaiable, used, all
?status=available
```

Response Body
```json
{
  "statusCode": 200,
  "data": [
    {
      "id": "encrypted-uuid-1",
      "code_tab": "education",
      "name": "Education",
      "icon": "MortarboardIcon",
      "is_active": true,
      "sort": true,
      "is_multiple": true,
      "is_mandatory": true
    },
    {
      "id": "encrypted-uuid-2",
      "code_tab": "work_experience",
      "name": "Work Experience",
      "icon": "BriefcaseIcon",
      "is_active": true,
      "sort": true,
      "is_multiple": true,
      "is_mandatory": true
    }
  ]
}
```

### Find Tab
`GET /master/tab-form/tab/{id}`

Response Body
```json
{
  "statusCode": 200,
  "data": {
    "id": "encrypted-uuid-2",
    "code_tab": "work_experience",
    "name": "Work Experience",
    "icon": "BriefcaseIcon",
    "is_active": true,
    "sort": true,
    "is_multiple": true,
    "is_mandatory": true
  }
}
```

### Update Tab - Set Active
`PATCH /master/tab-form/tab/{id}/active`

Request Body
```json
{
  "is_active": true,
}
```

Response Body
```json
{
  "statusCode": 200,
  "message": "Successfully Activated Tab"
}
```

### Update Tab - Rename
`PATCH /master/tab-form/tab/{id}/name`

Request Body
```json
{
  "name": "Work Experience Update",
}
```

Response Body
```json
{
  "statusCode": 200,
  "message": "Successfully Rename Tab"
}
```

### Update Tab - Set Mandatory
`PATCH /master/tab-form/tab/{id}/mandatory`

Request Body
```json
{
  "is_mandatory": true
}
```

Response Body
```json
{
  "statusCode": 200,
  "message": "Successfully Set Mandatory Tab"
}
```

<hr>

# Form

### Get Form

### Find Form

### Save Form

### Update Form 

### Delete Form
