## Beginner - Reduce but Grow

### Given a non-empty array of integers, return the result of multiplying the values together in order. Example:

```
[1, 2, 3, 4] => 1 * 2 * 3 * 4 = 24
```

#### The Solution


```javascript
// SOLUTION 1
// function grow(x){
//   result = x[0];
//   for (let i = 1; i < x.length; i++) {
//     result *= x[i];
//   }
//   return result;
// }

// SOLUTION 2
const grow = (x) => x.reduce((accumulator, curr) => accumulator * curr);
```