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

See above for a [Mininova](http://mininova.org) example (hosts copywrite-free torrents). You can use it with:

`SEARCH_PROVIDERS_URL` = `https://gist.githubusercontent.com/jpillora/e667f3d16a6bd403edc4/raw/af4ff4a66a1599ccfd6940d90c633a39ecbf6ba1/torrent-cloud-search-provider-example.json`

### `json-api`

In progress
