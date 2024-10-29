# Merchant Registration

***

<mark style="color:green;">`POST`</mark> `/api/v2/merchant-registrations`



Sending via command line using cURL.



```markup
curl -X POST https://console.bayar.cash/api/v2/merchant-registrations \
  --header 'Content-Type: application/json' \
  --header 'X-API-Key: <Enterprise_Partner_API_Key>' \
  --data-raw '{
        "organisation_name": string,
        "organisation_registration_number": string,
        "organisation_bank_id": integer,
        "organisation_bank_account_holder": string,
        "organisation_bank_account_number": string,
        "login_name": string,
        "login_email": string,
        "login_mobile_number": integer,
        "password": string,
        "password_confirmation": string
      }'
```

