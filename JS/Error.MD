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
### conlose.debug()、console.warn()、console.info()、console.error()
这四个方法的使用方法跟 console.log() 一模一样，差别在于输出的颜色与图标不同。下面是示例：
```html
<script type="text/javascript">
    console.debug("debug");
    console.warn("warning");
    console.info("info");
    console.error("error");
</script>
```
![Alt imgs](http://img.blog.csdn.net/20161215092759757 "console example")
### console.table()
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
