### Warehouses

#### GET Warehouses

###### Copy as curl
``` shell
curl --request GET --header 'Authorization: Bearer flx_...' --url 'https://2.flixlog.com/api/warehouses'
```

Example JSON Response
``` json
{
	"pagination": {
		"prev_url": "/api/warehouses?page=",
		"next_url": "/api/warehouses?page=",
		"count": 2,
		"page": 1,
		"next": null
	},
	"data": [
		{
			"id": 1,
			"name": "Galpão Paripueira",
			"description": "Galpão e-commerce",
			"zip": "05050100",
			"address": {
				"id": 191,
				"residential": null,
				"name": "André Kiffer",
				"email": "andre@flixlog.com",
				"federal_tax": "93123663272",
				"street": "AL 101 Norte",
				"complement": null,
				"neighborhood": "Centro",
				"number": "1251",
				"phone": "41995065196",
				"city": "São Paulo",
				"state": "SP",
				"zip": "05050100",
				"created_at": "2024-11-11T02:13:36.645-03:00",
				"updated_at": "2024-11-11T02:13:36.645-03:00"
			},
			"default": false,
			"created_at": "2024-02-08T14:45:14.186-03:00",
			"updated_at": "2024-11-11T02:13:36.646-03:00",
			"link": {
				"_self": "/api/warehouses/1"
			}
		}
	]
}
```

#### GET Warehouse

###### Copy as curl
``` shell
curl --request GET --header 'Authorization: Bearer flx_...' --url 'https://2.flixlog.com/api/warehouses/1'
```

Example JSON Response
``` json
{
	"id": 1,
	"name": "Galpão Paripueira",
	"description": "Galpão e-commerce",
	"zip": "05050100",
	"address": {
		"id": 188,
		"residential": null,
		"name": "André Kiffer",
		"email": "andre@flixlog.com",
		"federal_tax": "93123663272",
		"street": "AL 101 Norte",
		"complement": null,
		"neighborhood": "Centro",
		"number": "1251",
		"phone": "41995065196",
		"city": "São Paulo",
		"state": "SP",
		"zip": "05050100",
		"created_at": "2024-11-11T02:11:27.179-03:00",
		"updated_at": "2024-11-11T02:11:27.179-03:00"
	},
	"default": true,
	"created_at": "2024-02-08T14:45:14.186-03:00",
	"updated_at": "2024-11-11T02:11:27.190-03:00",
	"link": {
		"_self": "/api/warehouses/1"
	}
}
```

#### POST Create Warehouse

###### Copy as curl
``` shell
curl --request POST \
  --url https://2.flixlog.com/api/warehouses \
  --header 'Authorization: Bearer flx_...' \
  --header 'Content-Type: application/json' \
  --data '{
	"name": "Fulfillment",
	"address_attributes": {
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
    }
}'
```

Example JSON Response
``` json
{
	"id": 20,
	"name": "Fulfillment",
	"description": null,
	"zip": "05050100",
	"address": {
		"id": 192,
		"residential": null,
		"name": "André Kiffer",
		"email": "andre@flixlog.com",
		"federal_tax": "93123663272",
		"street": "AL 101 Norte",
		"complement": null,
		"neighborhood": "Centro",
		"number": "1251",
		"phone": "41995065196",
		"city": "São Paulo",
		"state": "SP",
		"zip": "05050100",
		"created_at": "2024-11-11T02:14:49.300-03:00",
		"updated_at": "2024-11-11T02:14:49.300-03:00"
	},
	"default": false,
	"created_at": "2024-11-11T02:14:49.302-03:00",
	"updated_at": "2024-11-11T02:14:49.302-03:00",
	"link": {
		"_self": "/api/warehouses/20"
	}
}
```

#### PATCH Update Warehouse

###### Copy as curl
``` shell
curl --request PATCH \
  --url https://2.flixlog.com/api/warehouses/1 \
  --header 'Authorization: Bearer flx_...' \
  --header 'Content-Type: application/json' \
  --data '{
	"address_attributes": {
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
    }
}'
```

Example JSON Response
``` json
{
	"id": 1,
	"name": "Galpão Paripueira",
	"description": "Galpão e-commerce",
	"zip": "05050100",
	"address": {
		"id": 193,
		"residential": null,
		"name": "André Kiffer",
		"email": "andre@flixlog.com",
		"federal_tax": "93123663272",
		"street": "AL 101 Norte",
		"complement": null,
		"neighborhood": "Centro",
		"number": "1251",
		"phone": "41995065196",
		"city": "São Paulo",
		"state": "SP",
		"zip": "05050100",
		"created_at": "2024-11-11T02:20:40.601-03:00",
		"updated_at": "2024-11-11T02:20:40.601-03:00"
	},
	"default": false,
	"created_at": "2024-02-08T14:45:14.186-03:00",
	"updated_at": "2024-11-11T02:20:40.603-03:00",
	"link": {
		"_self": "/api/warehouses/1"
	}
}
```
