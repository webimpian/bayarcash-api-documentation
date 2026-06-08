# Payment Intent

***

<mark style="color:red;">v2</mark>  <mark style="color:green;">`POST`</mark>  `console.bayar.cash/api/v2/payment-intents`<br>
<mark style="color:red;">v3</mark>  <mark style="color:green;">`POST`</mark>  `api.console.bayar.cash/v3/payment-intents`

***



Initialize payment intent request to Bayarcash. Make sure your account is enabled for selected payment channel. By default only FPX channel is activated.



<table data-full-width="true"><thead><tr><th width="269">Name</th><th width="546">Description</th><th width="121">Type</th><th>Condition</th></tr></thead><tbody><tr><td><code>payment_channel</code></td><td>Refer payment channel page</td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>portal_key</code></td><td>Portal key retrieve from Bayarcash console</td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>order_number</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>amount</code></td><td></td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_name</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_email</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_telephone_number</code></td><td>Currently we only accept Malaysia number</td><td><code>integer</code></td><td>Optional</td></tr><tr><td><code>payer_bank_code</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>payer_bank_name</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>autosubmit_form</code></td><td>Auto-submit the payment to the selected bank (FPX only). Requires <code>payer_bank_code</code></td><td><code>boolean</code></td><td>Optional</td></tr><tr><td><code>metadata</code></td><td>Currently only support order items from WooCommerce plugin</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>return_url</code></td><td>Server to browser redirect callback (use <mark style="color:blue;"><code>GET</code></mark>)</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>callback_url</code></td><td>Server to server redirect callback (use <mark style="color:green;"><code>POST</code></mark>) - only available on v3</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>terminal_mode</code></td><td>Enable terminal (POS) mode</td><td><code>boolean</code></td><td>Optional</td></tr><tr><td><code>link_expired_at</code></td><td>Payment link expiry datetime (<code>Y-m-d H:i:s</code>). Defaults to 1 hour from creation</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>platform_id</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>checksum</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>verify_identity</code></td><td>Enable payer identity verification. Only for FPX (1) and FPX B2B (23), single channel only - only available on v3</td><td><code>boolean</code></td><td>Optional</td></tr><tr><td><code>fpx_eaccount_number</code></td><td>Payer's bank account number (max 40). <mark style="color:red;">Required</mark> when <code>verify_identity</code> is <code>true</code> - only available on v3</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>fpx_ebuyer_id</code></td><td>Payer's NRIC / Passport / Business Registration Number (max 40). <mark style="color:red;">Required</mark> when <code>verify_identity</code> is <code>true</code> - only available on v3</td><td><code>string</code></td><td>Optional</td></tr></tbody></table>

***



Example of sending <mark style="color:green;">`POST`</mark> request with cURL.



```markup
curl -X POST https://api.console.bayar.cash/v3/payment-intents \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>' \
  --data-raw '{
        "payment_channel": 5,
        "portal_key": string,
        "order_number": string,
        "amount": 100,
        "payer_name": string,
        "payer_email": string,
        "payer_telephone_number": integer,
        "payer_bank_code": string,
        "payer_bank_name": string,
        "metadata": string,
        "return_url": string,
        "platform_id": string,
        "checksum": string
      }'
```



Example of JSON structured response.



```json
{
    "type": "payment_intent", // only available on v3
    "id": "pi_MGWpzp", // only available on v3
    "payer_name": "Mohd Ali",
    "payer_email": "mohd.ali@gmail.com",
    "payer_telephone_number": "60193000123",
    "order_number": "1351",
    "amount": "21.10",
    "url": "https://console.bayar.cash/payment-intent/pi_MGWpzp"
}
```



***



## Payer Identity Verification <mark style="color:red;">v3</mark>



FPX supports payer identity verification — checking whether the buyer/purchaser and the payer are the same person/entity, including verification of the source of funds. This is based on the payer's registered bank account number and/or their NRIC/Passport/Business Registration Number.



**Requirements**

* `payment_channel` **must be a single channel** — either FPX (`1`) or FPX B2B (`23`). Multi-channel payment intents are not supported for identity verification.
* `payment_channel` is **required** when `verify_identity` is `true`.
* `verify_identity` must be set to `true`.
* `fpx_eaccount_number` (string, max 40 chars) — **Required**. Payer's bank account number.
* `fpx_ebuyer_id` (string, max 40 chars) — **Required**. Payer's NRIC / Passport Number / Business Registration Number.



**Example request**

```json
{
  "payment_channel": 1,
  "portal_key": "your-portal-key",
  "order_number": "ORD001",
  "amount": 100.00,
  "payer_name": "MOHD ALI",
  "payer_email": "m.ali@gmail.com",
  "verify_identity": true,
  "fpx_eaccount_number": "1234567890",
  "fpx_ebuyer_id": "900101145678"
}
```



**Verification result**

After payment completion, the transaction callback and `GET /v3/transactions/{id}` response will include:

* `payer_identity_verified` (boolean | null) — `true` if identity verified, `false` if not, `null` for non-verification transactions.
* `fpx_extra_info` (object | null) — Detailed verification breakdown. Only present for verification transactions. Contains:
  * `fpx_extra_info.account_type` (string) — `"CASA"` (Current/Savings Account), `"LCA"` (Loan/Credit Account), or `"Undetermined"`.
  * `fpx_extra_info.account_number_verified` (boolean | null) — `true` if account number matches, `false` if not, `null` if undetermined.
  * `fpx_extra_info.buyer_id_verified` (boolean | null) — `true` if buyer ID matches, `false` if not, `null` if undetermined.



**Example callback response**

```json
{
  "record_type": "transaction",
  "transaction_id": "trx_abc123",
  "exchange_reference_number": "1-726-210-822-807492",
  "order_number": "ORD001",
  "currency": "MYR",
  "amount": 100.00,
  "payer_name": "MOHD ALI",
  "payer_email": "m.ali@gmail.com",
  "status": 3,
  "status_description": "Approved",
  "payer_identity_verified": true,
  "fpx_extra_info": {
    "account_type": "CASA",
    "account_number_verified": true,
    "buyer_id_verified": true
  },
  "checksum": "..."
}
```



***



## Idempotent Requests <mark style="color:red;">v3</mark>



The API supports idempotency for safely retrying requests without accidentally performing the same operation twice. This is useful when an API call is disrupted in transit and you do not receive a response.



To perform an idempotent request, provide an `Idempotency-Key` header with a unique key (we recommend a UUID v4). The key is scoped to your merchant account and portal, so different portals can use the same key without conflict.



Bayarcash's idempotency works by saving the resulting status code and body of the first request made for any given idempotency key. Subsequent requests with the same key and parameters return the same result. Keys expire after **24 hours**.



> **Important:** If you retry a request with the same idempotency key but different request parameters, the API will return an error to prevent accidental misuse.



**Example request with idempotency:**

```bash
curl https://api.console.bayar.cash/v3/payment-intents \
  -H "Authorization: Bearer <Personal_Access_Token>" \
  -H "Idempotency-Key: 8f14e45f-ceea-367f-a27f-c790e02b3045" \
  -H "Content-Type: application/json" \
  -d '{"portal_key":"xxx","payment_channel":[1],"order_number":"ORD001","amount":100.00,"payer_name":"MOHD ALI","payer_email":"m.ali@gmail.com"}'
```



**Error responses:**

| Scenario                       | Status | Description                                                       |
| ------------------------------ | ------ | ----------------------------------------------------------------- |
| Same key, different parameters | 422    | Idempotency key already used with different request parameters    |
| Concurrent request in progress | 409    | A request with this idempotency key is currently being processed  |
| Key exceeds 255 characters     | 422    | Idempotency key must not exceed 255 characters                    |

