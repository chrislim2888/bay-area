# List of Bay Area Cities
The *bay-area.csv* contains the list of cities grouped in San Francisco bay area. Below are the bay areas grouping

* Outer Bay
* East Bay
* North Bay
* South Bay
* Peninsula

The cities name list inside the list are compatible to cities name used in [IP2Location Database](http://www.ip2location.com) or [IP2Location LITE Database](http://lite.ip2location.com). In other words, you can easily match the IP address to bay area by linking the data of this bay area list to IP2Location record.

Despite the usage for IP2Location, this list could also be used for any solution any way you want.

You may visit [https://en.wikipedia.org/wiki/San_Francisco_Bay_Area](https://en.wikipedia.org/wiki/San_Francisco_Bay_Area) to learn more about the bay area.

# Import into MySQL Table

Below are the syntax on how to import the *bay_area.csv* data into a MySQL table.

```mysql
CREATE TABLE IF NOT EXISTS `bay_area` (
  `country_code` varchar(2) NOT NULL,
  `region_name` varchar(128) NOT NULL,
  `city_name` varchar(128) NOT NULL,
  `bay_area` varchar(10) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
```

You can use the below command to import the bay area data from the csv file into the newly created *bay_area* table

```mysql
LOAD DATA LOCAL
	INFILE 'location of bay_area.csv'
INTO TABLE
	`bay_area`
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\r\n'
IGNORE 1 LINES;
```

# Correction

Please feedback in the issues for any data correction.

