# Update Inactive e-Mandate Status to Active

***

<mark style="color:red;">v2</mark> <mark style="color:red;">`PATCH`</mark>  `console.bayar.cash/api/v2/mandates/{mandate_id}/activate`\
<mark style="color:red;">v3</mark> <mark style="color:red;">`PATCH`</mark>  `api.console.bayar.cash/v3/mandates/{mandate_id}/activate`

***


At any given time, you can request to update any `inactive` Direct Debit to `active`.

> Notes: This action will re-activate and include the Direct Debit in the next deduction. This action only allowed for the Direct Debit with status `inactive`.


Example of JSON structured response.



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
  "payer_name": "MOHD ALI",
  "payer_id": "800810065921",
  "payer_id_type": "1",
  "payer_bank_account_number": "1602119463111",
  "payer_email": "m.ali@gmail.com",
  "payer_telephone_number": "0199991122",
  "status": 3,
  "status_description": "Active",
  "return_url": "http://donations.net/donations/mandates/callback",
  "metadata": null,
  "portal": "Donation Portal",
  "merchant": {
    "name": "Sekolah Agama.",
    "email": "ska@gmail.com"
  }
}
```

