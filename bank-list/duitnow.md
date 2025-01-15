# DuitNow

***

<mark style="color:red;">v2</mark>  <mark style="color:blue;">`GET`</mark>  `console.bayar.cash/api/v2/duitnow/dobw/banks`\
<mark style="color:red;">v3</mark>  <mark style="color:blue;">`GET`</mark>  `api.console.bayar.cash/v3/duitnow/dobw/banks`

***



This API will return list of bank codes for DuitNow Online Banking/Wallets (also known as DOBW or DuitNow OBW) payment channel. Use this list for usage of `payer_bank_code` and `payer_bank_name` in payment request.

Sending via command line using cURL.



```markup
curl -X GET https://api.console.bayar.cash/v3/duitnow/dobw/banks \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
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

