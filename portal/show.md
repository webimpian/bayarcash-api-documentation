# Portal ID

***

<mark style="color:red;">v2</mark>  <mark style="color:blue;">`GET`</mark>  `console.bayar.cash/api/v2/portals/{portal_id}`<br>
<mark style="color:red;">v3</mark> <mark style="color:blue;">`GET`</mark>  `api.console.bayar.cash/v3/portals/{portal_id}`

***



Retrieve a single portal by its ID. It will return the portal object together with its enabled payment channels.

Example of sending <mark style="color:blue;">`GET`</mark> request with cURL.



```markup
curl -X GET https://api.console.bayar.cash/v3/portals/prt_PGMo1q \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
```



Example of JSON structured response.



```json
{
    "id": "prt_PGMo1q",
    "created_at": "2024-10-19 12:47:07",
    "portal_key": "8baf5e234dd88c2d1375d5f386d78d8f",
    "portal_name": "Payment Link",
    "url": "https://bcl.my/",
    "transaction_notification_email": "hai@bayarcash.com",
    "secondary_transaction_notification_email": null,
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
        }
    ]
}
```
