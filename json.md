# JSON

We basically have two things to remember:
- `jsondata = JSON.stringify(objIn)`, used to convert a javascript object into JSON;
- `objectdata = JSON.parse(jsondataIn)`, used to convert JSON into a javascript object;


Note that although JSON stands for Javascript Object Notation, we still
need to convert our objects into JSON when interacting with some APIs,
since the real object notation in javascript is less strict with respect
to the JSON format.
