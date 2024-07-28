# Mandate ID

***

<mark style="color:blue;">`GET`</mark> `/api/v2/mandates/{mandate_id}`



JSON structured response.



```json
{
  "id": "md_MGWpzp",
  "updated_at": "2024-07-21T15:07:09.000000Z",
  "mandate_reference_number": "E-20230408F00230289",
  "order_number": "1-680-631-498-908819",
  "application_reason": "Enrollment for 1-680-631-498-908819",
  "frequency_mode": "MT",
  "frequency_mode_label": "Monthly",
  "effective_date": "2023-04-05",
  "expiry_date": null,
  "currency": "MYR",
  "amount": 10,
  "payer_name": "Mohd Ali",
  "payer_id": "910810065921",
  "payer_id_type": "1",
  "payer_bank_account_number": "1602219363111",
  "payer_email": "mohd.ali@gmail.com",
  "payer_telephone_number": "60199971822",
  "status": 3,
  "status_description": "Active",
  "return_url": "http://website.net/transaction/mandates/callback",
  "metadata": null,
  "portal": "Portal ABC",
  "merchant": {
    "name": "Web Impian Sdn. Bhd.",
    "email": "webimpian.merchant@gmail.com"
  }
}
```

