# All Mandate Transactions

***

<mark style="color:red;">v3</mark>  <mark style="color:blue;">`GET`</mark>  `api.console.bayar.cash/v3/mandates/transactions?{query_parameter}`

***



Retrieve a paginated list of Direct Debit (e-Mandate) transactions, covering both mandate application and deduction transactions. Available query parameters are as below:



| Name                        | Description                                                                                              |
| --------------------------- | -------------------------------------------------------------------------------------------------------- |
| `order_number`              |                                                                                                          |
| `status`                    | Please [refer this page](https://api.webimpian.support/bayarcash/direct-debit/callback) for status code  |
| `exchange_reference_number` |                                                                                                          |
| `payer_email`               | Filter transactions by payer email                                                                       |

***



Example of sending <mark style="color:blue;">`GET`</mark> request with cURL.



```markup
curl -X GET https://api.console.bayar.cash/v3/mandates/transactions?order_number=DDD-24060323 \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
```



Example of JSON structured response.



```json
{
    "data": [
        {
            "id": "trx_GPk868",
            "transaction_type": "Deduction",
            "created_at": "2024-06-27 17:56:42",
            "payer_name": "Mohd Ali",
            "payer_email": "mohd.ali@gmail.com",
            "payer_telephone_number": "60197019001",
            "order_number": "DDD-24060323",
            "currency": "MYR",
            "amount": 10,
            "exchange_reference_number": "1-719-482-202-565809",
            "exchange_transaction_id": "2406271756420574",
            "payer_bank_name": "SBI Bank A",
            "status": 3,
            "status_description": "Approved",
            "return_url": "https://website.net/transactions/mandates/callback",
            "metadata": null,
            "payout": {
                "reference_number": null
            },
            "payment_gateway": {
                "id": 3,
                "name": "Direct Debit",
                "code": "FpxDirectDebit"
            },
            "portal": "Portal ABC",
            "merchant": {
                "name": "Web Impian Sdn. Bhd.",
                "email": "webimpian.merchant@gmail.com"
            },
            "mandate": {
                "id": "md_nq5oAG",
                "mandate_reference_number": "E-20241719482236",
                "order_number": "DDD-24060323",
                "frequency_mode": "MT",
                "frequency_mode_label": "Monthly",
                "amount": 200,
                "status": 3,
                "status_description": "Active"
            }
        }
    ],
    "links": {
        "first": "https://api.console.bayar.cash/v3/mandates/transactions?page=1",
        "last": "https://api.console.bayar.cash/v3/mandates/transactions?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "path": "https://api.console.bayar.cash/v3/mandates/transactions",
        "per_page": 25,
        "to": 1,
        "total": 1
    }
}
```
