# How to get payment details using Mercado Pago APIs

In the new integration with Shopify, there has been a change in the information available in the `payment_id` attribute available in the query of the transaction related to the order obtained through the [Shopify endpoint API](https://shopify.dev/docs/api/admin-rest/2023-04/resources/transaction). In the `payment_id` attribute present in the Shopify API response, where the Mercado Pago payment unique ID (`id`) was previously displayed, the Shopify payment unique ID (`id`) is now informed.

With this change, to obtain payment details using the Mercado Pago APIs, instead of querying the payment directly through its unique ID (`id`), it will be necessary to perform a search using its external reference ID (`external_reference `) to return a list of objects referring to the payments.

To do so, perform a GET by sending the `external_reference` and the `access-token` (obtained from the [Credentials](/developers/en/docs/shopify/additional-content/credentials) section in your [Dashboard](https://www.mercadopago.com/developers/panel/app) or in your account [Mercado Pago](https://www.mercadopago[FAKER][URL][DOMAIN]/settings/account/credentials)) to the endpoint [/v1/payments/search](/developers/en/reference/payments/_payments_search/get).

Example:

```curl
curl --location --request GET 'https://api.mercadopago.com/v1/payments/search?access_token={{AccessToken}}&sort=date_created&criteria=desc&external_reference=njzY7fKb5HH5TgYwXO6jsh2xp&status=approved' \
```

Alternatively, it is possible to obtain the payment ID through a call to the [payments search API](/developers/en/reference/payments/_payments_search/get) using its external reference and query it individually through the payments API. 

To do so, perform a GET by sending the `external_reference` and the `access-token` (generated by the OAuth authentication process) to the endpoint [/v1/payments/{id}](/developers/en/reference/payments/_payments/post).

Example:

```curl
curl -X GET \
        'https://api.mercadopago.com/v1/payments/search?access_token={{AccessToken}}&sort=date_created&criteria=desc&external_reference=njzY7fKb5HH5TgYwXO6jsh2xp&status=approved&attributes=results.id' \
```

Response:

```response
{
    "results": [
        {
            "id": 12345678909
        }
    ]
}
```

Finally, each payment returned in the list can be queried with the `curl` below.

```curl
curl -X GET \
      'https://api.mercadopago.com/v1/payments/56789012345' \
      -H 'Authorization: Bearer {{AccessToken}}'
```