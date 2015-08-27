# qbjs.github.io

qbjs.github.io nables you to publish statistical data based on [W3C The RDF Data Cube Vocabulary](http://www.w3.org/TR/vocab-data-cube/) and [JSON-LD](http://json-ld.org/) .  Reusable [qb:DataSet](http://www.w3.org/TR/vocab-data-cube/#datasets) and [JSON-LD Context](http://www.w3.org/TR/json-ld/#the-context) are provided.

# indicator.jsonld

Indicator.jsonld is designed to store statistical data with 3 dimension (indicator, area, time) and 1 measure (value).

<http://qbjs.github.io/indicator.jsonld> includes :

* JSON-LD Context
* Instance of qb:DataStrctureDefinition
* Instance of qb:DataSet


## example

<http://qbjs.github.io/example.jsonld>

	{
		"@context" : "http://qbjs.github.io/indicator.jsonld",
		"@id" : "http://qbjs.github.io/indicator.jsonld#this",	
		"head" : {
			"@id" : "",
			"license" : "https://creativecommons.org/licenses/by/4.0/",
			"attributionName" : "qbjs",
			"at	tributionURL" : "https://github.com/qbjs/"
		},
		"body" : [ {
			"indicator" : "http://worldbank.270a.info/classification/indicator/SP.POP.TOTL",
			"area" : "http://geonames.jp/resource/北海道札幌市豊平区",
			"year" : "1980",
			"unit" : "人",
			"value" : 218330
		}, {
			"indicator" : "http://worldbank.270a.info/classification/indicator/SP.POP.TOTL",
			"area" : "http://geonames.jp/resource/北海道札幌市豊平区",
			"year" : "1985",
			"unit" : "人",
			"value" : 249956
		}, {
			"indicator" : "http://worldbank.270a.info/classification/indicator/SP.POP.TOTL",
			"area" : "http://geonames.jp/resource/北海道札幌市豊平区",
			"year" : "1990",
			"unit" : "人",
			"value" : 277801
		} ]
	}


## Structure

	{
		// required: reference to JSON-LD Context 
		"@context" : "http://qbjs.github.io/indicator.jsonld",
		
		// required: reference to qb:DataSet instance
		"@id" : "http://qbjs.github.io/indicator.jsonld#this",

		// optional: meta data place holder
		"head" : {
			// required: "" means this JSON-LD url
			"@id" : "",
			// put your meta data here
		},
		
		// required: main data place holder
		"body" : [ 
			// put your data here
		]
	}

## Property


Name      | Description                             | Sample
----------|-----------------------------------------|----------------------------------------------------------------------
indicator | indicator URL                           | "http://worldbank.270a.info/classification/indicator/SP.POP.TOTL"
area      | area URL                                | "http://geonames.jp/resource/北海道札幌市豊平区"
year      | year String (#1)                        | "2012"
yearMonth | year-month String (#1)                  | "2012-01"
date      | date String (#1)                        | "2012-01-31"
unit      | Unit String (optional)                  | "人"
value     | main value, data type is not specified  | 277801

Note #1 : one of them is required

