# Checksum Validation

***



To ensure a secured request to Bayarcash API, you need to generate a checksum value using your API secret key. This checksum must be included in your request to validate its integrity and authenticity.&#x20;

You can generate your API secret key from Bayarcash portal at profile page.



* Ensure the API secret key is securely stored and not exposed in your client-side code.
* Always verify the checksum in the callback data to ensure data integrity and authenticity,
* The `ksort` function sorts the payload data by key, which is essential for checksum consistency.
* The `implode` function concatenates the sorted payload values using a delimiter (in this case is |), forming the string for the checksum calculation.
* The `hash_hmac` function generates the checksum using the SHA256 algorithm and your secret key.



{% hint style="success" %}
Note: The checksum value and checksum validation are optional, but it is recommended for enhanced security.
{% endhint %}

