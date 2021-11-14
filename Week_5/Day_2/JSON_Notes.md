## JSON (JS Object Notation)
---
JSON is built on two universal data structures:

1. A collection of name/value pairs.
2. An ordered list of values.

A JSON object looks like this!

```javascript
{
  "name": "New York City",
  "boroughs": [
    "Manhattan",
    "Queens",
    "Brooklyn",
    "The Bronx",
    "Staten Island"],
  "population": 8491079,
  "area_codes": [212, 347, 646, 718, 917, 929],
  "position": { "lat": 40.7127, "lng": -74.0059 }
}
```
Features of note:
- Double quoted strings!
- Syntax must be valid javascript

---
### Serialization
---
Serialization = converting objects (or data structures more generally) to a format that can be shared among computers (typically as a string)

Deserializing is going the opposite direction (string -> object)

JSON is used in JavaScript for serializing/deserializing

#### IMPORTANT METHODS!
**JSON.parse()**: Parse a string in JSON. Can also transform the outputed value/its properties and then return that value. 

**JSON.stringify()**: Return JSON string corresponding to the inputted value

---
### JSON Media Type
---
Media type for JSON files is **application/json** when these data are sent via HTTP req/response 


JSON is LANGUAGE INDEPENDENT! So we'll see it used all over the place :)
