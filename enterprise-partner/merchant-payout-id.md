# Merchant Payout ID

***

<mark style="color:red;">v2</mark>  <mark style="color:blue;">`GET`</mark>  `console.bayar.cash/api/v2/payouts/{payout_id}`\
<mark style="color:red;">v3</mark> <mark style="color:blue;">`GET`</mark>  `api.console.bayar.cash/v3/payouts/{payout_id}`&#x20;

***



Enterprise partners are able to retrieve settlement summary for all merchants registered from their API key. Example of JSON structured response.



```json
{
    "id": "pay_qK7gOq",
    "created_at": "2025-01-14 10:57:33",
    "merchant": {
        "id": "usr_Zz29gG",
        "name": "ABC Sdn. Bhd.",
        "email": "admin@abc.com"
    },
    "status": "Processing",
    "reference_number": "P1736823453599915",
    "split_payout": "-",
    "bank_transaction_reference_number": null,
    "amount": "1.50"
}
```

