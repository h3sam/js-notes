#js/basics [js.info](https://javascript.info/json)

# JSON.parse
```javascript
JSON.parse(str, reviver)
// str is the stringified version of a json file, and the reviver is
// a function that goes through the key:value pairs recursively and
// usually is used to **revive** data types that are lost in stringifying them.
```

# JSON.stringify
```javascript
JSON.stringify(obj, replacer, space)
```
- the object is the JSON object that we have and want to stringify
- the replacer is a function that goes through all the key:value pairs **recursively** and usually is used for filtering out specific keys or values.
### Replacer function gimmicks
- [!] this method has a very niche specification and that is it references to the whole object with an empty string key, that has the whole object.
```js
let room = {
  number: 23
};

let meetup = {
  title: "Conference",
  participants: [{name: "John"}, {name: "Alice"}],
  place: room // meetup references room
};

room.occupiedBy = meetup; // room references meetup

alert( JSON.stringify(meetup, function replacer(key, value) {
  alert(`${key}: ${value}`);
  return (key == 'occupiedBy') ? undefined : value;
}));

/* key:value pairs that come to replacer:
:             [object Object]
title:        Conference
participants: [object Object],[object Object]
0:            [object Object]
name:         John
1:            [object Object]
name:         Alice
place:        [object Object]
number:       23
occupiedBy: [object Object]
*/
```
>[!warning] This is to be cautious of when trying to get rid of the cyclic references; if you don't acknowledge the empty key when removing pairs with the object, you will completely bypass the whole thing.


- [*] while stringifying, the method ignores keys with undefined values and symbols
- [*] this method cannot stringify objects with circular references.