# MongoDB $inc Operator Error
This repository demonstrates a common error when using the `$inc` operator in MongoDB. The `$inc` operator is used to increment or decrement a numeric field. However, if the field is not a number, it can lead to unexpected behavior or data corruption.

## Bug
The following code snippet demonstrates the incorrect usage of the `$inc` operator.
```javascript
db.collection.updateOne({"_id":1},{"$inc":{"field":"value"}});
```
In this example, the `field` is not a number. The `$inc` operator expects a numeric value. Therefore, this code will throw an error.

## Solution
To fix this error, ensure that the field is a number before using the `$inc` operator.
```javascript
db.collection.updateOne({"_id":1},{"$inc":{"field":1}});
```