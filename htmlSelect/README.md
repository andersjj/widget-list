# htmlSelect

htmlSelect is a service that allows you to pass in JSON document that contains:

1. URL of document that you want to extract information from.
2. An array of `selectors` that include:
  * `selector` jQuery like selector to select HTML DOM elements
  * `name` attribute for return JSON
  * `attribute` optional, if included, will return the value of `attribute` in the selected HTML element.  If not included will return the HTML of the selected element.

``` 
{
	"url": "https://www.wired.com/story/virginia-i66-toll-road/",
	"selectors": [{
		"selector": "h1#articleTitle",
		"name": "title"
	},{
		"selector": "article.article-body-component > div > p",
		"name": "text"
	},{
		"selector": "div.image-group-component > img:nth-child(1)",
		"attribute": "src",
		"name": "url"
	}]
}
```

### Usage
Simply do an HTTP POST to 
```
https://www.widget-list.com:8088
```

With the JSON above as the body and you will return a JSON document with one attribute for each selector passed in.  Each attribute in the return JSON will have the value obtained by the selector.


