## 判断数组
``arr instance of Array,arr.constructor === Array,  Array.isArray(arr)``

## 数组分割
可以使用扩展运算符...以及 splice()

## 数组去重
``Array.from(new Set(arr))`` 
或者将值作为Map,key传入，并加入新的数组``map.has(arr[i])``用以判断。

reduce(function(初始为空，当前值))

## 数组扁平化
一：arr.flat(Infinity)\
二：arr.toString().split(',')\
三：``function flatten(arr){
    return arr.reduce(function(pre,cur){
        return cur.isArray?flatten(cur):cur
    },[])
} ``

## 数组乱序
利用sort\
``sort(()=>{0.5-Math.random()})``

## 提取数组的值出现的个数
也可以利用reduce()




