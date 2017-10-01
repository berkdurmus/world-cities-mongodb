# world-cities-database

 The app will save 2 collections to your mongodb: 
 1. `cities`(**23328** in total)
 1. `countries`(**252** in total)

 Easy to use and easy to update. Everything happens in seconds.

## Python version

- Python 3
- Python 2 should be fine, but haven't tried.

## How to use

1. `git clone https://github.com/Mr-Binary/world-cities-mongodb.git`

1. `pip install pymongo`

1. Open `settings.py`, set up your database settings.

1. `python main.py`

1. Enjoy :)

## Structure

- `[data]`: [Folder] Raw data from GeoNames
- `[models]`: [Folder] database model for city and country
- `[utils]`: [Folder] Helper function
- `settings.py`: Settings
- `main.py`: Main file

## About the data
- The data is from [GeoNames](http://www.geonames.org/).

- The `cities` contains cities which population greater than 15000.

- The foreign key to refer is `geo_name_id`

- To update the data, you just need to download them from GeoNames:
  - [cities15000.zip](http://download.geonames.org/export/dump/cities15000.zip)
  - [countryInfo.txt](http://download.geonames.org/export/dump/countryInfo.txt)
  - And update the according file in `data` folder.


## FAQ

### What will happen if I run the app twice

- Every execution will drop the previous collection and generate new one.

### How about support other database

- I think it's very easy, you just need to refactor the `save_cities()` and `save_countries()` in `mongodb.py`, then it will be called at run time with the list of data to insert.
