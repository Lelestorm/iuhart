## Error 对象

## Console 对象
### console.log()
```html
<script>
    console.log("Hello", "World");
    // Hello World
    // console.log() 的参数可以有多个，输出的结果以一个空格隔开。
    console.log("%d年%月%日", 2017, 08, 14);
    // 2017年08月14日
    // console.log() 可以使用 C 语言 printf() 风格的占位符，不过其支持的占位符种类较少，只支持字符串（%s）、整数（%d或%i）、浮点数（%f）和对象（%o）
</script>
```
### console.warn()、console.info()、console.error()
方法的使用方法跟 console.log() 一模一样，差别在于输出的颜色与图标不同。下面是示例：
```html
<script type="text/javascript">
    console.log("log");
    console.info("info");
    console.warn("warning");
    console.error("error");
</script>
```
![](./images/error-2-0.png "")
### console.table()
当输出类似于这种两层嵌套的对象时，我们可以选择 console.table() 以表格的形式输出。当然，嵌套三层及以上的也会以表格形式输出，但限于表格只能显示二维信息的特点，其会在嵌套三层或以上的地方会显示 "Object" 字符串。
```html
<script type="text/javascript">
    const car = {
        "BMW" : {"name" : "宝马z4", "price" : 87.4},
        "Benz" : {"name" : "奔驰SLC", "price" : 106.8},
        "Lamborghini" : {"name" : "兰博基尼", "price" : 432.6}
    }
    console.log(car);
    console.table(car);
</script>
```
控制台console.log() 对比 console.table()输出结果： 
![console.table()示例](./images/error-2-1.png "")
### console.time()、console.timeEnd()
在调试时，我们经常需要知道一段代码执行时间，用 console.time() 和 console.timeEnd() 包围要测试运行时间的代码，这两个方法的参数保持一致，以便正确识别和匹配代码开始和结束的位置。看下面一段代码：
```html 
<script type="text/javascript">
    console.time("for test")
    var arr = [];
    for(var i=0; i<=100000; i++){
        arr.push({"key":i});
    }
    console.timeEnd("for test");
</script>
```
输出为：for test: 22.484130859375ms
### console.assert()
console.assert() 类似于单元测试中的断言，当表达式为 false 时，输出错误信息。示例如下：
```html
<script type="text/javascript">
    var arr = [1,2,3];
    console.assert(arr.length === 4);
</script>
```
![](./images/error-2-2.png "")
### console.count()
调试代码时，我们经常需要知道一段代码被执行了多少次，我们可以使用 console.count() 来方便的达到我们的目的。示例如下：
```html
<script type="text/javascript">
    for(var i=0; i<=6; i++){
        console.count("For i");
    }
</script>
```
![](./images/error-2-3.png "")
### console.group()、 console.groupEnd() 与 console.groupCollapsed()
一般的 console.log() 方法的输出没有层级关系，在需要一些显示层级关系的输出中显得苍白无力，使用 console.group() 可以达到我们的目的。示例代码如下：
```html
<script type="text/javascript">
    console.group("One");
    console.log("1-0");
    console.log("1-1");
    console.log("1-2");
    console.groupEnd("One");
    console.group("Two");
    console.log("2-0");
    console.log("2-1");
    console.log("2-2");
    console.groupEnd("Two");
</script>
```
![](./images/error-2-4.png "")
把 "group" 换成 "groupCollapsed"，则默认为折叠运行结果。
### console.dir()
console.dir() 为了将特定的 JS 对象显示为可以交互的列表，而列表是折叠起来的。

在 Chrome 中打印 DOM 元素时，两个方法输出的结果大不一样。console.log() 会将 DOM 元素以 HTML 的形式输出，而 console.dir() 则会以 JSON 对象的形式输出。
![](http://img.blog.csdn.net/20161215094243638 "")
