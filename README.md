# Vivino API

Vivino API is Node.js console app to select vivino.com items by the following params:

- **name** - _Required_ wine name
- **country** - country to ship to. _Default_ = **US**
- **state** - U.S. state to shipt to. _Default_ **CA** for US, an **empty string** for other countries
- **minPrice** - min price
- **maxPrice** - max price
- **noPriceIncluded** - should items without a price be included?
- **minRatings** - min amount of ratings
- **maxRatings** - max amount of ratings
- **minAverage** - min average rating
- **maxAverage** - max average rating

Examples to run the app:

`> node vivino.js --name=malbec --minPrice=10 --maxPrice=25`

`> node vivino.js "--name=Pinot Noir" --minPrice=10 --maxPrice=25`

`> node vivino.js --name=malbec --minPrice=10 --maxPrice=25 --noPriceIncluded --minRatings=5000 --maxRatings=100000 --minAverage=3.1 --maxAverage=4.5`

`> node vivino.js "--name=Pinot Noir" --country=US --state=NY`

`> node vivino.js --country=RU --name=malbec --maxPrice=25 --minRatings=50000 --minAverage=4`

Results are output to **vivino-out.json** file in JSON format.

The **vivino-out.json** example:

    {
        "vinos": [
            {
            "name": "Trivento Reserve Malbec",
            "link": "https://www.vivino.com/wines/1527219",
            "thumb": "https://images.vivino.com/thumbs/diN0gK6qSpKsgbMApBbxNw_pl_375x500.png",
            "country": "Argentina",
            "region": "Mendoza",
            "average_rating": 3.6,
            "ratings": 52459,
            "price": 10.99
            },
            {
            "name": "Luigi Bosca Malbec",
            "link": "https://www.vivino.com/wines/4133550",
            "thumb": "https://images.vivino.com/thumbs/F7zv69HZS9OHt0UPrc6GRQ_pl_375x500.png",
            "country": "Argentina",
            "region": "Mendoza",
            "average_rating": 4,
            "ratings": 75409,
            "price": 18.79
            }
        ],
        "status": "FULL_DATA", // other statuses in case of an error
        "message": "some exception", // message - in case of an exception only
        "http_status": 403, // http status - in case of an error only
    	"page_index": 23 // index of the problem page - in case of an error only
    }
