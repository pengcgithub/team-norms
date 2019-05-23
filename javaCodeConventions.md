# Java 编码规范

## 编程规范

#### 命名规范

1、类名使用 UpperCamelCase 风格，但以下情形例外：DO / BO / DTO / VO / AO /
PO / UID 等。

*例：MarcoPolo / UserDO*

2、方法名、参数名、成员变量、局部变量都统一使用 lowerCamelCase 风格，必须遵从
驼峰形式。

*例： localValue / getHttpMessage() / inputUserId*

3、常量命名全部大写，单词间用下划线隔开。

*例：MAX_STOCK_COUNT*

4、抽象类命名使用 Abstract结尾；异常类命名使用 Exception 结尾；测试类
命名以它要测试的类的名称开始，以 Test 结尾、枚举使用 Enum 结尾，枚举成员名称需要全大写，单词间用下划线隔开、常量类使用constant结尾。

*例：UserAbstract / UserException / UserTest / ProcessStatusEnum*

5、包名统一使用小写，点分隔符之间有且仅有一个自然语义的英语单词。包名统一使用
单数形式，但是类名如果有复数含义，类名可以使用复数形式。

*例：应用工具类包名为 com.alibaba.ai.util、类名为 MessageUtils（此规则参考 spring
的框架结构）*

6、杜绝完全不规范的缩写、使用尽量完整的单词组合来表达其意，避免望文不知义。

7、如果模块、接口、类、方法使用了设计模式，在命名时需体现出具体模式。

*例：public class OrderFactory; public class LoginProxy;*

8、接口类中的方法和属性不要加任何修饰符号，保持代码的简洁性，并加上有效的 Javadoc 注释。

*例：接口方法签名 void commit()*

9、各层命名规约：

A) Service/DAO 层方法命名规约（动词+名称的结构）
<pre>
  1） 获取单个对象的方法用 get 做前缀。
  2） 获取多个对象的方法用 list 做前缀，复数形式结尾如：listObjects。
  3） 获取统计值的方法用 count 做前缀。
  4） 插入的方法用 save/insert 做前缀。
  5） 删除的方法用 remove/delete 做前缀。
  6） 修改的方法用 update 做前缀。
</pre>

B) 领域模型命名规约
<pre>
  1） 数据对象：xxxBean，xxx 即为数据表名。
  2） 数据传输对象：xxxDTO，xxx 为业务领域相关的名称。
  3） 展示对象：xxxVO，xxx 一般为网页名称。
</pre>

### 常量定义

1、不允许任何魔法值（即未经预先定义的常量）直接出现在代码中。

### 代码格式

1、大括号的使用约定。如果是大括号内为空，则简洁地写成{}即可，不需要换行；如果
是非空代码块则：
<pre>
1） 左大括号前不换行。
2） 左大括号后换行。
3） 右大括号前换行。
4） 右大括号后还有 else 等代码则不换行；表示终止的右大括号后必须换行。
</pre>

2、if/for/while/switch/do 等保留字与括号之间都必须加空格。

3、任何二目、三目运算符的左右两边都需要加一个空格。

例：运算符包括赋值运算符=、逻辑运算符&&、加减乘除符号等。*

4、采用 4 个空格缩进。

<pre>
public static void main(String[] args) {

    // 缩进 4 个空格
    String say = "hello";
    // 运算符的左右必须有一个空格
    int flag = 0;
    // 关键词 if 与括号之间必须有一个空格，括号内的 f 与左括号，0 与右括号不需要空格
    if (flag == 0) {
        System.out.println(say);
    }

    // 左大括号前加空格且不换行；左大括号后换行
    if (flag == 1) {
        System.out.println("world");
    // 右大括号前换行，右大括号后有 else，不用换行
    } else {
        System.out.println("ok");
    // 在右大括号后直接结束，则必须换行
    }

} 
</pre>

5、单行字符数限制不超过 120 个，超出需要换行。
<pre>
1） 第二行相对第一行缩进 4 个空格，从第三行开始，不再继续缩进，参考示例。
2） 运算符与下文一起换行。
3） 方法调用的点符号与下文一起换行。
4） 方法调用中的多个参数需要换行时，在逗号后进行。
</pre>

6、方法参数在定义和传入时，多个参数逗号后边必须加空格。

*例：method(args1, args2, args3);*

7、单个方法的总行数不超过 80 行。

8、不同逻辑、不同语义、不同业务的代码之间插入一个空行分隔开来以提升可读性。

### 注释规范

1、类、类属性、类方法的注释必须使用 Javadoc 规范，使用/**内容*/格式，不得使用
// xxx 方式。

2、所有的抽象方法（包括接口中的方法）必须要用 Javadoc 注释、除了返回值、参数、
异常说明外，还必须指出该方法做什么事情，实现什么功能。

3、方法内部单行注释，在被注释语句上方另起一行，使用//注释。方法内部多行注释
使用/* */注释，注意与代码对齐。

4、所有的枚举类型字段必须要有注释，说明每个数据项的用途。

5、代码修改的同时，注释也要进行相应的修改，尤其是参数、返回值、异常、核心逻辑
等的修改。

6、谨慎注释掉代码。在上方详细说明，而不是简单地注释掉。如果无用，则删除。

7、注释模板

<pre>
/**
 * 拼团主表的业务逻辑层.
 *
 * @author pengc
 * @date 2019/3/5
 * @see com.byl.group.service.impl
 */
</pre>

<pre>
/**
 * 获取参与团购用户的状态.
 * 主要标识用户是否可以参团，从当前参数的数量，以及新老用户两个维度衡量.
 * 
 * @param groupBuyId 团购ID
 * @param dictId 活动类型字典ID
 * @param userId 用户ID
 * @return {@link UserStatusVO}
 * @throws exception
 */
</pre>

## 编码辅助工具

[alibaba.p3c](https://github.com/alibaba/p3c)

## 参考

- Java开发者手册



