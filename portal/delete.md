# Delete Portal

***

<mark style="color:red;">v2</mark>  <mark style="color:red;">`DELETE`</mark>  `console.bayar.cash/api/v2/portals/{portal_id}`<br>
<mark style="color:red;">v3</mark> <mark style="color:red;">`DELETE`</mark>  `api.console.bayar.cash/v3/portals/{portal_id}`

***



Delete an existing portal by its ID. Once deleted, the portal can no longer be used to create payment intents.

> Notes: A portal that already has transactions cannot be deleted. On v2 the request will return a validation error in that case.

Example of sending <mark style="color:red;">`DELETE`</mark> request with cURL.



```markup
curl -X DELETE https://api.console.bayar.cash/v3/portals/prt_PGMo1q \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
```



Example of JSON structured response.



```json
{
    "success": true
}
```
