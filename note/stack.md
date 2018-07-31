# 概述
1. 栈的特点
2. 栈的应用
3. 栈的实现
4. 栈的应用

# 栈的特点
> 先进后出

# 栈的应用

函数调用栈：
```
A函数 调用 B函数 ，B函数 调用 C函数。
A函数先入栈
B函数再压入
C函数在压入

最后 C函数 弹出
B函数 弹出
A函数 弹出
```

# 栈的实现
## 操作

```
push： 压入一个元素
pop：推出一个元素
peek：返回栈顶元素
isEmpty: 是否为空
clear：清空栈元素
size：返回栈里面元素
```

## 实现代码

```javascript
function Stack(){
    var items=[];
    this.push = function(ele){
        items.push(ele);
    };
    this.pop = function(){
        return items.pop();
    };
    this.peek = function(){
        return itmes[items.length-1];
    };
    this.isEmpty = function(){
        return items.length == 0;
    };
    this.clear = function(){
        items = [];
    };
    this.size = function(){
        return items.length;
    }
}
```

# 栈的应用
实现十进制转换为二进制

```javascript
 function dec2bin(decNumber){
    var stack = new Stack();
    var remainder;
    // 任何数除以2，要么是0，要么是1
    while(decNumber > 0){
        remainder = decNumber % 2;
        decNumber = Math.floor(decNumber / 2);
        stack.push(remainder);
    }
    // 最后再进行拼接
    var binary = "";
    while(!stack.isEmpty()){
        binary += stack.pop();
    }
    return binary;
}
result = dec2bin(3);
alert(result); //11
```