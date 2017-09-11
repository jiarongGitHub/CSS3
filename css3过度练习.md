#### css3过度属性 transition
##### 由于c3效率极高，变换过程往往都是一瞬间完成，速度极快。css transition提供了一种在更改css属性时控制动画速度的方法，它可以让属性的变换成为一个持续一段时间的过程。比如，将一个元素的颜色从白色改为黑色，通常这个改变是立即生效的，使用 CSS transitions 后该元素的颜色将逐渐从白色变为黑色，按照一定的曲线速率变化。
**transition属性**
#####  transition是一个简写属性，用于 transition-property,transition-duration,transition-timing-function, 和transition-delay。 
----------
##### 接下来我们分别看一下transition的每一个属性
**transition-property**
##### 指定的是哪个属性将要进行动画的过度 比如:
```
transition-property:width; 
transition-property:height;
transition-property:background;
```
##### 它可以指定多个属性，中间用逗号隔开 比如:
```
transition-property:width,height; 
```
##### transition-property的默认值为all，表示所有能执行动画的属性都表现出过度动画，它是不可继承的。
##### transition-property属性值为none，表示没有过度动画。
----------
**transition-duration**
##### 以秒或毫秒为单位指定过度动画所需要的时间,此属性不接受负值且必须加单位s/ms 比如:
```
transition-duration:3s;
```
##### transition-duration可以指定多个时长，用逗号隔开，每个时长会被应用到由 transition-property 指定的对应属性上。如果指定的时长个数小于属性个数，那么时长列表会重复。如果时长列表更长，那么该列表会被裁减。两种情况下，属性列表都保持不变。
##### transition-property的默认值为0s，表示不出现过度动画，它是不可继承的。
----------
**transition-timing-function**
##### CSS属性受到 transition的影响，会产生不断变化的中间值，而 CSS transition-timing-function 属性用来描述这个中间值是怎样计算的。实质上，通过这个函数会建立一条加速度曲线，因此在整个transition变化过程中，变化速度可以不断改变。

##### 可以规定多个timing function,用逗号隔开，通过使用 transition-property属性，可以根据主列表(transition property的列表)给每个CSS属性应用相应的timing function.如果timing function的个数比主列表中数量少，缺少的值被设置为初始值（ease） 。如果timing function比主列表要多，timing function函数列表会被截断至合适的大小。

##### transition-timing-function的属性值有:

 1. ease:先加速后减速
 2. linear:匀速
 3. ease-in:加速
 4. ease-out：减速
 5. ease-in-out：先加速后减速
 6. cubic-bezier： 贝塞尔曲线([贝塞尔曲线](http://cubic-bezier.com)在此站点调好值直 接取值)
 7. step-start：等同于steps(1,start)
              step-end：等同于steps(1,end)
               steps(<integer>,[,[start|end]]?)
                      第一个参数：必须为正整数，指定函数的步数 第二个参数：指定每一步的值发生变化的时间点（默认值end）
```
transition-timing-function: ease;
transition-timing-function: ease-in;
transition-timing-function: ease-out;
transition-timing-function: ease-in-out;
transition-timing-function: linear;
transition-timing-function: step-start;
transition-timing-function: step-end;

transition-timing-function: steps(4, end);
transition-timing-function: cubic-bezier(0.1, 0.7, 1.0, 0.1);
```
##### transition-timing-function的默认值为ease，表示x先加速后减速，它是不可继承的。
----------
**transition-delay**
##### 规定在开始动画效果之前需要等待的时间
##### 可以指定多个延迟时间，每个延迟将会分别作用于你所指定的相符合的css属性。如果指定的时长个数小于属性个数，那么时长列表会重复。如果时长列表更长，那么该列表会被裁减。
##### 属性值以秒(s)或毫秒(ms)为单位，取正值表示动画将在何时开始，延长一段时间来响应过度效果;负值导致过度立即开始。
```
transition-delay: 3s;
transition-delay: 2s, 4ms;
```
##### transition-delay的默认值为0s，表示等待0s执行，它是不可继承的。

**过度完成会触发来检查过度是否完成**
##### 在标准浏览器下会触发transitionend；在webkit下，触发webkitTransitionEnd
注意:必须用dom2的形式绑定事件
```
var testNode = document.querySelector("#test");
		//dom0
		testNode.onmouseover=function(){
			this.style.width = "500px";
			this.style.height = "500px";
			//在transition完成前设置 display: none，事件同样不会被触发
			//this.style.display="none";
			//延迟加载则会触发
			setTimeout(function(){
					testNode.style.display="none";
			},2100)
		}
		//dom2
        testNode.addEventListener("transitionend",function(){
        	alert('完成');
        });
```
#####（每一个拥有过渡的属性在其完成过渡时都会触发一次transitionend事件）
##### 在transition完成前设置 display: none，事件同样不会被触发






 
