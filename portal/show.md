# Portal ID

***

<mark style="color:red;">v3</mark>  <mark style="color:blue;">`GET`</mark>  `api.console.bayar.cash/v3/portals/{portal_id}`

***



Retrieve a single portal by its ID. It will return the portal object together with its enabled payment channels and merchant details.

Example of sending <mark style="color:blue;">`GET`</mark> request with cURL.



```markup
curl -X GET https://api.console.bayar.cash/v3/portals/cbp_aZ9Klm \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
```



Example of JSON structured response.



```json
{
    "id": "cbp_aZ9Klm",
    "created_at": "2024-10-19 12:47:07",
    "portal_key": "8baf5e234dd88c2d1375d5f386d78d8f",
    "portal_name": "Payment Link",
    "website_url": "https://bcl.my/",
    "transaction_notification_email": "hai@bayarcash.com",
    "secondary_transaction_notification_email": null,
    "custom_payment_button_text": null,
    "enabled_sms_on_successful_transaction": 0,
    "split_payment_enabled": false,
    "split_payment_merchants": [],
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
    ],
    "merchant": {
        "id": "usr_kP3xQ2",
        "name": "Web Impian Sdn. Bhd.",
        "email": "webimpian.merchant@gmail.com"
    }
}
```
