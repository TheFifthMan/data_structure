# 概述
1. 什么是队列
2. 队列的应用场景
3. 队列的实现
4. 优先级队列
5. 优先级队列的使用

# 什么是队列
队列是一种受限的线性结构，执行了先进先出的原则，受限在于，它只能在前面弹出元素，在后面添加元素

# 队列的应用场景
1. 排队执行任务
2. 多线程队列执行任务。按照次序启动线程

# 队列的实现
1. enqueue: 先进
2. dequeue：先出
3. first：返回队列的第一个元素
4. isEmpty：是否空
5. size：队列长度

```javascript
function Queue(){
    var items = [];
    this.enqueue = function(elem){
        items.push(elem);
    };
    this.dequeue = function(){
        return items.shift();
    };
    this.isEmpty = function(){
        return items.length == 0;
    };
    this.size = function(){ 
        return items.length;
    };
    this.first = function(){
        return items[0];
    }
}
```
# 优先级队列
优先级队列，顾名思义就是优先级高的排在前面，先执行。

## 代码

```javascript
 function PriorityqQueue(){
    var items=[]
    function QueueElement(ele,priority){
        this.ele = ele;
        this.priority = priority;

    };
    this.enqueue = function(ele,priority){
        qe =new QueueElement(ele,priority);
        if(this.isEmpty()){
            items.push(qe);
        }else{
            var added = false;
            for(var i = 0;i<items.length;i++){
                // 数字越大，优先级越高
                if(qe.priority > items[i].priority){
                    items.splice(i,0,qe);
                    added = true;
                    break;
                }
            };

            if(!added){
                items.push(qe)
            }
            
        }
    };
    this.dequeue = function(){
        return items.shift();
    };
    this.isEmpty = function(){
        return items.length == 0;
    }
};

pe = new PriorityqQueue()
pe.enqueue('a',1);
pe.enqueue('b',2);
pe.enqueue('c',3);
pe.enqueue('d',4);
alert(pe.dequeue().ele);
alert(pe.dequeue().ele);
alert(pe.dequeue().ele);
alert(pe.dequeue().ele);

```


