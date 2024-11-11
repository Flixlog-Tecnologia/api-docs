### Products

#### GET Products
Available sorts: id


###### Copy as curl
``` shell
curl --request GET --header 'Authorization: Bearer flx_...' --url 'https://2.flixlog.com/api/products?page=1&sort=id:desc'
```

Example JSON Response
``` json
{
	"pagination": {
		"prev_url": "/api/products?page=&sort=id%3Adesc",
		"next_url": "/api/products?page=2&sort=id%3Adesc",
		"count": 46,
		"page": 1,
		"next": 2
	},
	"data": [
		{
			"id": 47,
			"reference": "SKU1234",
			"description": "Produt de teste",
			"price": "150.0",
			"deadline": 1,
			"weight": "15.0",
			"volumes": [
				{
					"height": 0.15,
					"length": 0.15,
					"width": 0.15,
					"quantity": 2
				}
			],
			"created_at": "2024-11-11T02:52:06.696-03:00",
			"updated_at": "2024-11-11T02:52:06.696-03:00",
			"volume": 0.0068,
			"link": {
				"_self": "https://2.flixlog.com/api/products/47"
			}
		},
		{
			"id": 46,
			"reference": "1R-1409",
			"description": "Quadro Decorativo",
			"price": "120.0",
			"deadline": 0,
			"weight": "5.0",
			"volumes": [
				{
					"height": 0.08,
					"length": 0.69,
					"width": 0.99,
					"quantity": 1
				}
			],
			"created_at": "2024-10-28T01:48:03.077-03:00",
			"updated_at": "2024-10-28T01:48:03.077-03:00",
			"volume": 0.0546,
			"link": {
				"_self": "https://2.flixlog.com/api/products/46"
			}
		}
	]
}
```

#### GET Product

###### Copy as curl
``` shell
curl --request GET --header 'Authorization: Bearer flx_...' --url 'https://2.flixlog.com/api/products/47'
```

Example JSON Response
``` json
{
	"id": 47,
	"reference": "SKU1234",
	"description": "Produt de teste",
	"price": "150.0",
	"deadline": 1,
	"weight": "15.0",
	"volumes": [
		{
			"height": 0.15,
			"length": 0.15,
			"width": 0.15,
			"quantity": 2
		}
	],
	"created_at": "2024-11-11T02:52:06.696-03:00",
	"updated_at": "2024-11-11T02:52:06.696-03:00",
	"volume": 0.0068,
	"link": {
		"_self": "http://localhost:3001/api/products/47"
	}
}
```

#### POST Create Product

###### Copy as curl
``` shell
curl --request POST \
  --url http://localhost:3001/api/products \
  --header 'Authorization: Bearer flx_...' \
  --header 'Content-Type: application/json' \
  --data '{
	"reference": "SKU1234",
	"description": "Produt de teste",
      "deadline": 1,
      "price": 150,
      "volumes": [{
				"width": 0.151,
				"length": 0.15,
				"height": 0.15,
				"quantity": 2}],
      "weight": 15
}'
```

Example JSON Response
``` json
{
	"id": 51,
	"reference": "SKU1234",
	"description": "Produt de teste",
	"price": "150.0",
	"deadline": 1,
	"weight": "15.0",
	"volumes": [
		{
			"height": 0.15,
			"length": 0.15,
			"width": 0.151,
			"quantity": 2
		}
	],
	"created_at": "2024-11-11T03:00:01.140-03:00",
	"updated_at": "2024-11-11T03:00:01.140-03:00",
	"volume": 0.0068,
	"link": {
		"_self": "http://localhost:3001/api/products/51"
	}
}
```

#### PATCH Update Product

###### Copy as curl
``` shell
ccurl --request PATCH \
  --url http://localhost:3001/api/products/51 \
  --header 'Authorization: Bearer flx_1f54cd1fd772f5f0eb560df6b0e3d7a' \
  --header 'Content-Type: application/json' \
  --data '{
    "reference": "SKU1234",
    "description": "Produt de teste",
    "deadline": 1,
    "price": 150,
    "volumes": [
        {
            "width": 0.152,
            "length": 0.15,
            "height": 0.15,
            "quantity": 2
        }
    ],
    "weight": 15
}'
```

Example JSON Response
``` json
{
	"id": 51,
	"reference": "SKU1234",
	"description": "Produt de teste",
	"price": "150.0",
	"deadline": 1,
	"weight": "15.0",
	"volumes": [
		{
			"height": 0.15,
			"length": 0.15,
			"width": 0.152,
			"quantity": 2
		}
	],
	"created_at": "2024-11-11T03:00:01.140-03:00",
	"updated_at": "2024-11-11T03:29:23.420-03:00",
	"volume": 0.0068,
	"link": {
		"_self": "http://localhost:3001/api/products/51"
	}
}
```
