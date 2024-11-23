Element Query operators

1)$exists
2)$type


//------------$exists-------------//

$exists => Return the docs which docs contains status field
[{
  "id":1,
  "data": 12,
  "status":"1"
},
{
  "id":2,
  "data": 20
},
{
    "id":3,
    "data": 22,
    "status":1
}]


find({status:{$exists:true}})

Output:[
  {
    "id":1,
    "data": 12,
    "status":"1"
  },
  {
    "id":3,
    "data": 22,
    "status":1
}
]


//------------$type-------------//

$type => Returns a string that specifies the BSON type of the argument.

Example types :

2 - string
4 - Array

You can see available BSON types in mongo db website

Link : https://www.mongodb.com/docs/manual/reference/operator/query/type/?

find({status:{$type:2}})  // return the docs which status field of docs contains string datatype

Output:

[{
    "id":1,
    "data": 12,
    "status":"1"
  }]