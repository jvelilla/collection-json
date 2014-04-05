# Attachment 

Support file attachements to send and receive CJ documents with file attachemtns.[1]


1. Add an optional property to the <code>data</code> object: files [ARRAY].

# Files
The files array SHOULD contain one or more anonymous objects. Each object  MAY have any of two possible properties: name (REQUIRED), value (OPTIONAL).  If present, the value property should be encoded using Base64



```
 {
  "template" : {
    "data" : [
      {"name" : "full-name", "value" : ""},
      {"name" : "email", "value" : ""},
      {"name" : "attachments", "files" : [ {"name": "", "value": "" } ] , "prompt" : "Attachments"}
    ]
  }
```

### References
1. https://groups.google.com/forum/#!topic/collectionjson/pzdkNGx-aPE
