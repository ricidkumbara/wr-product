# Tab

### Get
`GET /master/tab-form/tab`

Query Param (optional), default value with retrieve all list
```yaml
# available, used, all
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

### Find
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

### Update - Set Active
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

### Update - Rename
`PATCH /master/tab-form/tab/{id}/rename`

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

### Update - Set Mandatory
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

# Field

### Get
`GET /master/tab-form/tab/{tabId}/field`

Query Param (optional), default value with retrieve all list
```yaml
# available, used, all
?status=available
```

Response Body
```json
{
  "statusCode": 200,
  "data": [
    {
      "id": "encrypted-uuid-1",
      "tab_id": "encrypted-uuid-1",
      "name_code_field": "facility",
      "name": "Benefit",
      "field_type": "input",
      "form_type": "text",
      "max_value": 20,
      "class": "col-span-12 md:col-span-6",
      "placeholder": "Benefit",
      "is_border_top": true,
      "is_mandatory": true,
      "is_active": true,
      "is_deleted": false,
    },
    {
      "id": "encrypted-uuid-2",
      "tab_id": "encrypted-uuid-2",
      "name_code_field": "start_date",
      "name": "Start Date",
      "field_type": "input",
      "form_type": "text",
      "max_value": 20,
      "class": "col-span-12 md:col-span-6",
      "placeholder": "Your first day",
      "is_border_top": true,
      "is_mandatory": true,
      "is_active": true,
      "is_deleted": false,
    }
  ]
}
```

### Find
`GET /master/tab-form/tab/{tabId}/field/{fieldId}`

Response Body
```json
{
  "statusCode": 200,
  "data": {
    "id": "encrypted-uuid-2",
    "tab_id": "encrypted-uuid-2",
    "name_code_field": "start_date",
    "name": "Start Date",
    "field_type": "input",
    "form_type": "text",
    "max_value": 20,
    "class": "col-span-12 md:col-span-6",
    "placeholder": "Your first day",
    "is_border_top": true,
    "is_mandatory": true,
    "is_active": true,
    "is_deleted": false,
  }
}
```

### Update - Set Active
`PATCH /master/tab-form/tab/{tabId}/field/{fieldId}/active`

Request Body
```json
{
  "is_active": true  
}
```

Response Body
```json
{
  "statusCode": 200,
  "message": "Successfully Activate Field"
}
```

### Update - Rename
`PATCH /master/tab-form/tab/{tabId}/field/{fieldId}/rename`

Request Body
```json
{
  "name": "Start Date Updated"  
}
```

Response Body
```json
{
  "statusCode": 200,
  "message": "Successfully Rename Field"
}
```

### Update - Mandatory
`PATCH /master/tab-form/tab/{tabId}/field/{fieldId}/mandatory`

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
