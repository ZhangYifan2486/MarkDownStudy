# <font color=red>javascript</font>
## css优化
减少使用昂贵的属性\
减少使用import\
资源压缩\
合理使用选择器\

 # window对象的属性
 screen,document,navigator,location...

## promise then
``promise(  function(resolve,reject){
    setTimeOut(function(){
    },1000)
}).then(function(data){
},function(err){
}
)``
构造函数是同步执行，then是异步执行，用.then解决回调地狱的问题。\
三种状态：pending,fulfilled以及rejected\
九个方法：resolve,reject,then,catch(捕获异常),all(接受promise数组全部成功)，any(数组一个成功)，race(当任何一个promise的状态先确定（拒绝或者成功），则会执行.race中的回调函数),finally(无关状态，怎么都会执行),allSettled(每个promise状态确定)

## map,foreach数组区别以及为什么无法终止
map会创建一个新的数组\
内部接受参数为函数，无法通过抛出异常停止。

## every 和some区别
判断数组中是否每个元素都满足条件，只有全部都满足条件才返回true；只要有一个不满足就返回false；\
判断数组中是否至少有一个元素满足条件只要有一个满足就返true
只有都不满足时才返回false\


## async await
异步执行，隐式返回promise\
await遇到promise，会阻塞后面函数运行，并等待promise执行所有then返回。\
注意：如果 await 后的 Promise 被拒绝（rejected），那么 await 表达式将会抛出错误，需要用 try...catch 语句捕获。\

## js的数据类型：
基本类型：number,string,boolean,undefined,null,symbol\
复杂类型：object,array,function\
存储区别：一个存储在栈中，一个存储在堆中\

## var let const 区别
var可以变量提升，在声明前使用,剩下不行\
var不是块级作用域，可以块外使用，剩下不行\

## setTimeout() 和setInterval
setTimeout()广告
setInterval 轮播图

## ==和===的区别
==是会对数据进行转换，===不会做类型转换

## 浅拷贝以及深拷贝
浅拷贝情况：如果属性是基本类型，拷贝的就是基本类型的值。如果属性是引用类型，拷贝的就是内存地址\
深拷贝开辟一个新的栈，两个对象属完成相同，但是对应两个不同的地址，修改一个对象的属性，不会改变另一个对象的属性:.cloneDeep()\

## 如何实现深拷贝
①json.stringfy和json.parse
②loadsh的clonedeep
③jquery的extend 

## javascript自字面创建对象和new创建对象区别
字面不会调用，更加简洁
new 直接调用构造函数

## js执行流程
同步任务，微异步，宏异步

## 如何实现异步函数
回调函数，promise,generator

## 闭包
闭包函数没有自己的局部变量，可以访问本函数外部函数内的局部变量，
让外部访问函数内部变量成为可能,
返回函数\
注意：闭包的函数再使用后会保存在内存中，会改变父函数内部变量的值。


## 柯里化
避免频繁调用具有相同参数函数的同时，又能够轻松的重用\
``function getB(a){return a=>{a*b}},getAB = getB(a),getAB(B)``

## typeof 和 instanceof的区别
typeof()返回数据类型，instance返回bool值

## 数据转换
隐式转换，显示转换\
parseInt(),Number(),

## 原型链以及原型
原型对象也可能拥有原型，并从中继承方法和属性，一层一层、以此类推，称为原型链。\
每个通过构造函数创建出来的实例对象，其本身有个属性__proto__，这个属性会指向该实例对象的构造函数的原型对象\
当访问一个对象的某个属性时，会先在这个对象本身属性上查找，如果没有找到，则会通过它的__proto__隐式属性，找到它的构造函数的原型对象，如果还没有找到就会再在其构造函数的prototype的__proto__中查找，这样一层一层向上查找就会形成一个链式结构，我们称为原型链


## javascript的继承方法
原型链继承：\
构造函数继承:\
组合继承：\

## javascript本地存储的方法
cookie,sessionStrohe,localStroge,indexDB\
cookie可以设置过期时间\
``localStorage.setItem('username','cfangxu')``
``localStorage.getItem('username')``
无法像Cookie一样设置过期时间\
只能存入字符串，无法直接存对象\
sessionStorage和 localStorage使用方法基本一致，唯一不同的是生命周期，一旦页面（会话）关闭，sessionStorage 将会删除数据\

## 函数化编程
函数式编程是一种"编程范式"（programming paradigm），一种编写程序的方法论\
函数式编程更加强调程序执行的结果而非执行的过程\

## ajax
异步javascript和xml,流程：\
Ajax的核心对象 XMLHttpRequest对象,通过 XMLHttpRequest 对象的 open() 方法与服务端建立连接,通过XMLHttpRequest 对象的 send() 方法发送请求给服务器端。



# <font color=red>vue vue-router 响应式基础 props组件 生命周期 axios watch&computed vuex </font>
## vue和原生的区别
下载包更方便，组件类名不冲突，代码可读性更高

## mvvm设计模式原理
数据劫持以及发布者订阅模式\
数据劫持setter,getter,数据变动时发布

## vue3响应式原理
vue3通过proxy监听对象属性的变化\
vue3使用weakmap存储依赖关系，避免了watcher的内存泄露
## 组合式api
灵活，代码量少，
## 组件式开发的优点
降低代码耦合度\
调试方便，提高可维护性\

## setup(){}函数
参数接受props以及context
## ref和reactive
reactive：本质:将传入的数据包装成一个proxy对象,参数必须是一个对象或者数组,有时候要用到toRefs()\
ref:参数包括基本数据类型以及对象，需要添加value访问，ref响应式原理为object.defineProperty()的get()和set()的\
## 计算属性computed
计算属性会进行缓存，多次使用只会掉用一次\
使用一次调用一次，性能更好\
读取数据出发get方法，修改数据set方法\

## watch和watchEffect()
watch函数：侦听特定数据源，并在源变化时执行回调;deep为true出发深度监听\
watchEffect()：自动获取回到函数中的响应式数据，默认immediate为true,但是无法获得变化前的值

## watch 和 computed的区别以及使用场景
监听和计算属性\
computed支持缓存，当其依赖的属性的值发生变化时，计算属性会重新计算，反之，则使用缓存中的属性值；watch不支持缓存，当对应属性发生变化的时候，响应执行。\
computed不支持异步，有异步操作时无法监听数据变化；watch支持异步操作。\
computed第一次加载时就监听；watch默认第一次加载时不监听。\
场景：watch场景：一个数据影响多个数据，数据变化时执行异步操作。\
computed:一个数据受多个数据影响，多个属性影响一个属性时，例如购物车结算。



## provide inject 
用于父组件向子组件传递数据

## 生命周期
setup:组件初始化时\
onMounted；组件挂载或挂载前\
onUpdated:组件更新前\
onUnmounted:组件卸载后\
mounted和created的不同：mounted是在dom结构完成之后的操作，created是dom未生成的。

## A跳转B周期
B:created beforemunted
A:beforeDestory destory
B:mounted

## 刷新的生命周期
没有原页面的destoryed或者beforeDestory

## toRef() toRefs()
复制reactive对象的属性并将其转换为ref,保留了响应式以及引用，属于浅拷贝，共用一个引用。

## shallowreactive和shallowref
shallowReactive：只处理对象最外层属性的响应式（浅响应式）\
浅层作用的响应式数据处理：只处理第一层对象的数据，再往下嵌套的数据，操作数据是不起作用的

## toRaw与markRaw
toRaw，将响应式对象（由 reactive定义的响应式）转换为普通对象，然后赋值给新的变量（不影响原来的对象）\
markRaw，标记一个对象，使其不能成为一个响应式对象。\
使用场景:\
1、用于读取响应式对象对应的普通对象\
2、对这个普通对象的所有操作，不会引起页面更新。

## vue3中的父传子 子传父
父传子：
通过父组件中的子组件标签中传递props.数据继续接受\
父组件中设置子组件标签ref,

子传父：
通过setup函数的第二个参数context.emit:``emit(事件，传递的参数值)，@事件= 父组件函数``实现\


## 透传属性
调用子组件标签内的属性会透传到原本组件的标签内。\
子组件编辑时，可以添加attrs属性接受透传。

## 使用插槽
子组件使用`<slot></slot>`\
父组件注入插槽内容\
分为默认插槽，具名插槽\

## 路由守卫
onBeforeRouteLeave:组件导肮离开前\
onBeforeRouteUpdate：组件导航更新\

## useRoute和useRouter
useRoute是访问路由信息的\
useRouter是访问路由实例的\

## setup 语法糖的优势
更简洁的代码\

## vue3中nextTick的使用
将回调函数推迟到下一个dom更新后执行

## 原型绑定全局属性
1、通过config.globalProperties\
2、通过provide注入：在应用实例上设置一个可以被注入到应用范围内所有组件中的值。当组件要使用应用提供的 provide 值时，必须用 inject 来接收。\
3、在main.js中全局引入，然后在组件中获取\

## 封装组件
Vue.extend()，创建名为myCom的组件
注册组件：调用Vue.component( 组件名称，为组件创建时定义的变量 )(分为全局和局部)
调用；只需要在调用组件的地方，写上组件名字的标签即可

## scoped
防止样式污染

## v-for不再就地复用原理
指定key,不能是索引，因为索引会更新

## v-show和v-if原理
v-show改变css\
v-if对标签进行挂载以及卸载\

## v-for和v-if
if是通过条件判断\
for 是通过数组来遍历显示\
优先级for大于if\

## spa单页加载慢的原因以及解决方案
网络延迟、资源文件过大、

静态资源本地缓存,利用localStorage\
图片资源压缩\
减小入口文件体积\
动态加载路由\
elementUI框架按需要加载\

## vuex
state；存放共享变量\
getter；相当于计算属性，获得共享变量的值\
mutation:存放修改state的方法\
actions:修改state,异步操作\

## observable 
将数据转换为响应式对象

## keep-alive
将组件缓存在内存当中，防止重复渲染\
参数有include

## vue修饰符
v-model表单修饰符：\
lazy:光标离开时，才会获取值\
trim:去掉值的表格\
number:将输入值转换为数字\
事件修饰符：\
stop:阻止事件冒泡\
prevent:阻止时事件默认行为\
once:只触发一次事件\
等等


## v-model原理







