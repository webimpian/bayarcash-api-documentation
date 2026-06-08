# All Mandates

***

<mark style="color:red;">v3</mark>  <mark style="color:blue;">`GET`</mark>  `api.console.bayar.cash/v3/mandates?{query_parameter}`

***



Retrieve a paginated list of Direct Debit mandates. Available query parameters are as below:



| Name                        | Description                                                                                                |
| --------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `order_number`              |                                                                                                            |
| `mandate_reference_number`  |                                                                                                            |
| `status`                    | Please [refer this page](https://api.webimpian.support/bayarcash/direct-debit/callback) for status code    |
| `payer_email`               |                                                                                                            |
| `payer_id`                  |                                                                                                            |

***



Example of sending <mark style="color:blue;">`GET`</mark> request with cURL.



```markup
curl -X GET https://api.console.bayar.cash/v3/mandates?order_number=DDD-24060323 \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
```



Example of JSON structured response.



```json
{
    "data": [
        {
            "id": "md_MGWpzp",
            "updated_at": "2024-07-21T15:07:09.000000Z",
            "mandate_reference_number": "E-20230408F00230289",
            "order_number": "DDD-24060323",
            "application_reason": "Enrollment for DDD-24060323",
            "frequency_mode": "MT",
            "frequency_mode_label": "Monthly",
            "effective_date": "2023-04-05",
            "expiry_date": null,
            "currency": "MYR",
            "amount": 10,
            "payer_name": "Mohd Ali",
            "payer_id": "910810065921",
            "payer_id_type": "1",
            "payer_bank_account_number": "*********3111",
            "payer_email": "mohd.ali@gmail.com",
            "payer_telephone_number": "60199971822",
            "status": 3,
            "status_description": "Active",
            "return_url": "http://website.net/transaction/mandates/callback",
            "metadata": null,
            "portal": "Portal ABC",
            "application_histories": [],
            "merchant": {
                "name": "Web Impian Sdn. Bhd.",
                "email": "webimpian.merchant@gmail.com"
            }
        }
    ],
    "links": {
        "first": "https://api.console.bayar.cash/v3/mandates?page=1",
        "last": "https://api.console.bayar.cash/v3/mandates?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "path": "https://api.console.bayar.cash/v3/mandates",
        "per_page": 15,
        "to": 1,
        "total": 1
    }
}
```
