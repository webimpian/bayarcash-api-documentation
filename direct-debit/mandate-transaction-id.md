# Mandate Transaction ID

***

<mark style="color:red;">v2</mark>  <mark style="color:blue;">`GET`</mark>  `console.bayar.cash/api/v2/mandates/transactions/{transaction_id}`\
<mark style="color:red;">v3</mark> <mark style="color:blue;">`GET`</mark>  `api.console.bayar.cash/v3/mandates/transactions/{transaction_id}`

***



Example of JSON structured response.



```json
{
    "id": "trx_GPk868",
    "updated_at": "2024-06-27 17:57:01",
    "datetime": "2024-06-27 17:56:42",
    "order_number": "DDD-24060323",
    "payer_name": "Mohd Ali",
    "payer_email": "mohd.ali@gmail.com",
    "payer_telephone_number": "60197019001",
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
        "ref_no": null
    },
    "payment_gateway": {
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
        "updated_at": "2024-06-27T09:57:27.000000Z",
        "mandate_reference_number": "E-20241719482236",
        "order_number": "DDD-24060323",
        "application_reason": "Enrollment of DDD-24060323",
        "frequency_mode": "MT",
        "frequency_mode_label": "Monthly",
        "effective_date": "2024-06-30",
        "expiry_date": "2025-06-30",
        "currency": "MYR",
        "amount": 200,
        "payer_name": "Mohd Ali",
        "payer_id": "910909122211",
        "payer_id_type": "1",
        "payer_bank_account_number": "033112228108",
        "payer_email": "mohd.ali@gmail.com",
        "payer_telephone_number": "60197019001",
        "status": 4,
        "status_description": "Terminated",
        "return_url": "https://website.net/transactions/mandates/callback",
        "metadata": null,
        "portal": "Portal ABC",
        "merchant": {
            "name": "Web Impian Sdn. Bhd.",
            "email": "webimpian.merchant@gmail.com"
        }
    }
}
```

