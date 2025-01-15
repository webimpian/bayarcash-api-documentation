# FPX Bank List

***

<mark style="color:red;">v2</mark> <mark style="color:blue;">`GET`</mark> `console.bayar.cash/api/v2/banks`\
<mark style="color:red;">v3</mark> <mark style="color:blue;">`GET`</mark> `api.console.bayar.cash/v3/banks`



This API will return list of bank codes for FPX and Direct Debit payment channel. Use this list for usage of `payer_bank_code` and `payer_bank_name` in payment request.

Sending via command line using cURL.



```markup
curl -X GET https://console.bayar.cash/api/v2/banks \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
```



JSON structured response.



```json
[
    {
        "bank_display_name": "Affin Bank",
        "bank_name": "Affin Bank Berhad",
        "bank_code": "ABB0233",
        "bank_code_hashed": "472e729c398dbc372d96f5d852393b76",
        "bank_availability": true
    },
    {
        "bank_display_name": "AGRONet",
        "bank_name": "Bank Pertanian Malaysia Berhad (AgroBank)",
        "bank_code": "AGRO01",
        "bank_code_hashed": "6f692c003561e3c52f0d993805b6be01",
        "bank_availability": true
    }
]
```

