# All Transactions

***

<mark style="color:red;">v3</mark>  <mark style="color:blue;">`GET`</mark>  `api.console.bayar.cash/v3/transactions`

***



At any given time, you can request a transaction to check on the current status. It will return the transaction object.

Example of sending GET request with cURL.



```markup
curl -X GET https://api.console.bayar.cash/v3/transactions \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
```



Example of JSON structured response.



```json
{
    "data": [
        "id": "trx_q6LJdl",
        "updated_at": "2023-05-26 13:35:01",
        "datetime": "2023-05-26 13:29:06",
        "order_number": "24354620275",
        "payer_name": "Mohd Ali",
        "payer_email": "mohd.ali@gmail.com",
        "payer_telephone_number": "60111157245",
        "currency": "MYR",
        "amount": 50,
        "exchange_reference_number": "1-685-0718-946-53336",
        "exchange_transaction_id": "23052613290110936",
        "payer_bank_name": "Bank Islam",
        "status": 3,
        "status_description": "Approved",
        "return_url": "https://website.net/api/return_url",
        "metadata": null,
        "payout": {
            "reference_number": "P1685011113148329"
        },
        "payment_gateway": {
            "name": "FPX",
            "code": "FPX"
        },
        "portal": "Portal ABC",
        "merchant": {
            "name": "Web Impian Sdn. Bhd.",
            "email": "webimpian.merchant@gmail.com"
        }
    ],
    "links": {
        "first": "https://api.console.bayar.cash/v3/transactions?page=1",
        "last": "https://api.console.bayar.cash/v3/transactions?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "links": [
            {
                "url": null,
                "label": "&laquo; Previous",
                "active": false
            },
            {
                "url": "https://api.console.bayar.cash/v3/transactions?page=1",
                "label": "1",
                "active": true
            },
            {
                "url": null,
                "label": "Next &raquo;",
                "active": false
            }
        ],
        "path": "https://api.console.bayar.cash/v3/transactions",
        "per_page": 15,
        "to": 6,
        "total": 6
    }
}
```

