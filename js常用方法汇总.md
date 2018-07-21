## js基础常用方法一览
- length方法可以获取字符串和数组的长度
  + `console.log('天赐桃花源，桃香满天下'.length) // 11 `
  + `console.log(['天下隆中对', '传奇襄阳城'].length) // 2 `
- 检测简单的数据类型的方法
  + typeof方法用于检测简单的数据类型如`typeof 12`
  + instanceof的实例方法检测如`[] instanceof Array // true`
  + `arr.constructor == Array`判断arr的构造函数是否为数组，如果是则arr是数组
  + `Array.isArray([])`判断是否是数组
  + 精确判断数据类型`Object.prototype.toString.call(arr)`
- 数据类型之间的转化方法
  + toString()转换为字符串
  + parseInt()转换为整型
  + parseFloat()把字符串转换成浮点数
  + 取正转换为数值型`var str = '500';console.log(+str);`
  + Boolean()转换为布尔。2句口诀
  + 用取反隐式转换如`var str = '襄阳卡五星'; console.log(!str); // false`
- Math方法
  + Math.max(42,52)取2个值中的最大值 52
  + Math.min(42,33)取2个值中的最小值 33
  + Math.max.apply(null,arr) 取数组中的最大值
  + Math.min.apply(null,arr) 取数组中的最小值
  + Math.PI             // 圆周率
  + Math.random()       // 生成随机数
  + Math.floor()/Math.ceil()   // 向下取整/向上取整
  + Math.round()        // 取整，四舍五入`注意``Math.round(-1.5) // -1`
  + Math.abs()          // 绝对值
  + Math.max()/Math.min()    // 求最大和最小值
  + Math.sin()/Math.cos()    // 正弦/余弦
- Date对象相关
  + new Date() 来创建日期实例(对象)
  + getTime()     // 返回毫秒数和valueOf()结果一样，valueOf()内部调用的getTime()
  + getMilliseconds() 
  + getSeconds()  // 返回0-59
  + getMinutes()  // 返回0-59
  + getHours()    // 返回0-23
  + getDay()      // 返回星期几 0周日   6周6
  + getDate()     // 返回当前月的第几天
  + getMonth()    // 返回月份，***从0开始***
  + getFullYear() //返回4位的年份  如 2016
  - toDateString()
  - toTimeString()
  - toLocaleDateString()
  - toLocaleTimeString()
- console对象的方法
  + console.log()方法用于在控制台输出信息。它可以接受多个参数，逗号分隔
  + console.warn()方法用于输出黄色警告信息
  + console.error()方法用于输出红色错误信息
  + console.dir()方法用来对一个对象进行检查，并以易于阅读和打印的格式显示
- 数组的常用方法
  ```javascript
  push()      // 往数组中添加，并返回数组的长度
  pop()       // 删除数组中的最后一项，并返回删除的那一项
  shift()     // 取出数组中的第一个元素，修改length属性
  unshift()   // 在数组最前面插入项，返回数组的长度
  // 3 排序方法
  reverse() //翻转数组
  sort();   //即使是数组sort也是根据字符，从小到大排序
  // 带参数的sort是如何实现的？
  // 4 操作方法
  concat()    //把参数拼接到当前数组
  slice()     //从当前数组中截取一个新的数组，不影响原来的数组，参数start从0开始,end从1开始
  splice()    //删除或替换当前数组的某些项目，参数start, deleteCount, options(要替换的项目)
  // 5 位置方法
  indexOf()、lastIndexOf()   //如果没找到返回-1
  // 6 迭代方法 不会修改原数组(可选)  html5
  every()、filter()、forEach()、map()、some()
  // 7 方法将数组的所有元素连接到一个字符串中。
  join()
  // 8 将字符串分割为数组
  split()
  ```
- 清空数组
  ```javascript
  // 方式1 推荐 
  arr = [];
  // 方式2 
  arr.length = 0;
  // 方式3
  arr.splice(0, arr.length);
  // 补充 splice() 方法向/从数组中添加/删除项目，然后返回被删除的项目
  // 1. 语法： arrayObject.splice(index,howmany,item1,.....,itemX)
  // 1.1 index 必需。整数，规定添加/删除项目的位置，使用负数可从数组结尾处规定位置。
  // 1.2 howmany 必需。要删除的项目数量。如果设置为 0，则不会删除项目。
  // 1.3 item1, ..., itemX可选。向数组添加的新项目。
  // 1.4 具体使用案例
  var arr = ["张三","李四","王五","赵六","H5","CSS3"]
  document.write(arr + "<br />")
  arr.splice(2,3,"Itcast")
  document.write(arr)
  ```

- 字符串的方法介绍
  ```
  // 1 字符方法
  charAt()        //获取指定位置处字符
  charCodeAt()    //获取指定位置处字符的ASCII码
  str[0]          //HTML5，IE8+支持 和charAt()等效
  // 2 字符串操作方法
  concat()        //拼接字符串，等效于+，+更常用
  slice()         //从start位置开始，截取到end位置，end取不到
  substring()     //从start位置开始，截取到end位置，  end取不到
  substr()        //从start位置开始，截取length个字符
  三者区别[三者区别](https://www.cnblogs.com/littledu/archive/2011/04/18/2019475.html)
  // 3 位置方法
  indexOf()       //返回指定内容在元字符串中的位置
  lastIndexOf()   //从后往前找，只找第一个匹配的
  // 4 去除空白
  trim()          //只能去除字符串前后的空白
  // 5 大小写转换方法
  to(Locale)UpperCase()   //转换大写
  to(Locale)Lower Case()   //转换小写
  // 6 其他
  replace(a, b) 用法str.replace(a, b) 在str中用b替换a
  split()
  ```

## jsAPI常用方法

-  获取页面元素
   ```javascript
   // 1 通过id获取元素
   document.getElementById(id);
   // 2 通过标签获取元素
   document.getElementsByTagName('div');
   // 3 通过class获取 兼容性IE9+
   document.getElementsClassName()
   // 4 HTML5新增的选择器 兼容性IE9+
   // 4.1 默认选择是一个nodeList集合，可理解为数组
   document.querySelectorAll(selector)
   // 4.2 默认选择是数组中的第一个元素
   document.querySelector(selector)
   // 4.3 备注 selector参数可以是以前你们通过css方式找到某个元素的任何方式
   ```

- 设置DOM
  ```
  // 1. dom.classList.add(class)     增加一个class类
  // 2. dom.classList.remove(class)  移除一个class类
  // 3. dom.classList.toggle(class)  无则添加class有则去掉calss
  // 4. box.classList.contains('df') 判断box是否有df这个类
  ```

- 自定义属性操作和常见事件操作
  ```
  getAttribute() 获取标签行内属性
  setAttribute() 设置标签行内属性
  removeAttribute() 移除标签行内属性
  与element.属性的区别: 上述三个方法用于获取任意的行内属性。
  // 给元素注册事件     
  addEventListener()    事件监听
  removeEventListener() 移除事件监听
  onclick       鼠标单击事件
  onmouseover   鼠标移入 会冒泡到父元素上
  mouseenter    等同于mouseover不会会冒泡到父元素上
  onmouseout    鼠标移出
  onfocus       获得焦点
  onblur        失去焦点
  onmouseup     鼠标按键放开时触发
  onmousedown   鼠标按键按下触发
  onmousemove   鼠标移动触发
  onkeyup       键盘按键按下触发
  onkeydown     键盘按键抬起触发
  ```

- 获取父子节点
  ```
  // 1. parentNode 获取父节点 ***掌握***
  // 2.1 childNodes 获取子节点(包括属性、文本、元素节点)
  // 2.2 children   获取子元素 强烈推荐使用 ***掌握***
  // 3.1 nextSibling/previousSibling 获取前一个/后一个节点
  // 3.2 nextElementSibling/previousElementSibling 正常浏览器(ie9+)获取前一个/后一个元素
  // 4.1 firstChild/lastChild 获取第一个/最后一个子节点
  // 4.2 firstElementtChild/lastElementChild 正常浏览器(ie9+)获取前获取第一个/最后一个元素
  // 兼容
  // var nextTag = div.nextElementSibling || div.nextSibling
  // var prevTag = div.previousElementSibling || div.previousSibling
  // dom.hasChildNodes() 判断dom是否有子节点
  ```

- 常用元素操作方法
  ```
  // 节点操作，方法
  // 0. 创建元素节点
  document.createElement('ul')
  // 1. appendChild()
  // 注意如果页面上存在就会移除然后在插入到dom中去
  var ul = document.getElementById('ul')
  var sel = document.getElementById('sel')
  sel.appendChild(ul.children[0])
  // 2. insertBefore()
  var ul = document.getElementById('ul')
  ul.insertBefore(li, ul.children[0])   // 将li插入到ul的第一个元素前
  // 3. removeChild()
  ul.removeChild(ul.children[1])
  // 4. replaceChild()
  ul.replaceChild(div, ul.children[0])  // 用div替换ul中的第一个元素
  // 5. 克隆节点
  li.cloneNode(true)
  ```


- 取消默认行为的执行和阻止冒泡
  ```
  // 1 取消默认行为
  // 1.1取消默认行为执行
  return false;   

  // 1.2 DOM标准方法
  e.preventDefault();

  // 1.3 IE的老版本，非标准方式 了解
  e.returnValue = false;

  // 2 阻止冒泡
  // Propagation 传播
  // 停止事件传播  取消冒泡
  // 2.1.标准的DOM方法
  e.stopPropagation();

  // 2.2.取消冒泡  非标准的方式 老版本的IE支持
  e.cancelBubble = true;
  ```

- 定时器方法
  ```
  // 1 设置单次定时器和清除单次定时器
  setTimeout()和clearTimeout()
  // 2 定时调用的函数和清除
  setInterval()和clearInterval()
  ```

- 三大家族
  ```
  // 1 对比其他的top等方法类似
  偏移offsetWidth: width + padding + border
  卷曲scrollWidth: width + padding 不包含border 内部内容的大小
  可视clientWidth: width + padding 不包含border
  // 2 
  console.log(box.offsetParent); // 获取box的父定位元素
  console.log(box.offsetLeft);   // 获取box到父定位元素的左边距离
  console.log(box.offsetTop);    // 获取box到父定位元素上边的距离
  console.log(box.offsetWidth);  // 获取box的宽度边框以内
  console.log(box.offsetHeight); // 获取box的高度边框以内
  ```


- 其他
  ```
  1. ctrl + shift + p
  2. 输入i 找到 install package回车
  3. 等待数秒弹出窗口后 在输入框输入你要下载的插件回车等待
  4. 下载完成后关闭重启sublime

  如：下载sublimeServer
  1. ctrl + shift + p
  2. 输入i 找到 install package回车
  3. 等待数秒弹出窗口后 在输入框输入sublimeServer
  4. 下载完成后关闭重启sublime
  ```

- 赠言：不要在本该拼搏的时候选择安逸！