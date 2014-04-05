# Query/Template Lookup Values 

Support for autocomplete, table lookup and filtering.

1. Add an optional property to the <code>data</code> object: acceptableValues.


If it's present the value for the field can either be a list of key, a list of value pairs, or a URL.


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


### References
1. https://groups.google.com/forum/#!searchin/collectionjson/autocomplete/collectionjson/-l7IbsiMfh0/mktNpa2xLqcJ
