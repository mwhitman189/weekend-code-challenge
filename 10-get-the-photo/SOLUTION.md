# Solution

TBD

## Other solutions

## The reducer method - [mwhitman189](https://github.com/mwhitman189)

This seems like a problem screaming for '.reduce', so here it is:
```js
function getLargePhotos(photos) {
  return photos.reduce((acc, curr) => {
    acc.push(curr['large']);
    return acc;
  }, []);
}
```

However, as pointed out by [shin10kudev](https://github.com/shin10kudev), this could be refactored to make it more readable by using object destructuring:
```js
function getLargePhotos(photos) {
  return photos.reduce((acc, {large}) => {
    acc.push(large);
    return acc;
  }, []);
}
```

Or even further to make it a one-liner with implicit return (Thanks, [shin10kudev](https://github.com/shin10kudev)!):
```js
const getLargePhotos = (photos) => photos.reduce((acc, {large}) => [...acc, large], []);
```
