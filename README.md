# **NODEJS 技能树 (STILL IN PROGERSS)**

## **I: nodejs 主要学习三方面内容**

1. js 本身
2. nodejs 
3. 三方库

## **需要学的 ECMAScript, api, 函数等, 生态圈中的各种库**

### **1. ECMAScript (nodejs的根基, 即javasript)**

目前主要用es5, 出于兼容性考虑;

(重要)原型链, class

```
问题1: 1 + undefined = NaN, 1 + null = 1 
(ecmsript(es5 11.6.1) 规范中: 加法首先对两个值进行 toPrimitive 的操作, 对运算结果进行一个 toNumber 的操作)
```

```
问题2: 两个空对象的比较: var a = {}, var b = {}, a === b ?, a == b ?, a >= b ?, a <= b ? (es5 11.9.3, 11.8.5)
最直接的答案出自ecmsritpt规范;
```

### **2. nodejs 内置的 api**

> **nodejs 使用 v8 作为 javascript 的运行池, 使用 libuv 作为事件循环的框架**, 最后"上面像胶水一样黏上一堆易用的api就行成了nodejs";  
> **所以这些 api 就是学习 nodejs 时最先需要学习的必修课**;  
> 这些内容都在 nodejs 对应版本的文档中;  
> 注意: 一开始学的时候先过一遍, 先捡一些常见的学, 把这些先学熟悉了, 然后在日常的开发中慢慢积攒自己的肌肉记忆;  
> "很多东西不需要特别去记忆, 因为就算记下了, 下一个版本可能就变了, 死记无用";  
> 多注意一些版本更新的 changelog;  

### **3. nodejs 的生态圈 (最不需要学习的一部分)**

> 生态圈中的库的质量参差不齐;   
> 无论库是什么, 总之步骤都是: 检索, 看文档, 找不到就造轮子;  
> google 或 npm 自带搜索引擎;

例如: 框架 web 库, nodejs web framework, 找不到就自己造;  
npm 搜, 输入md5, 例如 md5.js, apche-md5, 使用就在包里查看他的文档就可以;  

> 使用 nodejs 生态圈里的包, 看文档就够了, 文档在看不懂就看官方教程, get start 之类, 总好过google 出来的抄来抄去的教程;   

找不到想要的包时:    
github: [me]  

> **重要: 学习如何查看文档, 重要的是学习使用 nodejs 生态圈中的库的学习方法;**  

### **4. nodejs 中包与模块机制**

nodejs 中包与模块机制都是借鉴于 commonjs 的包规范与模块规范; 参考知乎live;  

----------------------------------------
## **II. 异步**

异步: 回调地狱  

> **习惯异步是非常重要的**

> **callbakc 是 js 中异步的根本**

> promise, async, fs, http 等库中的函数都是依赖 callback

回调地域可以通过 async 包来解决, 而且 async 有非常多的流程控制函数, async.warterfall 等, 非常简单的实现了这些流程;  
**callback 是 nodejs, js 中最精髓的存在;**  

> "callback 非常慢, 但是并不是太慢, 为了解决 callback hell 引入的流程框架, 一个比一个更慢,  例如 async.await() 等
> 导致使用这些框架的应用性能直接下降 50 ~100 倍(未验证)"  

> callback 主要是要熟练, 及思维的转换; 

> promise 相较于 callback 更易学更容易掌控;  
> promise 主要配合菊花函数进行掌控(生成器函数);  

> **还是要学好 ecmacsript**;

> **async await 进行代码异步的编写**;

----------------------------------------
## **III. 深入学习**

> **"作为一个合格的后端 nodejs 开发者, 更深入的层次就是 忘记语言, 语言只是工具"**  

### **1. sql 需要学习: 检索语句的语法树索引等**    

高级的包括: **分表分库、读写分离**等, 虽然这些是 dba 需要进行的工作, 但是很多公司是不具有 dba 这个岗位的, 很多时候还是要靠自己;   
"现在大多数的 nodejs 程序都是使用 orm 来搞定, 所以其实很多情况下用不到去写 sql 语句, 而是通过 orm 中的函数进行搞定";     
本节中的数据库学习更多的还是针对于如何去**更好的设计一个数据库, 如表结构设计和 index 的设计**, 某种意义上说 redis 也是 nosql, 也不能滥用;   

### **学习 nodejs 的后端思想**  
1. 安全
2. 网络编程
3. 算法和数据结构
4. 数据库

> **2. 数据库是重要的后端内容**

**设计后端api时**  
首先考虑设计是否安全, 其次是性能和服务器压力等, 后端是一个应用的最后一道防线, 一定要严格把关;  
因为前端安全性再好, 一旦有人绕过前端直接给后端发请求的话, 攻击就直接发到后端了;   
因此学习后端思维非常重要;   
后端比较重要的一个抽象思维: mvc  
抽象还有很多种方式, "解耦的代码会非常好维护, 使得接盘侠非常方便; "  
比较推崇面向对象的抽象方法;  

**设计模式**   
一个合格的程序员可能所需要了解的;    
如 工厂模式、适配器模式、单例模式等, 在日常中会经常用到;  

**算法和数据结构重要**   
算法和数据结构在日常中不知不觉的就用到了;  
比如 redis 就是用了一个 set 的非常常见的数据结构, 查询等操作都已经封装好了, 然后通过网络返回结果;   
比如哈希(我为什么使用哈希*), 哈希的妙用(唯一组件问题)   

----------------------------------------
## **IV. nodejs 在其他领域的学习**
nodejs 作为一个在本地执行的运行时, 而不是像前端 js 一样只能寄宿于浏览器中, 理论上 nodejs 可以做其他同类型语言都可以做的事
如科学计算人工智能等等, 无非是领域的生态圈强不强;  

> **"语言只是工具"**  

> **V8 是 nodejs 的根本, 剖析 nodejs 源码前先了解 v8**

----------------------------------------
## **V. RECAP:**

- **贯彻 callback 的思想还是非常重要的, 毕竟 callback 才是 nodejs 的精髓所在**, 其他内容都是其他语言里借鉴过来的;
- 摸索出后端开发的的一套体系 -- "**nodejs 特色后端理论体系**"; 
- 数据库(性能优化, 表的设计);
- nodejs 也可以进行其他任何领域的事情;
- 在深入学习一整套体系的同时可以试着阅读 nodejs 的源码, 了解它到底是个什么样的东西;

> **对nodejs 的疑问不要局限于 "nodejs的语法如何" 或 "异步时采用什么样的方案比较好"**