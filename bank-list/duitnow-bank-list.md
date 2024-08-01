# DuitNow Bank List

***

<mark style="color:blue;">`GET`</mark> `/api/v2/duitnow/dobw/banks`&#x20;



This API will return list of bank codes for DuitNow Online Banking/Wallets (also known as DOBW) payment channel. Use this list for usage of `payer_bank_code` and `payer_bank_name` in payment request.

Sending via command line using cURL.



```markup
curl -X GET https://console.bayar.cash/api/v2/duitnow/dobw/banks \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <Personal_Access_Token>'
```



JSON structured response.



```json
[
    {
        "bank_name": "Affin Bank",
        "bank_code": "PHBMMYKL",
        "bank_availability": true
    },
    {
        "bank_name": "Agro Bank",
        "bank_code": "AGRO01",
        "bank_availability": true
    }
]
```

