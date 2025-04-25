### Pickups

#### GET Pickups

Available filters: carrier, status, date_start, date_end, reference

###### Copy as curl
``` shell
curl --request GET --header 'Authorization: Bearer flx_...' --url 'https://api.lixlog.com/v1/pickups'
```

###### Example JSON Response
``` json
{
  "pagination": {
    "prev_url": "/api/pickups?page=",
    "next_url": "/api/pickups?page=",
    "count": 2,
    "page": 1,
    "next": null
  },
  "data": [
    {
      "id": 2,
      "status": "accepted",
      "note": "sdfsdf",
      "pickup_date": "2025-02-04T07:14:00.000-03:00",
      "carrier_pickup_code": "123",
      "integration_request": null,
      "integration_response": null,
      "integration_status": null,
      "accepted_at": "2025-02-05T07:14:07.165-03:00",
      "performed_at": null,
      "canceled_at": null,
      "finished_at": null,
      "created_at": "2025-02-05T07:07:05.046-03:00",
      "updated_at": "2025-03-24T04:56:27.930-03:00",
      "carrier": {
        "id": 18,
        "name": "JADLOG LOGISTICA S.A",
        "federal_tax": "34028316000103",
        "link": {
          "_self": "/api/carriers/18"
        }
      },
      "warehouse": {
        "id": 1,
        "name": "Galpão Paripueira",
        "address": {
          "id": 4,
          "residential": null,
          "name": null,
          "email": null,
          "federal_tax": null,
          "street": "Rua Rio Iriri",
          "complement": "",
          "neighborhood": "Bairro Alto",
          "number": "270",
          "phone": null,
          "city": "Curitiba",
          "state": "PR",
          "zip": "82840310",
          "created_at": "2025-02-05T05:45:21.631-03:00",
          "updated_at": "2025-02-05T05:45:21.631-03:00",
          "extra_federal_tax": null
        },
        "link": {
          "_self": "/api/warehouses/1"
        }
      },
      "link": {
        "_self": "/api/orders/2",
        "public_url": "https://link/public-pickups/040e472f04414e5d7d03e1c5e8a0d01"
      }
    },
    {
      "id": 1,
      "status": "cancelled",
      "note": "xxx",
      "pickup_date": null,
      "carrier_pickup_code": null,
      "integration_request": null,
      "integration_response": null,
      "integration_status": null,
      "accepted_at": null,
      "performed_at": null,
      "canceled_at": "2025-02-05T07:07:00.431-03:00",
      "finished_at": null,
      "created_at": "2025-02-05T07:02:35.979-03:00",
      "updated_at": "2025-02-05T07:07:00.435-03:00",
      "carrier": {
        "id": 1,
        "name": "Favorita",
        "federal_tax": "12345678945787",
        "link": {
          "_self": "/api/carriers/1"
        }
      },
      "warehouse": {
        "id": 1,
        "name": "Galpão Paripueira",
        "address": {
          "id": 4,
          "residential": null,
          "name": null,
          "email": null,
          "federal_tax": null,
          "street": "Rua Rio Iriri",
          "complement": "",
          "neighborhood": "Bairro Alto",
          "number": "270",
          "phone": null,
          "city": "Curitiba",
          "state": "PR",
          "zip": "82840310",
          "created_at": "2025-02-05T05:45:21.631-03:00",
          "updated_at": "2025-02-05T05:45:21.631-03:00",
          "extra_federal_tax": null
        },
        "link": {
          "_self": "/api/warehouses/1"
        }
      },
      "link": {
        "_self": "/api/orders/1",
        "public_url": "https://link/public-pickups/f95fb05c4a8867113067625a271c901"
      }
    }
  ]
}
```

#### GET Pickup

###### Copy as curl
``` shell
curl --request GET --header 'Authorization: Bearer flx_...' --url 'https://api.lixlog.com/v1/pickups/2'
```

###### Example JSON Response
``` json
{
  "id": 2,
  "status": "accepted",
  "note": "sdfsdf",
  "pickup_date": "2025-02-04T07:14:00.000-03:00",
  "carrier_pickup_code": "123",
  "integration_request": null,
  "integration_response": null,
  "integration_status": null,
  "accepted_at": "2025-02-05T07:14:07.165-03:00",
  "performed_at": null,
  "canceled_at": null,
  "finished_at": null,
  "created_at": "2025-02-05T07:07:05.046-03:00",
  "updated_at": "2025-03-24T04:56:27.930-03:00",
  "carrier": {
    "id": 18,
    "name": "JADLOG LOGISTICA S.A",
    "federal_tax": "34028316000103",
    "link": {
      "_self": "/api/carriers/18"
    }
  },
  "warehouse": {
    "id": 1,
    "name": "Galpão Paripueira",
    "address": {
      "id": 4,
      "residential": null,
      "name": null,
      "email": null,
      "federal_tax": null,
      "street": "Rua Rio Iriri",
      "complement": "",
      "neighborhood": "Bairro Alto",
      "number": "270",
      "phone": null,
      "city": "Curitiba",
      "state": "PR",
      "zip": "82840310",
      "created_at": "2025-02-05T05:45:21.631-03:00",
      "updated_at": "2025-02-05T05:45:21.631-03:00",
      "extra_federal_tax": null
    },
    "link": {
      "_self": "/api/warehouses/1"
    }
  },
  "link": {
    "_self": "/api/orders/2",
    "public_url": "https://link/public-pickups/040e472f04414e5d7d03e1c5e8a0d01"
  }
}
```

#### POST Create Pickup

###### Copy as curl
``` shell
curl --request POST \
  --url https://api.lixlog.com/v1/pickups \
  --header 'Authorization: Bearer flx_...' \
  --header 'Content-Type: application/json' \
  --data '{
  "note": "Coleta urgente",
  "orders": [
    3
  ]
}'
```

###### Example JSON Response
``` json
[
  {
    "id": 6,
    "warehouse_id": 1,
    "company_id": 1,
    "created_by_id": 1,
    "status": "initial",
    "note": "Urgente",
    "pickup_date": null,
    "accepted_at": null,
    "performed_at": null,
    "canceled_at": null,
    "created_at": "2025-04-25T13:06:55.456-03:00",
    "updated_at": "2025-04-25T13:06:55.464-03:00",
    "carrier_id": 16,
    "public_access_token": "028ed823a78908d7ea787d04853dcd1",
    "carrier_pickup_code": null,
    "integration_request": null,
    "integration_response": null,
    "integration_status": null,
    "finished_at": null
  }
]
```