《代码整洁之道》

《[Clean Code: A Handbook of Agile Software Craftsmanship](https://www.amazon.com/-/zh/dp/0132350882/ref=sr_1_1?hvadid=241663626217&hvdev=c&hvlocphy=2840&hvnetw=g&hvqmt=e&hvrand=8238134522651387283&hvtargid=kwd-55663127008&hydadcr=16373_10302111&keywords=the+clean+code&qid=1681872845&sr=8-1)》 

#### 一，整洁的目的

1， 代码不要为了整洁而整洁，整洁的目的是为了提高代码的效率，易于阅读，修改。

2， 代码是写给人看的，不止别人看，过段时间自己也会反复看，而可能自己看的时候最多，机器只是执行而已，两方面都要保证。
 实际在工作中，读代码的时间要占很大比例，可能查过9/10，因此写出一眼就能看懂的代码有助于提高工作效率。

3， 代码整洁是内在逻辑清晰，有条理的外在表现，而不是一种表面形式。

#### 二，变量的命名

1， 见文知义。

2， 使用容易被搜索到的名字，如果只写个g，许多单词都有这字母，那搜索的时候有可能把要找到给错过去了，也没有充分利用IDE的快捷搜索功能。名称可以适当长一些。

#### 三，每个函数（方法）一个抽象层次

指方法内的代码都在一个处理级别上，每个方法下面都跟着下一层级的方法，这样层次分明。

错误范例：

```java
/*这里既有拼接字符串语句的具体操作，又有更高抽象层次的validate(..)方法，层次混乱，应把处理字符串的放大一个方法例*/
String trimmedUserName = username.trim();  
String handledStr = trimmedUserName.append("something");  
validate(handledStr);
```

正确范例：

```java
String handledStr = handleStr(username);
validate(handledStr);
```

#### 四，关于函数名称

长而具有描述性的名称比写长的注释要好，比短而描述不清的名称更好。