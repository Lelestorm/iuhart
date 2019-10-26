## 值属性

这些全局属性返回一个简单值，这些值没有自己的属性和方法。

* `Infinity`

  > 是一个数值，表示无穷大。[参考质料](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Infinity) 

* `NaN`

  > 表示不是一个数字（Not-A-Number）。[参考质料](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/NaN) 
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
  > 相关链接
    `Number.NaN`
    `Number.isNaN()`
    `isNaN()`
  
* [`Undefined`](#Undefined)
* [`null` 字面量](#null)
* [`globalThis`](#globalThis)
