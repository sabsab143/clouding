## Torrent cloud search provider specification

There are currently two types of search providers: `screen-scrape` and `json-api`

### `screen-scrape`

Here is an outline `screen-scrape` configuration file, where the documentation is between the `<` and `>`:

```
{
	"<search provider id>": {
		"name": <displayed name>,
		"type": <either "screen-scape" or "json-api">,
		"list": {
			"url": <search url with placeholders for the search query and page number>,
			"lastPage": <selector to the last page integer>,
			"items": <selector to the all result items>,
			"item": <within the context of each item> {
				"name": <selector to the item name>,
				"url": <selector to the item url>,
				"seeds": <selector to the item seeds integer>,
				"peers": <selector to the item peers integer>
			}
		},
		"item": <after following the item's url> {
			"infohash": <selector to the item infohash>,
			"tracker": <selector to the item tracker[s]>
		}
	}
}
```

Here is an example for [Mininova](http://mininova.org) (which only hosts copywrite-free torrents):

``` json
{
	"mininova": {
		"name": "Mininova",
		"list": {
			"url": "http://www.mininova.org/search/{query}/seeds/{page}",
			"lastPage": "",
			"items": "",
			"item": {
				"name":"",
				"url":"",
				"seeds": "",
				"peers": ""
			}
		},
		"item": {
			"infohash": "",
			"tracker": ""
		}
	}
}
```

### `json-api`

In progress
