# Customers API

Information about your customer API can be found in the Admin Dashboard under the Customer API menu item. You can perform the following actions using the Customer API.

* Create customers
* Read out customer data
* Edit / update customer data
* Delete customer
* Read all customerIds with domain data for statistical data
* Search for a customer ID with a string

Of course, all these actions can be performed only if there is an appropriate authorization.

## Connect to the API

To successfully process an API request, append the API key to **any request** by adding the GET parameter `apiKey` and setting the key as a value.

For each POST and PUT request, set the HTTP `Content-Type` header to `application/json`; that is, for each request that contains a message body. Encode the payload to be sent accordingly.

![screenshot-2020.10.01-13_53_19-1601553199653](../assets/screenshot-2020.10.01-13_53_19-1601553199653.jpg)

The real API keys are of course much more complex ;-) 

&gt; **Always keep your API key secret. If the key is compromised, you can change it here; after that you will need to update all your apps.**



## Use Hawk HTTP authentication

If you enable this option, a signed request can be verified. However, you must implement the client side for this authentication method yourself and integrate it into your applications.

Use the shared secret to sign your requests. To do this, you must derive a key from the shared secret using the `PBKDF2` algorithm 



## Use Hawk HTTP authentication

If you enable this option, a signed request can be verified. However, you must implement the client side for this authentication method yourself and integrate it into your applications.

Use the shared secret to sign your requests. To do this, you must derive a key from the shared secret using the `PBKDF2` algorithm 

&gt; This function is optional. Use this option to enable partial cryptographic verification of your requests.

See the following resources to sign your requests correctly.

- [Hawk - A PHP Implementation](https://github.com/dflydev/dflydev-hawk#building-a-client)
- [hash_pbkdf2 - Generate a PBKDF2 key derivation of a supplied password](https://www.php.net/manual/en/function.hash-pbkdf2.php)

![screenshot-2020.10.01-14_02_14-1601553734725](../assets/screenshot-2020.10.01-14_02_14-1601553734725.jpg)



# API endpoints

There are a total of 4 different API endpoints you can use, in detail these are:

## Create customers

**URL** `http://localhost/ccm19/cookie-consent-management/www/public/hosting/api/client`

**Method** `POST`

**Message body**

- `username`: *string
- `password`: *string* - The client's password in plain text
- `passwordHash`: *string* - **[optional]** A precomputed password hash (bcrypt: *$2y$*); `password` has priority
- `active`: *bool* - **[optional]** *(default: false)* Indicates whether the client can log in.
- `firstName`: *string* - **[optional]**
- `lastName`: *string* - **[optional]**
- `emailAddress`: *string*
- `company`: *string* - **[optional]**
- `domainMaxCount`: *int* - **[optional]** *(default value: 0)* Maximum number of domains a customer can manage in his account; -1 is unlimited
- `whitelabelMaxCount`: *int* - **[optional]** *(default value: 0)* Maximum number of whitelabel licenses available to a customer; -1 is unlimited
- `widgetDisplayMaxCount`: *int* - **[optional]** *(default: 0)* Specifies how many times the CCM19 widget is loaded in the frontend per month; -1 is unlimited



**Response (HTTP status codes)**

* 201- Customer was successfully created.
  * `id`: *string*
  * `username`: *string*
  * `active`: *bool*
  * `firstName`: *string*
  * `lastName`: *string*
  * `emailAddress`: *string*
  * `company`: *string*
  * `domainMaxCount`: *int*
  * `whitelabelMaxCount`: *int*
  * `widgetDisplayMaxCount`: *int*

- `400` - username or password is empty.
- `400` - username is already in use.
- `400` - email address is empty or invalid.



## Read customers

**URL** `http://localhost/ccm19/cookie-consent-management/www/public/hosting/api/client/~CLIENT_ID~`

**method** `GET`

**Query parameter**

- `~CLIENT_ID~`: *string* The ID of the CCM19 customer account.

**Response (HTTP status codes)**

* 200 - Success!
  * `id`: *string
  * `username`: *string*
  * `active`: *bool*
  * `firstName`: *string*
  * `lastName`: *string*
  * `emailAddress`: *string*
  * `company`: *string*
  * `domainCount`: *int*
  * `domainMaxCount`: *int*
  * `whitelabelCount`: *int*
  * `whitelabelMaxCount`: *int*
  * `widgetDisplayCount`: *int*
  * `widgetDisplayMaxCount`: *int*
* `404` - customer not found.



## Update customers

URL `http://localhost/ccm19/cookie-consent-management/www/public/hosting/api/client/~CLIENT_ID~`

Method `PUT`

Query parameter

- `~CLIENT_ID~`: *string* The ID of the CCM19 customer account.

Message body

- `password`: *string* - **[optional]** The password of the customer in plain text
- `passwordHash`: *string* - **[optional]** A precomputed password hash (bcrypt: *$2y$*); `password` has priority
- `active`: *bool* - **[optional]** Indicates whether the client can log in.
- `firstName`: *string* - **[optional]**
- `lastName`: *string* - **[optional]**
- `emailAddress`: *string* - **[optional]**
- `company`: *string* - **[optional]**
- `domainMaxCount`: *int* - **[optional]** Maximum number of domains a customer can manage in his account; -1 is unlimited
- `whitelabelMaxCount`: *int* - **[optional]** Maximum number of whitelabel licenses available to a customer; -1 is unlimited
- `widgetDisplayMaxCount`: *int* - **[optional]** Sets how many times the CCM19 widget is loaded in the frontend per month; -1 is unlimited

Response (HTTP status codes) 

* 200 - Customer was successfully updated.
  * `id`: *string*
  * `username`: *string*
  * `active`: *bool*
  * `firstName`: *string*
  * `lastName`: *string*
  * `emailAddress`: *string*
  * `company`: *string*
  * `domainMaxCount`: *int*
  * `whitelabelMaxCount`: *int*
  * `widgetDisplayMaxCount`: *int*
* `400` - Email address is empty or invalid.
* `404` - customer not found.



## Delete customer

```
DELETE
```

**URL** `http://localhost/ccm19/cookie-consent-management/www/public/hosting/api/client/~CLIENT_ID~`

Method `DELETE`

**Query parameter**

- `~CLIENT_ID~`: *string* The ID of the CCM19 customer account.

**Response (HTTP status codes)**

- `204` - customer was successfully deleted.
- `404` - customer not found.



## Read all customer Ids with domain data for statistical data

```
GET
```

URL `http://ccm19.localhost/hosting/api/client_all`

Method `GET`

Response (HTTP status codes)

- ```
  201
  ```

   

  - Success!

  - `userId`: *string*

  - `actualCallCount`: *int*

  - `domainCountData`: *array*

  - - `domName`: *string*
    - `count`: *int*

- `404` - No data found



## Search for a customer ID with a string

```
GET
```

URL `http://ccm19.localhost/hosting/api/clientgetid/~SEARCH_TERM~`

Method `GET`

Query parameter

- `~SEARCH_TERM~`: *string* - username, email address

Response (HTTP status codes)

- ```
  200
  ```

   

  - Success!

  - `id`: *string*

- `404` - No data found







