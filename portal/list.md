# Portal List

***

<mark style="color:red;">v2</mark>  <mark style="color:blue;">`GET`</mark>  `console.bayar.cash/api/v2/portals`\
<mark style="color:red;">v3</mark>  <mark style="color:blue;">`GET`</mark>  `api.console.bayar.cash/v3/portals`

***



Retrieve list of portal in Bayarcash. Sending via command line using cURL.



```markup
curl -X GET https://api.console.bayar.cash/v3/portals \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
```



JSON structured response.



```json
{
    "data": [
        {
            "id": 931,
            "created_at": "2024-10-19 12:47:07",
            "portal_key": "8baf5e234dd88c2d1375d5f386d78d8f",
            "portal_name": "Payment Link",
            "url": "https://bcl.my/",
            "transaction_notification_email": "hai@bayarcash.com",
            "custom_payment_button_text": null,
            "payment_channels": [
                {
                    "id": 1,
                    "code": "FPX",
                    "name": "FPX"
                },
                {
                    "id": 3,
                    "code": "FpxDirectDebit",
                    "name": "Direct Debit"
                },
                {
                    "id": 4,
                    "code": "FpxLineOfCredit",
                    "name": "FPX Line of Credit"
                }
            ]
        }
    ],
    "links": {
        "first": "https://api.console.bayar.cash/v3/portals?page=1",
        "last": "https://api.console.bayar.cash/v3/portals?page=1",
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
                "label": "pagination.previous",
                "active": false
            },
            {
                "url": "https://api.console.bayar.cash/v3/portals?page=1",
                "label": "1",
                "active": true
            },
            {
                "url": null,
                "label": "pagination.next",
                "active": false
            }
        ],
        "path": "https://api.console.bayar.cash/v3/portals",
        "per_page": 15,
        "to": 2,
        "total": 2,
        "merchant": {
            "name": "Bayarcash Sdn. Bhd.",
            "email": "hai@bayarcash.com",
            "created_at": "2024-10-19 12:45:42"
        }
    }
}
```

