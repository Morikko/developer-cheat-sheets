### Create a streams from a stream
[Stackoverflow source](http://stackoverflow.com/questions/12755997/how-to-create-streams-from-string-in-node-js)
```javascript
var s = new stream.Readable();
s._read = function noop() {};
s.push('your text here');
s.push(null);
```
