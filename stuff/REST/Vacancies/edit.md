Vacancies/edit
===

Parameters:

| Param        | Required           | Description  |
| ------------- |:-------------:| -----|
| method      | yes | Method name |
| access_token      | yes | API access token |
| project_id | yes      | ID of the Vacancy |
| title | no      | Vacancy title |
| reference | no      | Vacancy reference |
| crm_reference | no      | CRM reference |
| start_date | no      | Vacancy start date |
| job_benefits | no      | Vacancy job benefits |
| job_salary_min | no      | Vacancy salary min |
| job_salary_max | no      | Vacancy salary max |
| job_salary_per | no      | Vacancy salary max |
| status | no      | Vacancy status. Can be: `active`, `placed`, `archived`  |

Plain php example:
```php
$idibuAPIEndpoint = 'https://v3.idibu.com/c/oauth/v1';
$accessToken = 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx';

$data = [
'method' => 'vacancies/edit',
'access_token' => $accessToken,
'project_id' => 123, //idibu v3 vacancy id
'status' => 'archived' //'active', 'placed' or 'archived'
];

$ch = curl_init($idibuAPIEndpoint);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_POSTFIELDS, http_build_query($data));
$response = curl_exec($ch);
curl_close($ch);
```
