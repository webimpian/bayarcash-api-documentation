# Transaction ID

***

<mark style="color:green;">`GET`</mark> `api/v2/transactions/{transaction_id}`

At any given time, you can request a transaction ID to check on the status. It will return the transaction object.

Sending via command line using cURL.



```markup
curl -X GET https://console.bayar.cash/api/v2/transactions/trx_z88ymJ \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <Personal_Access_Token>'
```



JSON structure response.



```json
{
  "data": {
    "id": "trx_z88ymJ",
    "created_at": "2024-06-27 17:51:59",
    "updated_at": "2024-06-27 17:52:32",
    "datetime": "2024-06-27 17:51:59",
    "order_no": "24065427",
    "buyer_name": "Ali Hanafiah",
    "buyer_email": "alihanafiah@mail.com",
    "buyer_tel_no": "60199009000",
    "currency": "MYR",
    "amount": "4.00",
    "nett_payout_amount": "4.00",
    "fpx_exchange_order_no": "1-719-481-919-204580",
    "fpx_transaction_id": "2406271751590553",
    "business_model": "B2C",
    "buyer_bank_name": "Maybank2u",
    "status_code": 3,
    "status": "Successful",
    "status_description": "Approved",
    "return_url": "https://website.com/api/transactions?Transaction_ID=24065427",
    "raw": [],
    "description": null,
    "remarks": null,
    "payout": {
      "ref_no": "P1718294192365977"
    },
    "payment_gateway": {
      "name": "FPX",
      "code": "fpx"
    },
    "portal": "Portal Website A",
    "merchant": {
      "name": "Syarikat Sdn. Bhd.",
      "email": "notification@syarikat.com"
    }
  }
}
```

