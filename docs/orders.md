### Orders

#### GET Orders

Available filters: carrier, reference, invoice_number, status, date_start, date_end)

###### Copy as curl
``` shell
curl --request GET --header 'Authorization: Bearer flx_...' --url 'https://2.flixlog.com/api/orders'
```

###### Resposta
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
curl --request GET --header 'Authorization: Bearer flx_...' --url 'https://2.flixlog.com/api/orders/13'
```

###### Resposta
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

#### POST Send Invoice (NFe)
Send invoice xml encoded in base64[https://en.wikipedia.org/wiki/Base64] 

###### Copy as curl
``` shell
curl --request POST \
  --header 'Authorization: Bearer flx_...' \
  --url https://2.flixlog.com/api/orders/13/invoice \
  --data '{
	"xml": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz48bmZlUHJv\nYy..."
}'
```
###### Resposta
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
curl --request POST --header 'Authorization: Bearer flx_...' --url 'https://2.flixlog.com/api/orders/13/cancel'
```

###### Resposta
``` json
```

#### POST Mark as In Transit

###### Copy as curl
``` shell
curl --request POST --header 'Authorization: Bearer flx_...' --url 'https://2.flixlog.com/api/orders/13/in_transit'
```

###### Resposta
``` json
```

#### POST Mark as Delivered

###### Copy as curl
``` shell
curl --request POST --header 'Authorization: Bearer flx_...' --url 'https://2.flixlog.com/api/orders/13/deliver'
```

###### Resposta
``` json
```

#### POST Archive order

###### Copy as curl
``` shell
curl --request POST --header 'Authorization: Bearer flx_...' --url 'https://2.flixlog.com/api/orders/13/to_archive'
```

###### Resposta
``` json
```

#### POST Unarchive order

###### Copy as curl
``` shell
curl --request POST --header 'Authorization: Bearer flx_...' --url 'https://2.flixlog.com/api/orders/13/unarchive'
```

###### Resposta
``` json
```
