

### JavaScript是一门单线程语言
  
  一切JavaScript版的“多线程”都是用单线程模拟出来的，一起JavaScript多线程都是纸老虎。


### javascript事件循环

  1. 同步任务：指主线程上排队执行的任务，只有前一个任务执行完毕，才能执行后一个任务。
  2. 异步任务：指不进入主线程，某个异步任务可以执行了，该任务才会进入主线程执行。
  
  1. 同步和异步任务分别进入不同的执行“场所”，同步任务进入主线程，异步任务进入`Event Tableb`并注册函数。
  2. 当指定的事件完成时，`Event Table`会将这个函数移入`Event Queue`。
  3. 主线程内的任务执行完毕为空，去`Event Queue`读取相应的函数，进入主线程执行。
  上述过程会不断重复，也就常说的`Event Loop`（事件循环）
  （js引擎存在`monitroing process`进程，会持续不断的检查主线程执行栈是否为空，一旦为空，就会去`Event Queue`那里检查是否有等待被调用的函数。）
  
  
  
### 宏任务macrotask & 微任务microtask

### 相关阅读

  [并发模型与事件循环](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/EventLoop)


