## TweenMax 学习
[官网](http://greensock.com/timelinemax)
#### 提示
* 1.基于JQ ;
#### 方法说明
* 初始化
``` 
$(function () {
    var t = new TimelineMax();
});

```
* to() 
##### 创建动画，一共四个参数
    * 1.元素选择器或对象
	* 2.持续时间
	* 3.对象：例{height:300,width:200,complate:function(){}}
	* 4.[可选]动画延迟时间,参数可为具体数字，或者"+=1"类型，'+=1'是必须加引号
* play(),stop()
##### 播放，暂停动画
	* 1.to()方法下直接写stop()方法，动画会不执行
*reverse()
##### 反向执行动画
* onComplete(),onReverseComplete()
##### 运动结束后对应的函数，属于to方法第三个参数
* add()
##### 添加状态
	* 1.参数可为字符串
```
	 var t =new TimelineMax();
	 t.to("#div1",2,{left:300});
	 t.add("state1");
	 t.to("#div1",2,{width:300});
	 t.add("state2");
	 t.to("#div1",2,{height:300});
	 t.add("state3");

```
	* 2.参数可为函数
```
	  var t =new TimelineMax();
	  t.to("#div1",2,{left:300});
	  t.add(function(){
		  $("#div1").css("background","blue");
	  });
	  t.to("#div1",2,{width:300});
	  t.to("#div1",2,{height:300});
```
* tweenTo()
##### 完成指定的动画
	*参数为字符串【add()方法添加的状态】或指定时间（不需要加单位）
* seek()
##### 完成指定的动画（无过度效果）
	* 参数1：为字符串【add()方法添加的状态】或指定时间（不需要加单位)
	* 参数2：【可选】布尔值：true[不执行函数，默认];false[执行函数]
* time()
##### 动画已执行的时间
* clear()
##### 清除所有动画
* staggerTo()
##### 添加动画，类似于to()方法，参数同to()方法
##### 与to()区别：在设置相同的延迟时间的情况下，to()下的所有动画会同时进行，而staggerTo()下的动画会一个接着一个依次执行
* totalDuration()
##### 获取动画的总时长
* getLabelTime()
##### 返回从开始到当前状态的时间,返回值是一个数字
* currentLabel()
##### 获取当前状态, 返回值是状态的字符串
* getLabelAfter()
##### 获取下一个状态, 返回值是状态的字符串，如果没有下一个状态返回null
* getLabelBefore()
##### 获取上一个状态, 返回值是状态的字符串，如果没有上一个状态返回null
* ease
##### to()方法第三个参数，动画运动形式 [例](http://blog.sina.com.cn/s/blog_6d193c030100uhij.html)