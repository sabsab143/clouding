## Torrent cloud search provider specification

There are currently two types of search providers: `screen-scrape` and `json-api`

### `screen-scrape`

Here is an outline `screen-scrape` configuration file, where the dynamic values are documented between the `<` and `>`:

```
{
	"<search provider id>": {
		"name": <displayed name>,
		"type": <either "screen-scape" or "json-api">,
		"list": {
			"url": <search url with placeholders for the search query and page number>,
			"items": <selector to the all result items>,
			"item": <within the context of each item> {
				"name": <selector to the item name>,
				"url": <selector to the item url>,
				"seeds": <selector to the item seeds integer>,
				"peers": <selector to the item peers integer>,
				"magnet": <selector to the item magnet>
			}
		},
		"item": <after following the item's url> {
			"magnet": <selector to the item magnet>,
			"infohash": <selector to the item infohash (infohash+tracker = magnet)>,
			"tracker": <selector to the item main tracker (infohash+tracker = magnet)>
		}
	}
}
```

See below for an example: [Mininova](http://mininova.org) (hosts copywrite-free torrents).

### `json-api`

In progress
