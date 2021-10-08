# uni-app-list-
uni-app里list一些操作，添加、删除等等
【使数组发生更新】方法：修改了原始数组，会触发视图更新
push() 、 pop()、shift()、unshift()、 splice() 、sort()、 reverse()、 join()
【返回新数组、替换数组】：不会变更原始数组，而总是返回一个新数组
filter()、concat() 、 slice()、 map()
【 .filter() 】方法
filter创建一个新数组，新数组中的元素是符合指定条件的元素。

filter方法不会改变原数组，不对空数组进行检测。
举例：

const arr= [32, 33, 16, 40];
const arr1 = arr.filter(item => item >= 18)
console.log(arr) // [32, 33, 16, 40]
console.log(arr1) // [32, 33, 40]
【 .map() 】方法
map() 方法返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。
map() 方法按照原始数组元素顺序依次处理元素。

filter方法不会改变原数组，不对空数组进行检测。
举例：

const arr= [4, 9, 16, 25];
const arr1 = arr.map(item => item+2)
console.log(arr) // [4, 9, 16, 25]
console.log(arr1) // [6, 11, 18, 27]
【 .forEach() 】方法
forEach() 方法用于调用数组的每个元素，并将元素传递给回调函数。

注意: forEach() 对于空数组是不会执行回调函数的。
tips: forEach()中不支持使用break(报错)和return(不能结束循环)，有需要时可使用常规的for循环。

const arr= [4, 9, 16, 25];
const arr1 = [];
arr.forEach(item => arr1.push(item))
console.log(arr)   // [4, 9, 16, 25]
console.log(arr1)  // [4, 9, 16, 25]
【 .concat() 】方法：合并数组
举例：

// 数组直接和参数合并
const array = ['a','b','e'];
console.log(array.concat('h','i')); // "a", "b", "e", "h", "i"

// 2个数组合并
const array = ['a','b','e'];
const b = ['c','d']
console.log(array.concat(b));   // a b e c d

// 3个数组合并
const array = ['a','b','e'];
const b = ['c','d'];
const c = ['f','g'];
console.log(array.concat(c,b)); // "a", "b", "e", "f", "g", "c", "d"
【 .push() 】方法
push在数组的末尾增加一个元素，一次可以增加多个
举例：

const array = ['a','b','c'];
array.push('d');
console.log(array); // a b c d
array.push('e','f','g');
console.log(array); // a b c d e f g
【 .join() 】方法
join() 方法用于把数组中的所有元素放入一个字符串。
元素是通过指定的分隔符进行分隔的。

const array = ['a','b','e'];
console.log(array.join('-'));   // a-b-e
【 .pop() 】方法
pop在数组末尾删除一个元素
举例：

const array = ['a','b','c','d'];
array.pop();
console.log(array); // a b c 
【 .shift() 】方法
shift删除第一个元素
举例：

const array = ['a','b','c','d'];
array.shift();
console.log(array); // b c d
【 .unshift() 】方法
unshift在数组头部增加一个元素或者多个
举例：

const array = ['c','d'];
array.unshift('b');
console.log(array); // b c d
array.unshift('e','a');
console.log(array); // e a b c d
【 .splice() 】方法：根据索引设置元素
splice删除、插入或者替换元素。语法：this.arr.splice(index, num, value);
举例：

//  删除  index=1的1个元素
const array = ['a','b','c','d'];
array.splice(1, 1)
console.log(array); // a c d

//  插入  在index=1后插入e
const array = ['a','b','c','d'];
array.splice(1, 0, 'e')
console.log(array); // a e b c d

//  替换 index=1的1个元素
const array = ['a','b','c','d'];
array.splice(1, 1, 'e')
console.log(array); // a e c d
$set方法：删除、插入或者替换元素。
语法：arr.$set(index, num, value);和splice() 一样的语法。

【 .sort() 】方法
sort数组排序
举例：

const array = ['a','c','b','d'];
array.sort();
console.log(array); // "a", "b", "c", "d"
【 .reverse() 】方法
reverse 数组反转
举例：

const array = ['a','c','b','d'];
array.reverse();
console.log(array); // "d", "b", "c", "a"
【 .slice() 】方法：可从已有的数组中返回选定的元素。
语法：arr.slice(start,end);
2个参数分别是：即要返回项的起始和结束位置。

参数：
start 必需。规定从何处开始选取。如果是负数，那么它规定从数组尾部开始算起的位置。也就是说，-1 指最后一个元素，-2 指倒数第二个元素，以此类推。
end 可选。规定从何处结束选取。该参数是数组片断结束处的数组下标。如果没有指定该参数，那么切分的数组包含从 start 到数组结束的所有元素。如果这个参数是负数，那么它规定的是从数组尾部开始算起的元素。

返回值
返回一个新的数组，包含从 start 到 end （不包括该元素）的 arrayObject 中的元素。
说明
请注意，该方法并不会修改数组，而是返回一个子数组。
当只给slice()传递一个参数时，该方法返回从该参数指定位置开始到当前数组末尾的所有项。
举例：
const array = ['a','b','c','d'];
console.log(array.slice(1,3));  // b c
console.log(array.slice(1));    // b c d
console.log(array.slice(-3));   // b c d
console.log(array.slice(-1));   // d
【 .find() 】方法
find返回符合要求的第一个数组元素，
find方法使用时，数组中的每个元素都会执行find中的函数:

当数组中的元素满足函数条件时则返回true，find()返回符合要求的数组元素值，之后的值不会再调用执行函数。
当数组元素没有满足find中的函数条件时，则返回undefined。
注意:

find() 对于空数组，函数是不会执行的。
find() 并没有改变数组的原始值。
举例：
const arr= [4, 9, 16, 25];
const b = arr.find(item => item>10)
const c = arr.find(item => item<1)
console.log(arr)   // [4, 9, 16, 25]
console.log(b)  // 16
console.log(c)  // undefined
【 .findIndex() 】方法
findIndex返回符合函数条件的数组元素下标，空数组不会执行。
findIndex() 方法返回传入一个测试条件（函数）符合条件的数组第一个元素位置。
findIndex() 方法为数组中的每个元素都调用一次函数执行：

当数组中的元素在测试条件时返回 true 时, findIndex() 返回符合条件的元素的索引位置，之后的值不会再调用执行函数。
如果没有符合条件的元素返回 -1
注意:

findIndex() 对于空数组，函数是不会执行的。
findIndex() 并没有改变数组的原始值。
举例：

const arr= [4, 9, 16, 25];
const b = arr.findIndex(item => item>10)
const c = arr.findIndex(item => item<1)
console.log(arr)   // [4, 9, 16, 25]
console.log(b)  // 2
console.log(c)  // -1
【 .some() 】方法
some方法会检测数组中的元素是否满足指定条件（函数提供）。
some() 方法会依次执行数组的每个元素：

如果有一个元素满足条件，则表达式返回true , 剩余的元素不会再执行检测。
如果没有满足条件的元素，则返回false。
注意：

some() 不会对空数组进行检测。空数组不会执行。
some() 不会改变原始数组。
举例：
const arr= [4, 9, 16, 25];
const b = arr.some(item => item>10)
const c = arr.some(item => item<1)
console.log(arr)   // [4, 9, 16, 25]
console.log(b)  // true
console.log(c)  // false
【 .every() 】方法
every检测数组中的元素是否都满足条件，有一个不满足条件的则返回false，空数组不会执行。
every() 方法用于检测数组所有元素是否都符合指定条件（通过函数提供）。
every() 方法使用指定函数检测数组中的所有元素：

如果数组中检测到有一个元素不满足，则整个表达式返回 false ，且剩余的元素不会再进行检测。
如果所有元素都满足条件，则返回 true。
注意：

every() 不会对空数组进行检测。
every() 不会改变原始数组。
const arr= [4, 9, 16, 25];
const b = arr.every(item => item>10)
const c = arr.every(item => item>1)
console.log(arr)   // [4, 9, 16, 25]
console.log(b)  // false
console.log(c)  // true
