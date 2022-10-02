# JS-数组常用方法 
JS数组的常用方法 


```javascript
// 创建数组
var arr1 = [1, 2, 3];
console.log(arr1);

var arr2 = new Array(4, 5, 6);
console.log(arr2);

var arr3 = Array(7, 8, 9);
console.log(arr3);

var arr4 = Array.of(10, 11, 12);
console.log(arr4);

//访问数组
console.clear();

var arr = [1, 2, 3];
console.log(arr.length);
console.log(arr[0]);
console.log(arr[1]);
console.log(arr[2]);
console.log(arr[3]);

//添加元素
console.clear();

var arr = [1, 2, 3];
arr[0] = 4;
console.log(arr);
arr[3] = 5;
console.log(arr);
arr[8] = 9;
console.log(arr);

//删除元素
console.clear();
var arr = [1, 2, 3];
console.log(arr);
arr.length = 0;
console.log(arr);

var arr = [1, 2, 3, 4, 5, 6];
arr.splice(2, 1);
console.log(arr);
// 方法splice (从索引几开始,删除几个,要添加哪些)
arr.splice(1, 2, 3, 7, 8);
console.log(arr);

arr.splice(1, 0, 9, 10);
console.log(arr);

//数组遍历
console.clear();
var arr = [1, 3, 5, 7, 9];
//1.for循环遍历
for (let i = 0; i < arr.length; i++) {
  console.log(arr[i]);
}
console.log("for...of");
//2.for of遍历
for (let ele of arr) {
  console.log(ele);
}
//3.forEach遍历 (第一个元素,元素的索引，数组本身)
arr.forEach((ele, index, self) => {
  console.log(ele, index, self);
});

//栈模式  后进先出
console.clear();
var arr = [1, 2, 3];
arr.push(4, 5); // push方法 往数组末尾添加
console.log(arr);

arr.pop(); // pop 方法 删除数组末尾
console.log(arr);

//队列模式 先进先出
console.clear();
var arr = [1, 2, 3, 4, 5, 6];

arr.shift(); // shift方法 删除数组头部
console.log(arr);
arr.unshift(0, 1); //unshift 在数组头部增加
console.log(arr);

//反转数组
console.clear();
var arr = [1, 2, 3];
console.log(arr);
arr.reverse(); // reverse方法 将数组反转
console.log(arr);

console.log(
  "WonYves"
    .split("") //将字符串中的每一位分隔开形成一个数组
    .reverse() // 反转数组
    .join("") // 数组用连接符连接成为一个字符串
);

//数组排序
console.clear();
var arr = [2, 5, 1, 9, 7, 6, 3, 8, 4];
arr.sort(); //将数组自动排序
console.log(arr);

arr.sort((a, b) => b - a);
console.log(arr);

//数组的链接
console.clear();
var arr1 = [1, 2, 3];
var arr2 = [4, 5, 6];
console.log(arr1.concat(arr2)); //concat 连接方法

//数组的裁切
console.clear();
var arr = [1, 2, 3, 4, 5, 6, 7, 8];
console.log(arr.slice(3, -1));
// splice 是从索引开始 删除 第二个参数是从索引开始删除几个 第三个参数是需要添加的数值
// slice 是从索引开始裁切 第二个参数结束的索引 可以是负数 没有第三个参数

//map 映射数组
console.clear();
var arr = [1, 2, 3, 4];
var mapped = arr.map((ele) => ele * 2);
console.log(mapped);
console.log(arr);
// map和forEach的区别 两个都可以接受3个参数(当前元素,当前索引,原数组) forEach没有返回值 map有返回值  map遍历后会生成一个新的数组

console.clear();
//reduce 数组  可以完成数组求和
//接收4个参数(上一次计算的结果,当前遍历到的数组元素，当前遍历到的索引，原数组)
var arr = [1, 2, 3, 4, 5, 6];
var result = arr.reduce((a, b) => a + b, 0);
console.log(result);

var result2 = arr.reduce((c, d) => c + d);
console.log(result2);

//数组过滤 filter
console.clear();
var arr = [1, 2, 3, 4, 5, 6];
var filterS = arr.filter((item) => item > 4);
console.log(filterS); // 5,6

//数组测试
console.clear();
var arr = [1, 2, 3, 4, 5, 6];
var result = arr.every((item) => item > 5);
console.log(result);

var resultSome = arr.some((item) => item > 1);
console.log(resultSome);

//解构操作符
console.clear();
var arr = [1, 2, 3];
var [a, b, c] = arr;
console.log(a, b, c);

var [, f] = arr;
console.log(f);

function myparentens() {
  let name = "kerwin";
  let position = "前端相声演员";
  return [name, position];
}

var [myname, myposition] = myparentens();
console.log(myname, myposition);

//rest 操作符 展开运算符
console.clear();
var arr1 = [1, 2, 3, 4];
var arr2 = [5, 6, 7, 8];
var arr = [...arr1, ...arr2];
console.log(arr);

//多维数组
console.clear();
var arr = [];
for (let i = 0; i < 5; i++) {
  arr[i] = [];
  for (let j = 0; j < 4; j++) {
    arr[i][j] = i + j;
  }
}
console.log(arr);
