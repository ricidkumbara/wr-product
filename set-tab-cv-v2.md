# Tab
<!-- 
### Get Current Step
`GET /master/form-setting/step`

Response Body
```json
{
  "statusCode": 200,
  "company_id": "encrypted-uuid",
  "step": 1, // 1 Set Tab, 2 Set Field
  "status": "draft" // draft, submit
}
``` -->

### Get
`GET /master/form-setting/tab`

Query Param (optional), default value with retrieve all list
```yaml
# available, used, all
?status=available
```

Response Body
```json
{
  "statusCode": 200,
  "company_id": "encrypted-uuid",
  "company_name": "BI",
  "data": [
    {
      "id": "encrypted-uuid-1",
      "code_tab": "education",
      "name": "Education",
      "icon": "MortarboardIcon",
      "is_active": true,
      "sort": 1,
      "is_multiple": true,
      "is_mandatory": true,
      "is_configured": true, // Untuk keperluan icon thumbs, true jika sudah konfigurasi tab & form
    },
    {
      "id": "encrypted-uuid-2",
      "code_tab": "work_experience",
      "name": "Work Experience",
      "icon": "BriefcaseIcon",
      "is_active": true,
      "sort": 2,
      "is_multiple": true,
      "is_mandatory": true,
      "is_configured": true, // Untuk keperluan icon thumbs, true jika sudah konfigurasi tab & form
    }
  ]
}
```

### Find
`GET /master/form-setting/tab/{id}`

Response Body
```json
{
  "statusCode": 200,
  "company_id": "encrypted-uuid",
  "company_name": "BI",
  "data": {
    "id": "encrypted-uuid-2",
    "code_tab": "work_experience",
    "name": "Work Experience",
    "icon": "BriefcaseIcon",
    "is_active": true,
    "sort": 2,
    "is_multiple": true,
    "is_mandatory": true,
    "is_configured": true, // Untuk keperluan icon thumbs, true jika sudah konfigurasi tab & form
  }
}
```

### Save / Update
`POST /master/form-setting/tab`

Request Body
```json
{
  "status": "draft", // draft, submit
  "data": [
    {
      "tab_id": "uuid-1",
      "name": "Test-1",
      "is_mandatory": 1,
      "sort": 1
    },
    {
      "tab_id": "uuid-2",
      "name": "Test-2",
      "is_mandatory": 1,
      "sort": 2
    }
  ]
}
```

Response Body
```json
{
  "statusCode": 200,
  "message": "Successfully Saved"
}
```

<hr>

# Field

### Get
`GET /master/form-setting/tab/{tabId}/field`

Query Param (optional), default value with retrieve all list
```yaml
# available, used, all
?status=available
```

Response Body
```json
{
  "statusCode": 200,
  "company_id": "encrypted-uuid",
  "company_name": "BI",
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
      "sort": 1
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
      "sort": 2
    }
  ]
}
```

### Find
`GET /master/form-setting/tab/{tabId}/field/{fieldId}`

Response Body
```json
{
  "statusCode": 200,
  "company_id": "encrypted-uuid",
  "company_name": "BI",
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
    "sort": 2
  }
}
```

### Save / Update
`POST /master/form-setting/tab/{tabId}/field`

Request Body
```json
{
  "status": "draft", // draft, submit
  "data": [
    {
      "field_id": "uuid-1",
      "name": "Test-1",
      "is_mandatory": 1,
      "sort": 1
    },
    {
      "field_id": "uuid-2",
      "name": "Test-2",
      "is_mandatory": 1,
      "sort": 2
    }
  ]
}
```

Response Body
```json
{
  "statusCode": 200,
  "message": "Successfully Saved"
}
```
