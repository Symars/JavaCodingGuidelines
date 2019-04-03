# JavaCodingGuidelines

## 一、命名规范

##### 1.<font color=Red>【强制】</font>代码中的命名均不能以下划线或美元符号开始，也不能以下划线或美元符号结束。

<font color=Red>反例：</font>`_name / __name / $name / name_ / name$ / name__`

##### 2.<font color=Red>【强制】</font>代码中的命名严禁使用拼音与英文混合的方式，更不允许直接使用中文的方式。

<font color=Orange>说明：</font>正确的英文拼写和语法可以让阅读者易于理解，避免歧义。注意，即使纯拼音命名方式也要避免采用。

<font color=Green>正例：</font>`mega / taobao / youku / hangzhou` 等国际通用的名称，可视同英文。

<font color=Red>反例：</font>`DaZhePromotion [打折] / getPingfenByName() [评分] / int 某变量 = 3`

##### 3.<font color=Red>【强制】</font>类名使用 UpperCamelCase 风格，但以下情形例外：DO / BO / DTO / VO / AO / PO / UID 等。

<font color=Green>正例：</font>`MarcoPolo / UserDO / XmlService / TcpUdpDeal / TaPromotion`

<font color=Red>反例：</font>`macroPolo / UserDo / XMLService / TCPUDPDeal / TAPromotion`

##### 4.<font color=Red>【强制】</font>方法名、参数名、成员变量、局部变量都统一使用 lowerCamelCase 风格，必须遵从驼峰形式。

<font color=Green>正例：</font>`localValue / getHttpMessage() / inputUserId`

##### 5.<font color=Red>【强制】</font>常量命名全部大写，单词间用下划线隔开，力求语义表达完整清楚，不要嫌名字长。

<font color=Green>正例：</font>`MAX_STOCK_COUNT`

<font color=Red>反例：</font>`MAX_COUNT`

##### 6.<font color=Red>【强制】</font>抽象类命名使用 Abstract 或 Base 开头；异常类命名使用 Exception 结尾；测试类命名以它要测试的类的名称开始，以 Test 结尾。

<font color=Green>正例：</font>`AbstractOrderHandler`

##### 7.<font color=Red>【强制】</font>包名统一使用小写，点分隔符之间有且仅有一个自然语义的英语单词。包名统一使用单数形式，但是类名如果有复数含义，类名可以使用复数形式。

<font color=Green>正例：</font>应用工具类包名为 `com.mega.werewolf.util`、类名为 `StringUtil`（此规则参考 spring 的框架结构）。

##### 8.<font color=Red>【强制】</font>杜绝完全不规范的缩写，避免望文不知义。国际惯用缩写除外。

<font color=Green>正例：</font>`TcpClass`

<font color=Red>反例：</font>`AbstractClass`“缩写”命名成`AbsClass`；`condition`“缩写”命名成`condi`，此类随意缩写严重降低了代码的可阅读性。

##### 9.<font color=Red>【强制】</font>如果模块、接口、类、方法使用了设计模式，在命名时需体现出具体模式。

<font color=Orange>说明：</font>将设计模式体现在名字中，有利于阅读者快速理解架构设计理念。

<font color=Green>正例：</font>`public class OrderFactory; public class LoginProxy; public class ResourceObserver;`

##### 10.<font color=Red>【强制】</font>对于 Service 和 DAO 类，基于 SOA 的理念，暴露出来的服务一定是接口，内部的实现类用 Impl 的后缀与接口区别。

<font color=Green>正例：</font>`UserInfoDao`接口的实现类`UserInfoDaoImpl`。

##### 11.<font color=Red>【强制】</font>枚举类名带Enum后缀，枚举成员名称需要全大写，单词间用下划线隔开。

<font color=Orange>说明：</font>枚举类是特殊的常量类，构造方法被默认强制私有的。

<font color=Green>正例：</font>`UserStateEnum`类，成员变量：`LOGOUT / LOGIN GAMING / CREATEROOM / WATCH`

##### 12.<font color=Red>【强制】</font>领域模型（伪类，实体类）命名带Entity后缀。类中不允许写复杂的业务逻辑。

<font color=Green>正例：</font>`UserInfoEntity`用户信息类

## 二、代码风格

##### 1.<font color=Red>【强制】</font>大括号的使用约定。如果是大括号内为空，则简洁地写成{}即可，不需要换行； 如果是非空代码块则：
* 左大括号前不换行。
* 左大括号后换行。
* 右大括号前换行。
* 右大括号后还有 else 等代码则不换行； 表示终止的右大括号后必须换行。

<font color=Green>正例：</font> 
```
if (isActive) {
   ...
} else {
    ...
}
```

##### 2.<font color=Red>【强制】</font>左小括号和字符之间不出现空格；同样，右小括号和字符之间也不出现空格；而左大括号前需要空格。

<font color=Green>正例：</font>`if (a == b)`

<font color=Red>反例：</font>`if ( a == b )`

##### 3.<font color=Red>【强制】</font>if/for/while/switch/do等保留字与括号之间都必须加空格。

<font color=Green>正例：</font>`while (a > 0)`

<font color=Red>反例：</font>`while(a > 0)`

##### 4.<font color=Red>【强制】</font>任何二目、三目运算符的左右两边都需要加一个空格。

<font color=Orange>说明：</font>运算符包括赋值运算符=、逻辑运算符&&、加减乘除符号等。

<font color=Green>正例：</font>`int a = b;`

<font color=Red>反例：</font>`int a=b;`

##### 5.<font color=Red>【强制】</font>采用 4 个空格缩进，禁止使用 tab 字符。

<font color=Orange>说明：</font>如果使用 tab 缩进，必须设置 1 个 tab 为 4 个空格。 IDEA 设置 tab 为 4 个空格时，请勿勾选 `Use tab character`；而在 eclipse 中，必须勾选 `insert spaces for tabs`。

##### 6.<font color=Red>【强制】</font>注释的双斜线与注释内容之间有且仅有一个空格。

<font color=Green>正例：</font>
```
// 这是示例注释，请注意在双斜线之后有且仅有一个空格
StringBuilder sb = new StringBuilder();
```

##### 7.<font color=Red>【强制】</font>方法注释需要描述方法的功能，传入参数的意义，如果有返回值描述返回值的意义。

<font color=Green>正例：</font>

```
/**
 * 判断字符串是否非空
 * @param s 判断字符串
 * @return true:非空，false:空
 */
public static boolean isNotEmpty(String s) {
	if (s == null || "".equals(s)) {
		return false;
	}
	return true;
}

```

##### 8.<font color=Red>【强制】</font>方法参数在定义和传入时，多个参数逗号后边必须加空格。

<font color=Green>正例：</font>`method(args1, args2, args3);`

<font color=Red>反例：</font>`method(args1,args2,args3);`

##### 9.<font color=Gray>【推荐】</font>不同逻辑、不同语义、不同业务的代码之间插入一个空行分隔开来以提升可读性。

<font color=Orange>说明：</font>任何情形， 没有必要插入多个空行进行隔开。

## 三、OOP 规约

##### 1.<font color=Red>【强制】</font>避免通过一个类的对象引用访问此类的静态变量或静态方法，无谓增加编译器解析成本，直接用类名来访问即可。

<font color=Green>正例：</font>`String b = String.valueOf(1);`

<font color=Red>反例：</font>`String b = new String(); b.valueOf(1);`

##### 2.<font color=Red>【强制】</font>所有的覆写方法，必须加@Override 注解。

<font color=Orange>说明：</font>`getObject()`与`get0bject()`的问题。一个是字母的 O，一个是数字的 0，加`@Override`可以准确判断是否覆盖成功。另外，如果在抽象类中对方法签名进行修改，其实现类会马上编
译报错。

##### 3.<font color=Red>【强制】</font>相同参数类型，相同业务含义，才可以使用 Java 的可变参数，避免使用 Object。

<font color=Orange>说明：</font>可变参数必须放置在参数列表的最后。 （提倡同学们尽量不用可变参数编程）

<font color=Green>正例：</font>public List<User> listUsers(String type, Long... ids) {...}



#### 附录：参考文献

1. 《阿里巴巴Java开发手册》. 著：阿里巴巴集团技术团队.

<font color=Orange>说明：</font> 90%来自《阿里巴巴Java开发手册》
