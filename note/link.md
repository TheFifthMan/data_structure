# 概述
1. 什么是链表
2. 链表的好处
3. 链表的缺点
4. 实现一个链表

# 什么是链表
链表就像一个火车头，包含两部分数据： 元素的值|下一个元素的地址。优缺点如下

## 优点
1. 内存不是连续的，可以灵活，无限拓展

## 缺点
1. 查找元素的时候，需要一个个进行查找，插入元素和删除元素也是从头开始

# 实现一个单向链表

```js
function LinkNode(){
  function Node(element){
    this.element = element;
    this.next = null;
  }
  this.length = 0;
  this.head = null;

  LinkNode.prototype.append = function(element){
    var newNode = new Node(element);
    current = this.head
    if(this.head === null){
      current = newNode;
    }else{
      while(current.next){
        current = current.next;
      }
      current.next = newNode;
    }
    this.length ++;
  }
  LinkedNode.prototype.toString = function(){
    var str = ''
    var current = this.head;
    while(current){
      str += ','+current.element;
      current = current.next;
    }
    return str;
  }
  LinkedNode.prototype.insert = function(position,element){
    if (position < 0 || position > this.length) {
      return false;
    }
    var newNode = new Node(element);
    var current = this.head;
    if (position === 0) {
      newNode.next = this.head;
      this.head = newNode;
    }else{
      var index = 0;
      while(index < position) {
        prev = current;
        current = current.next;
      }
      prev.next = newNode;
      newNode.next = current;
    }
    this.length ++;
    return true;
  }

} 
```
