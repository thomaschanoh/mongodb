# mongodb

## Find all the items that are within the Polygon zone

Data:  

    "zone":{
        "type" : "Polygon",
        "coordinates":[
            [
                [-73.994679, 40.741355],
                [-73.987727, 40.739534],
                [-73.987298, 40.734656],
                [-73.994851, 40.73342],
                [-73.998284, 40.738363],
                [-73.994679, 40.741355]
            ]
        ]
    }

Query: 

    db.stores.find({ "zone": { $geoIntersects: { $geometry: { "type": "Point", "coordinates": [ -73.994679, 40.741355 ] } } } }).pretty()
