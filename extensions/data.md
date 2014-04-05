# Query/Template Lookup Values 

Support for autocomplete, table lookup and filtering.

1. Add an optional property to the <code>data</code> object: acceptableValues.


If it's present the value for the field can either be a list of key, a list of value pairs, or a URL.
If it's a URL, returns a valid collection json with a list of items that can be used by the client.

## Example using an array of value pairs


## Example using a list of keys
```
 {
  "template" : {
    "data" : [
      {"name" : "full-name", "value" : ""},
      {"name" : "email", "value" : ""},
      {"name" : "status", "acceptableValues" : ["Open","Close","Pending","Won't Fix"] ,value:"" "prompt" : "Status"}
    ]
  }
```


## Example using an array of value pairs
```
 {
  "template" : {
    "data" : [
      {"name" : "full-name", "value" : ""},
      {"name" : "email", "value" : ""},
      {"name" : "status", "acceptableValues" : [{"id":"1", "name":"Open"},{"id":"2", "name":"Close"},{"id":"3", "name":"Pending"},{"id":"4", "name":"Won't Fix"}] ,value:"" "prompt" : "Status"}
    ]
  }
```

## Example using a URL
```
 {
  "template" : {
    "data" : [
      {"name" : "full-name", "value" : ""},
      {"name" : "email", "value" : ""},
      {"name" : "status", "acceptableValues" : "http://.../status",value:"" "prompt" : "Status"}
    ]
  }
```

In this case the client will GET the following document

```
{
    "collection": {
        "version": "1.0",
        "href": "http:///status",
        "links": [ ....],
        "items": [
            {
                "href": "http://.../status/1",
                "data": [
                    {
                        "name": "Id",
                        "prompt": "Id",
                        "value": "1"
                    },
                    {
                        "name": "status",
                        "prompt": "Status",
                        "value": "Open"
                    }
                ]
            },
             ......
            {
                "href": "http://.../status/5",
                "data": [
                    {
                        "name": "Id",
                        "prompt": "Id",
                        "value": "5"
                    },
                    {
                        "name": "status",
                        "prompt": "Status",
                        "value": "Won't fix"
                    }
                ]
            }
        ]
    }
}
```


### References
1. https://groups.google.com/forum/#!searchin/collectionjson/autocomplete/collectionjson/-l7IbsiMfh0/mktNpa2xLqcJ
