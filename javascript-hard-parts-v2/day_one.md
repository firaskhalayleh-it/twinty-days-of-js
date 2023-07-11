# day one of learinig course javascript hard parts v2
## introduction




## javascript principles


## functions & callbacks 



# homeworks :

### homework [one](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem)
``` javascript
const squareList = arr => {
  // Only change code below this line
  const result  = arr.filter(val=>parseInt(val)===val&&val>0).map(val=>val*val)
  return result;
  // Only change code above this line
};

const squaredIntegers = squareList([4, 5.6, -9.8, 3.14, 42, 6, 8.34, -2]);
console.log(squaredIntegers);
```
### homework [tow](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs)
``` javascript
// Only change code below this line
function urlSlug(title) {
const res = title
.toLowerCase()
.split(' ')
.filter(val=>val!=='')
.join('-');
return res;
}
// Only change code above this line
console.log(
urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone"))
```
