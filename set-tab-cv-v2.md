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

###
`POST /master/tab-form/tab`

Request Body
```json
{
  "status": "draft", // draft, submit
  "data": [
    {
      "tab_id": "uuid-1",
      "name": "Test-1",
      "is_mandatory": 1
    },
    {
      "tab_id": "uuid-2",
      "name": "Test-2",
      "is_mandatory": 1
    }
  ]
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

###
`POST /master/tab-form/tab/{tabId}/field`

Request Body
```json
{
  "status": "draft", // draft, submit
  "data": [
    {
      "field_id": "uuid-1",
      "name": "Test-1",
      "is_mandatory": 1
    },
    {
      "field_id": "uuid-2",
      "name": "Test-2",
      "is_mandatory": 1
    }
  ]
}
```
