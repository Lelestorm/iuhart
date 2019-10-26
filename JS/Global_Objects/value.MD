## 值属性

这些全局属性返回一个简单值，这些值没有自己的属性和方法。

* `Infinity` [参考](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Infinity) 

  > 是一个数值，表示无穷大。

* `NaN` [参考](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/NaN)

  > 表示不是一个数字（Not-A-Number）。
  
  > 在执行自比较之中：`NaN`，也只有`NaN`，比较之中不等于它自己。
  ```JavaScript
    NaN === NaN;              // false
    Number.NaN === NaN;       // false
    isNaN(NaN);               // true
    
    function valueIsNaN(v) {
      return v !== v;
    }
    valueIsNaN(1);            // false
    valueIsNaN(Number.NaN);   // true  
  ```
  > 相关  `Number.NaN`  `Number.isNaN()`  `isNaN()`
  
* [`undefined`](#undefined) [参考](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/undefined) 

  > 表示原始值`undefined`。它是一个JavaScript的 原始数据类型 。
  > 如果一个函数没有使用return语句指定返回值，就会返回一个`undefined`值。
  > 使用`undefined`和**严格相等（或不相等）**操作符，或使用`typeof()`, 验证一个变量是否拥有值。
  ```JavaScript
    var x;
    if ( x === undefined ) {
      // 执行
    } else {
      // 不执行
    }
    
    if ( typeof x === 'undefined' ) {
      // 执行
    }
    
    // typeof 不会在一个变量未被声明的时候抛出一个错误
    if ( y === undefined ) {
      // 抛出错误 ReferenceError: y is not defined
    }
    if ( typeof y === 'undefined' ) { 
      // 没有错误，执行结果为 trun
    }
  ```
  
* [`null` 字面量](#null)
* [`globalThis`](#globalThis)
