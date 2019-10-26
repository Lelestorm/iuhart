## 值属性

这些全局属性返回一个简单值，这些值没有自己的属性和方法。

* [`Infinity`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Infinity) 

  > 是一个数值，表示无穷大。

* [`NaN`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/NaN)

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
  
* [`undefined`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/undefined) 

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
    
    // typeof 操作符返回一个字符串；不会在一个变量未被声明的时候抛出一个错误。
    if ( y === undefined ) {
      // 抛出错误 ReferenceError: y is not defined
    }
    if ( typeof y === 'undefined' ) { 
      // 没有错误，执行结果为 trun
    }
  ```
  
* [`null` 字面量](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/null)
  
  > 特指对象的值未设置。它是 JavaScript 基本类型 之一。
  
  > 值 null 是一个字面量，它不像undefined 是全局对象的一个属性。null 是表示缺少的标识，指示变量未指向任何对象。把 null 作为尚未创建的对象，也许更好理解。在 APIs 中，null 常在返回类型是对象，但没关联值的地方使用。
  ```JavaScript
    // foo不存在，它从未被定义过或初始化过。
    foo;
    "ReferenceError: foo is not defined"
    
    // foo现在是已知存在的，但它没有类型或值。
    var foo;
    foo = null;
    null
  ```
  
  > **`null` 与 `undefined` 的不同点** 
  ```JavaScript
    // 当检测 null 与 undefined 时，注意相等(==)与全等(===)两个操作符的区别，前者会执行类型转换。
    typeof null                           // "Object" 
    typeof undefined                      // "undefined"
    null === undefined                    // false
    null == undefined                     // true
    null === null; null == null; ! null   // true
    isNaN(1 + null)                       // false
    isNaN(1 + undefined)                  // true
  ```
  
* [`globalThis`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/globalThis)
  > **这是一个实验中的功能**




