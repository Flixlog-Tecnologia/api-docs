### Orders

#### GET Orders

Available filters: carrier, reference, invoice_number, status, date_start, date_end)

Available sorts: id, updated_at

###### Copy as curl
``` shell
curl --request GET --header 'Authorization: Bearer flx_...' --url 'https://api.lixlog.com/v1/orders?sort=id:asc'
```

###### Example JSON Response
``` json
{
  "pagination": {
    "prev_url": "/api/orders?page=",
    "next_url": "/api/orders?page=2",
    "count": 1,
    "page": 1,
    "next": null
  },
  "data": [
    {
      "id": 13,
      "reference": "123",
      "tracking_code": "FL4A3B2D5DF3FD-0001",
      "carrier_tracking_code": null,
      "status": "available_for_pickup",
      "archived_at": null,
      "delivered_at": null,
      "out_for_delivery_at": null,
      "pickuped_at": null,
      "items": [],
      "addressee": {
        "id": 165,
        "residential": null,
        "name": "ANDRE SOFTWARE",
        "email": "contato@andrekiffer.com.br",
        "federal_tax": "93123663272",
        "street": "Rua Arnaldo Pisseti",
        "complement": "",
        "neighborhood": "Bairro Alto",
        "number": null,
        "phone": "41995065196",
        "city": "Curitiba",
        "state": "PR",
        "zip": "82820350",
        "created_at": "2024-06-27T08:50:32.869-03:00",
        "updated_at": "2024-06-27T08:50:32.869-03:00"
      },
      "created_at": "2024-06-27T08:50:32.871-03:00",
      "updated_at": "2024-07-17T22:25:29.467-03:00",
      "carrier": {
        "id": 5,
        "name": "Favorita",
        "federal_tax": "12345678945783",
        "link": {
          "_self": "/api/carriers/5"
        }
      },
      "invoice": {
        "id": 41,
        "number": "19541",
        "serie": "4",
        "key": "43230503741819000106550040000195411767160405",
        "link": {
          "_self": "/api/invoices/41"
        }
      },
      "link": {
        "_self": "/api/orders/13"
      }
    }
  ]
}
```

#### GET Order

###### Copy as curl
``` shell
curl --request GET --header 'Authorization: Bearer flx_...' --url 'https://api.lixlog.com/v1/orders/13'
```

###### Example JSON Response
``` json
{
  "id": 13,
  "reference": "123",
  "tracking_code": "FL4A3B2D5DF3FD-0001",
  "carrier_tracking_code": null,
  "status": "available_for_pickup",
  "archived_at": null,
  "delivered_at": null,
  "out_for_delivery_at": null,
  "pickuped_at": null,
  "items": [],
  "addressee": {
    "id": 165,
    "residential": null,
    "name": "ANDRE SOFTWARE",
    "email": "contato@andrekiffer.com.br",
    "federal_tax": "93123663272",
    "street": "Rua Arnaldo Pisseti",
    "complement": "",
    "neighborhood": "Bairro Alto",
    "number": null,
    "phone": "41995065196",
    "city": "Curitiba",
    "state": "PR",
    "zip": "82820350",
    "created_at": "2024-06-27T08:50:32.869-03:00",
    "updated_at": "2024-06-27T08:50:32.869-03:00"
  },
  "created_at": "2024-06-27T08:50:32.871-03:00",
  "updated_at": "2024-07-17T22:25:29.467-03:00",
  "carrier": {
    "id": 5,
    "name": "Favorita",
    "federal_tax": "12345678945783",
    "link": {
      "_self": "/api/carriers/5"
    }
  },
  "invoice": {
    "id": 41,
    "number": "19541",
    "serie": "4",
    "key": "43230503741819000106550040000195411767160405",
    "link": {
      "_self": "/api/invoices/41"
    }
  },
  "link": {
    "_self": "/api/orders/13"
  }
}
```

#### POST Create Order

###### Copy as curl
``` shell
curl --request POST \
  --url https://api.lixlog.com/v1/orders \
  --header 'Authorization: Bearer flx_...' \
  --header 'Content-Type: application/json' \
  --data '{
    "reference": "FLIX123",
    "addressee_attributes": {
        "name": "André Kiffer",
        "federal_tax": "93123663272",
        "email": "andre@flixlog.com",
        "phone": "41995065196",
        "street": "AL 101 Norte",
        "number": "1251",
        "neighborhood": "Centro",
        "city": "São Paulo",
        "state": "SP",
        "zip": "05050100"
    },
    "items": [
        {
            "reference": "SKU123",
            "price": 10,
            "width": 0.1,
            "height": 0.1,
            "length": 0.1,
            "weight": 20,
            "quantity": 2
        },
      {
        "product_id": 51,
        "quantity": 2
        }
    ],
    "carrier_id": 5,
    "warehouse_id": 20
}'
```

###### Example JSON Response
``` json
{
  "id": 41,
  "reference": "FLIX123",
  "status": "initial",
  "archived_at": null,
  "delivered_at": null,
  "out_for_delivery_at": null,
  "pickuped_at": null,
  "items": [
    {
      "id": 172,
      "reference": "SKU123",
      "product_id": null,
      "tms_order_id": 41,
      "price": "10.0",
      "weight": "20.0",
      "volume": "0.002",
      "quantity": 2,
      "created_at": "2024-11-11T03:01:34.582-03:00",
      "updated_at": "2024-11-11T03:01:34.582-03:00",
      "volumes": [
        {
          "height": 0.1,
          "length": 0.1,
          "width": 0.1
        }
      ]
    },
    {
      "id": 173,
      "reference": "SKU1234",
      "product_id": 51,
      "tms_order_id": 41,
      "price": "150.0",
      "weight": "151.0",
      "volume": "0.0068",
      "quantity": 2,
      "created_at": "2024-11-11T03:01:34.585-03:00",
      "updated_at": "2024-11-11T03:01:34.585-03:00",
      "volumes": [
        {
          "height": 0.15,
          "length": 0.15,
          "width": 0.15,
          "quantity": 2
        }
      ]
    }
  ],
  "addressee_id": 204,
  "warehouse_id": 20,
  "company_id": 1,
  "created_by_id": 1,
  "created_at": "2024-11-11T03:01:34.557-03:00",
  "updated_at": "2024-11-11T03:01:34.557-03:00",
  "invoice_id": null,
  "supplier_invoice_id": null,
  "tracking_code": "FL5A5D14E6E046-0001",
  "carrier_id": 5,
  "review_id": null,
  "selected_rate_id": null,
  "leadtime": 0,
  "carrier_tracking_code": null
}
```

#### PATCH Update Order

###### Copy as curl
``` shell
curl --request PATCH \
  --url https://api.lixlog.com/v1/orders/13 \
  --header 'Authorization: Bearer flx_...' \
  --header 'Content-Type: application/json' \
  --data '{
    "carrier_id": 5
  }'
```

###### Example JSON Response
``` json
{
  "id": 41,
  "reference": "FLIX123",
  "status": "initial",
  "archived_at": null,
  "delivered_at": null,
  "out_for_delivery_at": null,
  "pickuped_at": null,
  "items": [
    {
      "id": 172,
      "reference": "SKU123",
      "product_id": null,
      "tms_order_id": 41,
      "price": "10.0",
      "weight": "20.0",
      "volume": "0.002",
      "quantity": 2,
      "created_at": "2024-11-11T03:01:34.582-03:00",
      "updated_at": "2024-11-11T03:01:34.582-03:00",
      "volumes": [
        {
          "height": 0.1,
          "length": 0.1,
          "width": 0.1
        }
      ]
    },
    {
      "id": 173,
      "reference": "SKU1234",
      "product_id": 51,
      "tms_order_id": 41,
      "price": "150.0",
      "weight": "151.0",
      "volume": "0.0068",
      "quantity": 2,
      "created_at": "2024-11-11T03:01:34.585-03:00",
      "updated_at": "2024-11-11T03:01:34.585-03:00",
      "volumes": [
        {
          "height": 0.15,
          "length": 0.15,
          "width": 0.15,
          "quantity": 2
        }
      ]
    }
  ],
  "addressee_id": 204,
  "warehouse_id": 20,
  "company_id": 1,
  "created_by_id": 1,
  "created_at": "2024-11-11T03:01:34.557-03:00",
  "updated_at": "2024-11-11T03:01:34.557-03:00",
  "invoice_id": null,
  "supplier_invoice_id": null,
  "tracking_code": "FL5A5D14E6E046-0001",
  "carrier_id": 5,
  "review_id": null,
  "selected_rate_id": null,
  "leadtime": 0,
  "carrier_tracking_code": null
}
```

#### POST Send Invoice (NFe)
Send invoice xml encoded in base64[https://en.wikipedia.org/wiki/Base64]

###### Copy as curl
``` shell
curl --request POST \
  --header 'Authorization: Bearer flx_...' \
  --url https://api.lixlog.com/v1/orders/13/invoice \
  --data '{
  "xml": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz48bmZlUHJv\nYy..."
}'
```
###### Example JSON Response
``` json
{
  "id": 63,
  "number": "249493",
  "serie": "2",
  "key": "35230535085.........",
  "amount": "1899.0",
  "freight": "0.0",
  "issue_date": "2023-05-12T10:28:51.000-03:00",
  "document_type": "invoice",
  "created_at": "2024-11-07T07:56:51.535-03:00",
  "updated_at": "2024-11-07T07:56:51.546-03:00",
  "weight": "27.0",
  "volumes": 1
}
```

#### POST Cancel Order

###### Copy as curl
``` shell
curl --request POST --header 'Authorization: Bearer flx_...' --url 'https://api.lixlog.com/v1/orders/13/cancel'
```

No parameters required. Returns 204 No Content if successful.

#### POST Mark as In Transit

###### Copy as curl
``` shell
curl --request POST --header 'Authorization: Bearer flx_...' --url 'https://api.lixlog.com/v1/orders/13/in_transit'
```

No parameters required. Returns 204 No Content if successful.

#### POST Mark as Delivered

###### Copy as curl
``` shell
curl --request POST --header 'Authorization: Bearer flx_...' --url 'https://api.lixlog.com/v1/orders/13/deliver'
```

No parameters required. Returns 204 No Content if successful.

#### POST Mark as In Return To Sender

###### Copy as curl
``` shell
curl --request POST --header 'Authorization: Bearer flx_...' --url 'https://api.lixlog.com/v1/orders/13/return'
```

No parameters required. Returns 204 No Content if successful.


#### POST Archive order

###### Copy as curl
``` shell
curl --request POST --header 'Authorization: Bearer flx_...' --url 'https://api.lixlog.com/v1/orders/13/to_archive'
```

No parameters required. Returns 204 No Content if successful.

#### POST Unarchive order

###### Copy as curl
``` shell
curl --request POST --header 'Authorization: Bearer flx_...' --url 'https://api.lixlog.com/v1/orders/13/unarchive'
```

No parameters required. Returns 204 No Content if successful.
