# Transaction ID

***

<mark style="color:blue;">`GET`</mark> `api/v2/transactions/{transaction_id}`



At any given time, you can request a transaction ID to check on the current status. It will return the transaction object.

Sending via command line using cURL.



```markup
curl -X GET https://console.bayar.cash/api/v2/transactions/trx_z88ymJ \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
```



JSON structured response.



```json
{
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
}
```

