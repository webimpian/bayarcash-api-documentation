# Merchant Settlement Summary

***

<mark style="color:red;">v2</mark>  <mark style="color:blue;">`GET`</mark>  `console.bayar.cash/api/v2/payouts`\
<mark style="color:red;">v3</mark> <mark style="color:blue;">`GET`</mark>  `api.console.bayar.cash/v3/payouts`&#x20;

***



Enterprise partners are able to retrieve settlement summary for all merchants registered from their API key. Example of JSON structured response.



```json
{
    "data": [
        {
            "id": "pay_YZ6jNY",
            "created_at": "2024-11-01 14:20:06",
            "status": "Processing",
            "package_subscription_id": 399,
            "payment_channel": "FPX",
            "reference_number": "P11229399384849",
            "split_payout": "Parent",
            "bank_transaction": null,
            "amount": "97.00"
        }
    ],
    "links": {
        "first": "https://api.console.bayar.cash/v3/payouts?page=1",
        "last": "https://api.console.bayar.cash/v3/payouts?page=2",
        "prev": null,
        "next": "https://api.console.bayar.cash/v3/payouts?page=2"
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 2,
        "links": [
            {
                "url": null,
                "label": "&laquo; Previous",
                "active": false
            },
            {
                "url": "https://api.console.bayar.cash/v3/payouts?page=1",
                "label": "1",
                "active": true
            },
            {
                "url": "https://api.console.bayar.cash/v3/payouts?page=2",
                "label": "2",
                "active": false
            },
            {
                "url": "https://api.console.bayar.cash/v3/payouts?page=2",
                "label": "Next &raquo;",
                "active": false
            }
        ],
        "path": "https://api.console.bayar.cash/v3/payouts",
        "per_page": 15,
        "to": 15,
        "total": 27
    }
}
```

