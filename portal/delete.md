# Delete Portal

***

<mark style="color:red;">v3</mark>  <mark style="color:red;">`DELETE`</mark>  `api.console.bayar.cash/v3/portals/{portal_id}`

***



Delete an existing portal by its ID. Once deleted, the portal can no longer be used to create payment intents.

Example of sending <mark style="color:red;">`DELETE`</mark> request with cURL.



```markup
curl -X DELETE https://api.console.bayar.cash/v3/portals/cbp_aZ9Klm \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
```



Example of JSON structured response.



```json
{
    "success": true
}
```
