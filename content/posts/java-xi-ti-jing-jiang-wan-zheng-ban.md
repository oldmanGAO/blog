---
title: Java习题精讲-完整版
subtitle: ''
date: '2026-09-09T22:00:59+08:00'
lastmod: '2026-09-10T08:18:28+08:00'
draft: false
authors: []
description: ''
tags: []
categories: []
series: []
hiddenFromHomePage: false
hiddenFromSearch: false
featuredImage: ''
featuredImagePreview: ''
toc:
  enable: true
math:
  enable: true
lightgallery: true
license: 本文采用 <a rel="license" href="https://creativecommons.org/licenses/by-nc/4.0/"
  target="_blank">CC BY-NC 4.0</a> 许可协议，转载请注明出处。
---

# Java习题精讲-完整版

> 题目 + 答案 + 详细解析。共 23 章，与《Java学习笔记》章节一一对应。
> 建议：先在题目版上独立作答，再到完整版核对答案、研读解析。

---

## 目录

- **第一部分 · Java 基础**
  - [第1章 Java开发环境与IDEA · 习题精讲](#第1章-java开发环境与idea--习题精讲)
  - [第2章 Java基础语法 · 习题精讲](#第2章-java基础语法--习题精讲)
  - [第三章 运算符 · 习题精讲](#第三章-运算符--习题精讲)
  - [第四章 方法 · 习题精讲](#第四章-方法--习题精讲)
  - [第五章 流程控制语句 · 习题精讲](#第五章-流程控制语句--习题精讲)
  - [第六章 数组 · 习题精讲](#第六章-数组--习题精讲)
  - [第7章 面向对象基础·习题精讲](#第7章-面向对象基础习题精讲)
  - [第8章 面向对象高级（上）·习题精讲](#第8章-面向对象高级上习题精讲)
  - [第9章 面向对象高级（下）·习题精讲](#第9章-面向对象高级下习题精讲)
  - [第10章 常用API与综合案例·习题精讲](#第10章-常用api与综合案例习题精讲)

- **第二部分 · JavaSE 进阶**
  - [第11章 面向对象进阶（一）：static 与继承 · 习题精讲](#第11章-面向对象进阶一static-与继承--习题精讲)
  - [第12章 面向对象进阶（二）：多态、final、抽象类与接口 · 习题精讲](#第12章-面向对象进阶二多态final抽象类与接口--习题精讲)
  - [第13章 面向对象进阶（三）· 习题精讲](#第13章-面向对象进阶三-习题精讲)
  - [第14章 常用 API（进阶）· 习题精讲](#第14章-常用-api进阶-习题精讲)
  - [第十五章 Lambda、算法与正则表达式 · 习题精讲](#第十五章-lambda算法与正则表达式--习题精讲)
  - [第十六章 异常处理与 List 集合 · 习题精讲](#第十六章-异常处理与-list-集合--习题精讲)
  - [第17章 Set 与 Map 集合·习题精讲](#第17章-set-与-map-集合习题精讲)
  - [第18章 Stream 流、File 类与递归·习题精讲](#第18章-stream-流file-类与递归习题精讲)
  - [第19章 字符集与字节流·习题精讲](#第19章-字符集与字节流习题精讲)
  - [第20章 字符流、缓冲流与 IO 高级流·习题精讲](#第20章-字符流缓冲流与-io-高级流习题精讲)
  - [第21章 特殊文件、日志技术与多线程·习题精讲](#第21章-特殊文件日志技术与多线程习题精讲)
  - [第22章 网络编程·习题精讲](#第22章-网络编程习题精讲)
  - [第23章 单元测试、反射、注解与动态代理·习题精讲](#第23章-单元测试反射注解与动态代理习题精讲)

---

# 第一部分 · Java 基础

<div style="page-break-after: always;"></div>

## 第1章 Java开发环境与IDEA · 习题精讲

> 做题建议：先独立作答，再看【答案】和【解析】。解析中的"▶ 关联"标注了与其他章节的联系，
> 遇到不懂的关联知识点可先标记，学到对应章节时再回看。
> 说明：本章还没学变量、分支等语法，编程题重点训练"开发流程"——建文件、编译、运行、排错。

### 一、填空题

**1.** Java 三大技术平台中，桌面应用开发、作为整个技术体系基础的是 ______；用于企业级互联网应用开发的是 ______；用于嵌入式小型设备、已被淘汰的是 ______。

**【答案】** JavaSE（标准版）；JavaEE（企业版）；JavaME（微型版）

**【解析】** JavaSE 是地基，我们本课程学的就是 JavaSE；JavaEE 建立在 JavaSE 之上，用来做网站、后台系统等企业级开发；JavaME 用于小型设备，现在基本被 Android 等技术取代。学习路线是"先 JavaSE 打基础，再 JavaEE 做企业开发"。

**2.** JDK、JRE、JVM 三者的包含关系是：______ > ______ > ______；其中真正运行 Java 程序的是 ______。

**【答案】** JDK > JRE > JVM；JVM

**【解析】** JVM（Java 虚拟机）是真正运行程序的地方；JRE（运行环境）= JVM + 核心类库，只能运行程序不能开发；JDK（开发工具包）= JRE + 编译/运行/调试工具（javac、java 等）。所以开发必须装 JDK，只装 JRE 没法编译代码。

**3.** javac 是 ______ 工具，它把 `.java` 源文件翻译成 ______ 文件；java 是 ______ 工具，它启动 ______ 来执行字节码。

**【答案】** 编译；`.class` 字节码；运行；JVM

**【解析】** 高级语言硬件不能直接识别，必须"先编译、后运行"：`.java --javac--> .class --java启动JVM--> 执行`。

**4.** 编译命令是 `javac` 后跟 ______（要带后缀）；运行命令是 `java` 后跟 ______（不能带后缀）。

**【答案】** 源文件名（如 `BookShop.java`）；类名（如 `BookShop`，不能写 `.class`）

**【解析】** 初学者最高频的错误：编译针对源文件要带 `.java`，运行针对类名不要带 `.class`。

**5.** Path 环境变量的作用是 ______；推荐额外配置 ______ 变量，以后 JDK 升级或换路径只改这一处。

**【答案】** 记住程序路径，让程序在命令行的任意目录都能启动；JAVA_HOME

**【解析】** 在命令行输入程序名时，系统先在当前目录找，找不到就去 Path 记录的路径里逐个找。配置 `JAVA_HOME=JDK安装目录`，再在 Path 中写 `%JAVA_HOME%\bin`，Maven、Tomcat、IDEA 等工具也会通过 JAVA_HOME 关联 JDK。

### 二、选择题

**1.** 关于 JDK、JRE、JVM，下列说法正确的是（　）。

A. 只安装 JRE 就可以用 javac 编译程序
B. JDK 包含 JRE，JRE 包含 JVM
C. JVM 中包含了 JDK 的全部开发工具
D. 安装 JRE 后就能开发 Java 程序，只是不能运行

**【答案】** B

**【解析】** 包含关系 JDK > JRE > JVM。A、D 错：javac 属于 JDK，JRE 只能运行不能开发；C 说反了，是 JDK 包含 JVM。

**2.** Java 能够"一次编译，多处运行"实现跨平台，根本原因是（　）。

A. Java 编译器把源码直接编译成了各个操作系统的机器码
B. 不同操作系统上安装对应版本的 JVM，字节码运行在 JVM 上，由 JVM 屏蔽系统差异
C. Java 程序不需要编译，解释执行
D. `.class` 文件本身就是各平台通用的机器码

**【答案】** B

**【解析】** 跨平台靠的是中间层 JVM：同一份 `.class` 字节码，放到 Windows、Linux、Mac 上各自的 JVM 中都能运行。C/C++ 编译后直接生成与平台绑定的机器码，所以不能跨平台。

**3.** 下列 JDK 版本中，**不属于** LTS（长期支持）版本的是（　）。

A. JDK 8　　B. JDK 11　　C. JDK 21　　D. JDK 15

**【答案】** D

**【解析】** 笔记口径：JDK 8、11、17、21 是 LTS 版本，很多企业仍在用 8/11，课程使用 JDK 21。JDK 15 是非 LTS 的过渡版本。

**4.** 在 `D:\code` 目录下有 `BookShop.java`，正确的编译运行命令是（　）。

A. `java BookShop.java` → `javac BookShop`
B. `javac BookShop.java` → `java BookShop.class`
C. `javac BookShop.java` → `java BookShop`
D. `javac BookShop` → `java BookShop`

**【答案】** C

**【解析】** 编译带 `.java`，运行带类名不带 `.class`。B 多了 `.class`，D 编译没带后缀，A 顺序和写法全错。

**5.** 在 IDEA 中，快速生成 main 方法和输出语句的方式是（　）。

A. 输入 `sout` 回车生成 main 方法，输入 `main` 回车生成输出语句
B. 输入 `psvm`（或 `main`）回车生成 main 方法，输入 `sout` 回车生成输出语句
C. 按 `Ctrl + N` 生成 main 方法
D. 按 `Ctrl + /` 生成输出语句

**【答案】** B

**【解析】** `psvm` = public static void main 的首字母，`sout` = System.out.println 的缩写。`Ctrl+N` 是搜索类，`Ctrl+/` 是单行注释。

### 三、判断题

**1.** 只要电脑上安装了 JRE，就可以进行 Java 程序开发。（　）

**【答案】** ✗ 错误

**【解析】** JRE 只包含 JVM 和核心类库，只能运行程序；开发需要 javac 等编译工具，必须安装 JDK。

**2.** Java 编译生成的 `.class` 字节码文件可以直接交给操作系统执行。（　）

**【答案】** ✗ 错误

**【解析】** 字节码运行在 JVM 上，而不是直接运行在操作系统上——这正是 Java 跨平台的原理。如果字节码能直接在操作系统上跑，反而就和 C/C++ 一样绑定平台了。

**3.** 被 `public` 修饰的类，其类名必须与源文件名完全一致。（　）

**【答案】** ✓ 正确

**【解析】** 例如 `public class BookShop` 必须放在 `BookShop.java` 文件中，且 Java 严格区分大小写。

**4.** 在 IDEA 中对模块执行 Remove Module 后，硬盘上的模块文件也会被彻底删除。（　）

**【答案】** ✗ 错误

**【解析】** Remove Module 只是把模块从工程中移除，硬盘上的文件夹还在；要彻底删除需再去磁盘目录手动删除。

### 四、简答题

**1.** 简述 JDK、JRE、JVM 各自的作用，以及三者的包含关系。

**【答案要点】**
- JVM：Java 虚拟机，真正运行 Java 字节码的地方；
- JRE：Java 运行环境，包含 JVM 和运行所需的核心类库，只能运行程序；
- JDK：Java 开发工具包，包含 JRE 以及 javac、java 等编译运行调试工具；
- 包含关系：**JDK > JRE > JVM**。开发要装 JDK，用户只运行程序装 JRE 即可。

**2.** 什么是跨平台？Java 是如何实现跨平台的？

**【答案要点】**
- 跨平台：一次编译生成的程序可以在不同操作系统（Windows、Linux、Mac）上运行，即"一次编译，多处运行"。
- 实现方式：在不同操作系统上安装各自版本的 JVM，`.class` 字节码运行在 JVM 上，由 JVM 屏蔽底层操作系统差异。
- 对比：C/C++ 编译后直接生成与特定平台相关的机器码，换系统就要重新编译，不能跨平台。

**3.** Path 环境变量和 JAVA_HOME 各有什么作用？为什么推荐配置 JAVA_HOME？

**【答案要点】**
- Path：记录可执行程序的路径，配置后在任意目录都能直接输入程序名启动。
- JAVA_HOME：记录 JDK 的安装根目录，Path 中用 `%JAVA_HOME%\bin` 引用。
- 推荐原因：Maven、Tomcat、IDEA 等工具会通过 JAVA_HOME 找 JDK；以后 JDK 升级或换路径，只改 JAVA_HOME 一处即可，不用改 Path。

### 五、代码阅读题

**1.** 某同学在命令行执行了下面两条命令，结果都报错，请指出错误并改正。

```bash
D:\day01> javac BookShop.class
D:\day01> java BookShop.java
```

**【答案】**
- 第一条：编译应针对源文件，改为 `javac BookShop.java`；
- 第二条：运行应针对类名且不带后缀，改为 `java BookShop`。

**【解析】** 记忆口诀："编译带 java，运行光类名"。

**2.** 下面代码保存在文件 `Test.java` 中，能否编译通过？为什么？如何修改？

```java
public class BookShop {
    public static void main(String[] args) {
        System.out.println("欢迎来到书香书店");
    }
}
```

**【答案】** 不能编译通过。

**【解析】** `public` 修饰的类名 `BookShop` 与文件名 `Test` 不一致。两种改法：① 把文件改名为 `BookShop.java`；② 把类名改为 `Test`（`public class Test`）。
▶ 关联：类名的大驼峰命名规范在第 2 章《Java基础语法》标识符一节讲解。

### 六、编程题（由易到难）

#### 编程题 1（入门）：书香书店欢迎语

**需求：** 书店开业，编写你的第一个 Java 程序：定义 public 类 `BookShop`，运行后在控制台打印两行文字——欢迎语和当日活动信息。要求写出完整代码、源文件名、编译命令和运行命令。

**【参考代码】**（文件名必须为 `BookShop.java`）

```java
public class BookShop {
    public static void main(String[] args) {
        System.out.println("欢迎来到书香书店！");
        System.out.println("今日全场图书 8 折，开学季特惠");
    }
}
```

**编译运行：**

```bash
javac BookShop.java
java BookShop
```

**运行结果：**

```text
欢迎来到书香书店！
今日全场图书 8 折，开学季特惠
```

**【思路讲解】**
1. `public class BookShop` 定义类，文件名必须叫 `BookShop.java`（public 类名与文件名一致）；
2. main 方法写法固定，是程序入口；字符串文字用双引号包裹；
3. 每条语句以英文分号 `;` 结尾；
4. javac 编译生成 `BookShop.class`，java 运行时不带 `.class` 后缀。

#### 编程题 2（基础）：快递驿站取件凭证

**需求：** 在 IDEA 中完成：创建一个空 Project（名 `JavaSEProject`），在其中新建模块 `day01`，在模块下建包 `com.express.day01`，在包中新建类 `PickTicket`，运行后打印一张取件凭证（标题、取件码、取件地址、温馨提示各一行）。请描述创建步骤并写出代码。

**【创建步骤】**
1. File → New → Project → Empty Project，命名 `JavaSEProject`；
2. File → New → Module，命名 `day01`；
3. 在 `day01/src` 上右键 New → Package，命名 `com.express.day01`（公司域名倒写 + 技术名，全小写）；
4. 在包上右键 New → Java Class，命名 `PickTicket`（大驼峰，只写类名不加 .java）；
5. 输入 `main` 回车生成 main 方法，输入 `sout` 回车生成输出语句，右键 Run 运行（IDEA 自动编译，class 文件在 out 目录）。

**【参考代码】**（第一行 package 语句由 IDEA 自动生成，不用手写）

```java
package com.express.day01;

public class PickTicket {
    public static void main(String[] args) {
        System.out.println("======== 快递取件凭证 ========");
        System.out.println("取件码：8-3-266");
        System.out.println("取件地址：学府路快递驿站 A 区货架");
        System.out.println("请凭取件码于 24 小时内取件，超时将被退回");
    }
}
```

**运行结果：**

```text
======== 快递取件凭证 ========
取件码：8-3-266
取件地址：学府路快递驿站 A 区货架
请凭取件码于 24 小时内取件，超时将被退回
```

**【思路讲解】**
1. IDEA 四级结构必须按 Project → Module → Package → Class 顺序创建，前三者本质都是文件夹，Class 才是写代码的文件；
2. 包名全小写、类名大驼峰；类放在包中后，IDEA 自动在文件顶部生成 `package com.express.day01;`；
3. IDEA 中不用手动敲命令，点 Run 即自动完成编译和运行。
▶ 关联：package 的语法与导包在第 9 章《面向对象高级（下）》讲解。

#### 编程题 3（进阶排错）：修复驿站欢迎程序

**需求：** 新手写出下面的程序，文件名为 `Station.java`，他又在命令行敲了 `java Test.class`，结果处处报错。请找出全部错误（代码 4 处 + 命令 1 处），写出改正后的完整代码和正确命令。

```java
public class Test {
    public static void mian(String[] args) {
        System.out.println("快递驿站欢迎您")；
        System.out.println("今日到站包裹 128 件")
    }
}
```

**【错误清单】**
1. 文件名是 `Station.java`，public 类名却是 `Test`——类名与文件名不一致：把文件改名为 `Test.java`（或把类名改为 `Station`）；
2. main 方法拼成了 `mian`——JVM 找不到入口，应为 `main`；
3. 第一行末尾是中文分号 `；`——Java 所有标点必须是英文半角，改为 `;`；
4. 第二行末尾漏了分号——补上 `;`；
5. 运行命令 `java Test.class` 错误——运行不带后缀，应为 `java Test`（类名随修改后的名字）。

**【正确代码】**（保存为 `Test.java`）

```java
public class Test {
    public static void main(String[] args) {
        System.out.println("快递驿站欢迎您");
        System.out.println("今日到站包裹 128 件");
    }
}
```

**正确命令：**

```bash
javac Test.java
java Test
```

**运行结果：**

```text
快递驿站欢迎您
今日到站包裹 128 件
```

**【思路讲解】**
排错对照本章"常见错误"清单逐条检查：① 文件扩展名是否真的是 `.java`（勾选文件扩展名）；② public 类名与文件名是否一致；③ 单词拼写（main、String、System）和大小写；④ 标点是否英文半角、括号是否成对；⑤ 编译运行命令是否写反/带错后缀。
▶ 关联：字符串、整数等数据的书写格式（字面量）在下一章《Java基础语法》学习；输出内容将随语法学习越来越丰富。

---

<div style="page-break-after: always;"></div>

## 第2章 Java基础语法 · 习题精讲

> 本章是 Java 语法的地基：注释、关键字、字面量、变量、标识符、8 种基本数据类型。
> 做题时特别注意"字符串 vs 字符"的引号区别、整数/小数默认类型、char 的编码值这三个高频考点。

### 一、填空题

**1.** Java 中注释有三种：单行注释用 ______，多行注释用 ______，文档注释用 ______；注释内容 ______（会/不会）参与程序的编译和运行。

**【答案】** `//`；`/* */`；`/** */`；不会

**【解析】** 注释只是给程序员看的说明性信息，编译时被忽略，不会进入 `.class` 文件，因此注释不影响程序运行效率。IDEA 中 `Ctrl+/` 单行注释、`Ctrl+Shift+/` 多行注释。

**2.** 字符类型字面量用 ______ 括起来，且里面有且只能有 ______；字符串类型字面量用 ______ 括起来。

**【答案】** 单引号 `' '`；一个字符；双引号 `" "`

**【解析】** `'男'`、`'A'`、`'0'` 是字符；`"男"`、`"Hello"` 是字符串。`'AB'` 写两个字符会编译报错。

**3.** 布尔类型 boolean 只有两个取值：______ 和 ______。

**【答案】** `true`（真）；`false`（假）

**【解析】** 布尔类型常用于表示"是/否"的判断结果，第 5 章《流程控制语句》的 if、while 条件都要用它。

**4.** 定义变量的格式是：______。

**【答案】** `数据类型 变量名 = 数据值;`，例如 `int age = 18;`

**【解析】** 变量是内存中的一块区域（可理解为盒子），通过变量名使用其中的数据，数据可以被替换。

**5.** 整数类型变量首选 ______，小数类型变量首选 ______；定义 long 型数据时数值后要加 ______ 标识，定义 float 型数据时数值后要加 ______ 标识。

**【答案】** `int`；`double`；`L`（建议大写）；`F`

**【解析】** int 装不下（超过约 ±21 亿）才用 long；long 字面量加 L 是因为所有整数默认 int，超出 int 范围不加 L 编译报错。float 加 F 是因为所有小数默认 double，8 字节的 double 赋给 4 字节的 float 可能损失精度。

### 二、选择题

**1.** 下列标识符中，**合法**的是（　）。

A. `2b`　　B. `class`　　C. `_money`　　D. `na me`

**【答案】** C

**【解析】** 标识符由字母、数字、`_`、`$` 组成，不能数字开头、不能是关键字、不能含空格。A 数字开头，B 是关键字，D 含空格；下划线开头是允许的，所以 C 合法。

**2.** 下列字面量书写**错误**的是（　）。

A. `'男'`　　B. `"HelloWorld"`　　C. `'AB'`　　D. `3.14`

**【答案】** C

**【解析】** 单引号是字符类型，里面只能有一个字符；`'AB'` 有两个字符，编译报错。两个字符以上的文本要用双引号写成字符串 `"AB"`。

**3.** 代码 `float f = 12.3;` 编译报错，原因是（　）。

A. float 类型不能存储小数
B. 12.3 默认是 double 类型（8 字节），赋给 4 字节的 float 可能损失精度，必须写成 `12.3F`
C. 变量名 `f` 是非法标识符
D. 小数不能直接用字面量赋值

**【答案】** B

**【解析】** 所有小数默认 double。double → float 是"大转小"，可能损失精度，Java 不允许自动完成，需加 F 明确声明这是 float 字面量。
▶ 关联：隐式转换与强制转换的系统规则在第 3 章《运算符》讲解。

**4.** 下面代码的输出结果是（　）。

```java
char c = 97;
System.out.println(c);
```

A. `97`　　B. `a`　　C. 编译报错　　D. 什么都不输出

**【答案】** B

**【解析】** 字符在底层用编码值表示，`'a'` 的 ASCII 编码是 97，所以 `char c = 97` 等价于 `char c = 'a'`，打印字符本身输出 `a`。常见编码值：`'A'`=65、`'a'`=97、`'0'`=48。

**5.** 下列说法**正确**的是（　）。

A. 变量只要定义了，不管赋没赋值都能直接使用
B. `int num = 12.3;` 是正确的写法
C. 变量只在自己所属的大括号 `{}` 内有效，同一范围内变量名不能重复
D. `Class` 是关键字，不能用作类名

**【答案】** C

**【解析】** A 错：变量使用时必须已有值；B 错：int 不能装小数；D 错：Java 区分大小写，`class` 是关键字而 `Class` 不是，`Class` 可以做名字（但不建议）。C 正是变量的作用域规则。

### 三、判断题

**1.** 注释会被编译进 `.class` 文件，所以注释写得越多，程序运行越慢。（　）

**【答案】** ✗ 错误

**【解析】** 注释不参与编译和运行，编译时被直接忽略，对程序性能没有任何影响，应该放心多写注释。

**2.** Java 的关键字全部是小写的，`class` 是关键字，但 `Class` 不是关键字。（　）

**【答案】** ✓ 正确

**【解析】** Java 严格区分大小写，关键字全小写。`Class` 首字母大写后只是一个普通标识符（实际上 Java 里还真有一个叫 Class 的类，见第 23 章反射）。

**3.** 代码中的整数 `10` 默认是 long 类型。（　）

**【答案】** ✗ 错误

**【解析】** 所有整数默认 int，所有小数默认 double。这也是 long 字面量要加 L、超范围整数不加 L 会报错的原因。

**4.** 变量定义时必须立刻赋初始值，否则编译报错。（　）

**【答案】** ✗ 错误

**【解析】** 变量可以先定义不赋值（`int age;` 不报错），但**使用时必须已有值**（`System.out.println(age);` 在赋值前会编译报错）。

### 四、简答题

**1.** 标识符的命名"规则"（必须遵守）和命名"规范"（建议遵守）分别是什么？

**【答案要点】**
- 规则（违反则编译报错）：① 由字母、数字、下划线 `_`、美元符 `$` 组成；② 不能以数字开头；③ 不能是关键字；④ 区分大小写。
- 规范（不报错但体现专业度）：① 见名知意，如 `age`、`studentName`，不要用 `a`、`b`；② 驼峰命名——变量名、方法名用小驼峰（`maxAge`），类名用大驼峰（`HelloWorld`）。

**2.** 使用变量有哪些注意事项？（至少答出 4 条）

**【答案要点】**
1. 变量要先声明才能使用；
2. 变量是什么类型，就必须装什么类型的数据（int 不能装小数）；
3. 变量只在自己所属的 `{}` 范围内有效（作用域）；
4. 同一作用域内变量名不能重复（不同 `{}` 范围可以同名）；
5. 变量定义时可以不赋值，但使用时必须有值；
6. 一条语句可以定义多个同类型变量，用逗号分隔：`int a = 10, b = 20;`。

**3.** 为什么 `char c = 97;` 不报错？打印 c 的结果是什么？这涉及什么概念？

**【答案要点】**
- 计算机只认识二进制，字符在底层也要用数值表示，这套"字符 ↔ 数值"的对应关系叫**编码表**（最早是 ASCII）。
- `'a'` 的编码值是 97，所以 char 变量可以接收 0~65535 的整数；
- `char c = 97` 等价于 `char c = 'a'`，打印结果是字符 `a`（打印的是字符本身而不是数字）。
- 记忆：`'A'`=65、`'a'`=97、`'0'`=48。

### 五、代码阅读题

**1.** 下面代码有三处编译错误，请逐行找出并说明原因。

```java
public class Test {
    public static void main(String[] args) {
        int age = 18;
        System.out.println(age);
        System.out.println(name);        // ①
        int num = 12.3;                  // ②
        {
            int a = 10;
        }
        System.out.println(a);           // ③
    }
}
```

**【答案】**
- ① `name` 变量从未声明，违反"先声明后使用"；
- ② int 类型不能存储小数 12.3，类型不匹配（应改为 `double num = 12.3;`）；
- ③ 变量 `a` 定义在内层 `{}` 中，出了大括号就超出作用域，访问不到。

**【解析】** 这三行分别对应变量的三条注意事项：先声明、类型匹配、作用域。

**2.** 写出下面代码的输出结果。

```java
System.out.println('a' + 1);
System.out.println("a" + 1);
```

**【答案】** 第一行输出 `98`，第二行输出 `a1`。

**【解析】**
- `'a'` 是字符，参与运算时取它的编码值 97，`97 + 1 = 98`，输出整数 98；
- `"a"` 是字符串，`+` 遇到字符串表示**拼接**，结果是字符串 `"a1"`。
▶ 关联：字符运算取编码值、类型提升、字符串拼接规则是第 3 章《运算符》的重点。

**3.** 图书馆借阅账户初始押金余额为 100.0 元。读者因图书逾期 3 天被扣费 1.5 元，随后在线充值 50 元。写出下面代码的输出结果。

```java
double balance = 100.0;
balance = balance - 1.5;
System.out.println(balance);
balance = balance + 50;
System.out.println(balance);
```

**【答案】** 依次输出 `98.5` 和 `148.5`。

**【解析】** 金额是小数，用 double 定义；`balance = balance - 1.5` 表示"取出变量里的值参与计算，再把结果存回变量"，这是变量"值可以被替换"的体现。扣费后 100.0 - 1.5 = 98.5；充值后 98.5 + 50 = 148.5。注意输出带小数点，因为结果是 double 类型。

### 六、编程题（由易到难）

#### 编程题 1（入门）：书店会员注册成功页

**需求：** 书店会员系统注册成功后，需要在控制台打印一张回执，包含：店名（字符串）、会员等级（整数 3）、折扣率（小数 0.85）、性别标识（字符 `'F'`）、是否激活（布尔 true）。请直接用字面量输出这五项，每项一行。

**【参考代码】**

```java
public class MemberReceipt {
    public static void main(String[] args) {
        System.out.println("书香书店会员中心");   // 字符串：双引号
        System.out.println(3);                  // 整数：直接写数字
        System.out.println(0.85);               // 小数：直接写，默认 double
        System.out.println('F');                // 字符：单引号，仅一个字符
        System.out.println(true);               // 布尔：只有 true/false
    }
}
```

**运行结果：**

```text
书香书店会员中心
3
0.85
F
true
```

**【思路讲解】**
1. 本题训练五类常用字面量的书写格式：字符串双引号、字符单引号、整数直接写、小数直接写、布尔 true/false；
2. 最容易错的是字符 `'F'` 用了双引号（那就变成字符串 `"F"`，虽然也能打印，但类型不对）；
3. 注意 `null` 不能直接打印，本题不涉及。
▶ 关联：字面量装进变量、用变量名输出，是编程题 2 的内容。

#### 编程题 2（基础）：今日天气记录

**需求：** 气象站需要记录一天的天气数据：城市名（"石家庄"）、最高气温 32 度、最低气温 24 度、天气状况一个汉字（`'晴'`）、降水量 0.0 毫米、是否发布高温预警（true）。请选择合适的数据类型定义变量描述这些数据，并逐行输出。

**【参考代码】**

```java
public class WeatherRecord {
    public static void main(String[] args) {
        String city = "石家庄";        // 城市名是文本：String
        int high = 32;                 // 气温是整数：int
        int low = 24;
        char sky = '晴';               // 天气状况用一个汉字表示：char，单引号
        double rain = 0.0;             // 降水量是小数：double
        boolean heatWarning = true;    // 是否预警只有是/否：boolean

        System.out.println(city);
        System.out.println(high);
        System.out.println(low);
        System.out.println(sky);
        System.out.println(rain);
        System.out.println(heatWarning);
    }
}
```

**运行结果：**

```text
石家庄
32
24
晴
0.0
true
```

**【思路讲解】**
1. 选类型口诀：文本 → String，整数 → int，单字符 → char，小数 → double，是非 → boolean；
2. 一个汉字也是"一个字符"，`'晴'` 合法；如果要存"晴转多云"四个字就必须用 String；
3. 变量名见名知意（`high`、`rain`、`heatWarning`），符合小驼峰规范；
4. 输出时写变量名，打印的是变量里装的值而不是变量名字面。

#### 编程题 3（进阶）：书店库存变动

**需求：** 书店某教辅书月初库存 200 本。本周发生三次变动：被学校团购借走 35 本、读者还回 12 本、出版社新到货 50 本。请用一个变量记录库存，每次变动后重新赋值并打印当前库存，最后打印一行最终库存说明。

**【参考代码】**

```java
public class BookStock {
    public static void main(String[] args) {
        int stock = 200;                 // 月初库存
        System.out.println("月初库存：" + stock);

        stock = stock - 35;              // 团购借出 35 本
        System.out.println("借出后库存：" + stock);

        stock = stock + 12;              // 还回 12 本
        System.out.println("还回后库存：" + stock);

        stock = stock + 50;              // 新到货 50 本
        System.out.println("到货后库存：" + stock);
    }
}
```

**运行结果：**

```text
月初库存：200
借出后库存：165
还回后库存：177
到货后库存：227
```

**【思路讲解】**
1. 库存是整数且数量不大，用 int；全程只用一个变量 `stock`，体现"变量里的数据可以被替换"；
2. `stock = stock - 35` 的执行顺序：先取 stock 现值 200，算 200-35=165，再把 165 存回 stock；
3. `"借出后库存：" + stock` 中字符串与整数用 `+` 拼接，结果是字符串（拼接规则第 3 章详讲）；
4. 验算：200 - 35 + 12 + 50 = 227。
▶ 关联：这里的加减运算是第 3 章《运算符》算术运算符的最简形式。

#### 编程题 4（挑战）：图书馆分区牌与馆藏编号

**需求：** 图书馆用字母给阅览分区编号（A 区、B 区……），用 13 位数字作为图书馆藏编号。请编写程序：
1. 利用字符编码值，让 char 变量接收整数 65，打印出 A 区的字母标识；再定义变量表示 B 区（思考 B 的编码值是多少）；
2. 定义一个 long 变量保存馆藏编号 `9787115600000`（13 位，已超出 int 范围），打印分区字母和馆藏编号；
3. 最后定义一个 double 变量表示本书定价 59.80 元并输出。

**【参考代码】**

```java
public class LibraryShelf {
    public static void main(String[] args) {
        char sectionA = 65;                       // 'A' 的编码值是 65
        char sectionB = 66;                       // 'B' 的编码值是 66
        System.out.println("一区标识：" + sectionA);
        System.out.println("二区标识：" + sectionB);

        long bookId = 9787115600000L;             // 13 位整数超出 int，必须用 long 并加 L
        System.out.println("馆藏编号：" + bookId);

        double price = 59.80;                     // 定价是小数，用 double
        System.out.println("定价：" + price + " 元");
    }
}
```

**运行结果：**

```text
一区标识：A
二区标识：B
馆藏编号：9787115600000
定价：59.8 元
```

**【思路讲解】**
1. char 底层存编码值：`'A'`=65、`'B'`=66，char 变量接收整数后打印出的是字符本身；
2. 13 位编号 9787115600000 约 9.7 万亿，远超 int 的约 ±21 亿上限，必须用 long；且所有整数默认 int，这个数字直接写会因"超出 int 范围"编译报错，**必须在末尾加 L**；
3. 定价 59.80 是小数用 double，`59.80` 输出为 `59.8`（double 不保留无意义的末尾 0）；
4. 本题综合了本章三个最容易错的细节：char 编码值、long 加 L、小数默认 double。
▶ 关联：字符与编码的完整体系（GBK、UTF-8、乱码成因）在第 19 章《字符集与字节流》讲解；long、double 等类型的取值范围见表 2.6.2。

---

<div style="page-break-after: always;"></div>

## 第三章 运算符 · 习题精讲

> 做题方法：先独立作答，再看【答案】与【解析】。解析中用「▶ 关联」标出与其他章节的联系，帮你把知识点串成网。
> 题目场景全部原创，考查的仍是本章知识点：算术/赋值/关系/逻辑/三元运算符、字符串拼接、自增自减、类型转换、Scanner 录入。

---

### 一、填空题

**1.** `System.out.println(7 / 2);` 输出 ______；`System.out.println(7 % 2);` 输出 ______。

**【答案】** `3`；`1`。

**【解析】** 两个整数做除法，`/` 取**商**、`%` 取**余**。整数相除结果只能是整数；想得到小数必须让浮点数参与运算（如 `7 / 2.0` 得 3.5）。
▶ 关联：`%` 取余在第6章《数组》中判断奇偶位置（`i % 2`）、第17章《Set与Map集合》哈希表定位时会反复用到。

---

**2.** 把一段视频的总秒数 `sec` 换算成"几分几秒"：分钟数 = `sec / ______`，剩余秒数 = `sec % ______`。

**【答案】** `60`；`60`。即 `sec / 60` 与 `sec % 60`。

**【解析】** 这是 `/` 与 `%` 的经典搭配：除以进制数得到"高位"，对进制数取余得到"低位"。例如 500 秒：`500 / 60 = 8`（分），`500 % 60 = 20`（秒）。同一套思路后面还会用于毫秒转秒、字节转 KB 等。

---

**3.** `byte`、`short`、`char` 三种类型的数据参与运算时，都会先提升为 ______ 类型，再进行运算。

**【答案】** `int`。

**【解析】** 哪怕两个 `byte` 相加，结果也是 `int`，所以 `byte c = a + b;` 编译报错。`char` 参与运算时取编码表中的数值（`'A'` 是 65）。
▶ 关联：char 取编码值的底层原因是字符集编码，第19章《字符集与字节流》讲 ASCII/GBK/UTF-8 时会从原理上再次解释。

---

**4.** 扩展赋值运算符 `+=`、`-=`、`*=` 等的一个重要特点是：自带 ______。

**【答案】** 强制类型转换。

**【解析】** `x += y;` 等价于 `x = (x的类型)(x + y);`。因此 `byte x = 10; byte y = 30; x += y;` 能运行，而 `x = x + y;` 编译报错。

---

**5.** 关系运算符（`>`、`==`、`!=` 等）的运算结果一定是 ______ 类型的值。

**【答案】** `boolean`（`true` 或 `false`）。

**【解析】** 关系表达式是所有流程控制的"条件"来源。注意 `==` 是比较、`=` 是赋值，在 `if` 条件里误写是高频错误。
▶ 关联：第5章《流程控制语句》中 `if`、`while` 的小括号里必须是 boolean 值；第9章《面向对象高级（下）》会讲到引用类型用 `==` 比地址、用 `equals` 比内容。

---

**6.** 短路与 `&&` 当左边为 `false` 时，右边表达式 ______；短路或 `||` 当左边为 `true` 时，右边表达式 ______。

**【答案】** 不会执行（被短路）；不会执行（被短路）。

**【解析】** 短路不仅省一次运算，更常用于防止异常，例如 `if (s != null && s.length() > 0)`——左边为 false 时右边不执行，就不会对 `null` 调方法产生空指针异常。
▶ 关联：空指针异常 `NullPointerException` 是第16章《异常与List集合》的重点异常。

---

### 二、选择题

**1.** 以下代码的输出是（　）

```java
int cups = 2;
System.out.println("订单" + cups + 'A');
System.out.println(cups + 'A' + "订单");
```

A. `订单2A` 和 `67订单`
B. `订单265` 和 `67订单`
C. `订单2A` 和 `2A订单`
D. 编译报错

**【答案】** A。

**【解析】** `+` 从左到右执行：第一行开头是字符串，之后全做拼接，字符 `'A'` 拼成字母，得 `订单2A`；第二行先算 `cups + 'A'`，char 取编码值 65，`2 + 65 = 67`，再拼接字符串得 `67订单`。**字符串开头全拼接，数值开头先加法**。

---

**2.** 以下代码能否编译通过？（　）

```java
byte b = 5 + 6;
```

A. 编译报错，5 + 6 是 int，赋给 byte 需要强转
B. 编译通过，运行时 b 的值是 11
C. 编译通过，运行时 b 的值是 56
D. 编译报错，byte 不能存字面量

**【答案】** B。

**【解析】** **字面量优化（编译期常量折叠）**：`javac` 编译时就把 `5 + 6` 算成 `11`，字节码里实际是 `byte b = 11;`，11 在 byte 范围内，合法。对比：`byte b3 = b1 + b2;`（变量相加）会报错，因为变量的值编译期不确定，只能按"提升为 int"处理。

---

**3.** 以下代码运行后 `stock` 的值是（　）

```java
int stock = 5;
boolean ok = (stock > 10) && (++stock > 0);
System.out.println(stock);
```

A. 5　　B. 6　　C. 0　　D. 编译报错

**【答案】** A。

**【解析】** `stock > 10` 为 false，`&&` 短路，右边 `++stock` 不执行，stock 仍是 5。换成 `&` 则右边一定执行、stock 变 6。

---

**4.** `double d = 19.9; int i = (int) d;` 执行后 `i` 的值是（　）

A. 20　　B. 19　　C. 19.9　　D. 编译报错

**【答案】** B。

**【解析】** 强制转换 `double → int` 时小数部分被**直接截断**（不是四舍五入），得 19。需要四舍五入应用 `Math.round(d)`（第14章《常用API》）。

---

**5.** 表达式 `a > b || a < b && a > b`（设 `a=10, b=20`）的结果是（　）

A. true　　B. false　　C. 编译报错　　D. 无法确定

**【答案】** B。

**【解析】** 优先级上 **`&&` 高于 `||`**，表达式等价于 `a > b || (a < b && a > b)`：`a > b` 为 false；括号内 `true && false` 为 false；整体 `false || false` = false。开发中用小括号明确顺序，不要让读者背优先级。

---

**6.** 以下三元运算符写法，能编译通过的是（　）

A. `int x = true ? "abc" : 123;`
B. `int max = 5 > 3 ? 5 : 3;`
C. `boolean b = 1 ? true : false;`
D. `String s = 5 > 3 ? 100 : "abc";`

**【答案】** B。

**【解析】** 规则：① 条件必须是 boolean（C 用 `1` 是 C 语言习惯，Java 不允许）；② `:` 两侧结果类型必须兼容（A、D 是 String 与 int 混用）。

---

### 三、判断题

**1.** `System.out.println(10++);` 可以正常输出 11。（　）

**【答案】** ✗ 错误。

**【解析】** 自增自减**只能操作变量，不能操作字面量**。`10` 是常量无法"加 1 存回"，编译报错。

---

**2.** `&` 和 `|` 无论左边结果是什么，右边表达式都一定会执行。（　）

**【答案】** ✓ 正确。

**【解析】** 这是普通逻辑运算符与短路运算符的核心区别。开发中推荐 `&&`、`||`。

---

**3.** `+=` 完全等价于 `a = a + b`，任何情况下两种写法都可以互换。（　）

**【答案】** ✗ 错误。

**【解析】** `+=` 自带强转，等价于 `a = (a的类型)(a + b)`。当 a 是 byte/short 时，`a = a + b` 编译报错，`a += b` 却能通过。

---

**4.** 三元运算符中，条件为 true 取冒号前的值，条件为 false 取冒号后的值。（　）

**【答案】** ✓ 正确。

**【解析】** 它是 `if-else` 的精简写法，只适用于"两个分支都返回一个值"的场景；复杂分支要用第5章《流程控制语句》的 `if-else`。

---

### 四、简答题

**1.** 简述 `&&` 与 `&` 的区别，开发中推荐用哪一个。

**【答案要点】** 运算结果相同（两边都 true 才 true）；区别在执行方式：`&` 两边一定都执行，`&&` 左边为 false 时右边短路不执行。推荐 `&&`：效率更高，还能避免异常（先判 null 再调方法）。`||` 与 `|` 同理。

---

**2.** 什么是隐式转换？什么是强制转换？各自规则和风险是什么？

**【答案要点】** 隐式转换：小范围类型自动转大范围（`byte → short → int → long → float → double`，char 可提升为 int），JVM 自动完成无风险；运算时 `byte/short/char` 先提升为 int。强制转换：大范围转小范围需手动写 `(目标类型)`，可能丢失精度（`(int)19.9` 得 19）。
▶ 关联：引用类型也有向上/向下转型，形式相似但原理不同，见第9章多态部分，注意对比。

---

**3.** 简述 `++a` 与 `a++` 的区别。

**【答案要点】** `++a` 先加 1 再用新值；`a++` 先用原值再加 1。单独成句时效果相同，参与赋值/运算时结果不同；只能作用于变量。

---

### 五、代码阅读题

**1.** 写出以下代码的输出结果：

```java
int count = 3;
System.out.println("订单" + count + "号");
System.out.println(count + 5 + "号");
```

**【答案】**

```text
订单3号
8号
```

**【解析】** 第一行字符串开头，全部拼接；第二行先算 `3 + 5 = 8`（数值加法），再与 "号" 拼接。

---

**2.** 写出以下代码的输出结果：

```java
int stock = 5;
boolean ok = (stock > 10) && (++stock > 0);
System.out.println(ok);
System.out.println(stock);
```

**【答案】**

```text
false
5
```

**【解析】** `stock > 10` 为 false，`&&` 短路，`++stock` 不执行，stock 保持 5。

---

**3.** 写出以下代码的输出结果（自增综合）：

```java
int m = 8;
int n = 4;
int r = ++m - n-- + m++ + --n;
System.out.println(r);
System.out.println(m);
System.out.println(n);
```

**【答案】**

```text
16
10
2
```

**【解析】** 从左到右逐项跟踪变量最新值：

| 子表达式 | 取值 | 执行后变量 |
| --- | --- | --- |
| 初始 | — | m=8, n=4 |
| `++m`（前缀） | m 先变 **9**，取 9 | m=9 |
| `n--`（后缀） | 取 **4** | n=3 |
| `m++`（后缀） | 取 **9** | m=10 |
| `--n`（前缀） | n 先变 **2**，取 2 | n=2 |

计算：`9 - 4 + 9 + 2 = 16`；最终 m=10，n=2。
这类写法工作中不推荐（可读性差），但"逐行跟踪变量状态"是第5章循环计数、第21章线程计数的基本功。

---

**4.** 写出以下代码的输出结果：

```java
char ch = 'A';
int code = ch + 1;
System.out.println(code);
System.out.println((char) (ch + 1));
```

**【答案】**

```text
66
B
```

**【解析】** `'A'` 的编码值是 65，`ch + 1` 中 char 提升为 int 得 66；再强转回 char，66 对应字符 `'B'`。
▶ 关联：字符与编码的对应关系就是字符集的内容，第19章《字符集与字节流》会讲 GBK/UTF-8 中中文的编码方式。

---

### 六、编程题（由易到难）

**1.【易】快递首重计费。** 录入包裹重量（整数千克）：1 千克及以内收 10 元，超过 1 千克的部分每千克加收 3 元。用三元运算符计算并打印运费。

**【参考答案】**

```java
import java.util.Scanner;

public class ExpressFee {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入包裹重量（千克）：");
        int weight = sc.nextInt();

        int fee = weight <= 1 ? 10 : 10 + (weight - 1) * 3;
        System.out.println("应付运费：" + fee + " 元");
    }
}
```

**【思路】** 条件"重量 ≤ 1"用三元判断：满足取 10；不满足则首重 10 元 + 超重部分 `(weight - 1) * 3`。
**运行结果**：输入 1 → `应付运费：10 元`；输入 3 → `10 + 2*3 = 16`，输出 `应付运费：16 元`。

---

**2.【易】视频时长换算。** 录入视频总秒数，换算成"X 分 Y 秒"打印。

**【参考答案】**

```java
import java.util.Scanner;

public class VideoTime {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入视频总秒数：");
        int sec = sc.nextInt();

        int min = sec / 60;    // 总分钟数：除以 60 取商
        int rest = sec % 60;   // 剩余秒数：对 60 取余
        System.out.println(sec + " 秒 = " + min + " 分 " + rest + " 秒");
    }
}
```

**【思路】** `/` 取高位、`%` 取低位。这与进制思想一致，后面毫秒转秒、字节换算都用同一套路。
**运行结果**：输入 500 → `500 秒 = 8 分 20 秒`。

---

**3.【中】三科成绩判定。** 依次录入三科成绩，判断是否**全部及格**（每科 ≥ 60），并打印成绩单与判定结果。

**【参考答案】**

```java
import java.util.Scanner;

public class ScoreCheck {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请依次输入三科成绩：");
        int s1 = sc.nextInt();
        int s2 = sc.nextInt();
        int s3 = sc.nextInt();

        boolean allPass = s1 >= 60 && s2 >= 60 && s3 >= 60;
        System.out.println("成绩单：" + s1 + ", " + s2 + ", " + s3);
        System.out.println(allPass ? "三科全部及格" : "有科目未及格，需要补考");
    }
}
```

**【思路】** 三个条件同时成立用 `&&` 连接（短路与：前面有一科不及格，后面的判断就不再执行）；最终输出用三元二选一。
**运行结果**：输入 80 55 90 → `有科目未及格，需要补考`；输入 70 65 88 → `三科全部及格`。

---

**4.【中】商场满减抹零。** 录入消费金额：满 200 打 8 折，满 100 打 9 折，不满 100 原价；结算时把角分直接抹掉（强制转换取整）。打印折后价与抹零后金额。

**【参考答案】**

```java
import java.util.Scanner;

public class MallDiscount {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入消费金额：");
        double money = sc.nextDouble();

        double pay = money >= 200 ? money * 0.8
                 : (money >= 100 ? money * 0.9 : money);
        int finalPay = (int) pay;   // 抹零：double 强转 int，小数部分丢弃
        System.out.println("折后金额：" + pay + " 元");
        System.out.println("抹零后收取：" + finalPay + " 元");
    }
}
```

**【思路】** 两个档位用三元**嵌套**：先判 ≥200，不满足再判 ≥100。`(int) pay` 利用强制转换截断小数实现"抹零"，注意这是截断不是四舍五入。
**运行结果**：输入 250 → 折后 200.0，抹零 200；输入 150 → 折后 135.0，抹零 135；输入 80 → 折后 80.0，抹零 80。

---

**5.【较难】停车场车位播报。** 停车场初始有 20 个空闲车位；依次发生：来两辆车、走一辆车、再来一辆车。要求每发生一次就打印当前空闲车位数，体会前缀 `--` 与后缀 `++` 的区别。

**【参考答案】**

```java
public class ParkingLot {
    public static void main(String[] args) {
        int spots = 20;
        System.out.println("初始空闲车位：" + spots);

        System.out.println("来一辆车，空闲车位：" + --spots);  // 前缀：先减再打印
        System.out.println("来一辆车，空闲车位：" + --spots);
        System.out.println("走一辆车，空闲车位：" + spots++);  // 后缀：先打印再加
        System.out.println("来一辆车，空闲车位：" + --spots);
        System.out.println("最终空闲车位：" + spots);
    }
}
```

**【思路】** 来车占用车位要"先减后用"，用前缀 `--spots`；走车释放车位时若写 `spots++`，打印的是加之前的旧值（本题故意用后缀制造对比，体会"先用后变"）。
**运行结果**：

```text
初始空闲车位：20
来一辆车，空闲车位：19
来一辆车，空闲车位：18
走一辆车，空闲车位：18
来一辆车，空闲车位：18
最终空闲车位：18
```

第三行打印 18 是后缀 `++` 的"先用后变"：先输出 18，spots 才变成 19；紧接着来车 `--spots` 又变回 18。实际开发中车位计数这类逻辑建议拆成独立语句，不要在输出里混用自增。
▶ 关联：这种计数器在第5章《流程控制语句》的循环累加（`sum += i`、`count++`）中大量使用。

---

<div style="page-break-after: always;"></div>

## 第四章 方法 · 习题精讲

> 做题方法：先独立作答，再看【答案】与【解析】。解析中用「▶ 关联」标出与其他章节的联系。
> 题目场景全部原创，考查的仍是本章知识点：方法定义与调用、形参与实参、返回值、栈内存执行原理、方法注意事项、方法重载。

---

### 一、填空题

**1.** 方法是一段具有独立功能的代码块，它的执行特点是：______。

**【答案】** 不调用就不执行。

**【解析】** 方法定义后只是存放在方法区的字节码中，只有被调用时才会压入栈内存运行。`main` 方法是程序入口，JVM 从它开始调用。

---

**2.** 方法被调用时进入 ______ 内存运行，该内存的特点是 ______。

**【答案】** 栈；先进后出（后进先出）。

**【解析】** 方法调用时"压栈"，执行完"弹栈"，最先调用的方法最后结束。弹栈后方法中的局部变量（含形参）随即消失。
▶ 关联：栈里存方法的局部变量；`new` 出来的对象（数组、学生对象）存放在堆中，见第6章《数组》、第7章《面向对象基础》的内存图。

---

**3.** 定义方法时要做到"两个明确"：明确 ______ 和明确 ______。

**【答案】** 参数（类型和个数）；返回值类型（有结果写具体类型，没有写 `void`）。

**【解析】** 例如计算电费：需要用电量参数、返回费用 double；只打印小票：有参数但无结果，用 `void`。

---

**4.** 方法重载的判断条件是：同一个类中，方法名 ______，形参列表 ______；与 ______ 和 ______ 无关。

**【答案】** 相同；不同（个数、类型或类型顺序不同）；返回值类型；形参名称。

**【解析】** 仅返回值类型不同不构成重载（编译器无法区分），仅形参名不同也不构成（`(int a)` 与 `(int b)` 签名相同）。
▶ 关联：重载（Overload）是同类中同名方法；重写（Override）是子类覆盖父类方法，见第8章《面向对象高级（上）》。

---

**5.** `void` 方法中 `return;` 的作用是 ______；且 `return` 语句之后 ______。

**【答案】** 提前结束方法；不能再写代码（写了编译报错，因为永远执行不到）。

---

### 二、选择题

**1.** 奶茶店定义了 `makeDrink` 系列方法，下列哪一个与 `public static void makeDrink(String flavor, int sugar)` 构成正确的重载？（　）

A. `public static String makeDrink(String flavor, int sugar) { return "ok"; }`
B. `public static void makeDrink(String taste, int sweet) { }`
C. `public static void makeDrink(int sugar, String flavor) { }`
D. 在另一个类中写 `public static void makeDrink(String flavor, int sugar) { }`

**【答案】** C。

**【解析】** A 仅返回值类型不同（void → String），形参列表完全一样，不是重载，同类中编译报错；B 仅形参名字不同，签名相同，不是重载；C 是**不同类型的顺序不同**（String,int → int,String），构成重载；D 重载必须发生在同一个类中。

---

**2.** 关于方法的说法，错误的是（　）

A. 方法与方法之间是平级关系，不能在一个方法体里定义另一个方法
B. 方法的编写顺序和执行顺序无关，执行顺序由调用顺序决定
C. 方法定义后会自动按书写顺序依次执行
D. `void` 类型的方法可以直接用 `方法名();` 调用

**【答案】** C。

**【解析】** 方法"不调用不执行"，书写顺序不影响执行顺序。

---

**3.** 阅读奶茶店代码，程序的输出顺序是（　）

```java
public static void main(String[] args) {
    makeMilkTea();
}
public static void makeMilkTea() {
    boilWater();
    System.out.println("加入茶汤");
    addPearls();
}
public static void boilWater() { System.out.println("烧开水"); }
public static void addPearls() { System.out.println("加珍珠"); }
```

A. 加入茶汤、烧开水、加珍珠
B. 烧开水、加入茶汤、加珍珠
C. 烧开水、加珍珠、加入茶汤
D. 加珍珠、加入茶汤、烧开水

**【答案】** B。

**【解析】** 压栈顺序 `main → makeMilkTea → boilWater`：boilWater 先执行完打印"烧开水"并弹栈，回到 makeMilkTea 打印"加入茶汤"，再调用 addPearls 打印"加珍珠"。

---

**4.** 关于带返回值方法的调用，说法正确的是（　）

A. 有返回值的方法必须用变量接收结果，否则编译报错
B. `void` 方法也能用变量接收返回值
C. 有返回值的方法可以直接调用不接收，但返回结果会丢失
D. 一个方法可以同时返回多个值

**【答案】** C。

**【解析】** 非 void 方法直接调用语法合法，只是返回值被丢弃；Java 方法一次只能 `return` 一个值（想"带回多个数据"要靠数组或对象，第6/7章会学）。

---

**5.** 健身房两次调用计费方法，下列说法正确的是（　）

```java
public static void main(String[] args) {
    calcFee(3);
    calcFee(12);
}
public static void calcFee(int months) {
    int price = months * 300;
    System.out.println(months + "个月费用：" + price);
}
```

A. 两次调用共用同一批局部变量，第二次 months 还是 3
B. 每次调用都是一次全新的压栈，形参重新赋值，两次互不影响
C. 第二次调用会因为方法已存在而报错
D. 第一次的 price 会保留下来影响第二次

**【答案】** B。

**【解析】** 调用时实参的值赋给形参，形参是随方法压栈的局部变量，弹栈后消失；第二次调用是全新压栈，`months=12`。两次分别输出 900 和 3600。
▶ 关联：这就是"值传递"的基础——基本类型传的是值的副本，方法内改形参不影响调用处；第6章数组、第7章对象传的是地址值副本，方法内能改对象内容，这是后续重点对比。

---

**6.** `System.out.println()` 可以接收 int、double、boolean、String 等多种参数，这体现了（　）

A. 方法重写　　B. 方法重载　　C. 方法递归　　D. 方法嵌套

**【答案】** B。

**【解析】** `println` 是一系列同名方法（`println(int)`、`println(double)`、`println(String)`…），形参类型不同，是典型重载，好处是调用者不用记忆一堆方法名。

---

### 三、判断题

**1.** 在一个方法的方法体内部可以再定义另一个方法。（　）

**【答案】** ✗ 错误。

**【解析】** 方法之间是**平级关系**，不能嵌套定义；方法里只能调用其他方法。

---

**2.** 只要方法名相同、返回值类型不同，就构成方法重载。（　）

**【答案】** ✗ 错误。

**【解析】** 重载看的是**形参列表**（个数、类型、顺序），与返回值类型无关；只有返回值不同时签名冲突，编译报错。

---

**3.** 方法编写在类中的先后位置，不影响程序的执行结果。（　）

**【答案】** ✓ 正确。

**【解析】** 执行顺序由**调用顺序**决定，与书写顺序无关。

---

**4.** 形参在定义时可以给初始值，如 `public static void m(int a = 10) {}`。（　）

**【答案】** ✗ 错误。

**【解析】** Java 形参**不能给默认值**（这是 C++/Python 的语法），形参值由调用时的实参决定。

---

### 四、简答题

**1.** 使用方法有哪两个主要好处？

**【答案要点】** ① 提高可维护性：臃肿代码按功能拆分，某功能出问题只需排查对应方法；② 提高代码复用性：同一功能写一次，需要时多次调用。

---

**2.** 简述方法调用时在栈内存中的执行过程。

**【答案要点】** 方法未调用时存于方法区；被调用时压入栈内存运行；栈是先进后出结构，调用链 `main → A → B → C` 压栈，执行完按 `C → B → A → main` 弹栈；即"最先调用的最后结束，最后调用的最先结束"；弹栈后局部变量随即消失。
▶ 关联：递归（方法自己调自己）就是利用压栈弹栈执行，没有正确终止条件会栈溢出，见第18章《JDK8新特性Stream与File》。

---

**3.** 判断方法重载的条件是什么？举例说明"类型顺序不同"也算重载。

**【答案要点】** 同一类中方法名相同、形参列表不同（个数、类型、类型顺序不同）；与返回值类型、修饰符、形参名无关。例：`fee(int months, double discount)` 与 `fee(double discount, int months)` 构成重载；但 `fee(int a, int b)` 与 `fee(int b, int a)` 签名相同，不算。

---

### 五、代码阅读题

**1.** 写出以下代码的输出结果：

```java
public static void main(String[] args) {
    System.out.println("门店开始营业");
    brewCoffee();
    System.out.println("出餐完成");
}
public static void brewCoffee() {
    int beans = 20;
    int water = 100;
    System.out.println("用" + beans + "克咖啡豆和" + water + "毫升水煮咖啡");
}
```

**【答案】**

```text
门店开始营业
用20克咖啡豆和100毫升水煮咖啡
出餐完成
```

**【解析】** main 压栈后先打印营业提示；调用 brewCoffee 压栈，打印煮咖啡的配方后弹栈；回到 main 打印"出餐完成"。

---

**2.** 写出以下代码的输出结果：

```java
public static void main(String[] args) {
    System.out.println(makeDrink(5));
    System.out.println(makeDrink("芋泥"));
    System.out.println(makeDrink("珍珠", 3));
    System.out.println(makeDrink(2, "红豆"));
}
public static String makeDrink(int sugar)                 { return sugar + "分糖原味茶"; }
public static String makeDrink(String flavor)             { return flavor + "奶茶"; }
public static String makeDrink(String flavor, int sugar)  { return flavor + "奶茶" + sugar + "分糖"; }
public static String makeDrink(int sugar, String topping) { return topping + "加料" + sugar + "分糖"; }
```

**【答案】**

```text
5分糖原味茶
芋泥奶茶
珍珠奶茶3分糖
红豆加料2分糖
```

**【解析】** JVM 按实参的个数和类型匹配重载版本：一个 int → 第1版；一个 String → 第2版；String+int → 第3版；int+String（顺序不同）→ 第4版。

---

**3.** 以下代码有什么问题？指出并改正：

```java
public static void main(String[] args) {
    double money = calcTicket(120);
    System.out.println("票价：" + money);
}
public static void calcTicket(double distance) {
    System.out.println("票价" + distance * 0.5 + "元");
}
```

**【答案】** 编译报错：`calcTicket` 是 `void` 方法，没有返回值，不能用变量接收。

**【解析】** 两种改正：
- 只想打印：直接调用 `calcTicket(120);`；
- 想拿到票价继续使用：改为带返回值：

```java
public static double calcTicket(double distance) {
    return distance * 0.5;
}
```

设计方法先问"两个明确"：结果要不要给调用者用？要用就声明返回值类型并 `return`。

---

### 六、编程题（由易到难）

**1.【易】咖啡店菜单。** 定义无参无返回值方法 `printMenu()`，打印 3 行菜单（美式 15 元、拿铁 22 元、摩卡 25 元）；在 main 中调用。

**【参考答案】**

```java
public class CoffeeShop {
    public static void main(String[] args) {
        printMenu();
    }

    // 明确参数：无；明确返回值：只打印，void
    public static void printMenu() {
        System.out.println("===== 今日咖啡菜单 =====");
        System.out.println("美式咖啡：15 元");
        System.out.println("拿铁咖啡：22 元");
        System.out.println("摩卡咖啡：25 元");
    }
}
```

**【思路】** 菜单内容固定、不需要外部数据，所以无参；只负责打印、不产生结果，所以 `void`，调用时直接写 `printMenu();`。
**运行结果**：打印菜单标题与三行价格。

---

**2.【易】电影票小票。** 定义有参无返回值方法 `printTicket(String movie, int row, int seat)`，打印一张电影票（影片名、排号、座号、票价提示"票价 35 元"）；main 中模拟售出两张票。

**【参考答案】**

```java
public class Cinema {
    public static void main(String[] args) {
        printTicket("流浪地球3", 5, 12);
        printTicket("长安三万里", 3, 8);
    }

    // 明确参数：影片名 String、排号 int、座号 int；明确返回值：void
    public static void printTicket(String movie, int row, int seat) {
        System.out.println("------ 电影票 ------");
        System.out.println("影片：" + movie);
        System.out.println("座位：" + row + " 排 " + seat + " 座");
        System.out.println("票价：35 元");
        System.out.println("--------------------");
    }
}
```

**【思路】** 每次售票的数据不同，用形参接收影片/排/座；方法只打印小票，`void`。两次调用是两次独立压栈，形参互不影响。
**运行结果**：先后打印两张内容不同的电影票。

---

**3.【中】阶梯电价计算。** 定义方法 `calcElectricFee(int kwh)` 返回电费：月用电 240 度以内 0.5 元/度；240~400 度的部分 0.55 元/度；超过 400 度的部分 0.8 元/度。main 中键盘录入本月用电量并打印电费。

**【参考答案】**

```java
import java.util.Scanner;

public class ElectricityFee {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入本月用电量（度）：");
        int kwh = sc.nextInt();
        double fee = calcElectricFee(kwh);   // 用变量接收返回结果
        System.out.println("本月电费：" + fee + " 元");
    }

    // 明确参数：用电量 int；明确返回值：电费 double
    public static double calcElectricFee(int kwh) {
        double fee;
        if (kwh <= 240) {
            fee = kwh * 0.5;
        } else if (kwh <= 400) {
            fee = 240 * 0.5 + (kwh - 240) * 0.55;
        } else {
            fee = 240 * 0.5 + (400 - 240) * 0.55 + (kwh - 400) * 0.8;
        }
        return fee;
    }
}
```

**【思路】** 电费要交给 main 打印（将来还可能用于汇总），所以方法返回 double。分段计价的关键是"高档只对超出部分计费"：第二档只算 `kwh-240` 这部分。
**运行结果**：输入 200 → `100.0 元`；输入 300 → `120 + 60*0.55 = 153.0 元`；输入 500 → `120 + 88 + 80 = 288.0 元`。
▶ 关联：`if-else if` 多分支语法见第5章《流程控制语句》。

---

**4.【中】闰年判断器。** 定义方法 `isLeapYear(int year)` 返回 boolean：能被 4 整除且不能被 100 整除，**或者**能被 400 整除的年份是闰年。main 中录入年份，调用方法并打印"闰年/平年"。

**【参考答案】**

```java
import java.util.Scanner;

public class LeapYear {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入年份：");
        int year = sc.nextInt();
        boolean leap = isLeapYear(year);
        System.out.println(leap ? year + " 年是闰年" : year + " 年是平年");
    }

    // 明确参数：年份 int；明确返回值：判断结果 boolean
    public static boolean isLeapYear(int year) {
        return (year % 4 == 0 && year % 100 != 0) || (year % 400 == 0);
    }
}
```

**【思路】** 判断类方法天然适合返回 boolean：条件用 `%` 取余判断整除、`&&` 连接"被4整除且不被100整除"、`||` 连接"被400整除"。调用处用三元运算符把 true/false 翻译成中文结论。
**运行结果**：输入 2024 → `闰年`；输入 1900（能被100整除但不能被400整除）→ `平年`；输入 2000 → `闰年`。
▶ 关联：`%`、`&&`、`||`、三元运算符都来自第3章《运算符》；boolean 返回值的方法在第7章面向对象中大量用于状态判断。

---

**5.【较难】健身房续费重载。** 用方法重载设计续费系统：
- `renew()`：默认续费 1 个月，价格 300 元；
- `renew(int months)`：续费指定月数，每月 300 元；
- `renew(int months, boolean withCoach)`：续费指定月数，若请私教（withCoach=true）每月再加 200 元。
三个方法都返回应付费用，main 中分别调用并打印。

**【参考答案】**

```java
public class GymRenew {
    public static void main(String[] args) {
        System.out.println("默认续费：" + renew() + " 元");
        System.out.println("续费半年：" + renew(6) + " 元");
        System.out.println("续费年卡+私教：" + renew(12, true) + " 元");
        System.out.println("续费季卡无教练：" + renew(3, false) + " 元");
    }

    // 版本1：无参，默认 1 个月
    public static int renew() {
        return 300;
    }

    // 版本2：指定月数（个数不同 → 重载）
    public static int renew(int months) {
        return months * 300;
    }

    // 版本3：月数 + 是否请私教（个数不同 → 重载）
    public static int renew(int months, boolean withCoach) {
        int pricePerMonth = withCoach ? 500 : 300;  // 含私教每月 300+200
        return months * pricePerMonth;
    }
}
```

**【思路】** 三个方法同名 `renew`，靠形参个数/类型区分——这就是重载。调用者只需记住"续费"这一个动作，传不同参数自动匹配对应版本，体现重载"减少记忆负担"的价值。无参版本可以复用逻辑写成 `return renew(1);`（调用重载的兄弟方法），这里写 300 更直观。
**运行结果**：

```text
默认续费：300 元
续费半年：1800 元
续费年卡+私教：6000 元
续费季卡无教练：900 元
```

▶ 关联：现在方法都用 `static` 修饰，static 的含义见第11章《面向对象进阶（一）》；学完面向对象后这类功能会改为对象的成员方法（第7章）；重载的分派机制在第12章多态中会与"重写"对比讲解。

---

<div style="page-break-after: always;"></div>

## 第五章 流程控制语句 · 习题精讲

> 做题前先回顾本章主线：**顺序 → 分支（if / switch）→ 循环（for / while / do-while）→ 跳转控制（break / continue / return）→ Random 随机数**，外加排查问题的利器 **Debug 断点调试**。
>
> ▶ 关联：条件表达式依赖第 3 章的关系/逻辑运算符；Scanner 录入也在第 3 章；方法调用与 return 的压栈弹栈见第 4 章；while(true)+break 的交互模式在第 21 章线程通信中还会出现；循环是第 18 章递归的基础。

---

### 一、填空题

**1.** 程序的三种执行结构是 ______ 结构、______ 结构和 ______ 结构。

**【答案】** 顺序；分支；循环

**【解析】** 顺序结构自上而下执行，是程序默认方式；分支结构（if、switch）按条件选择执行路径；循环结构（for、while、do-while）控制代码重复执行。任何复杂程序都是这三种结构组合出来的。

---

**2.** switch 表达式支持的类型有 byte、short、int、char，以及 JDK5 开始支持的 ______ 和 JDK7 开始支持的 ______；不支持 ______、float、long。

**【答案】** 枚举（enum）；String；double

**【解析】** switch 是"按值精确匹配"的跳转，底层靠整数/字符常量比较实现，所以 double、float 这类有精度误差的小数和 long 不能用。case 后的值必须是**字面量常量**且不能重复。▶ 关联：枚举类型在第 13 章详解。

---

**3.** `Random r = new Random(); r.nextInt(10);` 生成的随机整数范围是 ______；要生成 [5, 15] 闭区间的随机整数，公式是 `r.nextInt(______) + ______`。

**【答案】** [0, 10)，即 0~9（含 0 不含 10）；`15 - 5 + 1`（即 11）；`5`

**【解析】** 通用区间公式：`nextInt(max - min + 1) + min`。`max - min + 1` 决定"有多少个整数"（5 到 15 共 11 个数），`+ min` 把起点从 0 平移到 5。本章编程题"彩票号码生成"会在第 6 章用数组把这个公式升级为"不重复随机号码"。

---

**4.** 在循环中：______ 立即结束整个当前循环；______ 只跳过本次循环剩余语句、直接进入下一次判断；______ 结束的是整个方法。

**【答案】** break；continue；return

**【解析】** break 是"剩余的全部放弃"；continue 是"丢掉当前这一次、继续下一次"；return 是直接结束整个方法、后面代码都不执行。注意 continue 只能用在循环里；break 还能用在 switch 中。▶ 关联：return 在第 4 章方法中首次出现，void 方法的 return 不带值。

---

### 二、选择题

**1.** 阅读代码，输出结果是（　）

```java
double money = 200;
if (money >= 300); {
    System.out.println("享受8折优惠");
}
System.out.println("结账完成");
```

A. 什么都不输出　B. 结账完成　C. 享受8折优惠 / 结账完成　D. 编译报错

**【答案】** C

**【解析】** `if (条件);` 括号后多了一个分号，这个分号代表 if 控制的是一条**空语句**，后面的 `{ }` 变成与 if 无关的普通代码块，无条件执行——200 元不够 300 也照样打印"享受8折"。这是本章最高频笔误；for 循环后写分号同理（循环体变空语句）。

---

**2.** 下列 switch 代码的输出是（　）

```java
int level = 2;
switch (level) {
    case 1: System.out.print("青铜");
    case 2: System.out.print("白银");
    case 3: System.out.print("黄金"); break;
    default: System.out.print("未定级");
}
```

A. 白银　B. 白银黄金　C. 白银黄金未定级　D. 青铜白银黄金

**【答案】** B

**【解析】** 匹配 case 2 打印"白银"，但 case 2 后没有 break，发生**穿透**：继续执行 case 3 打印"黄金"，遇到 break 才跳出。忘写 break 是 bug；但多个 case 摞在一起共用一个执行体（如"三月/四月/五月都打印春季"）则是主动利用穿透简化代码。

---

**3.** 下列代码输出几行 "出货完成"？（　）

```java
for (int i = 1; i <= 3; i++); {
    System.out.println("出货完成");
}
```

A. 0　B. 1　C. 3　D. 编译报错

**【答案】** B

**【解析】** 括号后的分号让 for 的循环体成了空语句，循环空转 3 次，后面大括号里的打印脱离循环、只执行 1 次。对比记忆：`if(...) ;` 让代码块无条件执行一次；`for(...);` 让代码块只执行一次。

---

**4.** 关于三种循环，下列说法**错误**的是（　）

A. do-while 的循环体至少执行一次
B. for 和 while 都是先判断条件、为 true 才执行循环体
C. while 循环中控制循环的变量，循环结束后仍可继续使用
D. 已知循环次数时优先使用 while

**【答案】** D

**【解析】** 选用规范正好相反：**已知次数用 for，次数不确定用 while**（如等用户反复输入直到正确、数值反复翻倍直到达标）。for 的计数器定义在 `( )` 中，循环结束即释放；while 的变量定义在循环外，循环后还能用。do-while 先执行后判断，适合"先弹一次菜单再等选择"的交互。

---

**5.** 下列代码的输出是（　）

```java
for (int day = 1; day <= 6; day++) {
    if (day % 3 == 0) {
        continue;
    }
    System.out.print("第" + day + "天有退单 ");
}
```

A. 第1天有退单 第2天有退单 第4天有退单 第5天有退单
B. 第3天有退单 第6天有退单
C. 第1~6天全部输出
D. 什么都不输出

**【答案】** A

**【解析】** `day % 3 == 0`（第 3、6 天）时 continue 跳过打印，其余四天打印。continue 跳过的是"本次循环体剩余语句"，迭代语句 `day++` 照常执行，不会死循环。若换成 break，则第一天就直接结束整个循环。

---

### 三、判断题

**1.** Java 的 if 条件里可以像 C 语言那样写 `if (1)` 表示真、`if (0)` 表示假。（　）

**【答案】** ✗ 错误

**【解析】** if 的 `( )` 中必须是 **boolean 类型**结果（true/false），`if (1)` 编译报错。这是 Java 强类型的体现——布尔就是布尔，不能拿数字顶替。

---

**2.** 嵌套循环中，内层循环里的 break 默认只能结束内层循环；想直接结束外层循环，必须给外层循环加标号（label）。（　）

**【答案】** ✓ 正确

**【解析】** 笔记中的 `outer:` 标号写法：`break outer;` 直接跳出外层循环。默认 break/continue 只作用于"当前所在的那一层循环"。开发中三层以上嵌套极少用，标号也属少见写法，但读旧代码时要认识。

---

**3.** do-while 循环如果条件一开始就为 false，循环体一次也不会执行。（　）

**【答案】** ✗ 错误

**【解析】** do-while **先执行循环体，后判断条件**，所以无论条件真假，循环体至少执行一次。语法末尾的分号 `while(条件);` 不能忘。

---

**4.** for 循环 `( )` 中定义的计数器变量，在整个循环结束后就从内存释放，循环外不能再访问。（　）

**【答案】** ✓ 正确

**【解析】** 作用域问题：`for (int i = 0; ...)` 的 i 属于整个 for 循环，循环结束即释放；循环体 `{ }` 内定义的变量生命周期更短——每轮结束就释放，下一轮重新定义。这与第 2 章变量作用域、第 4 章栈内存弹栈回收局部变量是同一原理。

---

### 四、简答题

**1.** 连续写多个独立 if 和使用 if-else if-else 有什么区别？开发中如何选择？

**【答案】**
- 连续多个 if：每个 if 都独立判断一遍，条件互不影响，可能同时执行多个分支体；
- if-else if-else：从上到下匹配，只要命中一个 true，后面条件**不再判断**，整个结构只执行一个分支。

**【解析】** "互斥区间"类需求（如顾客消费额分档：满 500 送礼品、满 300 送券、满 100 送积分……一笔消费只能享一档）必须用 else if 链；而"多条件各管各的"场景（如会员打折、活动减价、优惠券可叠加）才用多个独立 if。用 Debug 单步 F8 可以直观看到 else if 命中后直接跳过剩余判断。

---

**2.** 简述使用 Debug 断点调试的完整步骤，以及 F8、F7、F9 的作用和三个观察窗口。

**【答案】**
1. **加断点**：代码行号后单击出现红点（想看循环就加在循环体第一行），再点一次取消；
2. **Debug 方式运行**：右键 `Debug '类名.main()'` 或点虫子图标，程序运行到断点处停下；
3. **控制执行**：F8 步过（执行一行，不进入方法内部）、F7 步入（进入本行调用的方法）、Shift+F8 步出（跳出当前方法）、F9 恢复（跑到下一个断点）、Ctrl+F2 结束；
4. **观察**：Variables 看变量实时变化、Frames 看方法调用链、Console 看输出。

**【解析】** Debug 的价值在于把"自己以为的执行流程"和"真实执行流程"逐行对比：循环转了几圈、变量每轮怎么变、方法按什么顺序调用，一目了然。▶ 关联：Frames 窗口的方法调用链就是第 4 章栈内存"压栈/弹栈"的可视化；第 21 章多线程还会用 Frames 观察多个线程的栈。

---

### 五、代码阅读题

**1.** 阅读嵌套循环，写出控制台输出。

```java
for (int floor = 1; floor <= 3; floor++) {
    for (int room = 1; room <= floor; room++) {
        System.out.print("■");
    }
    System.out.println(" 第" + floor + "层");
}
```

**【答案】**

```
■ 第1层
■■ 第2层
■■■ 第3层
```

**【解析】** 核心规律：**外循环控制行数（楼层），内循环控制每行个数（房间）；外循环走 1 次，内循环跑完整 1 圈**。关键在内层条件 `room <= floor`——第 floor 层就打印 floor 个方块。内层用 `print` 不换行，内圈结束后 `println` 换行并输出楼层文字。

---

**2.** 阅读代码，写出输出结果。

```java
outer:
for (int warehouse = 1; warehouse <= 3; warehouse++) {
    for (int box = 1; box <= 3; box++) {
        if (box == 2) {
            break outer;
        }
        System.out.println("仓库" + warehouse + "-货箱" + box);
    }
}
System.out.println("盘点结束");
```

**【答案】**

```
仓库1-货箱1
盘点结束
```

**【解析】** warehouse=1、box=1 时不满足条件，打印；box=2 时执行 `break outer`——标号 break 直接结束**外层**循环，不再有仓库 2、3。若去掉 outer（只写 break），则只结束内层，会继续打印仓库2-货箱1、仓库3-货箱1，最后才"盘点结束"。

---

**3.** 阅读代码，写出输出结果，并说明理由。

```java
int stock = 5;
do {
    System.out.println("启动自检，剩余库存：" + stock);
    stock++;
} while (stock <= 5);
System.out.println("自检结束，stock = " + stock);
```

**【答案】**

```
启动自检，剩余库存：5
自检结束，stock = 6
```

**【解析】** do-while 先执行循环体：打印一次，stock 变成 6；然后才判断 `6 <= 5` 为 false，循环结束。即使初始条件不成立，循环体也已执行一次——这是 do-while 与 while 的本质区别，所以它特别适合"菜单先显示一次再等用户选择"。

---

### 六、编程题（共 5 题，由易到难）

#### 编程题 1（基础 · if-else 分支）：路边停车场计时收费

**需求**：键盘录入车辆停车时长（分钟，整数）。收费规则：
- 30 分钟以内（含 30）：免费；
- 超过 30 分钟：第 1 小时收 5 元，之后每满 1 小时加收 2 元，**不足 1 小时按 1 小时计算**。

输出应付金额。

**参考代码**：

```java
import java.util.Scanner;

public class ParkingFee {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入停车时长（分钟）：");
        int minutes = sc.nextInt();

        if (minutes <= 30) {
            System.out.println("停车30分钟内免费，金额：0 元");
        } else {
            // 分钟换算小时并"向上取整"：(分钟 + 59) / 60 是整数除法实现向上取整的技巧
            int hours = (minutes + 59) / 60;
            int fee = 5 + (hours - 1) * 2;   // 首小时5元，超出的 (hours-1) 小时每小时2元
            System.out.println("停车 " + minutes + " 分钟，合计 " + hours + " 小时，金额：" + fee + " 元");
        }
    }
}
```

**思路讲解**：
1. 录入分钟数后先做免费判断（单分支 if）；
2. 难点是"不足 1 小时按 1 小时算"——即小时数要**向上取整**。整数除法中 `(a + b - 1) / b` 是标准向上取整写法，所以 `(minutes + 59) / 60`：61 分钟得 2，120 分钟得 2，125 分钟得 3；
3. 费用 = 首小时 5 元 + 剩余 `(hours-1)` 个小时 × 2 元。

**运行结果示例**：

```
输入 20  → 停车30分钟内免费，金额：0 元
输入 60  → 合计 1 小时，金额：5 元
输入 90  → 合计 2 小时，金额：7 元
输入 125 → 合计 3 小时，金额：9 元
```

▶ 关联：向上取整技巧用的是第 3 章整数除法"舍去小数"特性的反向利用；第 14 章学过 Math 类后也可以用 `Math.ceil()` 实现。

---

#### 编程题 2（基础 · Random + 循环 + 计数器）：快递柜取件码核验

**需求**：系统为一个 3 位取件码**随机生成**每一位数字（0~9）。用户键盘逐位输入猜测，程序逐位比对，统计"数字和位置都正确"的位数；3 位全对输出"取件成功"，否则提示正确位数，最后揭晓真实取件码。

**参考代码**：

```java
import java.util.Random;
import java.util.Scanner;

public class LockerCode {
    public static void main(String[] args) {
        Random r = new Random();
        Scanner sc = new Scanner(System.in);

        int rightCount = 0;
        String code = "";   // 暂存真实取件码，结束后揭晓

        for (int i = 1; i <= 3; i++) {
            int secret = r.nextInt(10);        // 0~9
            code += secret;
            System.out.println("请输入第 " + i + " 位数字（0~9）：");
            int input = sc.nextInt();
            if (input == secret) {
                rightCount++;                  // 位置和数字都对，计数+1
            }
        }

        System.out.println("真实取件码是：" + code);
        if (rightCount == 3) {
            System.out.println("3位全部正确，取件成功！");
        } else {
            System.out.println("只有 " + rightCount + " 位正确，请重新取号。");
        }
    }
}
```

**思路讲解**：
1. 循环 3 次，每轮生成一个 `nextInt(10)` 的数字、录入一个猜测、比对一次——**生成、录入、判断在同一轮内完成**，不需要数组（数组第 6 章才学）；
2. `rightCount` 是计数器套路：循环外初始化为 0，满足条件 `++`；
3. 真实码用字符串拼接暂存，比对过程不公布，结束才揭晓。

**运行结果示例**（真实码随机，每次不同）：

```
请输入第 1 位数字：7
请输入第 2 位数字：3
请输入第 3 位数字：9
真实取件码是：709
只有 2 位正确，请重新取号。
```

▶ 关联：计数器套路与第 6 章"统计符合条件元素个数"同源；升级为"6 位不重复号码"需要数组查重，见第 6 章编程题。

---

#### 编程题 3（中等 · 循环综合：求和/最值/计数）：奶茶店一周销量分析

**需求**：店长录入本店连续 7 天每天的销量（杯数，非负整数）。程序输出：
- 7 天总销量和日均销量；
- 销量最高的那天是星期几、卖了多少杯；
- 销量低于 50 杯的"冷清天"有几天。

**参考代码**：

```java
import java.util.Scanner;

public class MilkTeaSales {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int total = 0;        // 总销量（求和变量）
        int coldDays = 0;     // 冷清天计数
        int maxSales = -1;    // 最高销量（销量非负，-1 保证第一天一定替换）
        int maxDay = 0;       // 最高销量是星期几

        for (int day = 1; day <= 7; day++) {
            System.out.println("请输入周" + dayName(day) + "的销量（杯）：");
            int sales = sc.nextInt();

            total += sales;                       // 累加
            if (sales < 50) {
                coldDays++;                       // 冷清天计数
            }
            if (sales > maxSales) {               // 打擂台：更大就替换
                maxSales = sales;
                maxDay = day;
            }
        }

        System.out.println("7天总销量：" + total + " 杯");
        System.out.println("日均销量：" + total / 7.0 + " 杯");
        System.out.println("销量最高：周" + dayName(maxDay) + "，" + maxSales + " 杯");
        System.out.println("冷清天（低于50杯）共：" + coldDays + " 天");
    }

    // 把数字星期转成中文（方法封装见第4章）
    public static String dayName(int day) {
        switch (day) {
            case 1: return "一";
            case 2: return "二";
            case 3: return "三";
            case 4: return "四";
            case 5: return "五";
            case 6: return "六";
            default: return "日";
        }
    }
}
```

**思路讲解**：
1. 本题把本章三个套路合在一道题里：`total += sales` 求和、`coldDays++` 计数、`if (sales > maxSales)` 打擂台求最值；
2. maxSales 初始化为 -1 而不是 0：销量可能全是 0（停业一周），用 -1 保证第一天数据必然替换参照值——这就是第 6 章"参照值取第一个元素"思想的变量版；
3. `total / 7.0` 除以小数触发浮点除法，保留日均小数（第 3 章类型转换）；
4. switch 配合 return 把星期数字转中文，既复习 switch，又用了第 4 章的方法封装。

**运行结果示例**（依次录入 62、45、80、30、55、120、90）：

```
7天总销量：482 杯
日均销量：68.857... 杯
销量最高：周六，120 杯
冷清天（低于50杯）共：2 天
```

▶ 关联：这三个套路在第 6 章换成"遍历数组"版本（数据先存后算）；第 17 章 Map 集合还会做"按口味分组统计销量"。

---

#### 编程题 4（中等偏难 · do-while/while + switch + 死循环）：自助借还书机菜单

**需求**：图书馆借还机循环显示菜单：
- 1. 查询已借数量　2. 借书（数量+1，上限 5 本）　3. 还书（数量-1，不能为负）　0. 退出
- 输入 0 结束程序；其他非法数字提示"指令有误"。

**参考代码**：

```java
import java.util.Scanner;

public class LibraryMachine {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int borrowed = 2;   // 初始已借 2 本

        while (true) {                          // 菜单类程序：死循环 + 退出出口
            System.out.println("====== 自助借还书机 ======");
            System.out.println("1.查询  2.借书  3.还书  0.退出");
            int cmd = sc.nextInt();

            switch (cmd) {
                case 1:
                    System.out.println("您当前已借 " + borrowed + " 本");
                    break;
                case 2:
                    if (borrowed >= 5) {
                        System.out.println("最多借5本，先还几本吧！");
                    } else {
                        borrowed++;
                        System.out.println("借书成功，当前已借 " + borrowed + " 本");
                    }
                    break;
                case 3:
                    if (borrowed <= 0) {
                        System.out.println("您没有待还的书！");
                    } else {
                        borrowed--;
                        System.out.println("还书成功，当前已借 " + borrowed + " 本");
                    }
                    break;
                case 0:
                    System.out.println("欢迎下次使用！");
                    return;                     // 直接结束 main 方法（break 只能跳出 switch）
                default:
                    System.out.println("指令有误，请重新选择！");
            }
        }
    }
}
```

**思路讲解**：
1. 菜单程序的标准骨架是 `while(true)` + switch：反复显示菜单等指令，唯一出口是退出项；
2. 借书、还书都有**边界条件**：借满 5 本不能再借、0 本时不能再还——分支里先判断边界再改变量；
3. 退出用 `return` 而不是 break：break 在这里只能跳出 switch，跳完还在 while 里继续转圈；return 直接结束 main 方法。也可以用布尔标志位控制循环条件退出。

**运行结果示例**：

```
====== 自助借还书机 ======
1.查询  2.借书  3.还书  0.退出
2
借书成功，当前已借 3 本
...（菜单重复显示）
3
还书成功，当前已借 2 本
0
欢迎下次使用！
```

▶ 关联：while(true)+退出条件 的交互模式在第 21 章"生产者消费者"中演变为 `while(true) + wait/notify`；switch 的多值分发思想在读源码时很常见。

---

#### 编程题 5（较难 · 嵌套循环综合）：电影院座位图打印

**需求**：放映厅共 5 排，每排 6 个座位。打印座位图：
- 普通座位用 `○`，第 3 排是贵宾区用 `●`；
- 每排第 3 个座位后留出走廊空位（即座位 3 和 4 之间多空两格）；
- 每行开头显示"第x排："；
- 最后统计并输出全场总座位数。

**参考代码**：

```java
public class CinemaSeats {
    public static void main(String[] args) {
        int total = 0;   // 总座位计数器

        for (int row = 1; row <= 5; row++) {          // 外层：排
            System.out.print("第" + row + "排：");
            for (int seat = 1; seat <= 6; seat++) {   // 内层：每排的座位
                if (row == 3) {
                    System.out.print("● ");           // 贵宾区
                } else {
                    System.out.print("○ ");           // 普通座
                }
                if (seat == 3) {
                    System.out.print("  ");           // 第3座后是走廊，多空两格
                }
                total++;                              // 每打印一个座位计数+1
            }
            System.out.println();                     // 一排结束换行
        }

        System.out.println("全场共 " + total + " 个座位");
    }
}
```

**思路讲解**：
1. 嵌套循环铁律：**外循环控制行（排），内循环控制列（座）；外循环走 1 次，内循环完整跑 1 圈**；
2. 内层循环里做两件事：按排数判断座位符号（`row == 3` 是贵宾区）、按座位号判断走廊（`seat == 3` 后补空格）；
3. 内圈用 `print` 不换行，内圈结束后 `println()` 换排；
4. 总座位数其实就是 5×6=30，用计数器在内层 `++` 是为了练习"嵌套循环中计数"的通用写法（真实场景座位可能不规则）。

**运行结果**：

```
第1排：○ ○ ○   ○ ○ ○
第2排：○ ○ ○   ○ ○ ○
第3排：● ● ●   ● ● ●
第4排：○ ○ ○   ○ ○ ○
第5排：○ ○ ○   ○ ○ ○
全场共 30 个座位
```

▶ 关联：嵌套循环是第 15 章冒泡/选择排序（外层轮次、内层相邻比较）的直接基础；计数器思想在第 6 章数组遍历中反复使用。

---

### 本章自测清单

- [ ] 能不看书写出 if 三种形态、switch 语法和 for/while/do-while 三种循环
- [ ] 能指出 `if(条件);` 和 `for(...);` 两个分号陷阱的后果
- [ ] 能解释 switch 穿透现象，并能主动利用穿透合并分支
- [ ] 能手推嵌套循环的输出（外控行、内控列，外走 1 次内跑 1 圈）
- [ ] 能说清 break / continue / return 三者区别和标号用法
- [ ] 能默写 Random 区间公式 `nextInt(max-min+1)+min`
- [ ] 会加断点、用 F8/F7/F9 调试，会看 Variables 和 Frames 窗口

---

<div style="page-break-after: always;"></div>

## 第六章 数组 · 习题精讲

> 做题前先抓住本章主线：**数组是存同种类型数据的容器（引用类型、长度固定）→ 静态/动态两种初始化 → 索引访问与遍历 → 默认值规则 → 堆/栈/方法区内存图 → 经典操作（求和、最值、交换、反转）**。
>
> ▶ 关联：数组遍历用的是第 5 章的 for 循环；数组是引用类型，它的内存图（栈里存地址、堆里存数据）是第 7 章对象内存图的预演；越界异常和空指针异常在第 16 章异常体系中系统学习；长度可变的"升级版数组"就是第 10 章的 ArrayList。

---

### 一、填空题

**1.** 数组是一种存储 ______ 类型数据的容器，它属于 ______ 数据类型，长度 ______（可以/不可以）改变；数组变量中存储的是数组对象在 ______ 内存中的地址。

**【答案】** 相同（同种）；引用；不可以；堆

**【解析】** "什么类型的数组只能存什么类型的数据"；`new` 出来的数组对象在堆中占一块连续空间，变量里存的是地址（如 `[I@b4c966a`，`[I` 表示 int 数组），所以数组是引用类型。长度一旦确定不可改变——想动态增删要用 ArrayList（第 10 章）。

---

**2.** 数组的索引从 ______ 开始，最大索引是 ______；访问超出范围的索引会抛出 ______ 异常。

**【答案】** 0；`数组名.length - 1`；`ArrayIndexOutOfBoundsException`（数组索引越界异常）

**【解析】** 长度为 3 的数组合法索引只有 0、1、2，访问 arr[3] 立即越界报错。遍历标准写法 `for (int i = 0; i < arr.length; i++)` 正好覆盖 0 到 length-1，不会越界。▶ 关联：该异常在第 16 章归入 RuntimeException 运行时异常。

---

**3.** 动态初始化时元素的默认值：byte/short/int/long 为 ______，float/double 为 ______，char 为 ______，boolean 为 ______，String 等引用类型为 ______。

**【答案】** 0；0.0；空字符（`
`，编码值 0，不是空格）；false；null

**【解析】** 默认值只出现在"动态初始化"（只给长度不给元素）时；静态初始化直接给元素。char 的默认值最容易错——是空字符而不是空格 `' '`。null 表示引用类型变量不指向任何对象。

---

**4.** 两个变量指向同一个数组时，通过其中一个变量修改元素，另一个变量看到的结果 ______（会/不会）改变，因为它们存的是同一个 ______。

**【答案】** 会；地址

**【解析】** `int[] arr2 = arr1;` 复制的是地址，栈里两个变量指向堆中同一个数组对象，"一改全改"。这是引用类型与基本类型最本质的区别（基本类型变量里直接存值，互不影响）。

---

### 二、选择题

**1.** 下列代码运行结果是（　）

```java
int[] lockers = new int[3];
lockers[3] = 8;
System.out.println(lockers[3]);
```

A. 8　B. 0　C. 抛出 ArrayIndexOutOfBoundsException　D. 抛出 NullPointerException

**【答案】** C

**【解析】** 长度为 3 的数组合法索引是 0、1、2，`lockers[3]` 越界，抛索引越界异常。空指针异常（D）是引用为 null 时访问元素/属性才报的，注意区分这两种数组最常见的异常。

---

**2.** 下列代码的输出是（　）

```java
String[] couriers = new String[2];
System.out.println(couriers[0]);
char[] tags = new char[2];
System.out.println((int) tags[0]);
```

A. null　0　B. 空白行　0　C. null　空格的编码 32　D. 编译报错

**【答案】** A

**【解析】** String 是引用类型，动态初始化默认值为 null（打印 null，不是空字符串）；char 默认值是空字符，强转 int 后输出编码值 0（空格的编码是 32，注意区分）。

---

**3.** 下列代码运行后，`shelfA[1]` 的值是（　）

```java
int[] shelfA = {101, 102, 103};
int[] shelfB = shelfA;
shelfB[1] = 199;
System.out.println(shelfA[1]);
```

A. 102　B. 199　C. 编译报错　D. 运行报错

**【答案】** B

**【解析】** shelfB 拿到的是 shelfA 的地址，两个变量操作堆中同一个数组，通过 shelfB 改的就是 shelfA 看到的。打印 shelfA 和 shelfB 两个地址也完全相同。▶ 关联：第 7 章"两个引用指向同一个对象"、方法传参时引用类型"改内容生效"都源于此。

---

**4.** 下列数组定义，**编译会报错**的是（　）

```java
// ①
int[] a1 = {1, 2, 3};
// ②
int[] a2 = new int[]{1, 2, 3};
// ③
int[] a3;
a3 = {1, 2, 3};
// ④
int a4[] = {1, 2, 3};
```

A. ①　B. ②　C. ③　D. ④

**【答案】** C

**【解析】** 静态初始化的**简化格式** `{元素...}` 只能在定义数组的同一行使用；拆成两行必须写完整格式 `a3 = new int[]{1, 2, 3};`。②是完整格式正确；④ `int a4[]` 是 C 风格写法，Java 允许但不推荐。

---

**5.** 关于 `System.out.println(arr)` 直接打印数组变量，下列说法正确的是（　）

A. 打印数组所有元素　B. 打印数组长度　C. 打印数组的地址（如 [I@b4c966a）　D. 编译报错

**【答案】** C

**【解析】** 数组变量里存的是地址，直接打印看到 `[I@b4c966a`：`[I` 表示 int 类型一维数组，`@` 后是十六进制哈希值。想打印内容要么手写 for 遍历，要么用 `Arrays.toString(arr)`（需 `import java.util.Arrays;`）。▶ 关联：第 10 章打印 ArrayList 能直接看到内容，是因为集合的 toString 被重写过。

---

### 三、判断题

**1.** 数组创建之后，可以通过 `arr.length = 10;` 修改它的长度。（　）

**【答案】** ✗ 错误

**【解析】** 数组长度固定，`length` 是只读属性，不能赋值。需要动态增删元素应使用 ArrayList（第 10 章），它底层靠"数组复制扩容"实现长度可变。

---

**2.** 动态初始化的 int 数组，不赋值直接遍历，每个元素都是 0。（　）

**【答案】** ✓ 正确

**【解析】** 堆中新建数组时系统先给默认值（整数 0），之后再通过 `arr[i] = 值` 覆盖。停车场车位案例正是利用这一点：先 `new int[车位总数]` 占位（0 表示空位），有车停入再改成 1。

---

**3.** 数组变量赋值为 null 后，再访问它的 length 属性会返回 0。（　）

**【答案】** ✗ 错误

**【解析】** null 表示变量不指向任何数组对象，此时访问元素或 length 都会抛 **NullPointerException（空指针异常）**；只有 `System.out.println(arr)` 打印 null 本身不报错。

---

**4.** 双指针交换数组对称位置元素时，循环条件应写 `start < end`；两指针相遇（start == end）时中间元素不用交换。（　）

**【答案】** ✓ 正确

**【解析】** 奇数长度数组正中间的元素交换后位置不变，无需动；偶数长度时 start 和 end 擦肩而过。写成 `start <= end` 虽不出错，但相遇那次自己跟自己换，是无用功。

---

### 四、简答题

**1.** 运行 Java 程序主要涉及 JVM 哪三块内存区域？分别说说 `int a = 20;` 和 `int[] arr = new int[3];` 的执行原理。

**【答案】**
- **方法区**：编译后的 .class 字节码先加载到这里；
- **栈**：方法运行时进栈，方法中的局部变量在栈中；
- **堆**：`new` 出来的对象在这里开辟连续空间并产生地址。

`int a = 20;`：a 是基本类型变量，在栈中直接存储值 20；
`int[] arr = new int[3];`：`new int[3]` 在堆中开辟长度为 3 的数组（默认值全 0）并产生地址；arr 变量在栈中，存的是该数组的**地址值**，通过地址间接访问堆中数据。

**【解析】** 一句话记忆：**基本类型栈里存值，引用类型栈里存地址、堆里存对象**。这是整个 Java 内存模型的地基——第 7 章对象、第 11 章 static、第 12 章多态的内存图全部建立在这套规则上。用 Debug 的 Frames（栈帧）和 Variables 窗口可以边运行边验证。

---

**2.** 求数组最大值时，为什么建议把参照变量 max 初始化为 `arr[0]`，而不是初始化为 0？

**【答案】** 初始化 0 隐含假设了"数组里一定有比 0 大的数"。如果数组存的是冬季气温（如 {-5, -2, -9}）或误差值这类可能全负的数据，max 永远停在 0，结果错误。初始化为 arr[0] 表示"先假定第一个元素最大"，再从第二个元素起逐一比较替换，对任意数据都成立。

**【解析】** 算法步骤：① max = arr[0]，同时记下索引 0；② 从 i=1 遍历，`if (arr[i] > max) { max = arr[i]; }`；③ 循环结束 max 即最大值。最小值同理。本章编程题"体检队伍换位"还要额外记住最大值的**索引**，才能交换两个人的位置。▶ 关联：第 15 章选择排序正是"每轮找最值索引再交换"，思路同源。

---

### 五、代码阅读题

**1.** 写出控制台输出。

```java
int[] parcels = {10, 20, 30};
parcels[1] = 50;
System.out.println(parcels[0] + parcels[1] + parcels[2]);
System.out.println(parcels.length);
```

**【答案】**

```
90
3
```

**【解析】** `parcels[1] = 50` 通过索引把堆中第二个元素从 20 改成 50，数组变成 {10, 50, 30}，求和 90。修改元素不影响数组长度，length 仍是 3——长度固定，内容可变。

---

**2.** 写出控制台输出，并说明原因。

```java
int[] shelfA = {5, 6, 7};
int[] shelfB = shelfA;
shelfB[0] = 9;
System.out.println(shelfA[0]);
System.out.println(shelfA[1]);
```

**【答案】**

```
9
6
```

**【解析】** `shelfB = shelfA` 复制的是地址，两个库管账号操作同一个货架数组。`shelfB[0] = 9` 改的是共享的那份数据，所以 shelfA[0] 同步变成 9；shelfA[1] 没动过，仍是 6。若之后写 `shelfB = null;`，只是 shelfB 不再指向数组，shelfA 仍正常使用。

---

**3.** 体检队伍按编号 `{5, 6, 7, 8, 9}` 排队，现要用双指针把队伍顺序对调（变成 9~5）。写出每轮交换后的队伍和最终结果。

**【答案】**

- 初始：start=0，end=4；交换编号 5 和 9 → `{9, 6, 7, 8, 5}`，start=1，end=3
- 第二轮：交换编号 6 和 8 → `{9, 8, 7, 6, 5}`，start=2，end=2
- 此时 `start < end` 不成立（2 < 2 为 false），循环结束。中间的 7 位置不变。

最终结果：`{9, 8, 7, 6, 5}`

**【解析】** 奇数长度交换 (长度-1)/2 = 2 次；偶数长度（如 6 个元素）交换 3 次后 start=3、end=2 结束。每次交换都是 temp 三行：先存左边、右边覆盖左边、temp 倒给右边——少了 temp 暂存，左边原值会被永久覆盖。

---

### 六、编程题（共 5 题，由易到难）

#### 编程题 1（基础 · 静态初始化 + 遍历求和/最值）：一周气温分析

**需求**：气象站记录了本周 7 天的最高气温（摄氏度）：`{28, 31, 27, 33, 30, 26, 29}`。请计算并输出：
- 本周平均气温（保留一位小数）；
- 最高气温和最低气温；
- 最大温差（最高减最低）。

**参考代码**：

```java
public class WeatherAnalysis {
    public static void main(String[] args) {
        int[] temps = {28, 31, 27, 33, 30, 26, 29};   // 数据已知 → 静态初始化

        int sum = 0;
        int max = temps[0];   // 参照值取第一个元素
        int min = temps[0];

        for (int i = 0; i < temps.length; i++) {
            sum += temps[i];                       // 求和
            if (temps[i] > max) {
                max = temps[i];                    // 打擂台求最大
            }
            if (temps[i] < min) {
                min = temps[i];                    // 打擂台求最小
            }
        }

        double avg = sum * 1.0 / temps.length;     // *1.0 触发浮点除法
        System.out.println("平均气温：" + avg + " ℃");
        System.out.println("最高气温：" + max + " ℃");
        System.out.println("最低气温：" + min + " ℃");
        System.out.println("最大温差：" + (max - min) + " ℃");
    }
}
```

**思路讲解**：
1. 数据已知且固定，用静态初始化；
2. 一次遍历同时完成求和、求最大、求最小——sum 累加，max/min 用"打擂台"比较替换；
3. 平均气温 `sum * 1.0 / 7`：先乘 1.0 把 int 提升为 double，否则整数除法会丢掉小数（第 3 章类型转换）；
4. 温差就是 max - min，不用再遍历。

**运行结果**：

```
平均气温：29.142857... ℃
最高气温：33 ℃
最低气温：26 ℃
最大温差：7 ℃
```

▶ 关联：求最值时"参照值取 arr[0]"的原因见简答题 2；同样的遍历套路在第 10 章 ArrayList 上原样可用。

---

#### 编程题 2（基础 · 动态初始化 + 默认值 + 统计）：停车场车位管理

**需求**：路边停车场共 8 个车位，用数组记录占用情况：`0` 表示空位、`1` 表示已占用。
- 程序开始时车位全空（利用默认值）；
- 模拟车辆停入 3、5、7 号车位（注意：车位编号给用户看的是 1~8，数组索引是 0~7）；
- 输出当前空车位数量和已占用车位数量；
- 尝试查询 9 号车位状态时，程序要能提示"车位编号不存在"而不是崩溃。

**参考代码**：

```java
public class ParkingLot {
    public static void main(String[] args) {
        int[] spots = new int[8];   // 动态初始化：默认全 0（空位）

        // 车辆停入"3、5、7号车位"：用户编号 - 1 = 数组索引
        spots[3 - 1] = 1;
        spots[5 - 1] = 1;
        spots[7 - 1] = 1;

        int empty = 0;
        int used = 0;
        for (int i = 0; i < spots.length; i++) {
            if (spots[i] == 0) {
                empty++;
            } else {
                used++;
            }
        }
        System.out.println("空车位：" + empty + " 个，已占用：" + used + " 个");

        // 安全查询：先判断编号范围，避免索引越界异常
        int queryNo = 9;
        if (queryNo < 1 || queryNo > spots.length) {
            System.out.println("车位编号 " + queryNo + " 不存在（车场共 " + spots.length + " 个车位）");
        } else {
            System.out.println(queryNo + " 号车位状态：" + (spots[queryNo - 1] == 0 ? "空闲" : "占用"));
        }
    }
}
```

**思路讲解**：
1. 车位状态后期变化、初始全空，用动态初始化最自然——默认值 0 正好表示空位；
2. "第 n 号车位"与"索引 n-1"的换算是数组应用题最常见的坑（和第 5 章 Random 点名同理）；
3. 统计仍是计数器套路：遍历数组，按值分别计数；
4. 查询前先校验编号范围 `1 ~ length`，把可能发生的 ArrayIndexOutOfBoundsException 提前拦截——这是"防御性编程"的入门，第 16 章会用 try-catch 正式处理异常。

**运行结果**：

```
空车位：5 个，已占用：3 个
车位编号 9 不存在（车场共 8 个车位）
```

---

#### 编程题 3（中等 · 数组 + Random + 遍历查重）：彩票机选号码

**需求**：模拟彩票机选：从 1~33 中随机产生 **6 个不重复**的红球号码存入数组并输出。
要求：每生成一个号码，先和数组中**已有的**号码逐一比对，重复就重新生成，直到 6 个号码全部不重复。

**参考代码**：

```java
import java.util.Random;

public class LotteryMachine {
    public static void main(String[] args) {
        Random r = new Random();
        int[] balls = new int[6];     // 存 6 个红球号码
        int count = 0;                // 已成功生成的号码个数（也是下一个存放位置）

        while (count < 6) {
            int num = r.nextInt(33) + 1;          // 1~33（区间公式：nextInt(33-1+1)+1）
            boolean exists = false;
            for (int i = 0; i < count; i++) {     // 只和"已有"的号码比
                if (balls[i] == num) {
                    exists = true;                // 重复了
                    break;
                }
            }
            if (!exists) {
                balls[count] = num;               // 不重复才存入
                count++;
            }
            // 重复就什么都不做，while 继续转，重新生成
        }

        System.out.print("本期机选号码：");
        for (int i = 0; i < balls.length; i++) {
            System.out.print(balls[i] + " ");
        }
    }
}
```

**思路讲解**：
1. 号码区间用第 5 章公式 `nextInt(max-min+1)+min = nextInt(33)+1`；
2. 查重是数组遍历的经典用法：新号码与 balls[0..count-1] 逐一比较，**注意只比到 count**（后面的位置还没赋值，都是默认值 0）；
3. 用 `while (count < 6)` 而不是 for：因为重复生成时 count 不增长，循环次数事先不确定——正好呼应第 5 章"次数不确定用 while"；
4. `exists` 标志位 + break 是"判断是否存在"的通用写法（第 16 章 contains 方法的底层思路）。

**运行结果示例**（每次随机）：

```
本期机选号码：3 7 12 19 22 31
```

▶ 关联：查重逻辑在第 17 章 HashSet 中被底层自动化（集合元素天然不重复）；现在手写一遍是为了理解它的原理。

---

#### 编程题 4（中等偏难 · 最值索引 + temp 交换）：体检队伍换位

**需求**：10 名学生的身高（厘米）为：`{172, 165, 180, 158, 175, 169, 183, 162, 177, 170}`。
摄影师希望最矮的站队伍最左边（索引 0）、最高的站最右边（索引 9）。请找出最矮和最高的人的位置，用 temp 三行交换把他们换到两端，并输出换位后的队伍。

**参考代码**：

```java
public class HeightLineup {
    public static void main(String[] args) {
        int[] heights = {172, 165, 180, 158, 175, 169, 183, 162, 177, 170};

        int minIndex = 0;
        int maxIndex = 0;
        for (int i = 1; i < heights.length; i++) {
            if (heights[i] < heights[minIndex]) {
                minIndex = i;          // 记住更矮的"位置"
            }
            if (heights[i] > heights[maxIndex]) {
                maxIndex = i;          // 记住更高的"位置"
            }
        }
        System.out.println("最矮身高 " + heights[minIndex] + "，在索引 " + minIndex);
        System.out.println("最高身高 " + heights[maxIndex] + "，在索引 " + maxIndex);

        // 最矮的换到索引 0（temp 三行交换两个数组元素）
        int temp = heights[0];
        heights[0] = heights[minIndex];
        heights[minIndex] = temp;

        // 注意：如果最高的人原来在索引 0，第一次交换后他已经被移到 minIndex 了
        if (maxIndex == 0) {
            maxIndex = minIndex;       // 更新最高者的新位置
        }
        // 最高的换到索引 9
        temp = heights[heights.length - 1];
        heights[heights.length - 1] = heights[maxIndex];
        heights[maxIndex] = temp;

        System.out.print("换位后队伍：");
        for (int i = 0; i < heights.length; i++) {
            System.out.print(heights[i] + " ");
        }
    }
}
```

**思路讲解**：
1. 本题的关键升级：不只记录最值，还要记录最值的**索引**（交换位置必须知道人在哪）；
2. temp 三行交换是本章基本功：`temp = 左; 左 = 右; 右 = temp;`，少了 temp 暂存原值就会被覆盖；
3. 隐藏陷阱：如果最高的人原本就在索引 0，第一次交换会把他移到 minIndex 位置，所以第二次交换前要修正 maxIndex——这种"交换后索引失效"的细节在第 15 章选择排序中同样会遇到；
4. 本题数据中最矮 158 在索引 3、最高 183 在索引 6，不涉及上述陷阱，但代码把边界情况处理完整了。

**运行结果**：

```
最矮身高 158，在索引 3
最高身高 183，在索引 6
换位后队伍：158 165 180 172 175 169 170 162 177 183
```

▶ 关联："找最值索引 → 交换位置"就是第 15 章**选择排序**的核心动作，本题相当于选择排序的一轮预演。

---

#### 编程题 5（较难 · 双指针思想 + char 数组）：回文运单号校验

**需求**：物流系统要校验一个运单号是否为"回文"（正读反读都一样，如 `SF1221FS`、`AB33BA`）。
键盘录入一个运单字符串，把它转成字符数组，用**双指针**（start 从首、end 从尾向中间靠拢）逐对比较字符：
- 全部对称位置相同 → 输出"是回文运单"；
- 任意一对不同 → 输出"不是回文运单"。

**参考代码**：

```java
import java.util.Scanner;

public class PalindromeCheck {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入运单号：");
        String waybill = sc.next();

        char[] chars = waybill.toCharArray();   // 字符串转字符数组
        boolean palindrome = true;

        for (int start = 0, end = chars.length - 1; start < end; start++, end--) {
            if (chars[start] != chars[end]) {
                palindrome = false;   // 发现一对不对称
                break;               // 没必要再比，直接结束
            }
        }

        System.out.println(palindrome ? "是回文运单" : "不是回文运单");
    }
}
```

**思路讲解**：
1. `String.toCharArray()` 把字符串拆成字符数组，就能用索引访问每个字符（字符串本身的方法在第 10 章详解）；
2. 双指针从两端向中间：`start < end` 时比较 `chars[start]` 与 `chars[end]`，然后 start++、end--——和数组反转完全相同的移动方式，只是把"交换"换成"比较"；
3. 发现不对称立即 break 并置标志位为 false，这是"提前退出"的优化；
4. 偶数长度两指针擦肩、奇数长度中间字符不比，循环次数约为长度的一半。

**运行结果**：

```
输入 SF1221FS → 是回文运单
输入 SF1234FS → 不是回文运单
```

▶ 关联：双指针"首尾相向"是高频算法思想，第 15 章二分查找（left/right 相向夹逼）与本题同源；字符数组与字符串的转换在第 10 章 String 部分还会深入。

---

### 本章自测清单

- [ ] 能默写静态初始化（完整/简化）和动态初始化两种格式，知道简化格式不能拆行
- [ ] 能背出五类默认值，尤其 char 是空字符（编码 0）、引用类型是 null
- [ ] 能手画数组内存图：栈中变量存地址、堆中连续空间存元素
- [ ] 能解释"两个引用指向同一数组一改全改"和 null 空指针
- [ ] 能独立写出遍历求和、求最值（参照 arr[0]）、记最值索引、统计个数
- [ ] 能手写 temp 三行交换和双指针反转/对称比较，说清 `start < end` 的原因
- [ ] 能区分 ArrayIndexOutOfBoundsException 与 NullPointerException 的触发场景
- [ ] 能完成"用户编号 n 与索引 n-1"的换算，并在访问前做范围校验

---

<div style="page-break-after: always;"></div>

## 第7章 面向对象基础·习题精讲

> 做题方法：先独立作答全部题目，再对照【答案】与【解析】。解析中标注"▶ 关联"的地方，
> 说明该考点与其他章节的知识衔接，建议顺着关联点回顾，形成知识网络。
> 本篇全部业务场景均为原创设计（图书、银行账户、健身会员卡、书架、订单、宠物医院），考查的知识点不变。

---

### 一、填空题

**1.** 类是对一类具有相同属性和行为的事物的抽象描述，可以理解为"模板"或"蓝图"；对象是类的具体实例，通过 ______ 关键字创建。

**【答案】** `new`

**【解析】** 固定格式：`类名 对象名 = new 类名();`。写程序的顺序是"先设计类，再用类 new 对象"。
Scanner、Random 是 JDK 写好的类，直接 new 来用；业务中的实体类需要自己设计。
▶ 关联：第 9 章多态中 `父类引用 = new 子类对象()` 仍是这个格式的延伸；第 16 章集合中
`new ArrayList<>()` 创建的也是对象。

---

**2.** 在类中定义成员方法时，格式和之前定义方法完全一样，区别只是必须去掉 ______ 关键字，因为成员方法属于对象。

**【答案】** `static`

**【解析】** 测试类里写的方法都带 static（因为 main 是静态方法，静态只能直接调静态）；
而类中的成员方法描述对象的行为，必须去掉 static，通过 `对象名.方法名()` 调用。
属性（成员变量）描述名词特征，行为（成员方法）描述动词动作。
▶ 关联：static 方法的规则见本章 static 一节；第 11 章会深入 static 的加载时机与静态代码块。

---

**3.** this 代表 ______ 的引用（地址）：哪个对象调用了当前方法，this 就指向哪个对象。this 只能在成员方法、构造方法、代码块中使用，绝对不能在 ______ 方法中使用。

**【答案】** 当前类对象（当前对象）；static（静态）

**【解析】** 当局部变量（形参）与成员变量重名时，Java 遵循"就近原则"，方法内直接用名字访问到的是局部变量；
用 `this.成员变量` 才能访问成员变量。this 本质是存放在栈中的引用变量，保存堆中当前对象的地址。
静态方法随类加载而存在，那时可能还没有任何对象，所以 static 方法中禁止使用 this。
▶ 关联：第 8 章子类中 `super.成员变量` 与 this 是一对对应概念；构造器中
`this(...)` 调用本类其他构造器、`super(...)` 调用父类构造器，且二者争第一行不能共存。

---

**4.** 构造器的语法有三条硬性要求：方法名与 ______ 完全相同（大小写也要一致）；没有 ______，连 void 都不写；没有具体的返回值，不能由 return 带回结果数据。

**【答案】** 类名；返回值类型

**【解析】** 构造器本质作用是创建对象，结合执行时机看还有"给属性初始化"的作用。
它在 new 的时候自动调用，每 new 一次执行一次，不能手动调用。IDEA 中可用 Alt + Insert → Constructor 快速生成。
▶ 关联：第 8 章子类构造器第一行默认隐含 `super()` 调用父类无参构造器，
若父类只写了有参构造器，子类必须显式写 `super(参数)` 才能编译通过。

---

**5.** 封装的两个标准步骤：第一步给成员变量添加 ______ 私有修饰符；第二步在类内部提供 public 修饰的、成对的 ______ 方法作为对外访问入口。

**【答案】** `private`；`getXxx()` / `setXxx()`（get/set）

**【解析】** private 修饰的成员只能在本类内部访问，外部无法直接 `对象.属性` 赋值，从根源上杜绝非法数据；
getXxx 有返回值无参数负责取值，setXxx 是 void 有参数负责设值，并可在方法体内写校验逻辑。
▶ 关联：权限从大到小为 public > protected > default > private；第 8 章方法重写规则
"重写后权限只能更大不能更小"，依据就是这张权限表。

---

**6.** 被 static 修饰的成员有三个特点：被该类的所有对象 ______；可以直接通过 ______ 调用（推荐）；随着类的加载而加载，优先于对象存在。静态成员变量存储在方法区的 ______ 中。

**【答案】** 共享；类名；静态成员区

**【解析】** 普通成员变量每个对象在堆中各存一份；static 变量全类只有一份，存在方法区静态区，
所有对象访问同一份数据——典型用途是计数器、所有对象共享的公共名称。
▶ 关联：第 11 章会讲 static 完整加载时机、静态代码块与单例模式；
第 21 章多线程中 static 变量被多个线程共享，正是线程安全问题的来源之一。

---

**7.** 自定义工具类的三条编写规范：所有业务方法全部加 ______；写一个 ______ 化的无参构造器防止别人创建对象；类名命名为 ______。

**【答案】** `public static`；private（私有）；XXXUtil / XXXUtils

**【解析】** 工具类封装通用、高频复用的逻辑，方法全静态意味着直接 `类名.方法名()` 调用、无需 new；
私有构造器让 `new XXXUtil()` 编译报错。
▶ 关联：JDK 自带的 Math、System、Arrays、Objects（第 14 章）全部是这种设计。

---

### 二、选择题

**1.** 关于成员变量的默认值，下列说法正确的是（　）

A. int 类型成员变量默认值是 1
B. String 类型成员变量默认值是空字符串 ""
C. double 类型成员变量默认值是 0.0，boolean 类型默认值是 false
D. 成员变量没有默认值，不赋值就编译报错

**【答案】** C

**【解析】** new 对象时堆中成员变量先被赋予默认值：byte/short/int/long 为 0，float/double 为 0.0，
char 为 ' '，boolean 为 false，所有引用类型为 null。A 错（int 默认 0）；B 错（String 默认 null）；
D 说的是局部变量的规则。
▶ 关联：第 6 章数组元素默认值与这套规则完全相同（数组本身就是对象）；
引用类型默认 null 是第 14、16 章 NullPointerException 的根源。

---

**2.** 下列关于局部变量的说法，错误的是（　）

A. 局部变量定义在方法体内部、方法形参列表或代码块内部
B. 局部变量没有默认初始化值，使用之前必须手动赋值
C. 局部变量存储在堆内存中，随对象的消失而消失
D. 局部变量的作用域仅限它所属的大括号 {} 内

**【答案】** C

**【解析】** C 把两类变量说反了：局部变量存在栈内存的方法栈帧中，随方法弹栈而消失；
成员变量才存在堆中、随对象消失。记忆口诀："成员进堆有默认，局部进栈必赋值"。
▶ 关联：第 4 章方法压栈弹栈是局部变量生命周期的底层原理。

---

**3.** 阅读代码，输出结果是（　）

```java
Book b1 = new Book();
b1.name = "Java入门";

Book b2 = b1;       // 注意这一行
b2.name = "数据结构";

System.out.println(b1.name);
System.out.println(b2.name);
```

A. Java入门 / 数据结构
B. 数据结构 / 数据结构
C. Java入门 / Java入门
D. 编译报错

**【答案】** B

**【解析】** `Book b2 = b1;` 不是创建新对象，而是把 b1 中保存的对象地址复制给 b2，
两个引用指向堆中同一个对象。通过 b2 改 name，改的是同一个对象，所以 b1 再读也是"数据结构"。
如果第二行是 `new Book()`，才是两个独立对象、互不影响。
▶ 关联：第 6 章 `int[] arr2 = arr1;` 两个数组变量共享同一数组实体是同一原理；
第 16 章方法参数传引用类型传的也是地址。

---

**4.** 某类中已经手动定义了一个有参构造器，下列说法正确的是（　）

A. 编译器仍会自动赠送一个无参构造器
B. `new 类名()` 会正常调用自动生成的无参构造器
C. 编译器不再自动生成无参构造器，`new 类名()` 编译报错，需手动补写无参构造器
D. 有参构造器和无参构造器不能同时存在于一个类中

**【答案】** C

**【解析】** 类中没有手动定义任何构造器时，编译器才自动生成默认无参构造器；一旦手动写了有参构造器，
默认无参构造器就不再赠送。开发规范是：**无参、有参构造器全部手动给出**（很多框架依赖无参构造器）。
D 错：构造器可以重载，无参和有参能共存。
▶ 关联：第 8 章子类构造器第一行隐含 `super()`，父类只有有参构造器时子类必须显式 `super(参数)`。

---

**5.** 在 static 静态方法中，下列哪种写法可以编译通过（　）

```java
public class Printer {
    String brand1 = "惠普";
    static String brand2 = "佳能";

    public static void show() {
        // 此处访问
    }
}
```

A. `System.out.println(brand1);`
B. `System.out.println(this.brand1);`
C. `System.out.println(brand2);`
D. `this.show();`

**【答案】** C

**【解析】** 静态成员随类加载而加载，非静态成员需要 new 对象后才存在；static 方法中只能直接访问
静态成员（brand2），不能直接访问实例成员（brand1），也不能使用 this。A、B、D 全部编译报错。
若确实想访问 brand1，先 new 对象：`new Printer().brand1`。
▶ 关联：main 方法是 static，所以测试类里被 main 直接调用的方法必须加 static。

---

**6.** 关于权限修饰符的访问范围，下列说法正确的是（　）

A. private 修饰的成员在同包的其他类中可以访问
B. default（不写修饰符）修饰的成员在不同包的子类中可以访问
C. protected 修饰的成员在不同包的子类中可以访问，但在不同包的无关类中不能访问
D. public 修饰的成员只能在本类中访问

**【答案】** C

**【解析】** 权限从大到小：public（任意位置）> protected（本类、同包、不同包子类）
> default（本类、同包）> private（仅本类）。A 错：private 仅限本类；B 错：default 不出包；
D 说反了。封装常用组合：属性 private 藏起来、get/set 方法 public 暴露出去。
▶ 关联：第 8 章方法重写"权限只能放大不能缩小"的规则就建立在这张表上。

---

**7.** 下列不符合标准 JavaBean（实体类）编写规范的是（　）

A. 类使用 public 修饰
B. 成员变量全部使用 private 修饰，并提供 public 的 getXxx/setXxx
C. 必须提供一个无参构造器
D. 在实体类中编写大量业务逻辑方法（排序、统计、文件读写）

**【答案】** D

**【解析】** JavaBean 是"标准化的数据容器"，只负责数据存取（私有属性 + get/set + 构造器），
数据处理交给专门的操作类（Operator/Service），实现"数据与业务处理相分离"。
实体类通常放在 pojo 包中，日常开发中 JavaBean ≈ POJO。
▶ 关联：第 16、17 章"集合 + 实体类 + 操作类"是所有管理系统的标准三层结构。

---

### 三、判断题

**1.** 构造器是一种特殊的方法，所以定义时要写 `public void Account(){}`。（　）

**【答案】** ✗ 错误

**【解析】** 构造器**没有返回值类型，连 void 都不写**，正确写法是 `public Account(){}`。
写了 void 之后它就变成普通方法（方法名碰巧叫 Account），new 对象时不会执行它。

---

**2.** 一个类中如果没有手动定义任何构造器，编译器会自动生成一个默认的无参构造器。（　）

**【答案】** ✓ 正确

**【解析】** 这就是之前只写属性、不写构造器也能直接 `new 类名()` 的原因。
但一旦手动写了有参构造器，默认无参构造器就不再生成，需手动补写。

---

**3.** static 静态方法中可以直接使用 this 关键字来调用本类成员。（　）

**【答案】** ✗ 错误

**【解析】** this 代表当前对象的地址，而静态成员优先于对象存在，静态方法执行时可能还没有任何对象，
因此 static 中禁止使用 this，也不能直接访问非静态成员。

---

**4.** 一个类可以创建出多个对象，每个对象各自拥有一份成员变量，修改 p1 的属性不会影响 p2。（　）

**【答案】** ✓ 正确

**【解析】** 每次 new 都在堆中开辟一块新空间，栈中的引用各自保存不同地址，对象之间互不影响。
两个例外：`p2 = p1` 这种地址赋值会让两个引用指向同一对象；static 变量全类只有一份、所有对象共享。

---

**5.** 成员变量用 private 修饰后，外部类可以通过 `对象名.变量名` 直接读取和修改。（　）

**【答案】** ✗ 错误

**【解析】** private 修饰后外部直接访问会编译报错，必须通过 public 的 getXxx/setXxx 间接访问。
这正是封装"合理隐藏、合理暴露"的体现：set 方法中还可以拦截非法值。

---

**6.** static 修饰的成员变量在内存中只有一份，即使创建了 100 个对象，它们访问的也是同一份数据。（　）

**【答案】** ✓ 正确

**【解析】** 静态变量在类加载时存入方法区静态成员区，属于类而不属于某个对象。
▶ 关联：第 21 章多线程中，多个线程同时操作这"唯一一份"共享变量会产生线程安全问题，需要加锁。

---

### 四、简答题

**1.** 面向过程和面向对象有什么区别？面向对象编程有哪些好处？

**【参考答案】**

- 关注点不同：面向过程关注"怎么做"（第一步、第二步……），是执行者思维，代码是变量+方法的流水账；
  面向对象关注"谁来做"，把现实事物抽象成类和对象，是指挥者思维，属性和行为封装在类中。
- 面向对象的四大好处：
  1. 代码更简洁、调用更简单：新增一个事物只需 new 对象、设属性、调方法，不用传一堆参数；
  2. 属性和行为绑定在一起，`对象.方法()` 就对应现实中"谁做什么"，符合现实逻辑；
  3. 复用性极高、扩展方便（最核心）：类中加一个属性/方法，所有对象立即拥有；新增对象只需 new；
  4. 易维护易修改：某行为逻辑要改，只改类中的对应方法，一处修改、处处生效。

**【解析】** 理解"复用与扩展"是关键——这也是为什么第 8 章继承、第 9 章接口都在进一步强化复用能力。

---

**2.** 请列表对比成员变量和局部变量的区别。

**【参考答案】**

| 对比项 | 成员变量 | 局部变量 |
| --- | --- | --- |
| 定义位置 | 类中、方法体之外 | 方法体内、方法形参列表、代码块（for/if）内 |
| 初始化值 | 有默认值（int=0、引用类型=null 等） | 无默认值，使用前必须手动赋值 |
| 内存位置 | 堆内存（对象中） | 栈内存（方法栈帧中） |
| 生命周期 | 随对象创建而存在，随对象消失而消失 | 随方法调用而存在，方法弹栈即消失 |
| 作用域 | 整个类中有效 | 仅限所属的 {} 内 |

**【解析】** 记忆抓手：成员变量跟着对象住在堆里，所以有默认值、活得久；
局部变量跟着方法栈帧住在栈里，所以必须先赋值、方法结束就销毁。
▶ 关联：第 4 章方法栈、第 6 章堆/栈/方法区三大内存区域是这张表的底层支撑。

---

**3.** 什么是封装？封装的标准步骤是什么？有什么好处？

**【参考答案】**

- 含义（两层）：① 把数据（属性）和操作数据的方法捆绑到一个类中组成整体（类本身就是封装）；
  ② 通过访问修饰符控制权限，"合理隐藏、合理暴露"——属性 private 藏起来，get/set 方法 public 暴露出去，
  仅供内部使用的实现方法也可以 private 藏起来。
- 标准步骤：第一步，成员变量加 private；第二步，提供 public 的 getXxx()/setXxx()，
  并在 setXxx 中做数据合法性校验。
- 好处：① 保证数据安全正确（所有赋值经过 set 校验，过滤负数年龄、越界成绩）；
  ② 隐藏实现细节、降低耦合（使用者只调方法，不关心内部实现）；
  ③ 提升可维护性（修改校验规则只改类内部，外部调用代码一行不变）。

**【解析】** 不封装时 `对象.age = -18` 不会报错但数据非法；封装后非法值在 setAge 中被拦截。
Scanner、Random 也是封装好的类——我们只会调 nextInt()，从不需要知道它内部怎么实现。

---

### 五、代码阅读题

**1.** 阅读下面代码，分别写出【不加 this】和【加 this】两种情况下的输出。

```java
public class Pet {
    String name;       // 宠物名
    int age;

    public void feed(String name) {   // 形参 name 表示食物名称
        // 情况一：System.out.println(name + " 正在吃 " + name);
        // 情况二：System.out.println(this.name + " 正在吃 " + name);
    }
}
// 测试：
Pet p = new Pet();
p.name = "旺财";
p.age = 3;
p.feed("狗粮");
```

**【答案】**

- 情况一（不加 this）：`狗粮 正在吃 狗粮`
- 情况二（加 this）：`旺财 正在吃 狗粮`

**【解析】** 形参 name 与成员变量 name 重名时，Java 遵循就近原则：方法内直接写 name 访问到的是
离它最近的局部变量（形参"狗粮"），成员变量"旺财"被屏蔽。`this.name` 明确指向堆中当前对象的
成员变量。这就是构造器和 set 方法中 `this.name = name;` 的意义——等号左边是成员变量，右边是形参。

---

**2.** 阅读代码，写出程序输出。

```java
public class Account {
    String id;
    double balance;
}

public class Test {
    public static void main(String[] args) {
        Account acc = new Account();
        System.out.println(acc);          // ①
        System.out.println(acc.id);       // ②
        System.out.println(acc.balance);  // ③
        acc.id = "6228****1234";
        acc.balance = 5000.0;
        System.out.println(acc.id);       // ④
        System.out.println(acc.balance);  // ⑤
    }
}
```

**【答案】**

```
Account@2f4d3709   // ① 地址每次运行可能不同，格式固定为"全类名@十六进制哈希值"
null               // ② String 成员变量默认值
0.0                // ③ double 成员变量默认值
6228****1234       // ④
5000.0             // ⑤
```

**【解析】** new 对象时堆中成员变量先赋默认值（引用类型 null、浮点 0.0），直接打印对象引用输出
"类名@地址"；之后通过地址找到堆中对象修改属性。
▶ 关联：打印对象出现"类名@地址"说明用的是 Object 的 toString()，第 8 章学习重写 toString()
后打印对象就会显示属性内容；第 14 章讲 Object 类的完整方法。

---

**3.** 阅读代码，写出三处输出的结果。

```java
class MemberCard {
    String owner;
    static int totalCards;   // 健身房总发卡数
}

public class Test {
    public static void main(String[] args) {
        MemberCard.totalCards++;
        MemberCard c1 = new MemberCard();
        c1.owner = "张三";
        System.out.println(c1.totalCards);      // ①

        MemberCard.totalCards++;
        MemberCard c2 = new MemberCard();
        c2.owner = "李四";
        System.out.println(c2.totalCards);      // ②
        System.out.println(c1.totalCards);      // ③
    }
}
```

**【答案】** ① 1　② 2　③ 2

**【解析】** totalCards 被 static 修饰，全类只有一份，存在方法区静态区。第一次自增后变为 1，
c1 读到 1；第二次自增后变为 2，c2 读到 2；c1 再读时共享数据已经是 2，所以③也是 2（而不是 1）。
owner 没有 static，c1、c2 各自一份互不影响。推荐用 `类名.静态成员` 访问，语义更清晰。
▶ 关联：本章编程题第 3 题正是用这个原理实现"卡号自动递增"。

---

**4.** 阅读代码，写出输出，并说明原因。

```java
public class Book {
    private double price;

    public void setPrice(double price) {
        if (price > 0 && price <= 1000) {
            this.price = price;
        } else {
            System.out.println("图书价格不合法：" + price);
        }
    }

    public double getPrice() {
        return price;
    }
}
// 测试：
Book b = new Book();
b.setPrice(-9.9);
System.out.println(b.getPrice());   // ①
b.setPrice(59.5);
System.out.println(b.getPrice());   // ②
```

**【答案】**

```
图书价格不合法：-9.9
0.0
59.5
```

即①输出 0.0，②输出 59.5。

**【解析】** new 对象时 price 先有默认值 0.0。传入 -9.9 校验不通过，else 分支只打印提示、
不执行赋值，price 保持 0.0；传入 59.5 校验通过，`this.price = 59.5` 生效。
这就是封装"保证数据安全正确"的直观体现：非法数据被挡在对象之外。
▶ 关联：实际开发中非法参数通常抛出异常（第 16 章异常处理）而不是仅打印提示。

---

**5.** 下面代码能否编译通过？如果不能请说明原因，并给出两种修改方案。

```java
public class Printer {
    String brand = "惠普";

    public static void printBrand() {
        System.out.println(brand);
    }
}
```

**【答案】** 不能编译，报错位置在 `System.out.println(brand);`：
静态方法 printBrand 中不能直接访问非静态成员变量 brand。

原因：brand 是实例成员，要 new 对象后才存在；静态方法随类加载就可能被调用，那时对象还不存在。

两种修改方案：

```java
// 方案一：创建对象后再访问
public class Printer {
    String brand = "惠普";
    public static void printBrand() {
        Printer p = new Printer();
        System.out.println(p.brand);
    }
}

// 方案二：把成员变量改为 static
public class Printer {
    static String brand = "惠普";
    public static void printBrand() {
        System.out.println(brand);
    }
}
```

**【解析】** 这是初学者最高频的编译错误，判断口诀："静态只能直接访问静态"。
也正因为 main 是静态的，测试类中被 main 直接调用的自定义方法都必须加 static；
而实体类中的成员方法不加 static，通过对象调用——两者不要混淆。

---

### 六、编程题（6 道，由易到难）

> 要求：每题先独立完成，再对照参考代码。参考代码均可直接编译运行。

#### 第 1 题（基础）：图书类 JavaBean

**需求：** 设计图书类 `Book`：

- 私有属性：书名 name（String）、作者 author（String）、价格 price（double）、库存 stock（int）；
- 提供无参构造器和全参构造器；
- 提供全套 get/set 方法；其中 setPrice 只接收 0~1000（不含 0）、setStock 不接收负数，
  非法数据打印提示且不赋值；
- 编写测试类：用无参对象测试合法值与非法值，再用全参构造器创建第二本书并打印信息。

**【参考代码】**

```java
public class Book {
    private String name;
    private String author;
    private double price;
    private int stock;

    public Book() {
    }

    public Book(String name, String author, double price, int stock) {
        this.name = name;
        this.author = author;
        this.price = price;
        this.stock = stock;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getAuthor() {
        return author;
    }

    public void setAuthor(String author) {
        this.author = author;
    }

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        if (price > 0 && price <= 1000) {
            this.price = price;
        } else {
            System.out.println("图书价格不合法：" + price + "，需在 0~1000 之间");
        }
    }

    public int getStock() {
        return stock;
    }

    public void setStock(int stock) {
        if (stock >= 0) {
            this.stock = stock;
        } else {
            System.out.println("库存不能为负数：" + stock);
        }
    }
}
```

```java
public class BookTest {
    public static void main(String[] args) {
        Book b = new Book();
        b.setName("Java从入门到实战");
        b.setAuthor("张三");
        b.setPrice(69.9);
        b.setStock(100);
        System.out.println(b.getName() + "，作者：" + b.getAuthor()
                + "，价格：" + b.getPrice() + "，库存：" + b.getStock());

        b.setPrice(-20);    // 图书价格不合法：-20.0，需在 0~1000 之间
        b.setStock(-5);     // 库存不能为负数：-5
        System.out.println("校验后 → 价格：" + b.getPrice() + "，库存：" + b.getStock());

        Book b2 = new Book("数据结构图解", "李四", 88.0, 50);
        System.out.println(b2.getName() + "，作者：" + b2.getAuthor()
                + "，价格：" + b2.getPrice() + "，库存：" + b2.getStock());
    }
}
```

**【思路讲解】**

1. 类中四段固定结构：私有属性 → 构造器 → get/set →（可选）业务方法，这是标准 JavaBean 的骨架；
2. 全参构造器中用 `this.属性 = 参数` 区分重名，this.name 是成员变量、name 是形参；
3. 校验逻辑写在 set 方法里：非法时只打印提示、不执行 this 赋值，对象中的值保持不变；
4. 无参构造器必须手动写出——因为一旦写了有参构造器，编译器就不再赠送无参构造器。

**【运行结果】**

```
Java从入门到实战，作者：张三，价格：69.9，库存：100
图书价格不合法：-20.0，需在 0~1000 之间
库存不能为负数：-5
校验后 → 价格：69.9，库存：100
数据结构图解，作者：李四，价格：88.0，库存：50
```

非法值被拦截后，价格和库存仍是之前设置的合法值（69.9 和 100）。

---

#### 第 2 题（基础进阶）：银行账户类

**需求：** 设计银行账户类 `Account`：

- 私有属性：账号 id（String）、户主 name（String）、余额 balance（double）；
- 无参构造器、全参构造器（开户余额为负时提示并按 0 开户）；
- 提供 get 方法；余额不允许外部直接 set，只能通过业务方法变动；
- `deposit(double money)` 存款：money 大于 0 则余额增加并打印，否则提示"金额必须大于 0"；
- `withdraw(double money)` 取款：金额非法提示；超过余额提示"余额不足"；成功则扣减并打印；
- `showInfo()` 打印账户完整信息。
- 测试：开户存入 500，再存 1000、取 300、取 2000（应失败）、存 -50（应失败），最后打印账户信息。

**【参考代码】**

```java
public class Account {
    private String id;
    private String name;
    private double balance;

    public Account() {
    }

    public Account(String id, String name, double balance) {
        this.id = id;
        this.name = name;
        if (balance >= 0) {
            this.balance = balance;
        } else {
            System.out.println("开户余额不能为负，已按 0 元开户");
        }
    }

    public String getId() {
        return id;
    }

    public void setId(String id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getBalance() {
        return balance;
    }

    // 存款
    public void deposit(double money) {
        if (money > 0) {
            balance += money;
            System.out.println(name + " 存款成功 " + money + " 元，当前余额：" + balance + " 元");
        } else {
            System.out.println("存款金额必须大于 0：" + money);
        }
    }

    // 取款
    public void withdraw(double money) {
        if (money <= 0) {
            System.out.println("取款金额必须大于 0：" + money);
        } else if (money > balance) {
            System.out.println("余额不足！当前余额：" + balance + " 元，试图取款：" + money + " 元");
        } else {
            balance -= money;
            System.out.println(name + " 取款成功 " + money + " 元，当前余额：" + balance + " 元");
        }
    }

    public void showInfo() {
        System.out.println("账号：" + id + "，户主：" + name + "，余额：" + balance + " 元");
    }
}
```

```java
public class AccountTest {
    public static void main(String[] args) {
        Account acc = new Account("6222001", "王五", 500);
        acc.showInfo();
        acc.deposit(1000);
        acc.withdraw(300);
        acc.withdraw(2000);
        acc.deposit(-50);
        acc.showInfo();
    }
}
```

**【思路讲解】**

1. 余额是敏感数据，所以只暴露 getBalance（只读），不提供 public 的 setBalance，
   变动余额的唯一入口是 deposit/withdraw 两个业务方法——这是"合理隐藏、合理暴露"的进阶用法；
2. 业务方法内部分层判断：先判断金额合法性，再判断余额是否足够，最后才执行扣减；
3. 全参构造器中也做了防御性校验：即使创建对象时传入负余额也不会污染数据；
4. 方法内直接写 balance 而不是 getBalance()，因为同类内部可以直接访问私有成员。

**【运行结果】**

```
账号：6222001，户主：王五，余额：500.0 元
王五 存款成功 1000.0 元，当前余额：1500.0 元
王五 取款成功 300.0 元，当前余额：1200.0 元
余额不足！当前余额：1200.0 元，试图取款：2000.0 元
存款金额必须大于 0：-50.0
账号：6222001，户主：王五，余额：1200.0 元
```

最终余额 1200.0 = 500 + 1000 - 300，两笔失败操作没有影响数据。

---

#### 第 3 题（中等）：健身会员卡自动编号（static 共享）

**需求：** 设计健身房会员卡类 `MemberCard`：

- 私有实例属性：持卡人 owner（String）、卡号 cardId（int）；
- 私有静态属性：总发卡数 totalCards（int）；
- 每调用一次无参构造器（每办一张卡），totalCards 加 1，并把当前卡号 cardId 设为 totalCards
  （第一张卡卡号为 1，第二张为 2，依次递增）；
- 提供 owner 的 get/set、cardId 的 get 方法、静态方法 getTotalCards()；
- 实例方法 `consume(double money)`：打印"持卡人 xxx 使用卡号 N 消费 money 元"；
- 测试：办 3 张卡并设置持卡人，打印每张卡卡号、总发卡数，让第二张卡消费 299 元。

**【参考代码】**

```java
public class MemberCard {
    private String owner;
    private int cardId;
    private static int totalCards;

    public MemberCard() {
        totalCards++;               // 每办一张卡，共享计数器加 1
        this.cardId = totalCards;   // 卡号取最新计数器值
    }

    public String getOwner() {
        return owner;
    }

    public void setOwner(String owner) {
        this.owner = owner;
    }

    public int getCardId() {
        return cardId;
    }

    public static int getTotalCards() {
        return totalCards;
    }

    public void consume(double money) {
        System.out.println("持卡人：" + owner + "，使用卡号：" + cardId + "，本次消费：" + money + " 元");
    }
}
```

```java
public class MemberCardTest {
    public static void main(String[] args) {
        MemberCard c1 = new MemberCard();
        c1.setOwner("张三");
        MemberCard c2 = new MemberCard();
        c2.setOwner("李四");
        MemberCard c3 = new MemberCard();
        c3.setOwner("王五");

        System.out.println(c1.getOwner() + " 的卡号：" + c1.getCardId());
        System.out.println(c2.getOwner() + " 的卡号：" + c2.getCardId());
        System.out.println(c3.getOwner() + " 的卡号：" + c3.getCardId());
        System.out.println("当前总发卡数：" + MemberCard.getTotalCards());

        c2.consume(299.0);
    }
}
```

**【思路讲解】**

1. 卡号必须"全局唯一递增"，这个计数器不能是实例变量（每张卡各存一份就乱了），
   必须用 static——所有卡共享方法区中的同一份 totalCards；
2. 构造器是"每 new 一次必然执行一次"的方法，所以把计数器自增写在构造器里最可靠；
3. `this.cardId = totalCards;` 中左边是实例变量（每张卡不同），右边是静态变量（大家共享），
   一行代码体现了"共享数据分配给个体"的过程；
4. getTotalCards 是静态方法，推荐用类名调用：`MemberCard.getTotalCards()`。

**【运行结果】**

```
张三 的卡号：1
李四 的卡号：2
王五 的卡号：3
当前总发卡数：3
持卡人：李四，使用卡号：2，本次消费：299.0 元
```

▶ 关联：第 11 章单例模式、第 21 章多线程共享数据都会用到 static 的这种共享特性。

---

#### 第 4 题（中等偏难）：书架管理（实体类 + 操作类分层）

**需求：** 复用第 1 题的 Book 类（只需 name、author、price 属性及对应 get 方法），
设计书架操作类 `BookShelfOperator`：

- `printAll(Book[] books)`：遍历数组，跳过空位，按 `《书名》 作者：xx，价格：xx.xx 元` 格式展示全部图书；
- `searchByName(String name, Book[] books)`：按书名精确查找，找到则打印图书信息并返回该对象，
  找不到打印"书架上没有《xx》这本书"并返回 null；
- 测试类：数组中放入 4 本图书，提供循环菜单（1 查看全部 / 2 按书名查找 / 3 退出），
  用 Scanner 接收命令。

**【参考代码】**

```java
// 操作类：只负责业务逻辑，不存数据
public class BookShelfOperator {

    public void printAll(Book[] books) {
        System.out.println("====== 书架全部图书 ======");
        for (int i = 0; i < books.length; i++) {
            Book b = books[i];
            if (b == null) {
                continue;   // 跳过空位
            }
            System.out.println("《" + b.getName() + "》 作者：" + b.getAuthor()
                    + "，价格：" + String.format("%.2f", b.getPrice()) + " 元");
        }
    }

    public Book searchByName(String name, Book[] books) {
        for (int i = 0; i < books.length; i++) {
            Book b = books[i];
            if (b != null && b.getName().equals(name)) {
                System.out.println("已找到 → 《" + b.getName() + "》 作者：" + b.getAuthor()
                        + "，价格：" + String.format("%.2f", b.getPrice()) + " 元");
                return b;   // 查到立即返回，结束方法
            }
        }
        System.out.println("书架上没有《" + name + "》这本书");
        return null;
    }
}
```

```java
import java.util.Scanner;

public class BookShelfTest {
    public static void main(String[] args) {
        Book[] books = new Book[5];
        books[0] = new Book("Java入门", "张三", 59.9, 20);
        books[1] = new Book("数据结构", "李四", 78.0, 15);
        books[2] = new Book("设计模式", "王五", 99.0, 8);
        books[3] = new Book("计算机网络", "赵六", 66.6, 12);

        BookShelfOperator op = new BookShelfOperator();
        Scanner sc = new Scanner(System.in);

        while (true) {
            System.out.println("====== 1.查看全部图书  2.按书名查找  3.退出 ======");
            int cmd = sc.nextInt();
            switch (cmd) {
                case 1:
                    op.printAll(books);
                    break;
                case 2:
                    System.out.println("请输入要查找的书名：");
                    String name = sc.next();
                    op.searchByName(name, books);
                    break;
                case 3:
                    System.out.println("再见！");
                    return;
                default:
                    System.out.println("命令有误，请重新输入！");
            }
        }
    }
}
```

**【思路讲解】**

1. 三层分工：Book（实体类）只装数据，BookShelfOperator（操作类）只处理业务，
   BookShelfTest（测试类）负责组装和交互——这是所有管理系统的标准结构；
2. 数组长度 5 但只放 4 本书，遍历时必须 `if (b == null) continue` 跳过空位，否则空指针；
3. 字符串内容比较用 `b.getName().equals(name)`，不能用 ==（比的是地址）；
4. 查找方法找到后 `return b` 立即结束（类似 break 但能把结果带回），遍历完没找到才提示并返回 null；
5. 价格用 `String.format("%.2f", 价格)` 保留两位小数，避免 66.6 显示成 66.600000...。

**【运行结果】**（选择 1，再选 2 输入"设计模式"，再选 2 输入"操作系统"，最后 3 退出）

```
====== 1.查看全部图书  2.按书名查找  3.退出 ======
1
====== 书架全部图书 ======
《Java入门》 作者：张三，价格：59.90 元
《数据结构》 作者：李四，价格：78.00 元
《设计模式》 作者：王五，价格：99.00 元
《计算机网络》 作者：赵六，价格：66.60 元
====== 1.查看全部图书  2.按书名查找  3.退出 ======
2
请输入要查找的书名：
设计模式
已找到 → 《设计模式》 作者：王五，价格：99.00 元
……
2
请输入要查找的书名：
操作系统
书架上没有《操作系统》这本书
……
3
再见！
```

---

#### 第 5 题（较难）：订单工具类 OrderUtil

**需求：** 按照工具类三规范设计订单工具类 `OrderUtil`：

- `generateOrderId()`：生成订单号，格式为 `OD` + 当前时间戳后 8 位 + 2 位随机数（如 OD1234567847）；
- `calcDiscountPrice(double price, double discount)`：计算折后价，discount 为 0~1 的小数
  （0.85 表示 85 折）；价格或折扣非法时打印提示并返回 -1；
- `formatMoney(double money)`：把金额格式化为 `￥xx.xx` 字符串返回；
- 编写测试类：生成 3 个订单号，计算一本书 100 元打 85 折后的价格并格式化输出，
  再测试非法折扣 1.5 的拦截效果。

**【参考代码】**

```java
import java.util.Random;

public class OrderUtil {
    private static final Random R = new Random();

    // 私有构造器：禁止创建对象
    private OrderUtil() {
    }

    // 生成订单号：OD + 时间戳后8位 + 2位随机数
    public static String generateOrderId() {
        String time = String.valueOf(System.currentTimeMillis());
        String suffix = time.substring(time.length() - 8);
        int rand = R.nextInt(90) + 10;   // 10~99 的两位随机数
        return "OD" + suffix + rand;
    }

    // 计算折后价：discount 为 0~1（0.85 表示 85 折）
    public static double calcDiscountPrice(double price, double discount) {
        if (price <= 0 || discount <= 0 || discount > 1) {
            System.out.println("价格或折扣不合法：price=" + price + "，discount=" + discount);
            return -1;
        }
        return price * discount;
    }

    // 格式化金额：￥xx.xx
    public static String formatMoney(double money) {
        return "￥" + String.format("%.2f", money);
    }
}
```

```java
public class OrderUtilTest {
    public static void main(String[] args) {
        for (int i = 0; i < 3; i++) {
            System.out.println("生成订单号：" + OrderUtil.generateOrderId());
        }

        double pay = OrderUtil.calcDiscountPrice(100.0, 0.85);
        System.out.println("100 元图书打 85 折，应付：" + OrderUtil.formatMoney(pay));

        double wrong = OrderUtil.calcDiscountPrice(100.0, 1.5);
        System.out.println("非法折扣的返回值：" + wrong);
    }
}
```

**【思路讲解】**

1. 工具类三规范缺一不可：类名 Util 结尾、方法全部 `public static`、构造器 private
   （尝试 `new OrderUtil()` 会编译报错）；
2. Random 对象定义为 `private static final`：所有静态方法共享一个随机数生成器即可，
   不必每次调用都 new；
3. `System.currentTimeMillis()` 返回从 1970 年到现在的毫秒数（long 类型），
   取后 8 位再拼两位随机数，订单号既唯一又可读；
4. 折后价方法先做参数合法性校验，非法时返回约定值 -1，调用方可以据此判断是否出错；
5. `String.format("%.2f", money)` 是保留两位小数的标准写法。

**【运行结果】**（时间戳和随机数每次不同，格式一致）

```
生成订单号：OD8765432147
生成订单号：OD8765432283
生成订单号：OD8765432315
100 元图书打 85 折，应付：￥85.00
价格或折扣不合法：price=100.0，discount=1.5
非法折扣的返回值：-1
```

▶ 关联：JDK 的 Math、Arrays、Objects（第 14 章）源码与本工具类结构完全一致，
读懂本题再看官方工具类会发现"官方也是这么写的"。

---

#### 第 6 题（综合）：宠物医院挂号系统

**需求：** 综合运用类设计、构造器、this、封装、JavaBean 分层、static 共享，开发宠物医院挂号小系统：

- 实体类 `Pet`：私有属性 宠物名 name、类型 type（狗/猫/兔…）、年龄 age、主人电话 phone；
  无参构造器、全参构造器、全套 get/set；
- 操作类 `PetHospital`：
  - 静态成员医院名 `hospitalName = "爱心宠物医院"`（所有挂号单共享）；
  - 用 Pet 数组管理当日挂号（容量 5），用计数器 count 记录已挂号数量；
  - `register(Pet p)`：号源未满则存入数组，打印"医院名 挂号成功！《宠物名》排第 N 号"；
    已满则提示"今日号源已满"；
  - `findByPhone(String phone)`：按主人电话查找挂号宠物，找到打印宠物全部信息，
    找不到提示；
  - `showTodayCount()`：打印今日已挂号数量；
- 测试类：挂号 3 只宠物，统计今日数量，按电话查询一只存在的和一只不存在的，打印医院名。

**【参考代码】**

```java
public class Pet {
    private String name;
    private String type;
    private int age;
    private String phone;

    public Pet() {
    }

    public Pet(String name, String type, int age, String phone) {
        this.name = name;
        this.type = type;
        this.age = age;
        this.phone = phone;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getType() {
        return type;
    }

    public void setType(String type) {
        this.type = type;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public String getPhone() {
        return phone;
    }

    public void setPhone(String phone) {
        this.phone = phone;
    }
}
```

```java
public class PetHospital {
    public static String hospitalName = "爱心宠物医院";

    private Pet[] pets = new Pet[5];   // 当日号源容量 5
    private int count;                 // 已挂号数量

    // 挂号
    public void register(Pet p) {
        if (count >= pets.length) {
            System.out.println("今日号源已满，请明天再来！");
            return;
        }
        pets[count] = p;
        count++;
        System.out.println(hospitalName + " 挂号成功！《" + p.getName() + "》排第 " + count + " 号");
    }

    // 按主人电话查询
    public void findByPhone(String phone) {
        for (int i = 0; i < count; i++) {
            Pet p = pets[i];
            if (p.getPhone().equals(phone)) {
                System.out.println("查询到宠物 → 名字：" + p.getName() + "，类型：" + p.getType()
                        + "，年龄：" + p.getAge() + " 岁，主人电话：" + p.getPhone());
                return;
            }
        }
        System.out.println("没有查询到电话为 " + phone + " 的挂号宠物");
    }

    // 今日挂号统计
    public void showTodayCount() {
        System.out.println(hospitalName + " 今日已挂号 " + count + " 只宠物");
    }
}
```

```java
public class PetHospitalTest {
    public static void main(String[] args) {
        PetHospital hospital = new PetHospital();

        hospital.register(new Pet("旺财", "狗", 3, "13800000001"));
        hospital.register(new Pet("咪咪", "猫", 2, "13800000002"));
        hospital.register(new Pet("团团", "兔子", 1, "13800000003"));

        hospital.showTodayCount();

        hospital.findByPhone("13800000002");
        hospital.findByPhone("13900000000");

        System.out.println("医院名称：" + PetHospital.hospitalName);
    }
}
```

**【思路讲解】**

1. 本题把本章知识点全部串起来：Pet 是标准 JavaBean（私有属性 + 构造器 + get/set）；
   PetHospital 是操作类（数组存数据、方法处理业务）；hospitalName 用 static 体现"所有对象共享"；
2. `new Pet("旺财", "狗", 3, "13800000001")` 直接作为 register 的参数——匿名对象，
   用完即交给数组保存，省去额外声明变量；
3. register 中 `pets[count] = p; count++;` 是顺序存放的固定写法：count 既是已存数量，
   也是下一个空位下标；存满后 count >= 数组长度 时拦截；
4. 查询只遍历 `0 ~ count-1`（有效数据区），而不是整个数组，避免读到空位；
5. 电话比较用 equals：电话是字符串，== 比较的是地址不是内容。

**【运行结果】**

```
爱心宠物医院 挂号成功！《旺财》排第 1 号
爱心宠物医院 挂号成功！《咪咪》排第 2 号
爱心宠物医院 挂号成功！《团团》排第 3 号
爱心宠物医院 今日已挂号 3 只宠物
查询到宠物 → 名字：咪咪，类型：猫，年龄：2 岁，主人电话：13800000002
没有查询到电话为 13900000000 的挂号宠物
医院名称：爱心宠物医院
```

▶ 关联：本题的数组容量固定为 5，第 10 章学习 ArrayList 后可以换成集合，
挂号数量将不再受容量限制；第 16 章集合框架是这类管理系统的正式解法。

---

### 本篇知识点地图

做完本篇后，对照以下清单自查，全部能讲清楚即说明本章已掌握：

1. 类与对象的关系、new 对象的固定格式、成员变量/成员方法的定义位置；
2. 对象内存图：栈存引用、堆存对象、默认值、两个引用指向同一对象；
3. 成员变量 vs 局部变量五项对比；
4. this 的本质、就近原则、this 不能出现在 static 中；
5. 构造器的语法、执行时机、有参后无参消失的规则、构造器内存流程；
6. 封装两层含义、private + get/set 两步走、set 中校验数据、四个权限修饰符；
7. 标准 JavaBean 规范、实体类与操作类的分层；
8. static 三大特点、内存原理、静态方法访问规则、工具类三规范。

---

<div style="page-break-after: always;"></div>

## 第8章 面向对象高级（上）·习题精讲

> 覆盖考点：继承（extends、is-a、就近原则、方法重写、单继承/多层继承、this/super、子类构造器）、Object 与 toString()、final、抽象类、模板方法设计模式。
> 全部题目场景均为原创（图形、校园卡、快递、饮品），请先独立作答再看解析。解析中"▶ 关联"标注前后章节联系。

---

### 一、填空题

**1.** Java 中使用关键字 `______` 让类与类建立父子继承关系；被继承的类叫父类（基类/超类），继承的类叫子类（______类）。

**【答案】** `extends`；派生

**【解析】** 写法 `class 子类 extends 父类`。继承把多个子类的共性属性/方法抽到父类，子类直接复用。
▶ 关联：使用继承的前提是 **is-a 关系 + 共性内容**同时成立；"单继承不够用"的问题由接口解决（第 9 章）。

**2.** 继承中访问成员变量遵循 `______` 原则，查找顺序为：子类局部变量 → ______ → ______ → 报错。

**【答案】** 就近原则；子类成员变量；父类成员变量

**【解析】** 三级同名时用 `this.变量` 指定本类成员、`super.变量` 指定父类成员。
▶ 关联：this 代表本类对象引用（第 7 章构造器/封装已学）；super 的三种用法见本章及第 11 章。

**3.** 方法重写（Override）要求子类方法的 `______`、`______`、返回值类型与父类完全一致；建议加注解 `______` 让编译器检查。

**【答案】** 方法名；参数列表；`@Override`

**【解析】** 写错方法名或参数，加了 @Override 会直接编译报错。
▶ 关联：重写是运行时多态的基础（第 9 章）；对比重载 Overload（同名不同参，第 4 章）。

**4.** Java 只支持 `______` 继承、不支持多继承，但支持 `______` 继承；一个父类可以同时拥有多个子类。

**【答案】** 单；多层

**【解析】** 多继承时两个父类若有同名方法，子类调用产生歧义；多层继承的方法查找路径确定，无二义性。

**5.** 子类构造器第一行默认有一句 `______`（写不写都存在），调用父类无参构造器；若父类没有无参构造器，子类必须在第一行手写 `______`。

**【答案】** `super();`；`super(参数);`

**【解析】** 初始化"先父后子"：父类成员初始化完，子类构造器才继续。
▶ 关联：构造器初始化对象的原理见第 7 章；`this(...)` 也必须在第一行，所以它与 `super(...)` 不能共存。

**6.** Java 所有类的根类是 `______`；直接打印对象默认输出 `______@十六进制哈希值`，重写 `______` 方法后可打印对象内容。

**【答案】** `java.lang.Object`（Object）；类的全类名；`toString()`

**【解析】** 没写 extends 的类默认继承 Object；IDEA 中 `Alt + Insert` 可自动生成 toString()。
▶ 关联：Object 的 equals()、hashCode()、clone() 在第 14 章精讲。

**7.** final 修饰类表示该类 `______`；修饰方法表示该方法 `______`；修饰变量表示该变量 `______`。

**【答案】** 不能被继承；不能被子类重写（但可继承调用）；一旦赋值不能再修改

**【解析】** 高频易错点：final 修饰**引用类型**变量锁的是地址值，对象内部属性仍可修改。
▶ 关联：final 与 abstract 语义对立（第 12 章深入）。

**8.** 用 `______` 两个关键字共同修饰的成员变量称为常量；命名规范是字母全部 `______`，多个单词用 `______` 连接。

**【答案】** `static final`；大写；下划线 `_`

**【解析】** 如 `public static final double BASE_PRICE = 8.0;`。常量类通常私有化构造器防止实例化（工具类规范，第 7 章）。

**9.** 抽象方法用关键字 `______` 修饰，只有方法声明没有 `______`；子类继承抽象类后必须 `______`，否则该子类也得声明为抽象类。

**【答案】** `abstract`；方法体（大括号）；重写全部抽象方法

**【解析】** 抽象类不能 new（抽象方法无方法体，调用无代码可执行），但可以有构造器（供子类 super 调用）和普通方法。
▶ 关联：抽象类 vs 接口的全面对比在第 9、12 章；抽象类的经典应用是模板方法模式（本章编程题 5）。

---

### 二、选择题

**1.** 快递员有编号、姓名；快递包裹也有编号、重量。关于能否把二者共性抽到同一父类，正确的是（　）

A. 可以，都有编号属性，抽取父类能减少冗余
B. 不可以，二者不存在 is-a 关系，硬抽父类会不伦不类
C. 可以，继承层次越深越好
D. 只要代码能跑就没问题

**【答案】** B

**【解析】** 继承的前提是"共性内容 + is-a 关系"同时成立。快递员不是包裹、包裹不是快递员。

**2.** 关于方法重写，下列说法**错误**的是（　）

A. 子类方法访问权限必须大于或等于父类方法
B. 父类 private 方法不能被重写
C. 子类方法返回值类型可以与父类不同
D. static 静态方法不能被重写

**【答案】** C

**【解析】** 重写要求方法名、参数列表、返回值类型三者一致。权限顺序 `public > protected > default > private`，只能放大。

**3.** 父类方法用 `protected` 修饰，子类重写时下列哪种写法**编译报错**？（　）

A. public　B. protected　C. 不写任何修饰符（default）　D. 都不报错

**【答案】** C

**【解析】** default 权限小于 protected，重写时权限缩小，编译报错。

**4.** 关于子类构造器，下列说法正确的是（　）

A. 子类会继承父类的构造器
B. 创建子类对象时，子类构造器先执行完再调用父类构造器
C. 子类构造器第一行默认是 super()，先初始化父类成员再执行自己
D. this(...) 和 super(...) 可以写在同一个构造器的前两行

**【答案】** C

**【解析】** A 构造器不能继承；B 顺序反了，是先父后子；D 二者都必须在第一行，位置冲突不能共存。

**5.** 阅读代码，下列说法正确的是（　）

```java
public final class MathUtils {
    public static int square(int n) { return n * n; }
}
class MyUtils extends MathUtils { }   // 第2行
```

A. 正常编译　B. 第 2 行报错：final 类不能被继承
C. 第 1 行报错：final 不能修饰类　D. 运行时才报错

**【答案】** B

**【解析】** final 修饰的类是"最终类"，没有子类（JDK 中 String、System 就是 final 类）。

**6.** 阅读代码，哪一行会编译报错？（　）

```java
public class Test {
    public static void main(String[] args) {
        final double[] prices = {3.5, 6.0, 9.9};
        prices[0] = 4.0;            // ①
        prices[1] = prices[0] + 1;  // ②
        prices = new double[5];     // ③
        System.out.println(prices[1]);
    }
}
```

A. ①　B. ②　C. ③　D. 都不报错

**【答案】** C

**【解析】** final 修饰引用类型锁的是地址值：数组元素可以改（①②合法），让 prices 指向新数组（改地址）报错。
▶ 关联：对比 final 基本类型锁数据值、final 引用类型锁地址不锁内容。

**7.** 关于抽象类，下列说法**错误**的是（　）

A. 抽象类不能创建对象
B. 抽象类中可以没有抽象方法，但有抽象方法的类一定是抽象类
C. 抽象类中不能定义构造器
D. 抽象类中可以有普通成员方法

**【答案】** C

**【解析】** 抽象类可以有构造器——子类 super(...) 时调用它初始化父类成员。不能实例化是因为抽象方法没有方法体。

**8.** abstract 关键字不能与下列哪组关键字共同修饰方法？（　）

A. public、protected　B. final、private、static
C. void、int　D. synchronized

**【答案】** B

**【解析】** abstract 强制子类重写：final 禁止重写、private 子类不可见、static 可类名直接调用（抽象方法无方法体）——三者语义矛盾。

**9.** 模板方法设计模式中，定义流程骨架的"模板方法"建议用哪个关键字修饰？（　）

A. abstract　B. static　C. final　D. private

**【答案】** C

**【解析】** 模板方法是统一的流程骨架，用 final 禁止子类重写，保证流程不被篡改；个性化步骤定义为抽象方法交给子类实现。
▶ 关联：第 13 章会再次深化模板方法模式。

**10.** 下列代码的运行结果是（　）

```java
class Card {
    public void discount() { System.out.println("普通卡：无折扣"); }
}
class StudentCard extends Card {
    @Override
    public void discount() { System.out.println("学生卡：8折"); }
}
// 测试：
StudentCard sc = new StudentCard();
sc.discount();
```

A. 普通卡：无折扣　B. 学生卡：8折
C. 先输出"普通卡：无折扣"再输出"学生卡：8折"　D. 编译报错

**【答案】** B

**【解析】** 子类重写了 discount()，子类对象调用执行子类版本。重写方法上的 @Override 注解校验通过。

---

### 三、判断题

**1.** 子类可以继承父类的构造器，所以 new 子类对象时只会调用子类构造器。（　）

**【答案】** ✗ 错误

**【解析】** 构造器不能被继承。new 子类对象时子类构造器第一行先 super(...) 调用父类构造器，父类成员初始化完后子类构造器才继续——"先有父，后有子"。

**2.** 父类方法是 public，子类重写时改成 protected 也可以，权限变小不影响程序运行。（　）

**【答案】** ✗ 错误

**【解析】** 重写权限只能放大不能缩小，编译直接报错。原因：父类引用能访问的方法，子类对象必须也能访问（为第 9 章多态铺路）。

**3.** final 修饰的引用类型变量，它指向的对象里的成员属性也完全不能修改。（　）

**【答案】** ✗ 错误

**【解析】** final 锁的是变量存的地址值，不能让它指向新对象；对象内部属性可以正常修改。

**4.** 抽象类虽然不能实例化，但可以定义构造器，供子类构造器通过 super(...) 调用。（　）

**【答案】** ✓ 正确

**【解析】** 抽象类本质是"特殊的父类"，构造器在子类初始化父类成员时执行。

**5.** Java 中一个类只能有一个直接父类，但可以通过多层继承间接拥有多个祖先类。（　）

**【答案】** ✓ 正确

**【解析】** 如 `ColdPackage extends ExpressPackage`，而 ExpressPackage 默认继承 Object，ColdPackage 间接继承 Object，天然拥有 toString() 等方法。

---

### 四、简答题

**1.** 简述方法重写（Override）的规则，并对比它与方法重载（Overload）的区别。

**【答案与解析】**

重写规则：① 发生在父子类之间；② 方法名、参数列表、返回值类型与父类完全一致；③ 子类权限 ≥ 父类（public > protected > default > private）；④ private、static 方法不能重写；⑤ 建议加 @Override。

| 对比 | 重写 Override | 重载 Overload |
| --- | --- | --- |
| 位置 | 父子类之间 | 同一个类中 |
| 方法名 | 相同 | 相同 |
| 参数列表 | 必须相同 | 必须不同（个数/类型/顺序） |
| 返回值 | 必须一致 | 无要求 |
| 权限 | 只能放大 | 无要求 |
| 绑定时机 | 运行时（多态） | 编译期 |

▶ 关联：重载见第 4 章；重写是第 9 章多态"编译看左边、运行看右边"的实现基础。

**2.** 对比 this 与 super 的三种用法，并说明 this(...) 和 super(...) 为什么不能同时出现在一个构造器中。

**【答案与解析】**

| 关键字 | 成员变量 | 成员方法 | 构造方法 |
| --- | --- | --- | --- |
| this（本类对象引用） | `this.变量` | `this.方法()` | `this()` / `this(参数)` |
| super（父类存储空间标识） | `super.变量` | `super.方法()` | `super()` / `super(参数)` |

不能共存的原因：二者都**必须写在构造器第一行**，争夺同一个位置。this(...) 调用的本类其他构造器，其第一行仍会执行 super(...)，所以父类初始化只会发生一次。

**3.** 抽象类有哪些特点？为什么它不能实例化却可以有构造器？

**【答案与解析】**

特点：`abstract class` 定义；抽象方法无方法体；有抽象方法的类一定是抽象类，反之不然；不能 new；可以有构造器、普通方法、成员变量；子类必须重写全部抽象方法，否则自己也声明为 abstract；abstract 不能与 final/private/static 共用。

有构造器的原因：子类 super(...) 要调用它初始化继承来的父类成员。不能实例化的原因：抽象方法没有方法体，假如允许 new，调用抽象方法时无代码可执行，Java 从语法上直接禁止。
▶ 关联：抽象类与接口的对比见第 9、12 章。

---

### 五、代码阅读题

**1.** 写出下列代码的运行结果：

```java
class Shape {
    public Shape() { System.out.println("一个图形被创建"); }
}
class Circle extends Shape {
    public Circle() { System.out.println("一个圆形被创建"); }
    public Circle(double r) {
        System.out.println("一个半径为" + r + "的圆形被创建");
    }
}
// 测试：
new Circle();
System.out.println("--------");
new Circle(2.5);
```

**【答案】**

```
一个图形被创建
一个圆形被创建
--------
一个图形被创建
一个半径为2.5的圆形被创建
```

**【解析】** 每次 new 子类对象，子类构造器第一行都隐含 super()，先执行父类构造器，再执行子类构造器体。有参构造器里没有手写 super(...)，默认仍调用父类无参构造器。

**2.** 写出下列代码的运行结果：

```java
class Card {
    String holder;
    public Card(String holder) { this.holder = holder; }
    public void consume(double money) {
        System.out.println(holder + "实际扣款" + money + "元");
    }
}
class StudentCard extends Card {
    public StudentCard(String holder) { super(holder); }
    @Override
    public void consume(double money) {
        System.out.print("学生卡享8折，");
        super.consume(money * 0.8);
    }
}
// 测试：
new StudentCard("小王").consume(50);
```

**【答案】**

```
学生卡享8折，小王实际扣款40.0元
```

**【解析】** 子类重写 consume 实现折扣逻辑，再通过 `super.consume(...)` 复用父类的扣款打印逻辑——重写不代表父类代码作废，super 可以随时调用父类版本。构造器中 super(holder) 把姓名传给父类初始化。

**3.** 下列代码哪些行会编译报错？说明原因：

```java
public class Test {
    public static final double FREE_WEIGHT = 1.0;   // 常量
    public static void main(String[] args) {
        // FREE_WEIGHT = 2.0;                      // ①
        final double[] fees = {8.0, 10.0, 12.0};
        fees[0] = 8.5;                             // ②
        // fees = new double[4];                   // ③
        System.out.println(fees[0]);
    }
}
```

**【答案】** ① 和 ③ 报错（注释状态下不参与编译；放开注释则报错）。

**【解析】** ① static final 常量不能重新赋值；② final 数组的**元素内容**可以改，合法；③ 让 fees 指向新数组 = 修改地址值，final 禁止，报错。按当前代码运行输出 8.5。

**4.** 写出下列代码的运行结果：

```java
abstract class Drink {
    public final void make() {   // 模板方法
        System.out.println("第1步：取干净杯子");
        brew();
        addCondiment();
        System.out.println("第4步：放入封口机封口");
    }
    public abstract void brew();
    public abstract void addCondiment();
}
class Tea extends Drink {
    @Override public void brew() { System.out.println("第2步：冲泡乌龙茶叶"); }
    @Override public void addCondiment() { System.out.println("第3步：加入两片柠檬"); }
}
// 测试：
new Tea().make();
```

**【答案】**

```
第1步：取干净杯子
第2步：冲泡乌龙茶叶
第3步：加入两片柠檬
第4步：放入封口机封口
```

**【解析】** final 模板方法 make() 定义固定流程，其中 brew、addCondiment 两个抽象步骤在运行时执行子类 Tea 的实现。Tea 无法重写 make() 打乱流程。

**5.** 下列代码能否编译通过？若不能请改正：

```java
public abstract class Shape {
    public abstract double area();
}
public class Rectangle extends Shape {
    private double length;
    private double width;
    // 构造器、getter/setter 省略
}
```

**【答案】** 不能通过。Rectangle 继承抽象类 Shape 却没有重写抽象方法 area()。

**【解析】** 两种改法：① Rectangle 中实现 `@Override public double area(){ return length * width; }`；② 把 Rectangle 也声明为 `abstract class`，把实现责任继续向下传递。
▶ 关联：第 9 章接口同理——实现类必须重写接口的全部抽象方法。

---

### 六、编程题（由易到难）

#### 编程题 1（易）：图形面积体系——继承与 super

**需求：**
1. 编写父类 `Shape`（图形）：属性 `name`（图形名称），提供有参构造器；方法 `introduce()` 输出"这是一个：xxx"。
2. 编写子类 `Circle`（圆形）：属性 `radius`（半径），构造器用 super 初始化名称；方法 `area()` 返回面积 `π × r²`。
3. 编写子类 `Rectangle`（矩形）：属性 `length`、`width`，方法 `area()` 返回 `长 × 宽`。
4. 测试：半径 2 的圆形、长 3 宽 4 的矩形，分别介绍自己并打印面积（保留两位小数）。

**【参考答案】**

```java
public class Shape {
    String name;

    public Shape(String name) {
        this.name = name;
    }

    public void introduce() {
        System.out.println("这是一个：" + name);
    }
}
```

```java
public class Circle extends Shape {
    double radius;

    public Circle(String name, double radius) {
        super(name);          // 把名称交给父类构造器初始化
        this.radius = radius;
    }

    public double area() {
        return Math.PI * radius * radius;
    }
}
```

```java
public class Rectangle extends Shape {
    double length;
    double width;

    public Rectangle(String name, double length, double width) {
        super(name);
        this.length = length;
        this.width = width;
    }

    public double area() {
        return length * width;
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Circle c = new Circle("圆形", 2);
        c.introduce();
        System.out.printf("面积：%.2f%n", c.area());

        Rectangle r = new Rectangle("矩形", 3, 4);
        r.introduce();
        System.out.printf("面积：%.2f%n", r.area());
    }
}
```

**运行结果：**

```
这是一个：圆形
面积：12.57
这是一个：矩形
面积：12.00
```

**【解析】**
- `extends Shape` 后，Circle/Rectangle 直接拥有 name 属性和 introduce() 方法，共性代码只写一遍；
- 子类构造器第一行 `super(name)` 调用父类有参构造器初始化名称——这正是"先父后子"；
- 子类各自新增 area()，体现"父类放共性、子类放特性"。
▶ 关联：构造器与 this 的基础见第 7 章；下一题练习方法重写。

---

#### 编程题 2（中）：校园卡消费——方法重写与 super 复用

**需求：**
1. 父类 `Card`（校园卡）：私有属性 `holder`（持卡人）、`balance`（余额）；有参构造器；`deposit(money)` 充值并打印；`consume(money)` 消费扣款（余额不足则提示，扣款后打印余额）。
2. 子类 `StudentCard`（学生卡）：重写 consume，消费时**先打 8 折**再扣款，打印折扣提示。
3. 子类 `TeacherCard`（教师卡）：重写 consume，消费时**打 9 折**。
4. 测试：学生"小王"充值 100 元后消费 50 元；教师"李老师"充值 200 元后消费 100 元。

**【参考答案】**

```java
public class Card {
    private String holder;
    private double balance;

    public Card(String holder) {
        this.holder = holder;
    }

    public void deposit(double money) {
        balance += money;
        System.out.println(holder + "充值" + money + "元，当前余额：" + balance + "元");
    }

    public void consume(double money) {
        if (money > balance) {
            System.out.println(holder + "余额不足，消费失败");
            return;
        }
        balance -= money;
        System.out.println(holder + "扣款" + money + "元，当前余额：" + balance + "元");
    }
}
```

```java
public class StudentCard extends Card {
    public StudentCard(String holder) {
        super(holder);
    }

    @Override
    public void consume(double money) {
        System.out.print("学生卡专享8折，");
        super.consume(money * 0.8);   // 打折后复用父类扣款逻辑
    }
}
```

```java
public class TeacherCard extends Card {
    public TeacherCard(String holder) {
        super(holder);
    }

    @Override
    public void consume(double money) {
        System.out.print("教师卡专享9折，");
        super.consume(money * 0.9);
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        StudentCard sc = new StudentCard("小王");
        sc.deposit(100);
        sc.consume(50);

        System.out.println("--------");

        TeacherCard tc = new TeacherCard("李老师");
        tc.deposit(200);
        tc.consume(100);
    }
}
```

**运行结果：**

```
小王充值100.0元，当前余额：100.0元
学生卡专享8折，小王扣款40.0元，当前余额：60.0元
--------
李老师充值200.0元，当前余额：200.0元
教师卡专享9折，李老师扣款90.0元，当前余额：110.0元
```

**【解析】**
- 重写三一致：方法名 consume、参数列表 `(double)`、返回值 void 与父类完全相同，权限都是 public，加 @Override 校验；
- 余额 balance 是 private，子类不能直接访问，但子类调用 `super.consume(...)` 时进入父类方法，父类方法操作自己的私有属性完全合法——这是封装（第 7 章）与继承的配合；
- 折扣逻辑各子类不同（重写），扣款/校验逻辑复用父类（super 调用），代码没有重复。
▶ 关联：这种写法在第 9 章多态中会升级为 `Card c = new StudentCard(); c.consume(50);`，父类引用调子类方法。

---

#### 编程题 3（中）：快递运费计价——抽象类、重写与常量

**需求：**
1. 定义抽象类 `ExpressPackage`（快递包裹）：属性 `id`（运单号）、`weight`（重量 kg）；有参构造器；**抽象方法** `calcFee()` 返回运费；**final 方法** `printWaybill()` 打印运单（单号、重量、运费，运费通过 calcFee() 计算）。
2. 普通包裹 `StandardPackage`：首重 1kg 收 8 元，超出部分每 kg 加收 2 元（用 `static final` 常量表示费率）。
3. 冷链包裹 `ColdPackage`：每 kg 12 元，另收 5 元包装费。
4. 测试：3kg 普通包裹、2kg 冷链包裹，分别打印运单。

**【参考答案】**

```java
public abstract class ExpressPackage {
    String id;
    double weight;

    public ExpressPackage(String id, double weight) {
        this.id = id;
        this.weight = weight;
    }

    // 抽象方法：不同包裹计费方式不同，交给子类
    public abstract double calcFee();

    // final 方法：运单格式统一，不许子类篡改
    public final void printWaybill() {
        System.out.println("运单号：" + id + "，重量：" + weight + "kg，应付运费：" + calcFee() + "元");
    }
}
```

```java
public class StandardPackage extends ExpressPackage {
    public static final double BASE_FEE = 8.0;      // 首重费用
    public static final double EXTRA_PER_KG = 2.0;  // 续重单价
    public static final double BASE_WEIGHT = 1.0;   // 首重重量

    public StandardPackage(String id, double weight) {
        super(id, weight);
    }

    @Override
    public double calcFee() {
        if (weight <= BASE_WEIGHT) {
            return BASE_FEE;
        }
        return BASE_FEE + (weight - BASE_WEIGHT) * EXTRA_PER_KG;
    }
}
```

```java
public class ColdPackage extends ExpressPackage {
    public static final double PRICE_PER_KG = 12.0; // 冷链每kg单价
    public static final double PACK_FEE = 5.0;      // 冷链包装费

    public ColdPackage(String id, double weight) {
        super(id, weight);
    }

    @Override
    public double calcFee() {
        return weight * PRICE_PER_KG + PACK_FEE;
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        ExpressPackage p1 = new StandardPackage("SF1001", 3);
        p1.printWaybill();

        ExpressPackage p2 = new ColdPackage("SF1002", 2);
        p2.printWaybill();
    }
}
```

**运行结果：**

```
运单号：SF1001，重量：3.0kg，应付运费：12.0元
运单号：SF1002，重量：2.0kg，应付运费：29.0元
```

**【解析】**
- 运费怎么算父类无法决定，定义为抽象方法强制子类实现；ExpressPackage 因此必须是抽象类，不能 new；
- `printWaybill()` 用 final 修饰：运单格式是公司统一规定，子类只能填 calcFee() 的"空"，不能改打印流程——这是模板方法模式的雏形（编程题 5 完整实现）；
- 费率用 `static final` 常量管理，全大写下划线命名，调价时只改一处；
- 计算验证：普通包裹 8 + (3−1)×2 = 12；冷链 2×12 + 5 = 29。
▶ 关联：static 内存原理与工具类规范见第 7、11 章；final 方法不可重写见本章第三节。

---

#### 编程题 4（中难）：图形绘制系统——抽象类 + final 模板方法 + toString

**需求：**
1. 抽象类 `Shape2`：属性 `name`；构造器；抽象方法 `area()`（面积）、`category()`（图形分类）；
2. **final 模板方法** `draw()`：固定输出"开始绘制 → 名称 → 分类 → 面积（两位小数）→ 绘制完成"，面积通过 area() 取得；
3. 在 Shape2 中重写 `toString()`：返回 `名称（面积：xx）`（提示：父类普通方法中可以调用抽象方法，运行时执行子类版本）；
4. 子类 `Circle2`（半径）、`Rect2`（长、宽）、`Triangle2`（底、高，面积=底×高÷2）实现抽象方法；
5. 测试：圆形（r=2）、矩形（3×4）、三角形（底 4 高 3），分别调用 draw()，并直接打印对象验证 toString()。

**【参考答案】**

```java
public abstract class Shape2 {
    String name;

    public Shape2(String name) {
        this.name = name;
    }

    public abstract double area();
    public abstract String category();

    // final 模板方法：绘制流程固定
    public final void draw() {
        System.out.println("====== 开始绘制 ======");
        System.out.println("名称：" + name);
        System.out.println("分类：" + category());
        System.out.printf("面积：%.2f%n", area());
        System.out.println("====== 绘制完成 ======");
    }

    @Override
    public String toString() {
        return name + "（面积：" + String.format("%.2f", area()) + "）";
    }
}
```

```java
public class Circle2 extends Shape2 {
    double radius;

    public Circle2(String name, double radius) {
        super(name);
        this.radius = radius;
    }

    @Override public double area() { return Math.PI * radius * radius; }
    @Override public String category() { return "曲线图形"; }
}
```

```java
public class Rect2 extends Shape2 {
    double length;
    double width;

    public Rect2(String name, double length, double width) {
        super(name);
        this.length = length;
        this.width = width;
    }

    @Override public double area() { return length * width; }
    @Override public String category() { return "四边形"; }
}
```

```java
public class Triangle2 extends Shape2 {
    double base;
    double height;

    public Triangle2(String name, double base, double height) {
        super(name);
        this.base = base;
        this.height = height;
    }

    @Override public double area() { return base * height / 2; }
    @Override public String category() { return "三角形"; }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Shape2[] shapes = {
            new Circle2("圆形", 2),
            new Rect2("矩形", 3, 4),
            new Triangle2("三角形", 4, 3)
        };
        for (Shape2 s : shapes) {
            s.draw();
            System.out.println("直接打印对象：" + s);
            System.out.println();
        }
    }
}
```

**运行结果：**

```
====== 开始绘制 ======
名称：圆形
分类：曲线图形
面积：12.57
====== 绘制完成 ======
直接打印对象：圆形（面积：12.57）

====== 开始绘制 ======
名称：矩形
分类：四边形
面积：12.00
====== 绘制完成 ======
直接打印对象：矩形（面积：12.00）

====== 开始绘制 ======
名称：三角形
分类：三角形
面积：6.00
====== 绘制完成 ======
直接打印对象：三角形（面积：6.00）
```

**【解析】**
- `draw()` 是 final 模板方法：流程（开始→信息→结束）固定，子类不能改；变化的 area()、category() 定义为抽象方法由子类填充；
- 父类 toString() 中调用抽象方法 area() 完全合法——运行时 this 是哪个子类对象就执行哪个子类的 area()，这是多态的前兆（第 9 章）；
- 直接打印对象 `s` 自动调用 toString()，不再输出"全类名@哈希值"地址，说明重写生效（Object 类知识）；
- 数组类型用父类 Shape2，装任意子类对象，遍历统一调用 draw()——新增图形只需继承 Shape2，旧代码一行不改。
▶ 关联：Object/toString 见本章第二节；多态数组的正式讲解在第 9、12 章。

---

#### 编程题 5（难）：饮品店出餐系统——模板方法设计模式综合

**需求：** 饮品店所有饮品遵循统一制作流程，但不同饮品的主料和配料不同。请用模板方法模式实现：

1. 抽象模板类 `DrinkTemplate`：
   - **final 模板方法** `make()` 固定五步流程：取杯 → 冲泡主料 → 添加配料 → 封口 → 报价；
   - "取杯""封口""报价动作"是所有饮品完全相同的固定步骤（父类 private 方法写死）；
   - "冲泡主料" `brew()`、"添加配料" `addCondiment()`、"售价" `getPrice()` 是个性化内容，定义为抽象方法；
2. 子类 `MilkTea`（奶茶）：冲泡奶茶汤底、加黑糖珍珠、售价 12 元；
3. 子类 `Coffee`（咖啡）：萃取浓缩咖啡液加热水、加海盐奶盖、售价 18 元；
4. 子类 `LemonTea`（柠檬茶）：冲泡红茶汤底加冰、加鲜柠檬片、售价 10 元；
5. 测试：三种饮品依次出餐。

**【参考答案】**

```java
public abstract class DrinkTemplate {
    // 模板方法：final 锁死出餐流程
    public final void make() {
        takeCup();
        brew();
        addCondiment();
        seal();
        quote();
    }

    // 固定步骤：所有饮品相同，private 写死
    private void takeCup() {
        System.out.println("第1步：取出定制饮品杯");
    }
    private void seal() {
        System.out.println("第4步：放入封口机封口");
    }
    private void quote() {
        System.out.println("第5步：本杯售价" + getPrice() + "元");
    }

    // 个性化步骤：子类必须实现
    public abstract void brew();
    public abstract void addCondiment();
    public abstract int getPrice();
}
```

```java
public class MilkTea extends DrinkTemplate {
    @Override
    public void brew() {
        System.out.println("第2步：倒入冲泡好的奶茶汤底");
    }
    @Override
    public void addCondiment() {
        System.out.println("第3步：加入一勺黑糖珍珠");
    }
    @Override
    public int getPrice() {
        return 12;
    }
}
```

```java
public class Coffee extends DrinkTemplate {
    @Override
    public void brew() {
        System.out.println("第2步：萃取浓缩咖啡液，加入热水");
    }
    @Override
    public void addCondiment() {
        System.out.println("第3步：铺上一层海盐奶盖");
    }
    @Override
    public int getPrice() {
        return 18;
    }
}
```

```java
public class LemonTea extends DrinkTemplate {
    @Override
    public void brew() {
        System.out.println("第2步：冲泡红茶汤底并加冰");
    }
    @Override
    public void addCondiment() {
        System.out.println("第3步：加入两片鲜柠檬");
    }
    @Override
    public int getPrice() {
        return 10;
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        DrinkTemplate[] drinks = { new MilkTea(), new Coffee(), new LemonTea() };
        for (DrinkTemplate d : drinks) {
            d.make();
            System.out.println("--------");
        }
    }
}
```

**运行结果：**

```
第1步：取出定制饮品杯
第2步：倒入冲泡好的奶茶汤底
第3步：加入一勺黑糖珍珠
第4步：放入封口机封口
第5步：本杯售价12元
--------
第1步：取出定制饮品杯
第2步：萃取浓缩咖啡液，加入热水
第3步：铺上一层海盐奶盖
第4步：放入封口机封口
第5步：本杯售价18元
--------
第1步：取出定制饮品杯
第2步：冲泡红茶汤底并加冰
第3步：加入两片鲜柠檬
第4步：放入封口机封口
第5步：本杯售价10元
--------
```

**【解析】**
- 模板方法模式三要素：① final 模板方法 make() 固定五步骨架，子类不能重写；② 固定步骤（取杯、封口、报价动作）抽到父类 private 方法写死；③ 个性化步骤定义为抽象方法，子类只填这些"空"；
- 报价动作固定（都要打印"第5步：本杯售价x元"）但金额因饮品而异，所以 quote() 是父类普通方法、getPrice() 是抽象方法——模板方法中调用抽象方法是该模式的常用手法；
- 新增饮品（如"芒果果茶"）只需继承 DrinkTemplate 并实现 3 个抽象方法，流程代码一行不动——对扩展开放、对修改关闭；
- 抽象类不能 new，但数组 `DrinkTemplate[]` 装的是子类对象，make() 执行父类 final 方法，其内部抽象方法调用动态绑定到子类实现。
▶ 关联：抽象类语法（本章第四节）+ final 锁方法（第三节）在此联合落地；第 13 章会再次深化该模式；"父类模板调子类实现"的机制本质就是多态（第 9、12 章）。

---

### 本章知识网络回顾

```
继承 extends（前提：共性 + is-a）
  ├─ 成员变量：就近原则（局部→本类→父类），this / super 区分
  ├─ 成员方法：重写 Override（同名同参同返回、权限放大、@Override；private/static 不能重写）
  ├─ 构造器：不能继承；第一行 super(...)；先父后子；this(...)/super(...) 互斥
  └─ 特点：单继承、多层继承、一个父类多个子类
Object：所有类的根类 → toString() 默认"全类名@十六进制哈希值"，重写后打印内容
final：类不可继承 / 方法不可重写 / 变量不可改值（引用类型锁地址不锁内容）
       static final = 常量（全大写、下划线分词）
抽象类 abstract：抽象方法无方法体；不能 new；可有构造器和普通方法；
       子类重写全部抽象方法（否则自己也 abstract）；abstract 与 final/private/static 互斥
模板方法模式：final 模板方法定流程骨架 + 抽象方法交子类填个性化步骤
```

---

<div style="page-break-after: always;"></div>

## 第9章 面向对象高级（下）·习题精讲

> 本章覆盖：接口（interface/implements）、抽象类与接口对比、JDK8/9 接口新特性（default/static/private）、多态（三前提、成员访问规律、转型与 instanceof）、equals 与 Objects、代码块、package 包、内部类（重点匿名内部类）、Lambda 入门。
>
> 建议做法：先独立做题，再对答案、看解析。解析中"▶ 关联"标出与其他章节的联系，帮你把知识串成网。所有编程题均为原创业务场景，考查的知识点与课堂案例一致但代码全部重新设计。

---

### 一、填空题

**1.** 定义接口使用关键字 ______，类实现接口使用关键字 ______；一个类可以实现 ______ 个接口。

**【答案】** `interface`；`implements`；多（多个）

**【解析】** 接口是"规范/契约"，用 `interface 接口名{}` 定义；类用 `class 类名 implements 接口1,接口2{}` 实现。类与类只能单继承，但类可以实现多个接口——这正是接口"弥补单继承不足"的价值。实现类必须重写接口的**全部抽象方法**，否则该类要定义为抽象类。
▶ 关联：接口与多态配合是第16章集合遍历（`Collection` 接口接收任意集合）、第21章 `Runnable` 线程任务的基础。

---

**2.** JDK 7 及以前，接口中的成员变量默认带有修饰符 ______（三个），所以它们本质是 ______；接口中的成员方法默认带有修饰符 ______（两个），且没有 ______。

**【答案】** `public static final`；常量；`public abstract`；构造方法

**【解析】** 接口里写 `int AGE = 18;` 等价于 `public static final int AGE = 18;`，必须赋值、不能修改、可用接口名直接访问；方法写 `void show();` 等价于 `public abstract void show();`，没有方法体。接口不能创建对象、也没有构造方法（它没有实例变量需要初始化）。

---

**3.** JDK 8 开始接口中可以定义带方法体的方法：用 ______ 关键字修饰的默认方法和 ______ 方法；JDK 9 又新增了 ______ 方法，用于在接口内部抽取公共逻辑。

**【答案】** `default`；静态（`static`）；私有（`private`）

**【解析】**
- 默认方法 `public default void show(){}`：解决**接口升级**问题——接口新增方法时，老实现类不用改代码就能直接继承使用；实现类也可以重写（重写时**去掉 default**）。
- 静态方法 `public static void show(){}`：只能用**接口名**调用，不能用实现类对象调用。
- 私有方法（JDK9）`private void log(){}`：多个默认方法有重复逻辑时抽出来复用，但不对外暴露（普通私有方法服务默认方法，`private static` 服务静态方法）。

▶ 关联：接口升级思想在第14章 JDK8 日期时间 API、第21章线程池接口中大量体现——JDK 给老接口加 default 方法从不破坏已有代码。

---

**4.** 实现多态必须同时满足三个前提条件：①有 ______ 关系；②有 ______；③有 ______。

**【答案】** 继承（或实现）；方法重写；父类引用指向子类对象（`Fu f = new Zi();`）

**【解析】** 三条缺一不可：没有继承/实现就没有"父子类型"；没有方法重写，调用时执行的还是父类逻辑，体现不出"同一个行为多种表现"；没有父引用指子对象（向上转型），编译期就无法用统一类型接收。接口多态写法为 `接口名 变量 = new 实现类();`。

---

**5.** 多态下访问成员的口诀：成员变量"编译看 ______，运行看 ______"；成员方法"编译看 ______，运行看 ______"；静态方法"编译看 ______，运行看 ______"。

**【答案】** 左边（父类）；左边（父类）；左边（父类）；右边（子类）；左边（父类）；左边（父类）

**【解析】**
- 变量：父类引用只能访问父类空间的数据，取父类的值；
- 方法：运行时动态绑定到子类重写后的方法，这才是多态的核心；
- 静态方法：属于类不属于对象，`父类型.方法()` 在字节码里直接解析成父类的静态调用，与对象无关，所以静态方法不能被重写（加 `@Override` 会报错）。

---

**6.** 向下转型（父类引用转子类类型）时，如果对象的实际类型与目标类型不匹配，会抛出 ______ 异常；为避免该异常，应先用关键字 ______ 判断对象的真实类型。

**【答案】** `ClassCastException`（类型转换异常）；`instanceof`

**【解析】** 父类引用实际装着 A 子类对象，却强转成 B 子类类型，编译能过（都是父类的子类），运行时抛 ClassCastException。规范写法：`if (n instanceof SmsNotifier) { ((SmsNotifier) n).特有方法(); }`。`instanceof` 判断"左边对象是否是右边类型（或其子类）的实例"，返回 boolean。

---

**7.** 一个类中三种代码块的执行顺序是：______ → ______ → 构造方法；其中只在类加载时执行一次的是 ______，每创建一个对象都执行一次的是 ______。

**【答案】** 静态代码块；构造代码块（实例代码块）；静态代码块；构造代码块

**【解析】** 静态代码块 `static{}` 随类加载执行、全类一次，适合初始化只需执行一次的固定数据（如加载配置、驱动）；构造代码块 `{}` 在每次 new 对象时、构造方法执行**之前**执行，适合抽取所有构造器的重复代码；局部代码块（方法里的 `{}`）作用是限定变量生命周期。
▶ 关联：static 与类加载时机在第11章有更深入的讲解。

---

**8.** Lambda 表达式只能简化 ______ 接口的匿名内部类，这种接口可以用注解 ______ 标记校验；Lambda 的语法格式是 ______。

**【答案】** 函数式（有且仅有一个抽象方法的）；`@FunctionalInterface`；`(参数列表) -> {方法体}`

**【解析】** 函数式接口 = 接口 + 恰好一个抽象方法（default/static 方法不算）。Lambda 把"创建实现类对象 + 重写方法"压缩成一段箭头表达式。省略规则：参数类型可省；只有一个参数时 `()` 可省；方法体只有一行时 `{}`、分号、`return` 一起省。
▶ 关联：第15章会学方法引用（`类名::方法`）进一步简化 Lambda，以及 `Consumer`/`Predicate` 等 JDK 内置函数式接口；第18章 Stream 流的每个参数几乎都是 Lambda。

---

### 二、选择题

**1.** 下列关于接口成员的说法，正确的是（　）

A. 接口中可以定义构造方法
B. 接口中的成员变量可以不赋值
C. 接口中的方法默认是 `public abstract`
D. 接口中可以定义普通实例变量

**【答案】** C

**【解析】** 接口没有构造方法（A 错）；成员变量是 `public static final` 常量，必须赋值（B 错）；接口里只能写常量、不能写普通实例变量（D 错）。记忆：JDK7 接口 = 常量 + 抽象方法。

---

**2.** 阅读代码，输出结果是（　）

```java
class Device {
    String type = "通用设备";
    public void play() { System.out.println("设备播放中"); }
}
class Phone extends Device {
    String type = "手机";
    public void play() { System.out.println("手机播放音乐"); }
}
public class Test {
    public static void main(String[] args) {
        Device d = new Phone();
        System.out.println(d.type);
        d.play();
    }
}
```

A. 手机　手机播放音乐　　B. 通用设备　手机播放音乐　　C. 通用设备　设备播放中　　D. 手机　设备播放中

**【答案】** B

**【解析】** `d.type`：成员变量编译运行都看左边 Device，输出"通用设备"；`d.play()`：成员方法编译看左（Device 有 play 才能编译通过）、运行看右（动态绑定 Phone 重写的 play），输出"手机播放音乐"。变量不具备多态性，方法具备多态性——这是最常考的点。

---

**3.** 接口 `Gateway` 中定义了 `public static void version(){}`，正确的调用方式是（　）

A. `new GatewayImpl().version()`
B. `Gateway.version()`
C. `GatewayImpl.version()`
D. 实现类对象直接 `version()`

**【答案】** B

**【解析】** 接口的静态方法属于接口本身，只能用"接口名.方法名()"调用，不能通过实现类名或实现类对象调用（这和类的静态方法能用子类名调用不同）。

---

**4.** 一个类同时实现接口 A 和接口 B，两个接口中有同名的默认方法 `default void m()` 且逻辑不同，下列说法正确的是（　）

A. 编译时自动选择 A 的版本
B. 实现类必须重写 m()，否则编译报错
C. 可以在实现类中用 `A.m()` 调用 A 的版本
D. 默认方法不能被重写

**【答案】** B

**【解析】** 两个默认方法同名同参但逻辑冲突，编译器不知道该继承哪个，实现类**必须重写**；重写后若想复用某接口的逻辑，用 `A.super.m();`（注意是 `接口名.super.方法名()`，不是 `A.m()`）。

---

**5.** 下列代码的输出结果是（　）

```java
String s1 = "abc";
String s2 = "abc";
String s3 = new String("abc");
System.out.println(s1 == s2);
System.out.println(s1 == s3);
System.out.println(s1.equals(s3));
```

A. true true true　　B. true false true　　C. false false true　　D. true false false

**【答案】** B

**【解析】** `s1`、`s2` 都是字面量，字符串常量池中只存一份，地址相同，`==` 为 true；`s3` 是 new 出来的新对象，堆中有独立地址，`==` 为 false；String 重写了 equals 比内容，内容都是 "abc"，equals 为 true。
▶ 关联：字符串常量池与不可变性在第10章有完整内存图解。

---

**6.** 下列代码运行结果是（　）

```java
String s1 = null;
String s2 = "abc";
System.out.println(Objects.equals(s1, s2));
System.out.println(Objects.isNull(s1));
```

A. 报空指针异常
B. false　true
C. true　true
D. false　false

**【答案】** B

**【解析】** `Objects.equals(a,b)` 源码是 `return (a == b) || (a != null && a.equals(b));`——a 为 null 时短路，不再调用 equals，安全返回 false；`Objects.isNull(s1)` 等价于 `s1 == null`，返回 true。注意：Objects.equals 只是"空安全"，底层仍然依赖类自己重写的 equals，没重写还是比地址。
▶ 关联：Objects 是 JDK7 工具类，第14章还会学它的 `requireNonNull` 等方法。

---

**7.** 关于静态代码块，说法正确的是（　）

A. 每次 new 对象都会执行一次
B. 每次调用静态方法都会执行一次
C. 类加载时执行，且只执行一次
D. 执行时机晚于构造方法

**【答案】** C

**【解析】** 静态代码块随类的字节码加载而执行，一个类只加载一次，所以静态块只执行一次，且时机最早（静态块 → 构造块 → 构造方法）。用途：初始化全局只需要一份的固定数据（如配置参数、驱动加载）。

---

**8.** 下列关于匿名内部类和 Lambda 的说法，错误的是（　）

A. `new 接口(){ 重写方法 }` 本质是创建了该接口的一个实现类对象
B. 匿名内部类可以基于接口、抽象类或普通类创建
C. 只要是匿名内部类就都能用 Lambda 改写
D. Lambda 要求接口中有且仅有一个抽象方法

**【答案】** C

**【解析】** Lambda 只能简化**函数式接口**的匿名内部类；基于抽象类（哪怕只有一个抽象方法）的、或接口有多个抽象方法的匿名内部类都不能用 Lambda。匿名内部类本质是"一个没有名字的局部内部类 + 立刻创建它的对象"。

---

### 三、判断题

**1.** 接口中可以定义构造方法，方便实现类初始化。（　）

**【答案】** ✗

**【解析】** 接口不能创建对象、没有实例成员需要初始化，因此没有构造方法。有构造方法的是抽象类（供子类 super 调用）。
▶ 关联：抽象类有构造方法的原因见第8章子类构造器执行流程。

**2.** 多态形式下，`Notifier n = new SmsNotifier();` 可以直接写 `n.sendSignature();` 调用短信渠道的特有方法。（　）

**【答案】** ✗

**【解析】** 编译看左边，Notifier 接口中没有 sendSignature 方法，直接编译报错。必须向下转型：`((SmsNotifier) n).sendSignature();`，且转型前要用 instanceof 判断。

**3.** 静态代码块在每次创建对象时都会执行。（　）

**【答案】** ✗

**【解析】** 静态代码块随**类加载**执行且仅一次；每次创建对象都执行的是构造代码块和构造方法。

**4.** Lambda 表达式可以简化所有匿名内部类的写法。（　）

**【答案】** ✗

**【解析】** 只能简化函数式接口（一个抽象方法）的匿名内部类；基于抽象类/普通类的、或接口有多个抽象方法的都不行。

**5.** 接口与接口之间是多继承关系，一个接口可以同时继承多个接口。（　）

**【答案】** ✓

**【解析】** `interface C extends A, B {}` 合法；类实现 C 时要重写 A、B、C 三个接口的全部抽象方法。对比记忆：类与类单继承、多层继承；类与接口多实现；接口与接口多继承。

**6.** 接口中的 default 默认方法，实现类必须全部重写。（　）

**【答案】** ✗

**【解析】** 默认方法**不强制**重写（这正是它解决接口升级的意义——老实现类零改动）；但可以重写，重写时去掉 default 关键字。只有抽象方法才是必须重写的。

---

### 四、简答题

**1.** 请从成员变量、成员方法、构造方法、相互关系四个方面对比抽象类和接口，并说明各自的使用场景。

**【答案】**

| 对比项 | 抽象类 | 接口 |
| --- | --- | --- |
| 成员变量 | 可以有变量、也可以有常量 | 只能是常量（public static final） |
| 成员方法 | 可以有抽象方法、也可以有具体方法 | JDK8 前只能抽象；之后可有 default/static 方法；JDK9 可有 private 方法 |
| 构造方法 | 有（给子类用） | 没有 |
| 关系 | 类与类单继承（可多层） | 类多实现；接口间多继承 |

使用场景：**抽象类描述"事物是什么"**（is-a 的共性抽取），比如校园门禁系统里，员工卡和访客卡都有卡号、持有人这些共性数据，但开门逻辑不同，可把共性抽到抽象的"门禁卡"类中；**接口制定"行为规范/能做什么"**（like-a 的能力扩展），比如"通知发送"规范，短信、邮件、站内信各自实现。经验：优先用接口（灵活、可多实现），需要共享成员变量或构造逻辑时用抽象类。

---

**2.** 多态的好处和弊端分别是什么？实际开发中如何扬长避短？

**【答案】**

- **好处（提高扩展性）**：方法形参定义为父类/接口类型，就能接收该类型的**任意子类对象**。例如通知系统中 `dispatch(Notifier n, String msg)` 一个方法通吃短信、邮件、站内信三种实现，以后新增"微信通知"渠道，这个方法一行不改。这就是"面向接口编程"。
- **弊端**：父类引用不能直接调用子类特有的属性和方法（编译看左边）。
- **扬长避短**：共性行为（send 发送）直接用多态调用；需要子类特有行为（如短信渠道加签名、邮件渠道加附件）时，先用 `instanceof` 判断真实类型，再向下转型调用。

▶ 关联：第16章集合的 `Iterator`、第21章 `Runnable r = new 任务类()` 都是这个套路。

---

**3.** 简述多态下访问成员变量、成员方法、静态方法各自的"编译/运行看哪边"规律，并解释原因。

**【答案】**

- **成员变量：编译看左、运行看左。** 编译期检查父类有没有该变量；运行期父类引用只能访问父类空间的值（变量不覆盖、不动态绑定）。
- **成员方法：编译看左、运行看右。** 编译期检查父类有没有该方法；运行期 JVM 根据对象的**实际类型**动态绑定子类重写的方法——多态的体现。
- **静态方法：编译看左、运行看左。** 静态方法属于类，`父类型.方法()` 编译后就是父类的静态调用，与对象无关，因此静态方法不存在重写。

---

**4.** 简述 `==` 和 `equals()` 的区别；为什么重写 equals 时通常还要重写 hashCode？

**【答案】**

- `==`：基本类型比值；引用类型比**地址**（是否同一个对象）。
- `equals()`：Object 默认实现就是 `==`（比地址）；String、Integer 等类重写后比**内容**；自定义类想让"内容相同即相等"必须重写 equals（IDEA 中 Alt+Insert 生成）。
- 重写 equals 就要重写 hashCode：Java 规定"两个对象 equals 相等，hashCode 必须相同"。HashSet 去重、HashMap 存键时先比 hashCode 再比 equals（第17章详解），若不重写 hashCode，两个内容相同的对象会进不同的哈希桶，集合认为它们不相等，去重失效。

▶ 关联：hashCode 与哈希表原理见第17章 Set/Map 集合。

---

### 五、代码阅读题

**1.** 阅读代码，写出程序输出。

```java
class Shape {
    String name = "图形";
    public void draw() { System.out.println("绘制图形"); }
    public static void info() { System.out.println("Shape-图形信息"); }
}
class Circle extends Shape {
    String name = "圆形";
    public void draw() { System.out.println("绘制圆形"); }
    public static void info() { System.out.println("Circle-圆形信息"); }
}
public class Demo {
    public static void main(String[] args) {
        Shape s = new Circle();
        System.out.println(s.name);
        s.draw();
        s.info();
    }
}
```

**【答案】**

```
图形
绘制圆形
Shape-图形信息
```

**【解析】**
- `s.name`：变量看左 → Shape 的 name = "图形"；
- `s.draw()`：普通方法运行看右 → 动态绑定 Circle 重写版本，输出"绘制圆形"；
- `s.info()`：静态方法看左，字节码等价于 `Shape.info()`，输出"Shape-图形信息"（Circle 里的 info 只是"隐藏"了父类静态方法，不是重写）。

---

**2.** 阅读代码，写出程序输出。

```java
class DatabaseUtil {
    static {
        System.out.println("静态代码块：加载数据库驱动");
    }
    {
        System.out.println("构造代码块：获取数据库连接");
    }
    public DatabaseUtil() {
        System.out.println("构造方法：工具实例就绪");
    }
}
public class Demo {
    public static void main(String[] args) {
        new DatabaseUtil();
        System.out.println("----------");
        new DatabaseUtil();
    }
}
```

**【答案】**

```
静态代码块：加载数据库驱动
构造代码块：获取数据库连接
构造方法：工具实例就绪
----------
构造代码块：获取数据库连接
构造方法：工具实例就绪
```

**【解析】** 第一次 new 时类先加载：静态代码块执行（整个程序仅此一次）；然后每次 new：构造代码块先于构造方法执行。第二次 new 时类已加载，静态块不再执行，构造块和构造方法再来一遍。

---

**3.** 阅读代码，写出程序输出。

```java
interface Notifier {
    void send(String msg);
}
class SmsNotifier implements Notifier {
    public void send(String msg) { System.out.println("短信通知：" + msg); }
    // 短信渠道特有：附带签名
    public void sendSignature() { System.out.println("【短信签名：校园通】"); }
}
class EmailNotifier implements Notifier {
    public void send(String msg) { System.out.println("邮件通知：" + msg); }
    // 邮件渠道特有：添加附件
    public void addAttachment() { System.out.println("邮件已添加成绩单附件"); }
}
public class Demo {
    public static void dispatch(Notifier n, String msg) {
        n.send(msg);
        if (n instanceof SmsNotifier) {
            ((SmsNotifier) n).sendSignature();
        } else if (n instanceof EmailNotifier) {
            ((EmailNotifier) n).addAttachment();
        }
    }
    public static void main(String[] args) {
        dispatch(new SmsNotifier(), "明天开学");
        dispatch(new EmailNotifier(), "成绩单已出");
    }
}
```

**【答案】**

```
短信通知：明天开学
【短信签名：校园通】
邮件通知：成绩单已出
邮件已添加成绩单附件
```

**【解析】** `dispatch(Notifier n, ...)` 是对象多态：形参接口类型接收任意实现类对象。`n.send(msg)` 动态绑定各自重写版本；特有方法先 instanceof 判断真实类型再向下转型调用——若不判断直接强转，传入 EmailNotifier 却转 SmsNotifier 就会 ClassCastException。

---

**4.** 阅读代码，写出程序输出。

```java
interface MemberDiscount {
    default void apply() { System.out.println("会员价9折"); }
}
interface CouponDiscount {
    default void apply() { System.out.println("满100减10"); }
}
class CheckoutService implements MemberDiscount, CouponDiscount {
    @Override
    public void apply() {
        MemberDiscount.super.apply();
        CouponDiscount.super.apply();
        System.out.println("优惠结算完成");
    }
}
public class Demo {
    public static void main(String[] args) {
        new CheckoutService().apply();
    }
}
```

**【答案】**

```
会员价9折
满100减10
优惠结算完成
```

**【解析】** MemberDiscount、CouponDiscount 两个接口的默认方法同名冲突，CheckoutService 必须重写 apply()，否则编译报错；重写中用 `接口名.super.方法名()` 分别调用两个父接口的默认逻辑，再补充自己的结算逻辑。

---

### 六、编程题（共 7 题，由易到难）

#### 编程题 1（基础）：校园通知发送渠道

**需求：** 校园系统要通过多种渠道给师生发通知。定义通知接口 `Notifier`，包含抽象方法 `void send(String target, String content)`；编写三个实现类：短信通知 `SmsNotifier`、邮件通知 `EmailNotifier`、站内信通知 `StationLetterNotifier`，各自打印不同格式的发送信息。在测试类中键盘录入渠道编号（1/2/3），用**多态**接收实现类对象并统一调用 send。

**考查：** 接口定义、implements、向上转型、面向接口编程。

**参考代码：**

```java
import java.util.Scanner;

// 通知接口（规范）
public interface Notifier {
    void send(String target, String content);
}

// 短信渠道
public class SmsNotifier implements Notifier {
    @Override
    public void send(String target, String content) {
        System.out.println("【短信】发送给手机号 " + target + "：" + content);
    }
}

// 邮件渠道
public class EmailNotifier implements Notifier {
    @Override
    public void send(String target, String content) {
        System.out.println("【邮件】发送至邮箱 " + target + "：" + content);
    }
}

// 站内信渠道
public class StationLetterNotifier implements Notifier {
    @Override
    public void send(String target, String content) {
        System.out.println("【站内信】推送给用户 " + target + "：" + content);
    }
}

// 测试类
public class NotifyTest {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("选择通知渠道：1.短信  2.邮件  3.站内信");
        int type = sc.nextInt();

        Notifier notifier;   // 接口引用（多态）
        switch (type) {
            case 1:
                notifier = new SmsNotifier();
                break;
            case 2:
                notifier = new EmailNotifier();
                break;
            case 3:
                notifier = new StationLetterNotifier();
                break;
            default:
                System.out.println("没有该渠道");
                return;   // 直接结束，避免 notifier 为 null
        }

        notifier.send("张同学", "明天上午9点开学，请准时到校");
    }
}
```

**思路讲解：**
1. 接口只定规范（"能发送通知"），不关心具体怎么发；三个实现类各自重写 send，输出渠道特征。
2. `Notifier notifier;` 用接口类型统一接收——这就是向上转型。以后新增"微信通知"渠道，只需写新实现类 + switch 加一个分支，最后一行 `notifier.send(...)` 永远不变。

**运行结果（输入 1）：**

```
选择通知渠道：1.短信  2.邮件  3.站内信
1
【短信】发送给手机号 张同学：明天上午9点开学，请准时到校
```

---

#### 编程题 2（基础）：图书馆门禁卡系统

**需求：** 图书馆门禁有两种卡：读者卡 `ReaderCard` 和管理员卡 `AdminCard`。两种卡都有卡号 `cardId` 和持有人 `owner`，刷卡时都要"开闸"，但提示不同：读者卡提示"读者通道开启，请安静入馆"，管理员卡提示"管理员通道开启，可进入办公区"。请用**抽象类**设计门禁卡（共性数据抽到抽象类，开门方法定义为抽象方法），并用**多态数组**保存 3 张卡，循环调用开门。

**考查：** 抽象类（有成员变量、有构造器、抽象方法）、多态数组、方法重写。

**参考代码：**

```java
// 抽象门禁卡：共性抽取
public abstract class GateCard {
    private String cardId;
    private String owner;

    public GateCard(String cardId, String owner) {
        this.cardId = cardId;
        this.owner = owner;
    }

    public String getOwner() {
        return owner;
    }

    // 开门逻辑因卡种而异，定义为抽象方法强制子类实现
    public abstract void open();
}

// 读者卡
public class ReaderCard extends GateCard {
    public ReaderCard(String cardId, String owner) {
        super(cardId, owner);
    }

    @Override
    public void open() {
        System.out.println(getOwner() + " 刷卡：读者通道开启，请安静入馆");
    }
}

// 管理员卡
public class AdminCard extends GateCard {
    public AdminCard(String cardId, String owner) {
        super(cardId, owner);
    }

    @Override
    public void open() {
        System.out.println(getOwner() + " 刷卡：管理员通道开启，可进入办公区");
    }
}

// 测试类
public class GateTest {
    public static void main(String[] args) {
        GateCard[] cards = {
            new ReaderCard("R-1001", "王同学"),
            new AdminCard("A-002", "李馆长"),
            new ReaderCard("R-1002", "赵同学")
        };

        for (GateCard card : cards) {
            card.open();   // 成员方法：编译看 GateCard，运行看实际卡种
        }
    }
}
```

**思路讲解：**
1. 两种卡"是什么"完全一致（都是门禁卡，都有卡号和持有人），所以用抽象类抽共性数据和构造器——这正是接口做不到的（接口没有构造器、不能写实例变量）。
2. `open()` 是共性行为但逻辑不同，定义为抽象方法：子类不重写就编译报错，保证每张卡都会开门。
3. 数组类型声明为父类 `GateCard[]`，里面装的都是子类对象；循环中 `card.open()` 运行时动态绑定——多态数组。

**运行结果：**

```
王同学 刷卡：读者通道开启，请安静入馆
李馆长 刷卡：管理员通道开启，可进入办公区
赵同学 刷卡：读者通道开启，请安静入馆
```

▶ 关联：抽象类与接口如何取舍，本题与编程题1对照体会；权限修饰符 protected 在继承中的作用见第8/11章。

---

#### 编程题 3（中等）：报表导出器与类型判断

**需求：** 报表系统支持把数据导出为不同格式。定义导出接口 `Exporter`，抽象方法 `void export(String data)`；编写 PDF 导出器 `PdfExporter` 和 Excel 导出器 `ExcelExporter`。Excel 导出器有一个**特有方法** `setSheetName(String name)` 设置工作表名（默认 "Sheet1"），导出时要带上工作表名。编写方法 `doExport(Exporter e, String data)`：共性导出直接多态调用；若是 Excel 导出器，先调用其特有方法把工作表设为"统计数据页"再导出。

**考查：** 多态的弊端、instanceof 判断、向下转型。

**参考代码：**

```java
// 导出接口
public interface Exporter {
    void export(String data);
}

// PDF 导出
public class PdfExporter implements Exporter {
    @Override
    public void export(String data) {
        System.out.println("导出 PDF 文件，内容：" + data);
    }
}

// Excel 导出（含特有方法）
public class ExcelExporter implements Exporter {
    private String sheetName = "Sheet1";

    @Override
    public void export(String data) {
        System.out.println("导出 Excel 文件（工作表：" + sheetName + "），内容：" + data);
    }

    // 子类特有方法
    public void setSheetName(String sheetName) {
        this.sheetName = sheetName;
    }
}

// 测试类
public class ExportTest {
    public static void main(String[] args) {
        doExport(new PdfExporter(), "本月借阅统计");
        doExport(new ExcelExporter(), "本月到馆人次明细");
    }

    // 形参用接口类型：通吃所有导出器
    public static void doExport(Exporter e, String data) {
        // Excel 导出器需要先设置工作表名（子类特有功能）
        if (e instanceof ExcelExporter) {
            ExcelExporter excel = (ExcelExporter) e;   // 向下转型
            excel.setSheetName("统计数据页");
        }
        e.export(data);
    }
}
```

**思路讲解：**
1. `doExport` 形参是 `Exporter`，可以接收任意导出器，共性方法 `export` 直接调用——扩展性好。
2. 但 `setSheetName` 是 ExcelExporter 特有的，父接口中没有，直接写 `e.setSheetName(...)` 编译报错（多态的弊端）。
3. 先用 `instanceof` 判断真实类型，再向下转型调用特有方法；不判断直接强转，遇到 PdfExporter 就会 ClassCastException。

**运行结果：**

```
导出 PDF 文件，内容：本月借阅统计
导出 Excel 文件（工作表：统计数据页），内容：本月到馆人次明细
```

---

#### 编程题 4（中等）：会员去重——重写 equals

**需求：** 体育馆会员系统中，会员卡号 `cardNo` 和手机号 `phone` 相同即视为同一会员（即使姓名录入有出入）。请编写 `Member` 类并重写 `equals`（和 `hashCode`），测试：两个分别 new 出来、卡号手机号相同的会员 equals 结果为 true；使用 `Objects.equals` 比较 null 时不抛空指针。

**考查：** equals 重写三段式、Objects 空安全比较、hashCode 约定。

**参考代码：**

```java
import java.util.Objects;

public class Member {
    private String cardNo;
    private String phone;
    private String name;

    public Member(String cardNo, String phone, String name) {
        this.cardNo = cardNo;
        this.phone = phone;
        this.name = name;
    }

    @Override
    public boolean equals(Object o) {
        // 1. 地址相同：就是同一个对象
        if (this == o) return true;
        // 2. 对方为 null，或类型不一致：不相等
        if (o == null || getClass() != o.getClass()) return false;
        // 3. 向下转型，按业务规则比较关键字段
        Member member = (Member) o;
        return Objects.equals(cardNo, member.cardNo)
                && Objects.equals(phone, member.phone);
    }

    @Override
    public int hashCode() {
        return Objects.hash(cardNo, phone);
    }
}
```

```java
public class MemberTest {
    public static void main(String[] args) {
        Member m1 = new Member("M-001", "13800001111", "张三");
        Member m2 = new Member("M-001", "13800001111", "张三丰");  // 同一人，名字录错
        Member m3 = null;

        System.out.println(m1.equals(m2));            // true（卡号+手机号相同）
        System.out.println(Objects.equals(m1, m2));   // true
        System.out.println(Objects.equals(m3, m1));   // false（空安全，不报错）
        // System.out.println(m3.equals(m1));          // 直接调用会抛 NullPointerException
    }
}
```

**思路讲解：**
1. 不重写 equals 时，Object 版本用 `==` 比地址，两个 new 出来的对象地址不同，结果 false。
2. 重写三段式：先比地址（自己比自己）；再排除 null 和类型不符；最后向下转型逐字段比较。字符串字段用 `Objects.equals` 而不是 `cardNo.equals(...)`，避免字段为 null 时异常。
3. `Objects.equals(m3, m1)` 内部先判断 m3 为 null 直接返回 false，所以不会空指针。
4. hashCode 与 equals 保持一致（都用 cardNo+phone），将来把会员放进 HashSet 去重才不会失效。

**运行结果：**

```
true
true
false
```

▶ 关联：hashCode/equals 在哈希表中的去重流程见第17章 HashSet/HashMap。

---

#### 编程题 5（中等）：系统配置初始化——代码块执行时机

**需求：** 应用启动类 `AppConfig` 中，全局 API 地址 `apiUrl` 只需在类加载时初始化一次（静态代码块中赋值并打印"加载全局配置"）；每创建一个配置实例时，构造代码块打印"准备配置实例"，构造方法再打印具体实例信息。请编写该类，在 main 中分别用无参构造和带参构造创建两个实例，观察并解释输出顺序。

**考查：** 静态代码块、构造代码块、构造方法的执行时机。

**参考代码：**

```java
public class AppConfig {
    public static String apiUrl;   // 全局 API 地址
    private String instanceName;   // 实例名称

    // 静态代码块：类加载时执行一次
    static {
        apiUrl = "https://api.campus.example.com";
        System.out.println("静态代码块：加载全局配置，apiUrl = " + apiUrl);
    }

    // 构造代码块：每次 new 都执行，先于构造方法
    {
        System.out.println("构造代码块：准备配置实例");
    }

    public AppConfig() {
        System.out.println("构造方法：创建默认配置实例");
    }

    public AppConfig(String instanceName) {
        this.instanceName = instanceName;
        System.out.println("构造方法：创建配置实例 —— " + instanceName);
    }

    public static void main(String[] args) {
        new AppConfig();
        System.out.println("----------");
        new AppConfig("选课服务配置");
    }
}
```

**思路讲解：**
1. 第一次 new 触发类加载：静态代码块执行**一次**，初始化全类共享的 apiUrl。
2. 每次 new 对象：构造代码块先执行（适合放所有构造器共有的初始化逻辑），然后执行对应构造方法。
3. 第二次 new 时类已加载，静态块不再执行。

**运行结果：**

```
静态代码块：加载全局配置，apiUrl = https://api.campus.example.com
构造代码块：准备配置实例
构造方法：创建默认配置实例
----------
构造代码块：准备配置实例
构造方法：创建配置实例 —— 选课服务配置
```

▶ 关联：static 变量存方法区、类加载的完整过程见第11章。

---

#### 编程题 6（提高）：优惠结算——接口默认方法与冲突处理

**需求：** 商城结算服务实现两个优惠接口：`MemberDiscount`（会员优惠，默认方法 `apply()` 打印"会员价9折"）和 `CouponDiscount`（优惠券，默认方法 `apply()` 打印"满100减10"）。两个接口的 apply 都是 default 方法。请：
1. 说明结算实现类 `CheckoutService` 直接 implements 两个接口会发生什么；
2. 重写 `apply()`：本商城规定两种优惠不叠加，统一采用会员价，重写时通过 `接口名.super.方法名()` 调用会员优惠逻辑，并追加打印提示；
3. 再定义抽象下单方法 `void checkout(double money)`，在实现类中完成下单并调用优惠。

**考查：** default 默认方法、接口升级、多接口默认方法冲突、`接口名.super.方法()`。

**参考代码：**

```java
// 会员优惠接口
public interface MemberDiscount {
    // default 方法：接口升级时新增，老实现类不重写也能直接用
    default void apply() {
        System.out.println("会员价9折");
    }
}

// 优惠券接口
public interface CouponDiscount {
    default void apply() {
        System.out.println("满100减10");
    }
}

// 结算服务：同时实现两个接口
public class CheckoutService implements MemberDiscount, CouponDiscount {
    public void checkout(double money) {
        System.out.println("订单金额：" + money + " 元");
        apply();   // 调用重写后的优惠逻辑
    }

    // 两个接口的 default apply() 冲突，必须重写，否则编译报错
    @Override
    public void apply() {
        // 商城规则：不叠加，统一走会员价
        MemberDiscount.super.apply();
        System.out.println("（已按会员价结算，优惠券不叠加）");
    }

    public static void main(String[] args) {
        new CheckoutService().checkout(200);
    }
}
```

**思路讲解：**
1. default 方法设计初衷是**接口升级**：老接口新增方法时给默认实现，已有实现类零改动。
2. 但一个类实现的两个接口有同名同参 default 方法时，编译器无法决定继承哪个，**必须重写**。
3. 重写后想复用某个父接口的默认逻辑，用 `MemberDiscount.super.apply();`（不能写 `MemberDiscount.apply()`，那是静态方法的调用形式）。

**运行结果：**

```
订单金额：200.0 元
会员价9折
（已按会员价结算，优惠券不叠加）
```

▶ 关联：JDK9 还允许把两个 default 方法的公共逻辑抽成 `private` 方法放在接口内部复用。

---

#### 编程题 7（提高）：文本处理流水线——匿名内部类与 Lambda

**需求：** 定义函数式接口 `StringProcessor`，包含方法 `String process(String s)`。编写工具方法 `handle(String[] arr, StringProcessor p)`，对数组中每个字符串应用处理规则后打印。请分别用三种方式传入规则：
1. **匿名内部类**：给每个字符串加上书名号《》；
2. **Lambda 完整写法**：把字符串转为大写；
3. **Lambda 省略写法**：在每个字符串后加 `~`。

**考查：** 函数式接口、`@FunctionalInterface`、匿名内部类本质、Lambda 三种写法与省略规则。

**参考代码：**

```java
@FunctionalInterface   // 校验：有且仅有一个抽象方法
public interface StringProcessor {
    String process(String s);
}

public class TextTest {
    public static void main(String[] args) {
        String[] books = {"java", "python", "linux"};

        // 1. 匿名内部类：加书名号
        handle(books, new StringProcessor() {
            @Override
            public String process(String s) {
                return "《" + s + "》";
            }
        });

        // 2. Lambda 完整写法：转大写
        handle(books, (String s) -> {
            return s.toUpperCase();
        });

        // 3. Lambda 省略写法：加 ~（类型省略、单参数去括号、单行去 {} 和 return）
        handle(books, s -> s + "~");
    }

    // 工具方法：处理规则由调用者通过接口对象传入
    public static void handle(String[] arr, StringProcessor p) {
        for (String s : arr) {
            System.out.print(p.process(s) + "  ");
        }
        System.out.println();
    }
}
```

**思路讲解：**
1. `handle` 的第二个参数是接口类型，调用时要传一个"实现类对象"——传统写法得单独建一个实现类，只用一次太浪费，所以用匿名内部类当场 new 出来。
2. 匿名内部类做的事其实只有"传参数 s、返回处理结果"，Lambda 把样板代码全部压缩：`(String s) -> { return s.toUpperCase(); }`。
3. 省略规则逐步应用：参数类型可省 → `(s) -> {...}`；只有一个参数括号可省 → `s -> {...}`；方法体只有一行 return，`{}`、分号、return 一起省 → `s -> s + "~"`。
4. 注意三种方式能互换的前提：StringProcessor 是函数式接口（仅一个抽象方法）。

**运行结果：**

```
《java》  《python》  《linux》
JAVA  PYTHON  LINUX
java~  python~  linux~
```

▶ 关联：第15章方法引用 `String::toUpperCase` 还能再简化；第18章 Stream 的 `map(s -> s.toUpperCase())`、`filter(s -> s.length() > 3)` 都是本题的延伸。

---

### 本章自测要点回顾

- 接口：`interface` / `implements`、常量+抽象方法、无构造器、多实现、接口间多继承；
- JDK8/9 新特性：default（升级、不强制重写、冲突须重写+`接口名.super.方法()`）、static（接口名调用）、private（内部复用）；
- 多态：三前提；变量/静态看左、方法运行看右；好处是扩展性、弊端是不能调子类特有成员；向下转型 + instanceof 防 ClassCastException；
- equals：`==` 比地址、equals 重写后比内容、Objects.equals 空安全、重写 equals 要配 hashCode；
- 代码块：静态块（类加载一次）→ 构造块（每次 new）→ 构造方法；
- 内部类：成员/静态/局部了解，匿名内部类重点（快速造接口/抽象类的子类对象）；
- Lambda：只简化函数式接口的匿名内部类，`(参数) -> {方法体}`，三条省略规则。

---

<div style="page-break-after: always;"></div>

## 第10章 常用API与综合案例·习题精讲

> 本章覆盖：API 概念、`String`（创建方式/常用方法/不可变性/常量池/编译优化）、`StringBuilder`（拼接/反转/扩容机制）、`StringBuffer`、`ArrayList`（泛型/增删改查/遍历删除陷阱/底层扩容）、商品管理系统综合案例（JavaBean + 静态代码块 + 信号位思想）。
>
> 建议先合上笔记独立做题，再对照【答案】【解析】订正。

---

### 一、填空题

**1.** Java 中比较两个字符串的**内容**是否相同必须调用 `______` 方法；而 `==` 比较的是两个引用变量中存储的 `______`。

**【答案】** `equals`；地址值（对象地址）

**【解析】** String 是引用类型，`==` 比较的是栈中变量保存的地址。双引号字面量因常量池复用可能碰巧地址相同，但 `new` 出来的字符串地址一定不同。因此判断内容相等只能用 `equals`（区分大小写）或 `equalsIgnoreCase`（忽略大小写）。
▶ 关联：第9章多态章节学过的 `Objects.equals(a, b)` 能在比较前自动判空，第14章会讲 Object 类中 `equals` 的源码与重写。

**2.** `StringBuilder` 底层是一个字符数组，创建时默认容量为 `______` 个字符；当空位不足时按 `______` 的规则扩容，即 16 → `______` → 70。

**【答案】** 16；旧容量 × 2 + 2；34

**【解析】** 16×2+2=34，34×2+2=70。扩容时会把旧数组字符拷贝到新数组、丢弃旧数组。StringBuilder 始终在同一个容器上修改，不产生新字符串对象，这是它比 String 拼接快的根本原因。
▶ 关联：对比第16章 ArrayList 的扩容规则（10 → 15 → 22，约 1.5 倍），两者都是"数组满了就建新数组拷贝"，但倍数不同，注意不要记混。

**3.** JDK 8 中，`new ArrayList<>()` 无参构造时底层先创建一个默认长度为 `______` 的空数组；添加第 1 个元素时才创建长度为 `______` 的新数组；元素存满后再添加，按原容量的 `______` 倍扩容。

**【答案】** 0；10；1.5

**【解析】** 这是 JDK 8 的懒加载策略（JDK 7 是创建时直接给长度 10）。扩容四步：创建 1.5 倍新数组 → 原数据拷贝 → 新元素入新数组 → 旧数组丢弃。特例：若 `addAll` 批量添加时 1.5 倍仍放不下（如容量 10 一次倒入 11 个），新数组长度直接按实际需要（21）计算。
▶ 关联：正因为扩容要拷贝数组，ArrayList 查询快、频繁增删慢；频繁首尾增删的场景应选 LinkedList（第16章）。

**4.** ArrayList 的泛型中**不支持**基本数据类型，必须写 `______` 数据类型；若要存整数，泛型应写 `______`（int 的包装类）。

**【答案】** 引用；`Integer`

**【解析】** 集合容器设计上只能存放引用类型，基本类型要使用对应的包装类：`int→Integer`、`char→Character`、`double→Double`、`boolean→Boolean`。JDK 5 后有自动装箱拆箱，`list.add(1)` 会自动变成 `Integer.valueOf(1)`。
▶ 关联：包装类的装箱拆箱原理、常量池缓存（IntegerCache）见第14章；泛型类/泛型方法的自定义见第13章。

**5.** 以双引号 `"..."` 直接写出的字符串对象，会存储在堆内存的 `______` 中，相同内容在其中只存 `______` 份。

**【答案】** 字符串常量池（StringTable）；一

**【解析】** `String s1 = "abc"; String s2 = "abc";` 第二次赋值时常量池中已有 "abc"，直接把同一地址交给 s2，所以 `s1 == s2` 为 true。而 `new String("abc")` 每 new 一次都在堆中产生新对象。
▶ 关联：这种"复用不可变对象"的思想和第14章包装类、BigDecimal 一脉相承；读取文本文件时字符流解码出的字符串也在堆中（第20章）。

**6.** 数组用 `______` 属性获取长度，ArrayList 集合用 `______` 方法获取元素个数。

**【答案】** `length`；`size()`

**【解析】** 数组长度是固定属性 `arr.length`；集合长度可变，元素个数由方法 `list.size()` 给出。遍历时循环条件写 `i < list.size()`。注意 `size` 还有第二层含义：它既是已有元素个数，也是下一个元素的存放位置（ArrayList 底层靠它记录游标）。
▶ 关联：数组基础见第6章；第16章 List 集合、第17章 Set/Map 中 `size()` 用法相同。

---

### 二、选择题

**1.** 执行 `String s = new String("abc");` 这一行代码，总共创建了几个对象？

- A. 0 个
- B. 1 个
- C. 2 个
- D. 3 个

**【答案】** C

**【解析】** 两个对象：① `"abc"` 字面量在字符串常量池中创建 1 个；② `new` 在堆中再创建 1 个 String 对象，把常量池内容拷贝过来。若常量池中已有 "abc"（比如此前写过 `String x = "abc";`），则字面量不再新建，此行只创建堆中的 1 个对象。

**2.** 下面代码的输出结果是？

```java
String s1 = "abc";
String s2 = "a" + "b" + "c";
System.out.println(s1 == s2);
```

- A. true
- B. false
- C. 编译报错
- D. 运行异常

**【答案】** A

**【解析】** Java 存在**编译期优化**：`"a" + "b" + "c"` 是纯字面量拼接，编译时直接合并成 `"abc"`，运行时常量池复用同一对象，所以地址相同，结果 true。
对比：若拼接中含**变量**（如 `String t = "ab"; String s3 = t + "c";`），编译期无法确定结果，运行时才在堆中 new 出新对象，`s1 == s3` 为 false。

**3.** 关于循环中用 `+` 拼接字符串，下列说法正确的是？

- A. String 不可变，拼接会编译报错
- B. 每出现一个加号，底层会 new 一个 StringBuilder 并 toString 出一个新 String，堆中产生两个临时对象
- C. `+` 拼接和 StringBuilder 效率完全一样
- D. JDK 8 之后任何场景下 `+` 都不会产生新对象

**【答案】** B

**【解析】** 变量参与拼接时，一个加号底层 = `new StringBuilder()` + `toString()`，产生两个对象；循环 10 万次就产生约 20 万个用完即弃的临时对象，所以笔记实测 String 拼接 2946 毫秒、StringBuilder 仅 4 毫秒。JDK 8 编译器只对**简单**拼接做优化，循环内反复拼接仍应手动用 StringBuilder。

**4.** 已知 `ArrayList<String> list` 中元素为 `[A, B, C]`，执行 `list.add(1, "X");` 后再执行 `System.out.println(list.remove(2));`，输出和集合内容分别是？

- A. 输出 X，集合 `[A, B, C]`
- B. 输出 B，集合 `[A, X, C]`
- C. 输出 X，集合 `[A, B, C]`
- D. 输出 B，集合 `[A, X, B]`

**【答案】** B

**【解析】** `add(1,"X")` 在索引 1 处插入，原元素后移 → `[A, X, B, C]`；`remove(2)` 删除**索引 2** 处的元素 B 并**返回被删元素**，删除后元素左移 → `[A, X, C]`。
注意 remove 有两个重载：`remove(int index)` 按索引删、`remove(Object o)` 按内容删（返回 boolean，重复内容只删第一个）。

**5.** 下列关于 String、StringBuilder、StringBuffer 的对比，正确的是？

- A. 三者都不可变
- B. StringBuffer 的方法加了 synchronized 同步锁，多线程安全但效率较低
- C. StringBuilder 线程安全，适合多线程共享
- D. String 拼接效率最高

**【答案】** B

**【解析】** String 不可变；StringBuilder 与 StringBuffer 都是可变字符序列、API 完全相同。区别仅在 StringBuffer 方法带同步锁（第21章多线程会学 synchronized），安全但慢；StringBuilder 不安全但快。单线程业务代码（绝大多数场景）优先 StringBuilder。

**6.** 某音乐 App 的歌单为 `[雨一直下, 雨天, 晴天, 雨爱, 孤勇者]`，想下架所有歌名包含"雨"的歌曲，下列哪种写法能删干净？

- A. 正序遍历，`if(包含"雨") list.remove(i);`，不做其他处理
- B. 正序遍历，删除后执行 `i--;`
- C. 倒序遍历（`for(int i=size-1;i>=0;i--)`），满足条件就 `remove(i)`
- D. B 和 C 都可以

**【答案】** D

**【解析】** 直接正序删除会出错：删除后元素左移，下一次 i++ 恰好跳过补位过来的相邻元素。两种正确写法：①正序删除后 `i--`，让索引回退一位重新检查；②倒序遍历，删除元素只影响它后面的索引，而后面的元素已经检查过了。
▶ 关联：第16章会讲到，用迭代器的 `remove()` 或 JDK 8 的 `removeIf(条件)` 也能安全删除，本质是同一类"遍历中修改集合"的并发修改问题。

**7.** 综合案例中，初始测试数据放在 `static { }` 静态代码块里，关于它的说法正确的是？

- A. 每次 new 对象时执行一次
- B. 类加载时执行，且整个程序运行期间只执行一次
- C. 每次调用方法时执行一次
- D. 需要手动调用才会执行

**【答案】** B

**【解析】** 静态代码块随类加载（字节码文件加载进方法区）时执行，只执行一次，最适合做一次性初始化工作（如给静态集合装入默认数据）。这也是案例中 `Scanner` 和集合都定义为 `static` 的原因——静态的 main 方法只能直接访问静态成员。
▶ 关联：static、代码块的完整执行顺序（静态代码块→构造代码块→构造器）见第11章。

---

### 三、判断题

**1.** String 对象的内容可以被修改，`name += "程序员"` 就是把原字符串改成了新内容。（　）

**【答案】** ✗ 错误

**【解析】** String 是**不可变字符串**。`+=` 并没有修改原对象，而是拼接出一个全新的字符串对象、让变量指向新对象，旧对象内容纹丝不动。用 `System.identityHashCode(name)` 在拼接前后观察，会发现"身份地址"变了。

**2.** 判断两个字符串内容是否相等，可以用 `==`，因为双引号字符串地址本来就相同。（　）

**【答案】** ✗ 错误

**【解析】** 只有双引号字面量且内容相同时 `==` 才碰巧为 true；只要涉及 `new String`、变量拼接、键盘录入（`sc.next()` 返回的是 new 出来的对象），地址就可能不同。比较内容必须用 `equals`，这是面试和开发中的硬性规范。

**3.** ArrayList 长度可变，所以它底层不是数组。（　）

**【答案】** ✗ 错误

**【解析】** ArrayList 底层**就是数组**，"长度可变"是靠自动扩容模拟出来的：存满就建更大的新数组、把数据拷过去。理解这一点才能理解它"查询快（按索引直接定位）、增删慢（要移动元素/扩容拷贝）"的特性。

**4.** `list.remove(2)` 和 `list.remove("2")` 对于 `ArrayList<String>` 是完全一样的调用。（　）

**【答案】** ✗ 错误

**【解析】** 前者是 `remove(int index)`，删除索引 2 处的元素并返回被删元素；后者是 `remove(Object o)`，删除内容等于 "2" 的元素并返回 boolean。重载方法的参数列表不同，行为完全不同。
▶ 关联：方法重载（Overload）的定义见第4章。

---

### 四、简答题

**1.** 为什么说 String 是不可变的？字符串常量池有什么作用？

**【参考答案】**

- **不可变**：String 对象一旦在堆中创建，其字符内容就不能被修改。所有"修改"操作（`+`、`replace`、`substring` 等）都是创建并返回一个新的 String 对象，原对象不变。
- **常量池**：以 `"..."` 字面量创建的字符串存放在堆中的字符串常量池（StringTable）。相同内容的字面量在池中只存一份，多个变量可以指向同一个对象，从而**节省内存、提高复用率**，并用 `==`/`equals` 快速比较。
- `new String(...)` 不走复用：每 new 一次都在堆中开辟新对象。
- 意义：不可变让字符串可以安全共享（多线程下无需加锁）、hashCode 可以缓存（第17章 HashMap 用 String 做键时性能更好）。

▶ 关联：不可变 + 常量池思想在第14章包装类（Integer 缓存 -128~127）中再次出现。

**2.** 对比 String、StringBuilder、StringBuffer，并说明什么场景该用谁。

**【参考答案】**

| 类 | 可变性 | 线程安全 | 拼接效率 | 适用场景 |
| --- | --- | --- | --- | --- |
| String | 不可变 | 安全 | 最低（每次拼接产生新对象） | 内容固定、不频繁修改的字符串 |
| StringBuilder | 可变 | 不安全 | 最高（同一缓冲区操作） | 单线程下频繁拼接、反转（绝大多数业务） |
| StringBuffer | 可变 | 安全（synchronized） | 较低 | 多线程共享同一拼接容器 |

频繁循环拼接（如拼 SQL、拼 JSON、拼文件内容）必须用 StringBuilder；String 与 StringBuilder 可通过 `new StringBuilder(str)` 和 `sb.toString()` 互转。
▶ 关联：synchronized 同步锁原理见第21章。

**3.** 简述 ArrayList 的底层扩容机制。为什么说它"适合查询、不适合频繁增删"？

**【参考答案】**

- JDK 8：`new ArrayList<>()` 先建长度 **0** 的空数组；添加第 1 个元素时才建长度 **10** 的数组；
- 每次添加元素 `size++`，size 既是元素个数也是下一个存放位置；
- 存满后再添加：新建 **1.5 倍**容量的数组（10→15→22），拷贝原数据，旧数组丢弃；
- `addAll` 批量添加时若 1.5 倍仍不够，直接按实际需要长度建新数组（如 10 容量倒入 11 个 → 长度 21）。
- **查询快**：底层是数组，按索引 `get(i)` 直接定位，O(1)；
- **增删慢**：中间插入/删除需要移动后续元素，扩容还要整体拷贝，频繁增删代价高。首尾频繁增删可用 LinkedList（链表，第16章）。

---

### 五、代码阅读题

**1.** 阅读代码，写出每行输出。

```java
String s = "我爱Java";
System.out.println(s.length());        // ①
System.out.println(s.charAt(2));       // ②
System.out.println(s.substring(2));    // ③
System.out.println(s.substring(0, 2)); // ④
System.out.println(s.contains("java")); // ⑤
```

**【答案】** ① `6`　② `J`　③ `Java`　④ `我爱`　⑤ `false`

**【解析】** 字符索引：我0、爱1、J2、a3、v4、a5，长度 6。`charAt(2)` 取索引 2 的 J；`substring(2)` 从索引 2 截到末尾得 "Java"；`substring(0,2)` **包前不包后**，取索引 0、1 得 "我爱"；`contains` 区分大小写，"java" 与 "Java" 不同，故 false。
▶ 关联：字符在底层按编码值存储（'a'=97），字符比较大小、编码知识见第2章与第19章字符集。

**2.** 阅读代码，写出 5 个打印结果。

```java
String s1 = "abc";
String s2 = "abc";
String s3 = new String("abc");
String s4 = "a" + "b" + "c";
String t = "ab";
String s5 = t + "c";
System.out.println(s1 == s2);          // ①
System.out.println(s1 == s3);          // ②
System.out.println(s1 == s4);          // ③
System.out.println(s1 == s5);          // ④
System.out.println(s1.equals(s3));     // ⑤
```

**【答案】** ① `true`　② `false`　③ `true`　④ `false`　⑤ `true`

**【解析】**
- ① 双引号字面量，常量池复用同一地址 → true；
- ② new 在堆中产生新对象，地址不同 → false；
- ③ 纯字面量拼接被编译期优化成 "abc"，常量池复用 → true；
- ④ 含变量 t 的拼接在运行时于堆中产生新对象 → false；
- ⑤ equals 只比内容，内容都是 abc → true。
这组题把"常量池、new、编译优化、变量拼接、equals"五个考点一次串清，是经典面试题。

**3.** 阅读代码，写出输出。

```java
StringBuilder sb = new StringBuilder();
sb.append("稻香").append("晴天").append("告白气球");
System.out.println(sb);            // ①
System.out.println(sb.length());   // ②
sb.reverse();
System.out.println(sb);            // ③
String result = sb.toString();
System.out.println(result);        // ④
```

**【答案】** ① `稻香晴天告白气球`　② `8`　③ `球气白告天晴香稻`　④ `球气白告天晴香稻`

**【解析】** `append` 返回 StringBuilder 对象本身，所以可以**链式编程**；8 个字符 length 为 8；`reverse()` 原地逐位反转整个字符序列；`toString()` 把可变容器转成不可变 String，转换后内容相同但类型不同——需要用 String 独有方法（如 `split`、`substring`）时先 toString。

**4.** 阅读代码，写出每行输出。

```java
ArrayList<String> list = new ArrayList<>();
list.add("A");
list.add("B");
list.add("C");
list.add(1, "X");
System.out.println(list);            // ①
System.out.println(list.remove(2));  // ②
System.out.println(list);            // ③
System.out.println(list.set(1, "Y"));// ④
System.out.println(list);            // ⑤
System.out.println(list.size());     // ⑥
```

**【答案】**
① `[A, X, B, C]`　② `B`　③ `[A, X, C]`　④ `X`　⑤ `[A, Y, C]`　⑥ `3`

**【解析】**
- `add(1,"X")` 在索引 1 插入，B、C 后移 → ①；
- `remove(2)` 删索引 2 的 B 并**返回被删元素**，C 左移补位 → ②③；
- `set(1,"Y")` 把索引 1 的 X 替换为 Y，**返回修改前的旧值** X → ④⑤；
- 最终剩 A、Y、C 三个元素 → ⑥。
记忆口诀：add 加、remove 删（返回被删的）、set 改（返回旧的）、get 查。

**5.** 某音乐 App 歌单为 `[雨一直下, 雨天, 晴天, 雨爱, 孤勇者]`，下面这段"下架所有歌名含'雨'的歌曲"的代码有什么问题？输出是什么？请给出修正写法。

```java
ArrayList<String> list = new ArrayList<>();
list.add("雨一直下");
list.add("雨天");
list.add("晴天");
list.add("雨爱");
list.add("孤勇者");
for (int i = 0; i < list.size(); i++) {
    if (list.get(i).contains("雨")) {
        list.remove(i);
    }
}
System.out.println(list);
```

**【答案】** 输出 `[雨天, 晴天, 孤勇者]`——"雨天"被漏删了。

**【解析】** 过程推演：i=0 是"雨一直下"，删除后列表变为 `[雨天, 晴天, 雨爱, 孤勇者]`，元素左移；i 自增到 1，此时索引 1 是"晴天"（补位到索引 0 的"雨天"被跳过，没有被检查）；i=2 是"雨爱"，删除 → `[雨天, 晴天, 孤勇者]`；i=3 时 size 已是 3，循环结束。

修正写法二选一：

```java
// 写法一：正序遍历，删除后 i 回退
for (int i = 0; i < list.size(); i++) {
    if (list.get(i).contains("雨")) {
        list.remove(i);
        i--;
    }
}

// 写法二：倒序遍历
for (int i = list.size() - 1; i >= 0; i--) {
    if (list.get(i).contains("雨")) {
        list.remove(i);
    }
}
```

修正后输出 `[晴天, 孤勇者]`。
▶ 关联：第16章学完迭代器后，推荐用 `list.removeIf(s -> s.contains("雨"))` 一行解决（Lambda 写法见第15章）。

---

### 六、编程题

**1.（易）歌词字幕预处理**　音乐播放器在歌词滚动前需要预处理歌词。键盘录入一句歌词，程序完成：① 输出歌词总字符数；② 统计其中"爱"字出现的次数；③ 把所有"爱"替换成 `*` 生成"静音字幕"；④ 截取前 4 个字符作为歌词预览。

**【参考代码】**

```java
import java.util.Scanner;

public class LyricProcess {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一句歌词：");
        String lyric = sc.nextLine();   // 整句歌词可能含空格，用 nextLine

        // ① 总字符数
        System.out.println("歌词总字符数：" + lyric.length());

        // ② 统计"爱"字出现次数：charAt 逐位取出比较
        int count = 0;
        for (int i = 0; i < lyric.length(); i++) {
            if (lyric.charAt(i) == '爱') {
                count++;
            }
        }
        System.out.println("「爱」字出现了：" + count + " 次");

        // ③ 静音字幕：replace 返回新字符串，原歌词不变（不可变）
        String muted = lyric.replace("爱", "*");
        System.out.println("静音字幕：" + muted);

        // ④ 前 4 个字符作为预览（substring 包前不包后，取索引 0~3）
        if (lyric.length() >= 4) {
            System.out.println("歌词预览：" + lyric.substring(0, 4));
        }
    }
}
```

**【运行结果】** 输入 `爱情爱到底`，输出：总字符数 5、「爱」字出现了 2 次、静音字幕 `*情*到底`、歌词预览 `爱情爱到`。

**【逐段讲解】**
- `length()` 是 String 的方法，返回字符个数（中文、英文、符号都算一个字符）；
- 遍历字符串用 `charAt(i)` 按索引取字符，索引从 0 开始，配合 `length()` 控制循环；
- `replace(旧, 新)` 不修改原字符串，而是**返回一个替换后的新字符串**——这正是 String 不可变性的体现，必须用变量接住返回值；
- `substring(0, 4)` 包前不包后，取索引 0、1、2、3 共 4 个字符；加长度判断是为了歌词不足 4 个字时避免索引越界异常。

▶ 关联：Scanner 的 `next()` 与 `nextLine()` 区别见第3章；字符能与 `'爱'` 直接比较是因为底层按编码值存储（第2章 char、第19章字符集）；字符串索引越界会抛 `StringIndexOutOfBoundsException`，异常体系见第16章。

**2.（中）快递运单号与取件校验码**　快递柜系统录入三段信息：公司代号（如 SF）、10 位运单数字、国家码（如 CN）。要求：① 用 StringBuilder 把三段**链式拼接**成完整运单号；② 把运单号反转生成取件校验码；③ 判断运单号是否以 "SF" 开头、是否包含 "CN"。

**【参考代码】**

```java
import java.util.Scanner;

public class ExpressNo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入公司代号：");
        String company = sc.next();
        System.out.println("请输入10位运单数字：");
        String number = sc.next();
        System.out.println("请输入国家码：");
        String country = sc.next();

        // ① StringBuilder 链式拼接：append 返回对象本身
        StringBuilder sb = new StringBuilder();
        sb.append(company).append(number).append(country);
        String waybillNo = sb.toString();   // 先转成 String 保存
        System.out.println("完整运单号：" + waybillNo);

        // ② 反转生成校验码：reverse 直接改动 sb 自身
        String checkCode = sb.reverse().toString();
        System.out.println("取件校验码：" + checkCode);

        // ③ String 的判断方法
        System.out.println("是否顺丰单号：" + waybillNo.startsWith("SF"));
        System.out.println("是否国际件：" + waybillNo.contains("CN"));
    }
}
```

**【运行结果】** 依次输入 `SF`、`1234567890`、`CN`：完整运单号 `SF1234567890CN`；取件校验码 `NC0987654321FS`；是否顺丰单号 `true`；是否国际件 `true`。

**【逐段讲解】**
- `append()` 返回 StringBuilder 对象本身，所以可以连续 `.append().append()` 链式调用；
- 关键细节：`waybillNo = sb.toString()` 在反转**之前**执行，String 不可变，之后 `sb.reverse()` 反转的是 StringBuilder 容器，`waybillNo` 不受影响——对比之下能直观理解"String 不可变、StringBuilder 可变"；
- `reverse()` 也是原地修改并返回自身，再 `toString()` 转回 String；
- `startsWith` / `contains` 是 String 的常用判断方法，返回 boolean。

▶ 关联：若运单号要在循环中逐段拼接（如扫描多个包裹），必须用 StringBuilder 而不是 `+`（第10章拼接原理：一个加号产生两个临时对象）；`toString()` 是 Object 类的方法，第14章会讲所有类都有它。

**3.（中）会员积分清算**　健身房录入 6 位会员的本月积分存入集合，要求：① 遍历输出全部积分；② 求总积分与平均积分；③ 清除所有低于 60 分的积分记录；④ 给清除后榜单上的第一位会员发满勤奖，积分改为 100，并打印其原来的积分。

**【参考代码】**

```java
import java.util.ArrayList;
import java.util.Scanner;

public class MemberPoints {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        ArrayList<Integer> points = new ArrayList<>();   // 泛型用包装类 Integer

        System.out.println("请依次录入6位会员的本月积分：");
        for (int i = 0; i < 6; i++) {
            points.add(sc.nextInt());   // int 自动装箱为 Integer
        }
        System.out.println("全部积分：" + points);

        // ② 总分、平均分
        int total = 0;
        for (int i = 0; i < points.size(); i++) {
            total += points.get(i);     // Integer 自动拆箱为 int 参与运算
        }
        System.out.println("总积分：" + total + "，平均积分：" + (total / points.size()));

        // ③ 倒序遍历删除低于 60 的记录
        for (int i = points.size() - 1; i >= 0; i--) {
            if (points.get(i) < 60) {
                System.out.println("清除积分：" + points.remove(i));  // remove 返回被删元素
            }
        }
        System.out.println("清除后：" + points);

        // ④ 首位会员满勤奖：set 修改并接收旧值
        if (points.size() > 0) {
            int old = points.set(0, 100);
            System.out.println("首位会员积分由 " + old + " 修改为 100");
        }
        System.out.println("最终榜单：" + points);
    }
}
```

**【运行结果】** 依次输入 `80 50 90 40 70 55`：总积分 385、平均积分 64；倒序清除 55、40、50；清除后 `[80, 90, 70]`；首位会员积分由 80 修改为 100；最终榜单 `[100, 90, 70]`。

**【逐段讲解】**
- 集合不能存基本类型，`ArrayList<int>` 报错，必须写包装类 `ArrayList<Integer>`；`add(80)` 时 int 自动装箱、`total += get(i)` 时 Integer 自动拆箱（第14章详解）；
- **删除必须倒序**：若正序删除，删完元素左移会跳过补位元素（与代码阅读题 5 同一个坑）；倒序时删除只影响后面已检查过的索引；
- `remove(i)` 返回被删除的元素，可直接打印；`set(0, 100)` 用新值覆盖并**返回修改前的旧值**；
- 集合长度用 `size()` 不是 `length`。

▶ 关联：装箱拆箱与包装类见第14章；遍历删除的并发修改问题在第16章还有迭代器、`removeIf` 两种更简洁的写法；`ArrayList<Integer>` 底层扩容机制见本章 5.5 节。

**4.（难）通讯录管理系统**　用 `ArrayList<Contact>` 实现一个通讯录：联系人有姓名、手机号、分组（朋友/家人/同事）。功能菜单：① 添加联系人（**手机号不能重复**）；② 浏览全部；③ 按姓名删除；④ 按姓名查到联系人并修改其分组；⑤ 退出。

**【参考代码】**

```java
// ---- Contact 实体类（JavaBean）----
public class Contact {
    private String name;
    private String phone;
    private String group;

    public Contact() {
    }

    public Contact(String name, String phone, String group) {
        this.name = name;
        this.phone = phone;
        this.group = group;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getPhone() {
        return phone;
    }

    public void setPhone(String phone) {
        this.phone = phone;
    }

    public String getGroup() {
        return group;
    }

    public void setGroup(String group) {
        this.group = group;
    }
}
```

```java
// ---- 通讯录主程序 ----
import java.util.ArrayList;
import java.util.Scanner;

public class ContactBook {
    static Scanner sc = new Scanner(System.in);
    static ArrayList<Contact> book = new ArrayList<>();   // 静态方法共享，定义为 static

    public static void main(String[] args) {
        while (true) {
            System.out.println("=====通讯录=====");
            System.out.println("1.添加联系人  2.浏览全部  3.按姓名删除  4.修改分组  5.退出");
            switch (sc.next()) {
                case "1": addContact(); break;
                case "2": showAll(); break;
                case "3": deleteByName(); break;
                case "4": updateGroup(); break;
                case "5":
                    System.out.println("再见！");
                    return;
                default:
                    System.out.println("输入有误！");
            }
        }
    }

    // 添加：手机号查重后再加入
    private static void addContact() {
        System.out.println("请输入姓名：");
        String name = sc.next();
        System.out.println("请输入手机号：");
        String phone = sc.next();
        for (int i = 0; i < book.size(); i++) {
            if (book.get(i).getPhone().equals(phone)) {   // 字符串内容比较用 equals
                System.out.println("该手机号已存在，添加失败！");
                return;   // 查重失败直接结束方法，不再往下录入
            }
        }
        System.out.println("请输入分组（朋友/家人/同事）：");
        String group = sc.next();
        book.add(new Contact(name, phone, group));
        System.out.println("添加成功！当前共 " + book.size() + " 位联系人");
    }

    // 浏览
    private static void showAll() {
        if (book.size() == 0) {
            System.out.println("通讯录是空的，先添加联系人吧");
            return;
        }
        for (int i = 0; i < book.size(); i++) {
            Contact c = book.get(i);
            System.out.println((i + 1) + ". " + c.getName() + "  "
                    + c.getPhone() + "  [" + c.getGroup() + "]");
        }
    }

    // 按姓名删除：信号位思想
    private static void deleteByName() {
        System.out.println("请输入要删除的姓名：");
        String name = sc.next();
        boolean flag = false;   // 先假设没找到
        for (int i = 0; i < book.size(); i++) {
            if (book.get(i).getName().equals(name)) {
                book.remove(i);
                flag = true;
                System.out.println("删除成功！");
                break;
            }
        }
        if (!flag) {
            System.out.println("没有找到该联系人！");
        }
    }

    // 按姓名修改分组
    private static void updateGroup() {
        System.out.println("请输入要修改的联系人姓名：");
        String name = sc.next();
        boolean flag = false;
        for (int i = 0; i < book.size(); i++) {
            Contact c = book.get(i);
            if (c.getName().equals(name)) {
                System.out.println("请输入新的分组：");
                c.setGroup(sc.next());   // 集合中存的是对象地址，setter 改属性即生效
                flag = true;
                System.out.println("修改成功！");
                break;
            }
        }
        if (!flag) {
            System.out.println("没有找到该联系人！");
        }
    }
}
```

**【运行结果说明】** 选择 1 添加"王小明/13800001111/朋友"提示添加成功；再次添加相同手机号提示"该手机号已存在，添加失败"；选择 2 浏览列出全部联系人；选择 3 输入姓名删除，找不到时提示"没有找到该联系人"；选择 4 输入姓名可把分组由"朋友"改为"同事"；选择 5 退出程序。

**【逐段讲解】**
1. **JavaBean 封装数据**：Contact 类私有字段 + 无参/有参构造 + get/set，符合第7章封装规范；
2. **`ArrayList<Contact>` 存对象**：集合里存的是对象的地址，`book.get(i)` 取出对象后调 `setGroup()` 修改属性，集合中的对象同步改变——**修改对象属性不需要再 set 回集合**；
3. **`while(true) + switch`** 搭菜单框架（第5章），`return` 结束 main 方法即退出程序；
4. **查重与信号位**：添加时手机号重复直接 `return` 结束方法；删除/修改用 `flag` 信号位记录是否找到，遍历结束后根据 flag 给出不同提示；
5. **所有字符串内容比较一律 `equals`**：手机号、姓名都用 `equals`，不能用 `==`；
6. Scanner 与集合定义为 `static`，因为 main 及各方法都是静态的，静态方法只能直接访问静态成员。

▶ 关联：JavaBean/封装/this 见第7章；static 成员与静态代码块见第11章；switch/while 见第5章；本系统按姓名查找是线性遍历，第17章学完 HashMap 后可以用"手机号→联系人"的键值对实现 O(1) 查找，第18章 Stream 流可把浏览筛选写得更简洁。

---

### 本章考点自查清单

做完题后对照检查，全部能答出即掌握本章：

- [ ] 为什么字符串比较内容必须用 equals？`==` 在什么场景下碰巧为 true？
- [ ] `new String("abc")` 创建几个对象？纯字面量拼接与变量拼接的区别（编译期优化）？
- [ ] String 不可变的含义与常量池的作用
- [ ] `substring` 的"包前不包后"、`charAt` 索引从 0 开始
- [ ] StringBuilder 为什么快？初始容量 16、扩容 ×2+2
- [ ] `+` 拼接底层为什么慢（一个加号两个临时对象）
- [ ] String/StringBuilder/StringBuffer 三者区别
- [ ] ArrayList 泛型为何只能用引用类型？基本类型对应哪些包装类？
- [ ] add/get/remove/set/size 的用法与返回值（remove 返回被删元素、set 返回旧值）
- [ ] 遍历中删除元素的两种正确写法（i-- / 倒序）
- [ ] ArrayList 底层扩容：0→10→1.5 倍；为什么查询快增删慢
- [ ] 综合案例三要素：JavaBean + 静态代码块初始化 + 信号位查找

---

# 第二部分 · JavaSE 进阶

<div style="page-break-after: always;"></div>

## 第11章 面向对象进阶（一）：static 与继承 · 习题精讲

> 题型：填空、选择、判断、简答、代码阅读、编程（编程题 6 道，由易到难）。
> 每题给出【答案】与【解析】，解析中用「▶ 关联」串联前后章节。

---

### 一、填空题

**1.** 被 ______ 关键字修饰的成员变量称为类变量（静态变量），它属于 ______，在内存中只有 ______ 份，被该类的所有对象共享。

**【答案】** `static`；类；一

**【解析】** 类变量随着类的加载而存在，放在方法区的静态区，无论 new 多少个对象都只存一份；没有 static 修饰的实例变量每个对象各存一份。判断标准：数据需要被所有对象共享、只需要一份，就用 static。
▶ 关联：第7章《面向对象基础》初识 static；static 共享计数在第21章《日志与多线程》中被用来统计线程总数。

**2.** 访问类变量和类方法，推荐使用 ______ 的方式；工具类为了不让外界创建对象，通常把它的 ______ 私有化。

**【答案】** 类名.成员名（如 `Student.schoolName`）；构造器

**【解析】** 用对象名也能访问静态成员，但需要先 new 对象、浪费内存，且语义不清；构造器私有后外界无法 new，工具类方法全部设计为 static，直接类名调用（JDK 的 `Math` 类就是这样）。
▶ 关联：工具类三规范（构造器私有、方法 static、类名调用）见第7章；本章编程题第 2 题实操。

**3.** 静态代码块在 ______ 时自动执行，且只执行 ______ 次；实例代码块在 ______ 时执行。

**【答案】** 类加载；一；每次创建对象（new）

**【解析】** 类整个程序运行期间只加载一次，所以 static 代码块只跑一次，适合做类变量初始化、加载配置文件、注册驱动；实例代码块每 new 一次执行一次，作用与构造器类似。
▶ 关联：第9章《面向对象高级（下）》对比过两种代码块的执行时机与顺序。

**4.** 单例设计模式要满足三个要求：定义一个 ______ 记住类的对象、把 ______ 私有化、定义一个 ______ 返回对象。

**【答案】** 类变量（静态变量）；构造器；静态方法（类方法）

**【解析】** 三步缺一不可：静态变量持有唯一实例，私有构造器堵住外界 new 的入口，静态方法作为全局访问点。饿汉式在类加载时就把对象创建好；懒汉式第一次调用方法时才创建。
▶ 关联：JDK 中的 `Runtime` 类就是单例；单例思想在第21章日志框架、第23章配置读取中常见。

**5.** Java 中类与类之间是 ______ 继承的（一个类只能有一个直接父类），但支持 ______ 继承；所有类都直接或间接继承自 ______ 类。

**【答案】** 单；多层；`java.lang.Object`

**【解析】** `class A extends B, C` 编译报错，但 `A extends B`、`B extends C` 这样的继承链可以无限延续；Object 是所有类的祖宗类，因此任何对象都能直接使用 `toString()`、`equals()` 等方法。
▶ 关联：Object 的 toString/equals 在第8章初识、第14章深入学习重写。

**6.** 四种权限修饰符从开放到严格依次是：public > ______ > ______ > private。

**【答案】** protected；缺省（default，不写修饰符）

**【解析】** private 本类可见；缺省同包可见；protected 同包 + 不同包的子类可见；public 到处可见。方法重写时，子类方法的权限必须大于或等于父类方法权限，依据就是这张表。
▶ 关联：封装 private + get/set 见第7章；重写权限规则见第8章。

**7.** 子类所有构造器的第一行默认都有一句 ______，它会先调用父类的 ______ 构造器；如果父类没有无参构造器，子类必须手写 ______。

**【答案】** `super()`；无参；`super(实参)` 调用父类有参构造器

**【解析】** 创建子类对象时，先初始化父类这部分数据、再初始化子类这部分，所以子类构造器一定先跑父类构造器。父类只有有参构造器时，默认的 super() 找不到无参构造器会编译报错，必须手写 super(...) 且放在第一行。
▶ 关联：this(...) 调用本类兄弟构造器也必须在第一行，所以 this(...) 与 super(...) 不能同时出现——见本章编程题第 6 题。

---

### 二、选择题

**1.** 关于 static 修饰的成员变量，下列说法正确的是（　）

A. 每个对象各存一份，互不影响
B. 必须创建对象后才能访问
C. 属于类，所有对象共享同一份
D. 只能在静态代码块中访问

**【答案】** C

**【解析】** A 描述的是实例变量；B 错，类变量推荐类名直接访问；D 错，任何地方都能按权限访问。共享是类变量的核心特征：一个对象改了，所有对象看到的都是新值（代码阅读题第 1 题验证）。

**2.** 下列工具类的写法，最规范的是（　）

```java
A. public class MyUtil {
       public MyUtil() {}
       public String getCode() { return "abc"; }
   }
B. public class MyUtil {
       private MyUtil() {}
       public static String getCode() { return "abc"; }
   }
C. public class MyUtil {
       private MyUtil() {}
       public String getCode() { return "abc"; }
   }
D. public class MyUtil {
       public static String getCode() { return "abc"; }
       public MyUtil() {}
   }
```

**【答案】** B

**【解析】** 工具类三规范：构造器私有（不让 new）、方法 static（类名直接调）、调用方式 `MyUtil.getCode()`。A/D 构造器公开就能 new 出无意义的对象；C 方法是实例方法却构造器私有，根本调不到。
▶ 关联：编程题第 2 题 CodeUtil 即此规范。

**3.** 关于饿汉式与懒汉式单例，下列说法错误的是（　）

A. 饿汉式在类加载时就创建好对象
B. 懒汉式第一次调用 getInstance() 时才创建对象
C. 两种方式拿到的对象都只有一个
D. 懒汉式的静态变量在声明时就必须 new 出对象

**【答案】** D

**【解析】** 声明时就 new 对象是饿汉式（`private static A a = new A();`）；懒汉式声明时只是 `null`，在方法里判断 `if (b == null) b = new B();`。两种方式最终都保证全局唯一实例。
▶ 关联：编程题第 3、4 题分别实现两种单例，可对照"加载中"提示出现的次数。

**4.** 父类中有一个 `protected void work()` 方法，子类重写时下列哪种写法是合法的（　）

A. `private void work()`
B. `void work()`（缺省权限）
C. `public void work()`
D. `protected int work()`（改了返回值类型）

**【答案】** C

**【解析】** 重写要求方法名、参数列表完全一致，返回值类型一致（或子类类型），权限只能放大不能缩小。protected 可以放大为 public；A（缩小为 private）、B（缩小为缺省）都违规；D 返回值变了不再是重写。
▶ 关联：方法重写"声明不变，重新实现"见第8章；重载（同名不同参）是第4章内容，二者对比见简答题第 2 题。

**5.** 关于子类构造器，下列说法正确的是（　）

A. 子类构造器会把父类构造器继承下来直接调用
B. 子类构造器第一行默认是 super()，先执行父类构造器
C. 父类没有无参构造器时，子类可以不写任何 super 语句
D. super(...) 和 this(...) 可以同时出现在一个构造器前两行

**【答案】** B

**【解析】** 构造器不能被继承（A 错）；父类只有有参构造器时，子类必须手写 super(实参)，否则编译报错（C 错）；this(...) 和 super(...) 都要求在第一行，所以二者互斥（D 错）。
▶ 关联：代码阅读题第 3 题演示构造器执行顺序；编程题第 6 题同时用到 this(...) 与 super(...)（分别在不同构造器中）。

**6.** 下列代码中，子类能直接访问的父类成员是（　）

```java
// 父类
public class Parent {
    public String a;
    protected String b;
    String c;          // 缺省
    private String d;
}
// 子类与父类在同一个包中
public class Child extends Parent {
    public void test() {
        // 此处能访问哪些？
    }
}
```

A. 只能访问 a
B. 能访问 a、b、c
C. 能访问 a、b、c、d
D. 只能访问 a、b

**【答案】** B

**【解析】** 同包子类中：public、protected、缺省都可见，private 不可见。如果子类换到不同包，则缺省的 c 也不可见，只剩 a、b。private 成员子类"拥有但不能直接访问"，要通过父类的 get/set 方法间接操作。
▶ 关联：第7章封装中 private 配合 get/set 的写法。

---

### 三、判断题

**1.** 静态方法中可以直接访问实例变量，也可以直接调用实例方法。（　）

**【答案】** ✗ 错误

**【解析】** 静态方法属于类，调用时可能还没有任何对象存在，而实例变量/实例方法必须依赖对象，所以静态方法中不能直接访问实例成员（代码阅读题第 2 题可见编译错误）。记忆口诀：静态只能直接访问静态；实例方法静态、实例都能访问；`this` 只能出现在实例方法中。
▶ 关联：main 方法是 static 的，所以 main 中直接调用本类的实例方法也会报错——第7章强调过。

**2.** 静态代码块每次 new 对象都会执行一次。（　）

**【答案】** ✗ 错误

**【解析】** 静态代码块在类加载时执行，类只加载一次，所以静态代码块只执行一次；每次 new 都执行的是实例代码块和构造器。

**3.** Java 支持一个类同时继承多个父类。（　）

**【答案】** ✗ 错误

**【解析】** Java 类是单继承的（一个亲爹），但支持多层继承链；想获得多种能力要靠接口多实现（一个类可以 implements 多个接口）。
▶ 关联：接口多实现在第9章、第12章学习。

**4.** 子类构造器执行前，一定会先调用父类的构造器。（　）

**【答案】** ✓ 正确

**【解析】** 子类构造器第一行默认 super()，手写了 super(实参) 则调用父类有参构造器；无论哪种，都是父类构造器先执行完、再回来执行子类构造器。这样保证子类对象中"父类那部分数据"先被初始化。
▶ 关联：代码阅读题第 3 题可看到打印顺序。

---

### 四、简答题

**1.** 类变量（静态变量）和实例变量有什么区别？请从所属、内存份数、访问方式、生命周期四个角度对比。

**【答案要点】**

| 对比项 | 类变量（static） | 实例变量（无 static） |
| --- | --- | --- |
| 所属 | 属于类 | 属于每个对象 |
| 内存份数 | 全类一份，所有对象共享 | 每个对象各一份 |
| 访问方式 | 推荐 类名.变量名（对象也能调） | 必须先 new 对象，对象.变量名 |
| 生命周期 | 类加载时产生，类消失时销毁 | 对象创建时产生，对象被回收时销毁 |
| 典型用途 | 共享数据、计数器、系统配置 | 描述对象自己的状态（姓名、年龄） |

**【解析】** 选择题第 1 题和代码阅读题第 1 题考的都是"共享"这一本质：一个对象改了类变量，其他对象看到的也是新值。
▶ 关联：第7章在线人数 onLineNumber 案例；第21章多线程中静态变量被多线程共享会引发线程安全问题。

**2.** 方法重写（Override）和方法重载（Overload）有什么区别？

**【答案要点】**

| 对比项 | 重写 Override | 重载 Overload |
| --- | --- | --- |
| 发生位置 | 子父类之间 | 同一个类中 |
| 方法名 | 相同 | 相同 |
| 参数列表 | 必须完全相同 | 必须不同（个数/类型/顺序） |
| 返回值 | 相同（或子类类型） | 无要求 |
| 权限 | 子类只能放大不能缩小 | 无要求 |
| 关系 | 多态的前提 | 同名方法的多种参数形态 |

**【解析】** 重载是"同一个名字干同类的事，参数不同"（如 println 能打印各种类型）；重写是"子类觉得父类实现不好，覆盖重写"。
▶ 关联：重载在第4章《方法》学习；重写在第8章学习，是第12章多态的核心机制。

**3.** 为什么子类构造器一定要先调用父类构造器？this(...) 和 super(...) 为什么不能共存？

**【答案要点】**
- 子类对象中包含父类那部分成员，必须先由父类构造器把这部分初始化好，子类构造器才能安全使用；所以子类构造器第一行默认 super()。
- this(...) 是调用本类其他构造器、super(...) 是调用父类构造器，两者都被语法要求必须出现在构造器的第一行，同一个第一行只能放一句，因此互斥。
- 注意 this(...) 调用的兄弟构造器里仍然会执行 super(...)，所以父类构造器依然会被调用、且只调用一次。

**【解析】** 编程题第 6 题中，两参构造器用 this(...) 把默认类型传给三参构造器，三参构造器里不再写 super（系统仍会默认 super()）；而子类 FreshExpress 的构造器直接 super(...) 调父类三参。
▶ 关联：第7章构造器基础、第8章子类构造器执行流程。

---

### 五、代码阅读题

**1.** 阅读代码，写出运行结果。

```java
class GymMember {
    static String clubName = "力健健身";
    String name;
    public GymMember(String name) {
        this.name = name;
    }
}

public class Test {
    public static void main(String[] args) {
        GymMember m1 = new GymMember("阿强");
        GymMember m2 = new GymMember("阿珍");
        m2.clubName = "铁馆健身";
        System.out.println(m1.clubName + " - " + m1.name);
        System.out.println(GymMember.clubName + " - " + m2.name);
    }
}
```

**【答案】**

```
铁馆健身 - 阿强
铁馆健身 - 阿珍
```

**【解析】** `clubName` 是 static 类变量，全类一份，m2 把它改成"铁馆健身"后，m1 看到的也是新值；`name` 是实例变量，m1、m2 各自一份互不影响。
▶ 关联：填空题第 1 题的"共享一份"；第7章 static 在线人数案例同一原理。

**2.** 下列代码哪些行会编译报错？说明原因。

```java
class Warehouse {
    static String city = "上海";
    int stock = 100;

    public static void showCity() {
        System.out.println(city);      // ①
        System.out.println(stock);     // ②
        showStock();                   // ③
    }

    public void showStock() {
        System.out.println(stock);     // ④
        System.out.println(city);      // ⑤
    }
}
```

**【答案】** ②、③ 编译报错；①、④、⑤ 合法。

**【解析】** showCity 是静态方法：①访问静态变量 city 合法；②访问实例变量 stock 非法（静态方法中没有对象，实例变量无处依附）；③调用实例方法 showStock() 非法。showStock 是实例方法：④⑤都合法——实例方法中静态成员、实例成员都能直接访问。
▶ 关联：判断题第 1 题；第7章"测试类里其他方法为什么也要加 static"。

**3.** 阅读代码，写出运行结果。

```java
class Vehicle {
    public Vehicle() {
        System.out.println("Vehicle 无参构造");
    }
    public Vehicle(String type) {
        System.out.println("Vehicle 有参构造：" + type);
    }
}

class Bike extends Vehicle {
    public Bike() {
        System.out.println("Bike 无参构造");
    }
    public Bike(String brand) {
        super("非机动车");
        System.out.println("Bike 有参构造：" + brand);
    }
}

public class Test {
    public static void main(String[] args) {
        new Bike();
        System.out.println("--------");
        new Bike("永久");
    }
}
```

**【答案】**

```
Vehicle 无参构造
Bike 无参构造
--------
Vehicle 有参构造：非机动车
Bike 有参构造：永久
```

**【解析】** `new Bike()` 第一行默认 super()，先跑父类无参构造，再跑子类无参构造；`new Bike("永久")` 手写了 super("非机动车")，先跑父类有参构造。两次都是"父先子后"。
▶ 关联：填空题第 7 题；第8章子类构造器执行流程的文字内存说明。

**4.** 阅读代码，写出运行结果。

```java
class Parcel {
    String type = "普通包裹";
    public void deliver() {
        System.out.println("按标准时效配送");
    }
}

class FreshParcel extends Parcel {
    String type = "生鲜包裹";
    @Override
    public void deliver() {
        System.out.println(type + "：优先配送");
        System.out.println(super.type + "：父类逻辑→");
        super.deliver();
    }
}

public class Test {
    public static void main(String[] args) {
        new FreshParcel().deliver();
    }
}
```

**【答案】**

```
生鲜包裹：优先配送
普通包裹：父类逻辑→
按标准时效配送
```

**【解析】** 子类有同名变量 type，就近原则先拿到子类的"生鲜包裹"；想访问父类的同名成员用 `super.变量名`；想执行父类被重写的方法用 `super.方法名()`。
▶ 关联：this 的就近原则在第7章；super 三种用法（变量、方法、构造器）见第8章对比表；重写方法的动态绑定是第12章多态。

---

### 六、编程题（共 6 题，由易到难）

#### 编程题 1（基础）：驿站入库计数器

**需求：** 驿站每入库一件包裹就生成一个取件码（A-1、A-2、A-3……），并能统计今日入库总数。驿站名称所有包裹共享。请设计 `CourierPackage` 类并测试。

**【参考答案】**

```java
public class CourierPackage {
    static String stationName = "菜鸟驿站(学府店)";
    static int todayCount;          // 共享计数器
    String pickupCode;              // 每个包裹自己的取件码

    public CourierPackage() {
        todayCount++;               // 每 new 一件，计数器 +1
        pickupCode = "A-" + todayCount;
    }

    public static void main(String[] args) {
        CourierPackage p1 = new CourierPackage();
        CourierPackage p2 = new CourierPackage();
        CourierPackage p3 = new CourierPackage();

        System.out.println(p1.pickupCode);   // A-1
        System.out.println(p2.pickupCode);   // A-2
        System.out.println(p3.pickupCode);   // A-3
        System.out.println("今日" + stationName + "共入库 " + todayCount + " 件");
    }
}
```

**运行结果：**

```
A-1
A-2
A-3
今日菜鸟驿站(学府店)共入库 3 件
```

**【解析】** 驿站名和计数器是所有包裹共享的数据 → static；取件码每件不同 → 实例变量。计数器在构造器中自增，保证"每创建一个对象 +1"。
▶ 关联：第7章统计班级人数案例的同款思路；static 计数器在第21章多线程中要加锁才能保证准确（线程安全）。

#### 编程题 2（基础）：取件码工具类

**需求：** 设计工具类 `CodeUtil`：①生成 6 位数字取件码；②把 11 位手机号脱敏为 `138****5678` 形式。要求外界不能创建该类对象，直接用类名调用。

**【参考答案】**

```java
import java.util.Random;

public class CodeUtil {
    private CodeUtil() {}   // 构造器私有

    // 生成 6 位数字取件码
    public static String createPickupCode() {
        Random r = new Random();
        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < 6; i++) {
            sb.append(r.nextInt(10));
        }
        return sb.toString();
    }

    // 手机号脱敏：前 3 位 + **** + 后 4 位
    public static String maskPhone(String phone) {
        if (phone == null || phone.length() != 11) {
            return "号码格式有误";
        }
        return phone.substring(0, 3) + "****" + phone.substring(7);
    }

    public static void main(String[] args) {
        System.out.println(CodeUtil.createPickupCode());     // 如 483920
        System.out.println(CodeUtil.maskPhone("13812345678")); // 138****5678
    }
}
```

**【解析】** 工具类三规范：构造器私有、方法全部 static、类名调用。脱敏用 substring 截取：substring(7) 从第 8 位（索引 7）取到末尾，正好是后 4 位。
▶ 关联：String 的 substring/length 方法见第10章；StringBuilder 拼接见第10章。

#### 编程题 3（中等）：打印机池（饿汉式单例）

**需求：** 公司打印机全局只有一台，所有人提交文档都进同一个打印队列。请用饿汉式单例实现 `PrinterManager`，验证两次获取的是同一个对象，并统计队列中的文档数。

**【参考答案】**

```java
public class PrinterManager {
    // 1. 类变量记住唯一对象，类加载时就创建（饿汉式）
    private static final PrinterManager instance = new PrinterManager();
    private int queueCount;

    // 2. 构造器私有
    private PrinterManager() {}

    // 3. 静态方法返回对象
    public static PrinterManager getInstance() {
        return instance;
    }

    public void submit(String docName) {
        queueCount++;
        System.out.println("已提交打印：" + docName + "，当前队列 " + queueCount + " 份");
    }

    public static void main(String[] args) {
        PrinterManager p1 = PrinterManager.getInstance();
        PrinterManager p2 = PrinterManager.getInstance();
        System.out.println(p1 == p2);   // true，同一个对象

        p1.submit("毕业论文.pdf");
        p2.submit("简历.docx");
    }
}
```

**运行结果：**

```
true
已提交打印：毕业论文.pdf，当前队列 1 份
已提交打印：简历.docx，当前队列 2 份
```

**【解析】** `==` 比较引用类型比的是地址，true 说明 p1、p2 指向同一个对象；正因为是同一对象，p2 提交时队列计数接着 p1 的 1 变成 2。饿汉式对象在类加载时就建好，线程安全、写法简单。
▶ 关联：`==` 比较地址、equals 比较内容见第9/14章；单例在第21章日志对象、配置管理中广泛使用。

#### 编程题 4（中等）：网站配置加载器（懒汉式单例）

**需求：** 网站配置只需加载一次，但希望第一次用到时才加载（节省启动时间）。请用懒汉式单例实现 `ConfigLoader`：第一次获取对象时打印"配置文件加载中..."，之后再获取不再打印；并提供 getDbUrl() 方法。

**【参考答案】**

```java
public class ConfigLoader {
    private static ConfigLoader instance;   // 先不创建对象

    private ConfigLoader() {
        System.out.println("配置文件加载中...（只应出现一次）");
    }

    public static ConfigLoader getInstance() {
        if (instance == null) {
            instance = new ConfigLoader();  // 第一次使用时才创建
        }
        return instance;
    }

    public String getDbUrl() {
        return "jdbc:mysql://localhost:3306/express";
    }

    public static void main(String[] args) {
        ConfigLoader c1 = ConfigLoader.getInstance();
        ConfigLoader c2 = ConfigLoader.getInstance();
        System.out.println(c1 == c2);        // true
        System.out.println(c2.getDbUrl());
    }
}
```

**运行结果：**

```
配置文件加载中...（只应出现一次）
true
jdbc:mysql://localhost:3306/express
```

**【解析】** 懒汉式与饿汉式的区别只在对象创建时机：饿汉式声明时就 new，懒汉式在 getInstance 里判断 null 后才 new。两次调用只 new 了一次，所以加载提示只打印一行。注意懒汉式在多线程下可能被创建多个对象，需要加锁，第21章学完 synchronized 后可以回来改进。
▶ 关联：饿汉式对照编程题第 3 题；线程安全问题见第21章《特殊文件日志与多线程》。

#### 编程题 5（进阶）：快递站点人员继承体系

**需求：** 站点有快递员（负责某片区派送）和分拣员（属于某班组）。两类人都有姓名、年龄，都要"工作"但工作内容不同。请设计父类 `Staff` 和两个子类 `Courier`、`Sorter`，用 super 初始化公共属性，重写 work()，并用一个 Staff 数组统一遍历调用。

**【参考答案】**

```java
public class Staff {
    private String name;
    private int age;

    public Staff() {}
    public Staff(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void work() {
        System.out.println(name + " 在站点工作");
    }

    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public int getAge() { return age; }
    public void setAge(int age) { this.age = age; }
}
```

```java
public class Courier extends Staff {
    private String area;

    public Courier(String name, int age, String area) {
        super(name, age);          // 公共属性交给父类构造器初始化
        this.area = area;
    }

    @Override
    public void work() {
        System.out.println("快递员 " + getName() + " 负责 " + area + " 片区派送");
    }
}
```

```java
public class Sorter extends Staff {
    private String team;

    public Sorter(String name, int age, String team) {
        super(name, age);
        this.team = team;
    }

    @Override
    public void work() {
        System.out.println("分拣员 " + getName() + " 在 " + team + " 班组分拣快件");
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Staff[] staffs = {
            new Courier("阿强", 28, "海淀"),
            new Sorter("阿珍", 35, "早班一组")
        };
        for (Staff s : staffs) {
            s.work();    // 数组里是父类类型，调用时执行各自子类的重写版本
        }
    }
}
```

**运行结果：**

```
快递员 阿强 负责 海淀 片区派送
分拣员 阿珍 在 早班一组 班组分拣快件
```

**【解析】** name/age 是两类人共性数据，抽到父类并用 super(name, age) 初始化；work() 是共性行为但实现不同，子类重写。`Staff[]` 装子类对象、循环调 work() 已经是多态的雏形。
▶ 关联：private 成员子类通过 get/set 访问（第7章封装）；数组存对象见第6/10章；这里的 `s.work()` 动态绑定在第12章《面向对象进阶（二）》正式讲透。

#### 编程题 6（综合）：快件计费（this(...) 兄弟构造器 + super(...) + 方法重写）

**需求：**
- 父类 `Express`：属性单号 code、重量 weight（kg）、类型 type；运费规则：首重 1kg 收 10 元，超出部分每 kg 加 2 元。
- 两参构造器 `Express(code, weight)` 默认类型为"标准快递"，要求用 this(...) 调用三参构造器，不许重复赋值代码。
- 子类 `FreshExpress`（生鲜快件）：类型固定"生鲜快件"，运费在普通运费基础上加 5 元冷链费，要求重写 fee() 并复用父类计算逻辑。

**【参考答案】**

```java
public class Express {
    private String code;
    private double weight;
    private String type;

    public Express() {}

    // 两参构造器：默认标准快递，用 this(...) 调三参，避免重复代码
    public Express(String code, double weight) {
        this(code, weight, "标准快递");
    }

    public Express(String code, double weight, String type) {
        this.code = code;
        this.weight = weight;
        this.type = type;
    }

    public double fee() {
        return weight <= 1 ? 10 : 10 + (weight - 1) * 2;
    }

    public String getCode() { return code; }
    public double getWeight() { return weight; }
    public String getType() { return type; }
}
```

```java
public class FreshExpress extends Express {
    public FreshExpress(String code, double weight) {
        super(code, weight, "生鲜快件");   // 子类用 super(...) 初始化父类部分
    }

    @Override
    public double fee() {
        return super.fee() + 5;            // 复用父类运费算法，再加冷链费
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Express e1 = new Express("SF001", 3);
        System.out.println(e1.getType() + " 运费：" + e1.fee());   // 10 + 2*2 = 14

        FreshExpress e2 = new FreshExpress("SF002", 3);
        System.out.println(e2.getType() + " 运费：" + e2.fee());   // 14 + 5 = 19
    }
}
```

**运行结果：**

```
标准快递 运费：14.0
生鲜快件 运费：19.0
```

**【解析】**
- this(...) 用在 Express 两参构造器第一行，把默认类型传给三参构造器，省掉重复赋值；
- FreshExpress 构造器第一行用 super(code, weight, "生鲜快件") 调父类三参构造器；
- 重写 fee() 时用 `super.fee()` 调用父类原算法，再追加冷链费——这就是"声明不变、重新实现"中复用父类逻辑的典型写法。
- this(...) 与 super(...) 分别出现在不同构造器中，所以不冲突；同一个构造器里二者不能共存。

▶ 关联：构造器、this 见第7章；super 与方法重写见第8章；`e2.fee()` 调用子类版本属于多态，第12章展开。

---

<div style="page-break-after: always;"></div>

## 第12章 面向对象进阶（二）：多态、final、抽象类与接口 · 习题精讲

> 题型：填空、选择、判断、简答、代码阅读、编程（编程题 6 道，由易到难）。
> 每题给出【答案】与【解析】，解析中用「▶ 关联」串联前后章节。

---

### 一、填空题

**1.** 实现多态必须满足三个条件：有 ______ 关系、子类 ______ 了父类方法、______ 引用指向 ______ 对象。

**【答案】** 继承（或实现）；重写；父类类型（父类引用）；子类（new 子类）

**【解析】** 形如 `Animal a = new Cat();` 之后 `a.eat()` 执行的是 Cat 的实现。注意：多态是对象和方法的多态，成员变量没有多态——变量编译、运行都看父类。
▶ 关联：重写规则在第8/11章；多态参数（父类类型作形参）见编程题第 1 题。

**2.** 多态下不能直接调用子类的独有方法，需要 ______ 转型（强转）；强转前应使用 ______ 关键字判断对象的真实类型，否则可能抛出 ______ 异常。

**【答案】** 向下（强制）；`instanceof`；`ClassCastException`（类型转换异常）

**【解析】** 向上转型（父类引用 = new 子类）自动完成；向下转型 `(Cat) animal` 编译不报错，但运行时真实类型不匹配就抛 ClassCastException。instanceof 判断后再强转是标准写法。
▶ 关联：编程题第 3 题售后检测即此套路。

**3.** final 修饰类表示该类不能被 ______；修饰方法表示该方法不能被 ______；修饰变量表示该变量只能赋值 ______ 次。

**【答案】** 继承；重写；一

**【解析】** final 修饰基本类型变量，数据值不能改；final 修饰引用类型变量（数组、对象），锁定的是地址值，对象里的内容仍然可以修改。
▶ 关联：第8章 final 初识；代码阅读题第 3 题专门验证引用类型的情况。

**4.** 使用 static final 共同修饰的成员变量称为 ______，命名规范是单词全部 ______、多个单词用 ______ 连接。

**【答案】** 常量；大写；下划线（_）

**【解析】** 如 `public static final double SERVICE_FEE_RATE = 0.05;`，常量常集中放在构造器私有的常量类中，一处修改全局生效。
▶ 关联：static 用法见第11章；常量类编程见编程题第 4 题。

**5.** 抽象类用关键字 ______ 修饰；抽象方法没有 ______；一个类继承抽象类后，必须 ______，否则这个类自己也得定义成抽象类。

**【答案】** abstract；方法体（直接分号结束）；重写全部抽象方法

**【解析】** 抽象类不能 new 对象，但可以有构造器（给子类 super 调用）、成员变量、普通方法；抽象类中不一定有抽象方法，但有抽象方法的类一定是抽象类。
▶ 关联：第8章抽象类入门；抽象类与接口如何取舍见简答题第 3 题。

**6.** 接口用关键字 ______ 定义，类用关键字 ______ 实现接口；一个类可以实现 ______ 个接口，接口与接口之间是 ______ 关系。

**【答案】** interface；implements；多；多继承

**【解析】** JDK7 接口中成员变量默认是 public static final 常量、方法默认是 public abstract 抽象方法；类实现接口必须重写全部抽象方法。接口多继承用逗号：`interface C extends A, B {}`。
▶ 关联：第9章接口入门；JDK8 默认方法见填空题第 7 题。

**7.** JDK8 开始接口新增了用 ______ 修饰的默认方法（用实现类对象调用）和用 ______ 修饰的静态方法（只能用接口名调用）；JDK9 又新增了 ______ 方法。

**【答案】** default；static；私有（private）

**【解析】** 默认方法用于给接口增加通用实现、子类可直接继承或重写；私有方法用来抽取默认方法之间的重复代码。
▶ 关联：编程题第 6 题智能设备用到默认方法。

---

### 二、选择题

**1.** 关于多态，下列说法错误的是（　）

A. 父类引用可以调用子类重写过的方法
B. 多态下成员变量看的是父类的值
C. 多态下可以直接调用子类特有的方法
D. 使用父类类型作方法形参，可以接收一切子类对象

**【答案】** C

**【解析】** 编译看左边（父类），父类中没有声明子类独有方法，直接调用编译报错，必须向下转型。B 正确：变量没有多态，编译运行都看父类；D 是多态最实用的场景——一个方法处理所有子类。
▶ 关联：代码阅读题第 1 题验证方法动态绑定。

**2.** 下列代码运行结果是（　）

```java
class Payment {
    public void pay() { System.out.println("现金支付"); }
}
class WeChatPay extends Payment {
    @Override
    public void pay() { System.out.println("微信支付"); }
}
public class Test {
    public static void main(String[] args) {
        Payment p = new WeChatPay();
        p.pay();
    }
}
```

A. 现金支付
B. 微信支付
C. 编译报错
D. 运行异常

**【答案】** B

**【解析】** 编译看左（Payment 有 pay()，编译通过），运行看右（真实对象是 WeChatPay，执行重写版本）。这就是行为多态。
▶ 关联：第8章重写是多态的前提。

**3.** `Animal a = new Dog();` 想调用 Dog 类独有的 lookDoor() 方法，正确写法是（　）

A. `a.lookDoor();`
B. `(Dog) a.lookDoor();`
C. `((Dog) a).lookDoor();`
D. `(Animal) a.lookDoor();`

**【答案】** C

**【解析】** 先把 a 强转为 Dog，再调用方法，强转要用括号包住 `(Dog) a`；B 的写法只强转了方法返回值，编译报错。生产代码中强转前应先 `if (a instanceof Dog)` 判断。
▶ 关联：代码阅读题第 2 题演示不判断直接强转的异常。

**4.** 关于 final 修饰引用类型变量，下列说法正确的是（　）

```java
final Account a = new Account("阿强");
```

A. `a.owner = "阿珍";` 编译报错
B. `a = new Account("阿珍");` 编译报错
C. 两句都报错
D. 两句都不报错

**【答案】** B

**【解析】** final 锁的是变量中存的地址值：不能让 a 指向新对象（B 报错），但对象内部的属性可以改（A 合法）。final 修饰数组时同理——元素能改，数组不能整个换新。
▶ 关联：代码阅读题第 3 题逐行判断。

**5.** 关于抽象类，下列说法错误的是（　）

A. 抽象类不能创建对象
B. 抽象类中可以有构造器、成员变量和普通方法
C. 抽象类中必须包含抽象方法
D. 子类不重写全部抽象方法，子类也必须是抽象类

**【答案】** C

**【解析】** 抽象类中不一定有抽象方法（但有抽象方法的类一定是抽象类）。抽象类不能实例化，因为抽象方法没有方法体、调用了无代码可执行。
▶ 关联：第8章"抽象类为什么不能实例化"。

**6.** 下列关于接口的说法，正确的是（　）

A. 接口可以创建对象
B. 一个类只能实现一个接口
C. 接口中的静态方法可以用实现类对象调用
D. 接口中的默认方法（default）用实现类对象调用

**【答案】** D

**【解析】** 接口不能 new（A 错）；类可以多实现（B 错）；接口静态方法只能用"接口名.方法名"调用（C 错）；默认方法是实例方法，通过实现类对象调用，也可被重写。
▶ 关联：编程题第 6 题 connect() 是默认方法。

**7.** 一个方法参数设计为 `void feed(Animal a)`，下列调用不合法的是（　）

A. `feed(new Cat());`
B. `feed(new Dog());`
C. `Animal a = new Cat(); feed(a);`
D. `Cat c = new Cat(); feed(c.lookDoor());`（假设 lookDoor 返回 void）

**【答案】** D

**【解析】** 形参是 Animal，传任何 Animal 子类对象都合法（A、B、C 都是向上转型）；D 传的是 `c.lookDoor()` 的返回值 void，类型完全不匹配，编译报错。
▶ 关联：多态参数在集合遍历中大量使用——第16章 List 存任意子类对象。

---

### 三、判断题

**1.** 多态场景下，成员变量也表现为"运行看子类"。（　）

**【答案】** ✗ 错误

**【解析】** 成员变量没有多态：编译看左边、运行还看左边（父类的值）；只有方法是"编译看左、运行看右"。口诀：变量看左边，方法动态绑定。
▶ 关联：第9章多态成员访问特点有完整对比。

**2.** 向下转型只要编译通过，运行就一定不会出错。（　）

**【答案】** ✗ 错误

**【解析】** 有继承关系编译就放行，但运行时真实类型与强转类型不符会抛 ClassCastException。标准做法是 instanceof 判断后再强转。
▶ 关联：代码阅读题第 2 题。

**3.** final 修饰的对象，其属性内容也不能修改。（　）

**【答案】** ✗ 错误

**【解析】** final 锁引用类型变量锁的是地址，对象内部属性、数组元素都能改；只有让变量指向新对象/新数组才报错。

**4.** 抽象类不能创建对象，所以抽象类中不能定义构造器。（　）

**【答案】** ✗ 错误

**【解析】** 抽象类可以有构造器，供子类 super(...) 调用以初始化抽象类中定义的共性属性；它只是不能被 new。
▶ 关联：第11章子类构造器先调父类构造器。

**5.** 一个类实现多个接口时，必须重写所有接口中的全部抽象方法。（　）

**【答案】** ✓ 正确

**【解析】** 实现类对每个接口的抽象方法都要重写；如果不想全部重写，只能把自己也声明为抽象类，把实现任务继续转嫁给下一个子类。
▶ 关联：接口多继承时还要连同父接口的抽象方法一起重写。

---

### 四、简答题

**1.** 多态有什么好处？又有什么弊端？如何解决弊端？

**【答案要点】**
- 好处：① 右边对象解耦，`Animal a = new Cat();` 右边随时可以换成 Dog、Pig，调用代码不用改，扩展性强；② 用父类类型作方法形参，可以接收一切子类对象，一个方法替代一堆重载方法。
- 弊端：多态下不能调用子类的独有方法（编译看父类，父类没有该方法）。
- 解决：向下转型 `(子类) 引用`，且强转前用 instanceof 判断真实类型，避免 ClassCastException。

**【解析】** 编程题第 1 题收银台只写一个 checkout(Member, price) 就能服务所有会员类型；第 3 题售后方法内用 instanceof 分流各设备独有功能，正好演示好处与解决方式。
▶ 关联：多态三条件见填空题第 1 题；集合框架中 List/Map 接口多态见第16/17章。

**2.** final 修饰类、方法、变量分别是什么效果？引用类型变量被 final 修饰时到底"锁"住了什么？

**【答案要点】**
- 修饰类：最终类，不能被继承（如 String、JDK 中的 Math）。
- 修饰方法：最终方法，不能被子类重写，但可以被继承调用。
- 修饰变量：只能赋值一次。基本类型锁数据值；引用类型锁地址值（不能指向新对象），但对象内容/数组元素可以修改。
- static final 联合修饰是常量，命名全大写下划线分隔。

**【解析】** 模板方法设计模式中，固定流程的方法用 final 修饰防止子类重写、可变步骤用抽象方法交给子类——编程题第 5 题就是这个组合。
▶ 关联：第8章 final 基础；第13章模板方法模式深入。

**3.** 抽象类和接口有什么区别？什么时候用抽象类、什么时候用接口？

**【答案要点】**

| 对比项 | 抽象类 | 接口 |
| --- | --- | --- |
| 关键字 | abstract class | interface / implements |
| 成员变量 | 普通变量、常量都可以 | 只能是 public static final 常量 |
| 构造器 | 有（供子类 super） | 没有 |
| 方法 | 抽象方法 + 普通方法 | JDK7 只有公共抽象方法；JDK8+ 有 default/static；JDK9+ 有 private |
| 关系 | 类单继承 | 类多实现、接口多继承 |
| 设计含义 | "是什么"——抽取一类事物的共性（含数据） | "能做什么"——定义行为规范/能力 |

- 多个类有共同的数据（属性）和行为，用抽象类抽共性；
- 只是约定一组行为能力、且一个类可能具备多种能力，用接口（如可充电、可联网）。

**【解析】** 编程题第 5 题快递模板用抽象类（包裹名称等共性数据 + 固定流程）；第 6 题"可充电""可联网"是两种能力，用接口、一个设备类可同时实现。
▶ 关联：第8/9章两章分别讲过抽象类与接口；第13章泛型、第23章动态代理都建立在接口之上。

---

### 五、代码阅读题

**1.** 阅读代码，写出运行结果。

```java
class Payment {
    public void pay(double money) {
        System.out.println("现金支付 " + money + " 元");
    }
}
class WeChatPay extends Payment {
    @Override
    public void pay(double money) {
        System.out.println("微信支付 " + money + " 元，立减 0.5 元");
    }
}
class BankCardPay extends Payment {
    @Override
    public void pay(double money) {
        System.out.println("银行卡支付 " + money + " 元");
    }
}
public class Test {
    public static void main(String[] args) {
        Payment p1 = new WeChatPay();
        Payment p2 = new BankCardPay();
        p1.pay(10);
        p2.pay(10);
    }
}
```

**【答案】**

```
微信支付 10.0 元，立减 0.5 元
银行卡支付 10.0 元
```

**【解析】** p1、p2 声明类型都是 Payment，但真实对象分别是 WeChatPay、BankCardPay，方法调用动态绑定到子类重写版本。double 字面量 10 输出为 10.0。
▶ 关联：选择题第 2 题同考点；实际开发中"面向接口编程"见第16章集合（`List<String> list = new ArrayList<>()`）。

**2.** 阅读代码回答问题：程序输出什么？如果把注释行①放开会发生什么？

```java
class Device { }
class Phone extends Device {
    public void call() { System.out.println("打电话"); }
}
class Laptop extends Device {
    public void keyboardLight() { System.out.println("键盘背光开启"); }
}

public class Test {
    public static void main(String[] args) {
        Device d = new Laptop();
        // Phone p = (Phone) d;   // ①
        if (d instanceof Phone) {
            ((Phone) d).call();
        } else {
            System.out.println("不是手机，不能打电话");
        }
        if (d instanceof Laptop) {
            ((Laptop) d).keyboardLight();
        }
    }
}
```

**【答案】** 当前输出：

```
不是手机，不能打电话
键盘背光开启
```

放开①后：编译通过（Phone 与 Device 有继承关系，编译器放行），运行时抛出 `ClassCastException`——d 的真实类型是 Laptop，不能转成 Phone。

**【解析】** instanceof 判断真实类型：d 是笔记本，不是手机，走 else；是笔记本，强转后调用背光方法成功。这正是"强转前先判断"的原因。
▶ 关联：编程题第 3 题把这套判断写成售后检测方法。

**3.** 下列代码中标号的各行，哪些能编译通过、哪些报错？

```java
class Account {
    String owner;
    Account(String owner) { this.owner = owner; }
}
public class Test {
    public static void main(String[] args) {
        final int MAX = 3;
        // MAX = 5;                       // ①
        final int[] arr = new int[2];
        arr[0] = 9;                       // ②
        // arr = new int[3];              // ③
        final Account a = new Account("阿强");
        a.owner = "阿珍";                 // ④
        // a = new Account("阿强");       // ⑤
        System.out.println(arr[0] + "," + a.owner);
    }
}
```

**【答案】** ①③⑤ 编译报错；②④ 合法。最终输出：`9,阿珍`。

**【解析】** ①final 基本类型不能再赋值；③final 数组不能换新数组（地址锁定），但②改元素合法；⑤final 对象变量不能指向新对象，但④修改对象属性合法。
▶ 关联：填空题第 3 题；第8章 final 引用类型小节。

**4.** 下列代码有多处编译错误，请找出至少 3 处并说明原因。

```java
abstract class Printer {
    public abstract void print(String doc);
    public void warmUp() { System.out.println("预热中"); }
}
interface Scannable {
    String TYPE = "A4";
    void scan(String doc);
}
class AllInOne extends Printer implements Scannable {
    public void print(String doc) { System.out.println("打印：" + doc); }
    public void scan(String doc) { System.out.println("扫描：" + doc); }
}
public class Test {
    public static void main(String[] args) {
        Printer p = new Printer();          // ①
        Scannable s = new AllInOne();
        s.scan("合同");                      // ②
        s.print("合同");                     // ③
        System.out.println(s.TYPE);         // ④
    }
}
```

**【答案】**
- ① 报错：抽象类不能实例化，应改为 `new AllInOne()`。
- ③ 报错：接口类型引用只能调用接口中声明的方法（scan），print 是抽象类 Printer 中的方法，Scannable 引用看不到。
- ④ 写法不规范：TYPE 是接口常量（public static final），应通过 `Scannable.TYPE` 访问（用对象 s 访问静态常量虽然能编译但不推荐）。
- ② 合法：接口方法 scan 通过实现类对象动态绑定调用。

**【解析】** 这道题把抽象类、接口、多态引用的可见范围综合在一起：左边是什么类型，就只能调用那个类型里声明过的成员。
▶ 关联：第9章"接口类型只能访问接口中定义的行为"；第16章 `List<String> list = new ArrayList<>()` 后调不到 LinkedList 特有方法是同一道理。

---

### 六、编程题（共 6 题，由易到难）

#### 编程题 1（基础）：会员折扣（抽象类 + 多态参数）

**需求：** 影院会员分黄金会员（8 折）和白银会员（9 折）。设计抽象会员类 `Member`（持有姓名，抽象方法 `double discount(double price)`），两个子类分别实现折扣；再设计收银台类 `Cashier`，只写一个 `checkout(Member m, double price)` 方法就能为任何会员结算。

**【参考答案】**

```java
public abstract class Member {
    private String name;
    public Member(String name) {
        this.name = name;
    }
    public String getName() {
        return name;
    }
    // 抽象方法：不同会员折扣不同，交给子类实现
    public abstract double discount(double price);
}
```

```java
public class GoldMember extends Member {
    public GoldMember(String name) {
        super(name);
    }
    @Override
    public double discount(double price) {
        return price * 0.8;
    }
}
```

```java
public class SilverMember extends Member {
    public SilverMember(String name) {
        super(name);
    }
    @Override
    public double discount(double price) {
        return price * 0.9;
    }
}
```

```java
public class Cashier {
    // 父类类型作形参：黄金、白银会员都能接收
    public void checkout(Member m, double price) {
        System.out.println(m.getName() + " 原价 " + price + " 元，实付 "
                + m.discount(price) + " 元");
    }

    public static void main(String[] args) {
        Cashier c = new Cashier();
        c.checkout(new GoldMember("阿强"), 100);   // 80.0
        c.checkout(new SilverMember("阿珍"), 100); // 90.0
    }
}
```

**运行结果：**

```
阿强 原价 100.0 元，实付 80.0 元
阿珍 原价 100.0 元，实付 90.0 元
```

**【解析】** discount 是共性行为但算法不同 → 抽象方法；checkout 形参用抽象父类 Member，新增"学生会员 75 折"时只需再加一个子类，收银台代码一行不改——这就是多态的解耦价值。
▶ 关联：抽象类语法见填空题第 5 题；多态参数好处见简答题第 1 题。

#### 编程题 2（基础）：多渠道通知（接口 + 接口多态数组）

**需求：** 系统告警要同时通过短信、邮件、App 推送发送。定义通知接口 `Notifier`（`void send(String message)`）和三个实现类；通知服务类用一个方法把消息发给传入的所有渠道。

**【参考答案】**

```java
public interface Notifier {
    void send(String message);
}
```

```java
public class SmsNotifier implements Notifier {
    @Override
    public void send(String message) {
        System.out.println("[短信] " + message);
    }
}
```

```java
public class EmailNotifier implements Notifier {
    @Override
    public void send(String message) {
        System.out.println("[邮件] " + message);
    }
}
```

```java
public class PushNotifier implements Notifier {
    @Override
    public void send(String message) {
        System.out.println("[App推送] " + message);
    }
}
```

```java
public class NoticeService {
    // 接口类型数组：装任意实现类对象
    public void broadcast(Notifier[] channels, String message) {
        for (Notifier n : channels) {
            n.send(message);
        }
    }

    public static void main(String[] args) {
        NoticeService service = new NoticeService();
        Notifier[] channels = {
            new SmsNotifier(),
            new EmailNotifier(),
            new PushNotifier()
        };
        service.broadcast(channels, "服务器 CPU 使用率超过 90%");
    }
}
```

**运行结果：**

```
[短信] 服务器 CPU 使用率超过 90%
[邮件] 服务器 CPU 使用率超过 90%
[App推送] 服务器 CPU 使用率超过 90%
```

**【解析】** "能发通知"是一种能力约定，用接口；三种渠道互不相关（没有共同数据），不适合抽象类。新增"微信通知"只需写新实现类，数组里加一个元素即可。
▶ 关联：第9章接口定义；接口多态与第16章集合遍历（`List<Notifier>`）思路一致。

#### 编程题 3（中等）：售后检测（instanceof + 向下转型）

**需求：** 售后系统收到的设备可能是手机、笔记本、平板。手机能打电话 call()、笔记本有键盘背光 keyboardLight()、平板支持触控笔 stylus()。设计设备父类 `Device`（型号）和三个子类，售后检测方法 `diagnose(Device d)` 内根据真实类型调用对应独有功能。

**【参考答案】**

```java
public class Device {
    private String model;
    public Device(String model) {
        this.model = model;
    }
    public String getModel() {
        return model;
    }
}
```

```java
public class Phone extends Device {
    public Phone(String model) {
        super(model);
    }
    public void call() {
        System.out.println(getModel() + " 正在拨打电话");
    }
}
```

```java
public class Laptop extends Device {
    public Laptop(String model) {
        super(model);
    }
    public void keyboardLight() {
        System.out.println(getModel() + " 开启键盘背光");
    }
}
```

```java
public class Tablet extends Device {
    public Tablet(String model) {
        super(model);
    }
    public void stylus() {
        System.out.println(getModel() + " 使用触控笔书写");
    }
}
```

```java
public class AfterSaleService {
    public void diagnose(Device d) {
        System.out.println("开始检测 " + d.getModel());
        if (d instanceof Phone) {
            ((Phone) d).call();
        } else if (d instanceof Laptop) {
            ((Laptop) d).keyboardLight();
        } else if (d instanceof Tablet) {
            ((Tablet) d).stylus();
        }
    }

    public static void main(String[] args) {
        AfterSaleService service = new AfterSaleService();
        service.diagnose(new Phone("XPhone 15"));
        service.diagnose(new Laptop("ThinkBook 14"));
        service.diagnose(new Tablet("Tab Pro"));
    }
}
```

**运行结果：**

```
开始检测 XPhone 15
XPhone 15 正在拨打电话
开始检测 ThinkBook 14
ThinkBook 14 开启键盘背光
开始检测 Tab Pro
Tab Pro 使用触控笔书写
```

**【解析】** 形参用父类 Device 接收所有设备（多态的好处）；独有方法父类没有，必须 instanceof 判断真实类型后向下转型调用。省略判断直接强转，设备类型不符就抛 ClassCastException。
▶ 关联：代码阅读题第 2 题；第9章 instanceof 语法。

#### 编程题 4（中等）：系统常量类（static final 常量）

**需求：** 定义常量类 `AppConstants` 保存校园快递应用的固定配置：应用名、服务费率（5%）、最大重试次数 3；构造器私有。再写费用计算器：服务费 = 运费 × 费率；连接失败时按最大重试次数循环重试。

**【参考答案】**

```java
public class AppConstants {
    private AppConstants() {}   // 常量类不让创建对象

    public static final String APP_NAME = "校园快递通";
    public static final double SERVICE_FEE_RATE = 0.05;
    public static final int MAX_RETRY = 3;
}
```

```java
public class FeeCalculator {
    public double serviceFee(double freight) {
        return freight * AppConstants.SERVICE_FEE_RATE;
    }

    public static void main(String[] args) {
        FeeCalculator c = new FeeCalculator();
        System.out.println(AppConstants.APP_NAME);
        System.out.println("100 元运费的服务费：" + c.serviceFee(100) + " 元");

        for (int i = 1; i <= AppConstants.MAX_RETRY; i++) {
            System.out.println("第 " + i + " 次连接服务器...");
        }
    }
}
```

**运行结果：**

```
校园快递通
100 元运费的服务费：5.0 元
第 1 次连接服务器...
第 2 次连接服务器...
第 3 次连接服务器...
```

**【解析】** 固定不变的配置用 `static final` 常量：全类一份（static）、不可修改（final）；命名全大写下划线分隔；集中在构造器私有的常量类中，改费率只改一处。
▶ 关联：工具类/常量类构造器私有的原因见第11章；final 三种修饰见简答题第 2 题。

#### 编程题 5（进阶）：快递配送模板（抽象类 + final 模板方法）

**需求：** 所有快件配送都遵循固定流程：称重 → 打包 → 运输 → 签收。其中称重、打包、签收对所有运输方式都一样，只有"运输"不同（陆运走公路、空运走航空）。请用抽象类设计：固定流程方法不允许子类改动，运输步骤交给子类实现。

**【参考答案】**

```java
public abstract class DeliveryTemplate {
    // 模板方法：固定流程，用 final 防止子类重写改动流程
    public final void deliver(String pkg) {
        weigh(pkg);
        pack(pkg);
        transport(pkg);
        sign(pkg);
    }

    private void weigh(String pkg) {
        System.out.println(pkg + " 称重完成");
    }
    private void pack(String pkg) {
        System.out.println(pkg + " 打包完成");
    }
    private void sign(String pkg) {
        System.out.println(pkg + " 已签收");
    }

    // 可变步骤：子类必须实现
    public abstract void transport(String pkg);
}
```

```java
public class LandDelivery extends DeliveryTemplate {
    @Override
    public void transport(String pkg) {
        System.out.println(pkg + " 走公路运输");
    }
}
```

```java
public class AirDelivery extends DeliveryTemplate {
    @Override
    public void transport(String pkg) {
        System.out.println(pkg + " 走航空运输");
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        DeliveryTemplate d1 = new LandDelivery();
        d1.deliver("包裹A");
        System.out.println("--------");
        DeliveryTemplate d2 = new AirDelivery();
        d2.deliver("包裹B");
    }
}
```

**运行结果：**

```
包裹A 称重完成
包裹A 打包完成
包裹A 走公路运输
包裹A 已签收
--------
包裹B 称重完成
包裹B 打包完成
包裹B 走航空运输
包裹B 已签收
```

**【解析】** 这是模板方法设计模式：父类用 final 方法锁定"骨架"流程（final 方法不能重写），把会变化的步骤定义为抽象方法强迫子类实现；通用步骤用 private 方法封装。新增"铁路运输"只需加子类实现 transport()。
▶ 关联：第8/13章模板方法模式；final 方法不能重写见填空题第 3 题。

#### 编程题 6（综合）：智能设备（接口多实现 + 默认方法）

**需求：**
- 定义"可充电"接口 `Rechargeable`：charge()；
- 定义"可联网"接口 `Connectable`：默认方法 connect()（公共逻辑：打印"已连接到校园 WiFi"），抽象方法 sendData(String data)；
- 智能手表 `SmartWatch` 同时具备两种能力；智能音箱 `SmartSpeaker` 只具备联网能力；
- sendData 中先调用 connect() 再上传各自的数据。用接口多态测试音箱。

**【参考答案】**

```java
public interface Rechargeable {
    void charge();
}
```

```java
public interface Connectable {
    // 默认方法：所有联网设备的连接逻辑相同，直接在接口中给通用实现
    default void connect() {
        System.out.println("已连接到校园 WiFi");
    }
    void sendData(String data);
}
```

```java
public class SmartWatch implements Rechargeable, Connectable {
    @Override
    public void charge() {
        System.out.println("手表磁吸充电中");
    }
    @Override
    public void sendData(String data) {
        connect();   // 直接继承接口的默认方法
        System.out.println("手表上传心率数据：" + data);
    }
}
```

```java
public class SmartSpeaker implements Connectable {
    @Override
    public void sendData(String data) {
        connect();
        System.out.println("音箱上传播放记录：" + data);
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        SmartWatch watch = new SmartWatch();
        watch.charge();
        watch.sendData("72次/分");

        System.out.println("--------");
        Connectable speaker = new SmartSpeaker();   // 接口多态
        speaker.sendData("民谣歌单");
    }
}
```

**运行结果：**

```
手表磁吸充电中
已连接到校园 WiFi
手表上传心率数据：72次/分
--------
已连接到校园 WiFi
音箱上传播放记录：民谣歌单
```

**【解析】** "可充电""可联网"是两种独立能力，用接口、可以多实现；connect() 的连接逻辑所有设备相同，用 JDK8 默认方法写在接口里，实现类直接继承、不必重复编码——这正是默认方法的价值。`Connectable speaker = new SmartSpeaker()` 是接口多态，但只能调用 Connectable 中声明的 connect/sendData。
▶ 关联：JDK8 接口新特性见填空题第 7 题；接口多态在第21章 Runnable（线程任务就是接口）、第23章 JDK 动态代理中反复使用。

---

<div style="page-break-after: always;"></div>

## 第13章 面向对象进阶（三）· 习题精讲

> 本章考点：模板方法设计模式、四种内部类（重点：匿名内部类）、枚举、泛型（泛型类/接口/方法、通配符、上下限、泛型擦除）。
> 建议先做题，再看【答案】与【解析】。编程题场景全部原创，请先自己动手写再对答案。

---

### 一、填空题

**1.** 模板方法设计模式中，固定流程骨架的方法称为______方法，建议用______关键字修饰，防止子类重写导致流程失效；不同的部分定义为______方法交给子类实现。

**【答案】** 模板；`final`；抽象

**【解析】** 模板方法把多个子类中重复的代码抽到父类一份，差异部分用抽象方法"留空"。模板方法是给对象直接调用的流程骨架，一旦子类重写它，流程就被破坏，所以用 `final` 封住（JDK 中的 `DateFormat` 就是这样做的）。
▶ 关联：模板方法依赖抽象类，抽象类基础见第8章《面向对象高级（上）》；本章是对第8章模板方法模式的正式总结。

**2.** 匿名内部类的语法格式是 `new ______() { 重写方法 }`，它本质上是一个______，并且会立即创建出该子类的______。

**【答案】** 类或接口（抽象类/接口）；子类；对象

**【解析】** `new 接口(){...}` 并不是在 new 接口（接口不能实例化），而是定义了一个没有名字的实现类并立刻创建它的对象。编译后会生成 `外部类名$1.class` 这样的字节码文件。
▶ 关联：匿名内部类是第9章《面向对象高级（下）》Lambda 入门的前置知识——第15章会学到，当接口是函数式接口时，匿名内部类还能用 Lambda 进一步简化。

**3.** 创建成员内部类对象的完整格式是：`外部类名.内部类名 对象名 = ______`；在内部类中访问外部类成员变量（与局部变量重名时）要用______。

**【答案】** `new 外部类().new 内部类()`；`外部类名.this.成员变量`

**【解析】** 成员内部类对象依赖外部类对象而存在，所以要先 `new 外部类()` 再 `.new 内部类()`。重名时三级访问：局部变量直接写变量名、内部类成员用 `this.变量名`、外部类成员用 `外部类名.this.变量名`。
▶ 关联：`this` 的本质与就近原则见第7章《面向对象基础》，`外部类名.this` 是它在内部类场景下的延伸用法。

**4.** 枚举类第一行罗列的是______，每个都记住枚举类的一个______；枚举类的构造器默认是______的，枚举类本身是______类，不能被继承。

**【答案】** 常量名称；对象；私有（private）；最终（final）

**【解析】** 枚举是存放一组固定常量的特殊类（继承 `java.lang.Enum`）。构造器私有所以外部不能 new，对象只有第一行罗列的那几个；枚举是最终类所以不能被继承。
▶ 关联：`static final` 常量类是枚举的"低配版"，常量与 static 知识见第7章、第11章；枚举常配合 `switch` 使用，switch 语法见第5章《流程控制语句》。

**5.** 泛型工作在______阶段，编译成 class 文件后泛型信息就不存在了，这一现象称为______；因此泛型只能约束______数据类型，集合中存整数要写 `ArrayList<______>`。

**【答案】** 编译；泛型擦除；引用（对象）；`Integer`

**【解析】** 泛型是编译期的类型检查机制：写代码时限死类型、取出元素无需强转；但运行期 class 里没有泛型（反射可以绕过，第23章会学到）。泛型不支持 8 种基本类型，必须用包装类。
▶ 关联：包装类 `Integer` 见第14章《常用API进阶》；集合上的泛型应用见第16章《异常与List集合》、第17章《Set与Map集合》。

**6.** 泛型通配符中，`? extends Car` 称为泛型______，表示能接收 Car 及其______；`? super Car` 称为泛型______，表示能接收 Car 及其______。

**【答案】** 上限；子类；下限；父类

**【解析】** `?` 代表"使用泛型时"的任意类型；`extends` 限定"最多到 Car"（Car 和子类），`super` 限定"最少是 Car"（Car 和父类）。记忆：extends 管向下（儿子），super 管向上（父亲）。
▶ 关联：父子类、向上转型是理解上下限的前提，见第8章继承、第9/12章多态。

---

### 二、选择题

**1.** 关于匿名内部类，下列说法正确的是（　）

A. 匿名内部类必须先在包中定义一个有名字的类才能使用
B. 匿名内部类的本质是一个接口
C. `new 接口(){ 重写方法 }` 本质是定义了一个子类并立刻创建其子类对象
D. 匿名内部类不能作为方法的实参传递

**【答案】** C

**【解析】** 匿名内部类 = 无名子类 + 立即创建对象，正好解决"只用一次的实现类还要单独建文件"的麻烦；它非常常见的用法就是直接作为实参传给形参为接口/抽象类的方法。A 错（这正是它要省掉的步骤）；B 错（它是类不是接口）；D 错。
▶ 关联：接口作为方法形参（多态参数）见第9章；第15章 Lambda 表达式就是匿名内部类在函数式接口上的简写。

**2.** 静态内部类中，可以访问外部类的（　）

A. 实例成员变量和实例方法
B. 静态成员变量和静态方法
C. 静态成员和实例成员都可以
D. 外部类的一切成员都不能访问

**【答案】** B

**【解析】** 静态内部类有 `static` 修饰，随外部类加载而存在，不依赖外部类对象；而实例成员必须先有对象才能访问，所以静态内部类只能碰外部类的静态成员。这和"静态方法不能直接访问实例成员"是同一条规则。
▶ 关联：static 成员与实例成员的访问规则见第7章、第11章《面向对象进阶（一）》。

**3.** 下列关于枚举的说法，错误的是（　）

A. 枚举类第一行只能罗列合法的常量名，多个用逗号隔开
B. 枚举类可以像普通类一样被其他类继承
C. 枚举自带 `values()` 方法，可以获取所有常量
D. 枚举可以直接用在 switch 语句中

**【答案】** B

**【解析】** 枚举类是最终类（final），不可以被继承；构造器也是私有的，对外不能 new。枚举相比"常量类"的最大优势就是参数取值受约束、类型安全。
▶ 关联：final 修饰类的含义见第8章、第12章；switch 语法见第5章。

**4.** 关于泛型的作用，下列说法正确的是（　）

A. 泛型在程序运行期检查数据类型
B. 使用泛型后取出集合元素仍然需要强制类型转换
C. 泛型在编译期约束操作的数据类型，避免强转和 ClassCastException
D. 泛型信息会一直保留在运行期的 class 文件中

**【答案】** C

**【解析】** 不用泛型时集合什么都能存，取出来都是 Object，一强转就可能在运行期抛 ClassCastException；加了泛型，存错类型编译就报错，取出直接是目标类型。泛型只在编译期有效（泛型擦除）。
▶ 关联：ClassCastException 即类型转换异常，与多态中的向下转型相关，见第9章；集合遍历见第16章。

**5.** 已有 `class Fu {}`、`class Car extends Fu {}`、`class BENZ extends Car {}`、`class BMW extends Car {}`，下列方法调用中**编译报错**的是（　）

```java
public static void test(ArrayList<? extends Car> list) {}
```

A. `test(new ArrayList<Car>())`
B. `test(new ArrayList<BENZ>())`
C. `test(new ArrayList<BMW>())`
D. `test(new ArrayList<Fu>())`

**【答案】** D

**【解析】** `? extends Car` 是上限：只接收 Car 本身和 Car 的子类。BENZ、BMW 都是 Car 子类没问题；Fu 是 Car 的父类，超出上限，编译报错。
▶ 关联：继承体系与向上转型见第8章；泛型集合见第16章。

**6.** 模板方法设计模式中，定义在父类里的抽象方法的作用是（　）

A. 把所有子类的流程固定死，子类什么都不用做
B. 代表流程中因子类而异的部分，由子类重写实现
C. 用 static 修饰，供外部直接调用
D. 方法体里写公共代码

**【答案】** B

**【解析】** 模板方法（final）= 公共流程骨架；抽象方法 = 流程中"各家不同"的填空位。子类只重写抽象方法，公共代码一份都不用重复写。
▶ 关联：抽象方法没有方法体、子类必须重写，规则见第8章抽象类、第12章《面向对象进阶（二）》。

---

### 三、判断题

**1.** 匿名内部类编译后会生成类似 `Test$1.class` 的字节码文件。（　）

**【答案】** 正确。

**【解析】** 匿名内部类虽然代码里没名字，但编译后 JVM 仍需要一个类来承载它，命名规则是"外部类名$序号"。这也说明它在字节码层面是一个真实存在的子类。

**2.** 枚举类可以被其他类继承，从而扩展新的常量。（　）

**【答案】** 错误。

**【解析】** 枚举类是最终类，不能被继承；枚举的取值在定义时就固定了，这正是"固定数量常量集合"的含义。要新增常量只能改枚举类源码。

**3.** 泛型方法的类型变量声明（如 `<T>`）写在方法的返回值类型之前。（　）

**【答案】** 正确。

**【解析】** 格式为 `修饰符 <T> 返回值类型 方法名(形参列表)`，如 `public static <T> T get(T data)`。`<T>` 先告诉编译器"T 是一个类型占位符"，后面的返回值和形参才能使用它。
▶ 关联：占位符思想和泛型类 `<E>` 一致，泛型类在 ArrayList 上的应用见第10章。

**4.** `ArrayList<int> list = new ArrayList<>();` 是合法写法。（　）

**【答案】** 错误。

**【解析】** 泛型只支持引用类型，不支持基本类型。存整数要写 `ArrayList<Integer>`，存入 `int` 时自动装箱、取出时自动拆箱。
▶ 关联：自动装箱/拆箱见第14章包装类。

**5.** 局部内部类可以在定义它的方法之外，通过 `new` 创建对象使用。（　）

**【答案】** 错误。

**【解析】** 局部内部类定义在方法/代码块/构造器中，作用域仅限于该局部范围，出了方法就不可见，只能在方法内部 new 对象并使用。
▶ 关联：局部变量的作用域见第7章成员变量与局部变量对比。

---

### 四、简答题

**1.** 模板方法设计模式解决了什么问题？写出它的编写要点。

**【答案】**
- 解决的问题：多个子类的方法中存在大量重复代码（流程相同、个别步骤不同），重复维护成本高。
- 编写要点：
  1. 定义一个抽象类作为父类；
  2. 在父类中定义**模板方法**：把相同的流程代码放进去，用 `final` 修饰防止子类重写；
  3. 把流程中因子类而异的步骤定义为**抽象方法**，由各子类重写；
  4. 调用时使用父类引用（或直接 new 子类）调用模板方法即可。

**【解析】** 一句话：流程骨架父类定（final 保住骨架），差异步骤子类填。
▶ 关联：抽象类与抽象方法语法见第8章；第9章的接口也能定义"规范"，但接口没有方法体、不能承载公共代码，所以模板方法必须用抽象类。

**2.** 列表对比四种内部类的定义位置与重点程度。

**【答案】**

| 分类 | 定义位置 | 创建/特点 | 重点程度 |
| --- | --- | --- | --- |
| 成员内部类 | 类中成员位置，无 static | `new 外部类().new 内部类()`；可用 `外部类名.this` 访问外部成员 | 了解 |
| 静态内部类 | 类中成员位置，static 修饰 | 只能访问外部类静态成员 | 了解 |
| 局部内部类 | 方法/代码块/构造器中 | 只能在定义它的局部范围内使用 | 了解 |
| 匿名内部类 | 方法中，`new 接口/抽象类(){...}` | 本质是无名子类并立即创建对象，常作方法实参 | **重点** |

**【解析】** 开发中真正高频使用的是匿名内部类：当方法形参是接口/抽象类，而实现类只用一次时，就地 new 一个匿名内部类最简洁。
▶ 关联：第9章已初步接触匿名内部类；第15章 Lambda 会把它再简化一层。

**3.** 相比"常量类"，枚举有什么优势？请举例说明。

**【答案】**
- 常量类（`public static final String BOY = "男"`）作为参数时，形参是 String，调用方可以传任意字符串（如 `"嘿嘿"`），**参数值不受约束**，编译不报错、运行出问题。
- 枚举作为参数时，形参是枚举类型，调用方只能传枚举中定义的常量（如 `Sex.BOY`），传别的值**编译就报错**，类型安全、可读性好，还能直接用于 switch。

**【解析】** 枚举 = 类型安全的常量集合。适合表达性别、星期、季节、订单状态、支付方式等"取值固定"的数据。
▶ 关联：switch 匹配枚举见第5章；常量（static final）见第7/11章。

**4.** 简述泛型中 `?`、`T/E/K/V`、`? extends X`、`? super X` 的区别。

**【答案】**
- `E、T、K、V`：在**定义**泛型类/接口/方法时声明的类型变量（占位符）；
- `?` 通配符：在**使用**泛型时代表"任意类型"，如 `ArrayList<?>` 可接收任何泛型集合；
- `? extends X`：上限，接收 X 及其子类；
- `? super X`：下限，接收 X 及其父类。

**【解析】** 记忆口诀：定义用字母（T/E），使用用问号（?）；extends 向下收子类，super 向上收父类。设计层面越通用越好（大量用泛型），使用层面越精确越好（明确具体类型）。
▶ 关联：泛型在集合框架中的实际使用见第16、17章。

---

### 五、代码阅读题

**1.** 阅读代码，写出运行结果。

```java
public class Library {
    private int level = 1;          // 图书馆共有 1 层对外开放

    public class Bookshelf {
        private int level = 2;      // 书架有 2 层隔板
        public void show() {
            int level = 3;          // 本次清点第 3 层隔板
            System.out.println(level);
            System.out.println(this.level);
            System.out.println(Library.this.level);
        }
    }

    public static void main(String[] args) {
        Library.Bookshelf shelf = new Library().new Bookshelf();
        shelf.show();
    }
}
```

**【答案】**
```
3
2
1
```

**【解析】** 三级重名按就近原则：
- `level` → 方法内局部变量 3；
- `this.level` → 当前内部类对象的成员 2；
- `Library.this.level` → 外部类 Library 对象的成员 1。
▶ 关联：this 与就近原则见第7章；成员内部类对象必须依托外部类对象（`new Library().new Bookshelf()`）。

**2.** 下面代码能否编译通过？如果不能，指出错误行并说明原因、给出修改方法。

```java
public class Outer {
    private static String brand = "顺丰";
    private String address = "深圳";

    public static class Inner {
        public void test() {
            System.out.println(brand);      // 第1处
            System.out.println(address);    // 第2处
        }
    }
}
```

**【答案】** 第2处编译报错。静态内部类不能访问外部类的实例成员 `address`。

**【解析】** `Inner` 是静态内部类，随外部类加载，此时外部类对象还不一定存在，而实例成员 `address` 必须有对象才能访问。第1处 `brand` 是静态成员，可以访问。修改方法任选：把 `address` 也加 `static`；或在方法内创建外部类对象后访问：`System.out.println(new Outer().address);`。
▶ 关联：静态成员不能直接访问实例成员，这条规则在 static 方法上同样成立，见第7章、第11章。

**3.** 阅读代码，写出运行结果。

```java
public interface NumberFilter {
    boolean match(int n);
}

public class FilterTest {
    public static int count(int[] data, NumberFilter f) {
        int c = 0;
        for (int n : data) {
            if (f.match(n)) c++;
        }
        return c;
    }

    public static void main(String[] args) {
        int[] nums = {12, 33, 4, 9, 100, 7};
        int even = count(nums, new NumberFilter() {
            public boolean match(int n) { return n % 2 == 0; }
        });
        int big = count(nums, new NumberFilter() {
            public boolean match(int n) { return n > 10; }
        });
        System.out.println(even + "," + big);
    }
}
```

**【答案】**
```
3,3
```

**【解析】**
- 第一个匿名内部类筛选偶数：12、4、100 共 3 个；
- 第二个筛选大于 10 的数：12、33、100 共 3 个。
`count` 方法的形参是接口 `NumberFilter`，调用时用匿名内部类就地给出不同实现，不需要为每种筛选单独建类文件。
▶ 关联：接口作为方法形参是多态的典型用法（第9章）；这段代码在第15章可以用 Lambda 简化为 `count(nums, n -> n % 2 == 0)`。

**4.** 阅读代码，写出运行结果。

```java
public enum TeaSize {
    SMALL, MEDIUM, LARGE
}

public class TeaTest {
    public static void price(TeaSize size) {
        switch (size) {
            case SMALL:
                System.out.println("小杯 3 元");
                break;
            case MEDIUM:
                System.out.println("中杯 5 元");
                break;
            case LARGE:
                System.out.println("大杯 7 元");
                break;
        }
    }

    public static void main(String[] args) {
        price(TeaSize.LARGE);
        System.out.println(TeaSize.values().length);
    }
}
```

**【答案】**
```
大杯 7 元
3
```

**【解析】** switch 匹配枚举常量时，case 后直接写常量名（不带枚举类名前缀）。`values()` 是编译器给枚举类新增的方法，返回全部常量组成的数组，长度为 3。
▶ 关联：switch 语法与 break 穿透见第5章。

**5.** 阅读代码，写出运行结果。

```java
public class GenericMethodTest {
    public static <T> T first(T[] arr) {
        return arr[0];
    }

    public static void main(String[] args) {
        String s = first(new String[]{"顺丰", "京东"});
        Integer i = first(new Integer[]{100, 200});
        System.out.println(s + i);
    }
}
```

**【答案】**
```
顺丰100
```

**【解析】** 泛型方法"传什么类型，T 就是什么类型"：传 String[] 返回 String，传 Integer[] 返回 Integer，无需强转。最后 `s + i` 是字符串拼接（+ 遇到字符串变拼接），结果 `顺丰100`。
▶ 关联：字符串拼接规则见第3章《运算符》；泛型方法在第15章 Arrays、第18章 Stream 中大量出现。

---

### 六、编程题（共 5 题，由易到难）

#### 编程题 1（基础）：快递下单流程模板

**需求：** 各家快递公司的下单流程都是"填信息 → 计价 → 出电子面单 → 运输 → 完成"，其中**填信息、出面单、完成三步完全相同**，但**计价规则和运输方式各不相同**。请用模板方法设计模式实现：

- 顺丰空运：首重 1kg 收 18 元，每多 1kg 加 6 元，飞机运输；
- 京东陆运：首重 1kg 收 10 元，每多 1kg 加 3 元，汽车运输。

**参考代码：**

```java
// 抽象父类：快递下单模板
public abstract class ExpressOrder {
    // 模板方法：流程固定，final 修饰禁止子类重写
    public final void placeOrder() {
        System.out.println("【1】客户线上填写寄件信息");
        calculateFee();
        System.out.println("【3】系统生成电子面单");
        transport();
        System.out.println("【5】快件发出，下单流程结束");
        System.out.println("------------------");
    }

    // 抽象步骤：交给各家快递公司实现
    protected abstract void calculateFee();
    protected abstract void transport();
}
```

```java
// 顺丰空运
public class SfAirExpress extends ExpressOrder {
    private int weight;   // 重量（整 kg）

    public SfAirExpress(int weight) {
        this.weight = weight;
    }

    @Override
    protected void calculateFee() {
        int fee = 18 + (weight - 1) * 6;
        System.out.println("【2】顺丰空运计价：" + weight + "kg，运费 " + fee + " 元");
    }

    @Override
    protected void transport() {
        System.out.println("【4】快件交由航空部，飞机运输");
    }
}
```

```java
// 京东陆运
public class JdLandExpress extends ExpressOrder {
    private int weight;

    public JdLandExpress(int weight) {
        this.weight = weight;
    }

    @Override
    protected void calculateFee() {
        int fee = 10 + (weight - 1) * 3;
        System.out.println("【2】京东陆运计价：" + weight + "kg，运费 " + fee + " 元");
    }

    @Override
    protected void transport() {
        System.out.println("【4】快件交由陆运部，汽车运输");
    }
}
```

```java
public class ExpressTest {
    public static void main(String[] args) {
        ExpressOrder e1 = new SfAirExpress(3);   // 18 + 2*6 = 30
        e1.placeOrder();
        ExpressOrder e2 = new JdLandExpress(5);  // 10 + 4*3 = 22
        e2.placeOrder();
    }
}
```

**运行结果：**
```
【1】客户线上填写寄件信息
【2】顺丰空运计价：3kg，运费 30 元
【3】系统生成电子面单
【4】快件交由航空部，飞机运输
【5】快件发出，下单流程结束
------------------
【1】客户线上填写寄件信息
【2】京东陆运计价：5kg，运费 22 元
【3】系统生成电子面单
【4】快件交由陆运部，汽车运输
【5】快件发出，下单流程结束
------------------
```

**【解析】** 公共流程（1/3/5 步）只在父类模板方法里写一份；两个子类只关心自己的计价和运输方式。以后新增"圆通"只需要再写一个子类，流程代码一行都不用动。
▶ 关联：抽象类、abstract 方法见第8章；多态下父类引用调用模板方法见第9/12章。

#### 编程题 2（基础）：会议室设备自检

**需求：** 会议室开会前要对多种设备做自检，每种设备的检查内容不同。请定义一个"设备自检"接口，测试方法接收接口对象并打印结果；在 main 中用**匿名内部类**分别完成投影仪、音响、空调三项检测，不允许单独创建实现类文件。

**参考代码：**

```java
public interface DeviceCheck {
    void check();
}
```

```java
public class MeetingRoom {
    // 形参是接口：传什么设备，就跑什么设备的自检
    public static void runCheck(String deviceName, DeviceCheck check) {
        System.out.print("正在检测【" + deviceName + "】：");
        check.check();
    }

    public static void main(String[] args) {
        runCheck("投影仪", new DeviceCheck() {
            @Override
            public void check() {
                System.out.println("灯泡正常，输出分辨率 1080P");
            }
        });
        runCheck("音响", new DeviceCheck() {
            @Override
            public void check() {
                System.out.println("左右声道正常，音量适中");
            }
        });
        runCheck("空调", new DeviceCheck() {
            @Override
            public void check() {
                System.out.println("制冷正常，已设为 26℃");
            }
        });
    }
}
```

**运行结果：**
```
正在检测【投影仪】：灯泡正常，输出分辨率 1080P
正在检测【音响】：左右声道正常，音量适中
正在检测【空调】：制冷正常，已设为 26℃
```

**【解析】** 三个设备只在这一次自检中使用，为它们各建一个类文件很啰嗦；匿名内部类就地实现接口、就地创建对象，代码紧凑。
▶ 关联：接口作方法形参（多态）见第9章；这段代码在学完第15章后可用 Lambda 写成 `runCheck("投影仪", () -> System.out.println("..."))`。

#### 编程题 3（中等）：快递订单状态枚举

**需求：** 快递订单有四种状态：待揽收、运输中、派送中、已签收。请用枚举表示（每个状态带中文描述和一句给客户的提示语），并编写方法根据状态打印客户提示；遍历输出全部状态。

**参考代码：**

```java
public enum OrderStatus {
    // 第一行：常量，每个常量记住枚举类的一个对象，构造时传入描述和提示
    WAIT_PICKUP("待揽收", "请保持电话畅通，等待快递员上门"),
    IN_TRANSIT("运输中", "包裹正在运输网络中流转，可查看物流轨迹"),
    DELIVERING("派送中", "包裹已到达网点，请准备好取件码"),
    SIGNED("已签收", "包裹已签收，感谢使用");

    private final String desc;
    private final String tip;

    // 枚举构造器默认私有，private 可省略
    OrderStatus(String desc, String tip) {
        this.desc = desc;
        this.tip = tip;
    }

    public String getDesc() {
        return desc;
    }

    public String getTip() {
        return tip;
    }
}
```

```java
public class OrderStatusTest {
    public static void showTip(OrderStatus status) {
        switch (status) {
            case WAIT_PICKUP:
            case IN_TRANSIT:
            case DELIVERING:
            case SIGNED:
                System.out.println(status.getDesc() + "：" + status.getTip());
                break;
        }
    }

    public static void main(String[] args) {
        // values() 获取全部常量
        for (OrderStatus status : OrderStatus.values()) {
            showTip(status);
        }
    }
}
```

**运行结果：**
```
待揽收：请保持电话畅通，等待快递员上门
运输中：包裹正在运输网络中流转，可查看物流轨迹
派送中：包裹已到达网点，请准备好取件码
已签收：包裹已签收，感谢使用
```

**【解析】** 枚举从第二行起可以定义成员变量、构造器、方法；构造器在第一行罗列常量时自动调用。如果用 String 表示状态，调用方可能传入 `"已发货"` 这种不存在的值，枚举则从编译层面杜绝。
▶ 关联：switch 见第5章；增强 for 遍历见第10章 ArrayList。

#### 编程题 4（中等）：快递柜泛型格子

**需求：** 快递柜的每个格子可以存放一个物品，存入后占用、取出后空闲。请用**泛型类**设计格子 `LockerBox<T>`，使其既能存放快递包裹对象，也能复用来存放文件袋（String）；要求处理"格子已占用再存"和"空格子取件"两种提示。

**参考代码：**

```java
// T 是占位符：使用时指定格子里存什么类型
public class LockerBox<T> {
    private T item;
    private boolean empty = true;

    public void put(T item) {
        if (!empty) {
            System.out.println("格子已被占用，存入失败");
            return;
        }
        this.item = item;
        this.empty = false;
        System.out.println("存入成功：" + item);
    }

    public T take() {
        if (empty) {
            System.out.println("格子是空的，无件可取");
            return null;
        }
        T t = item;
        item = null;
        empty = true;
        System.out.println("取出成功：" + t);
        return t;
    }

    public boolean isEmpty() {
        return empty;
    }
}
```

```java
public class Parcel {
    private String code;
    private String company;

    public Parcel(String code, String company) {
        this.code = code;
        this.company = company;
    }

    @Override
    public String toString() {
        return company + "快递（取件码：" + code + "）";
    }
}
```

```java
public class LockerTest {
    public static void main(String[] args) {
        // 1 号柜：只存 Parcel 包裹，存错类型编译就报错
        LockerBox<Parcel> box = new LockerBox<>();
        box.put(new Parcel("8-3-1209", "顺丰"));
        box.put(new Parcel("1-1-0001", "京东"));   // 已占用，失败
        box.take();
        box.take();                                 // 已空，失败

        // 另一个格子复用同一泛型类，存 String 类型的文件袋编号
        LockerBox<String> docBox = new LockerBox<>();
        docBox.put("机密文件袋 A-07");
    }
}
```

**运行结果：**
```
存入成功：顺丰快递（取件码：8-3-1209）
格子已被占用，存入失败
取出成功：顺丰快递（取件码：8-3-1209）
格子是空的，无件可取
存入成功：机密文件袋 A-07
```

**【解析】** 一个泛型类 `LockerBox<T>` 同时服务于"存包裹"和"存文件袋"两种场景，代码复用；而且 `LockerBox<Parcel>` 中调用 `put("字符串")` 编译直接报错，类型安全。
▶ 关联：泛型在 ArrayList 上的用法见第10章；toString 重写见第8/14章。

#### 编程题 5（进阶）：泛型工具方法 + 上限通配符

**需求：**
1. 写一个泛型方法 `printAll(T[] arr)`，能打印任意类型数组（String 数组、Integer 数组、Double 数组都行），格式 `[a, b, c]`；
2. 写一个方法 `sumWeight(List<? extends Number> list)`，统计一批"数字重量"的总和——整数重量 `List<Integer>` 和小数重量 `List<Double>` 都能传入，方法内部统一按 double 求和。

**参考代码：**

```java
import java.util.ArrayList;
import java.util.List;

public class WeightTool {
    // 泛型方法：<T> 声明在返回值前，传入什么类型数组就打印什么类型
    public static <T> void printAll(T[] arr) {
        StringBuilder sb = new StringBuilder("[");
        for (int i = 0; i < arr.length; i++) {
            sb.append(arr[i]);
            if (i < arr.length - 1) {
                sb.append(", ");
            }
        }
        sb.append("]");
        System.out.println(sb);
    }

    // 泛型上限：只接收 Number 及其子类（Integer、Double、Long...）
    public static double sumWeight(List<? extends Number> list) {
        double sum = 0;
        for (Number n : list) {
            sum += n.doubleValue();   // Number 是所有数值包装类的共同父类
        }
        return sum;
    }

    public static void main(String[] args) {
        printAll(new String[]{"顺丰", "京东", "圆通"});
        printAll(new Integer[]{1, 2, 3});
        printAll(new Double[]{1.5, 2.5});

        List<Integer> intWeights = new ArrayList<>();
        intWeights.add(3);
        intWeights.add(5);
        System.out.println("整数重量合计：" + sumWeight(intWeights));

        List<Double> doubleWeights = new ArrayList<>();
        doubleWeights.add(2.5);
        doubleWeights.add(4.0);
        System.out.println("小数重量合计：" + sumWeight(doubleWeights));
    }
}
```

**运行结果：**
```
[顺丰, 京东, 圆通]
[1, 2, 3]
[1.5, 2.5]
整数重量合计：8.0
小数重量合计：6.5
```

**【解析】**
- 泛型方法让一个方法适配所有类型的数组；
- `? extends Number` 保证集合里元素一定是 Number 的子类，所以可以安全调用 `doubleValue()`；若形参写成 `List<Integer>`，Double 集合就传不进来。
▶ 关联：包装类 Integer/Double 与 Number 父类见第14章；List/ArrayList 见第10、16章。

---

### 本章自测清单

- [ ] 能说出模板方法模式"final 模板方法 + 抽象方法"的写法和作用
- [ ] 能写出成员内部类创建对象格式、三级重名访问方式
- [ ] 能说出静态内部类的访问限制
- [ ] 能随手写匿名内部类作为方法实参，并知道它编译后生成 `$序号.class`
- [ ] 能定义带属性的枚举，用 values() 遍历、用 switch 匹配
- [ ] 能写泛型类、泛型接口、泛型方法
- [ ] 能区分 `?`、`? extends X`、`? super X`
- [ ] 能解释泛型擦除、泛型不支持基本类型的原因

---

<div style="page-break-after: always;"></div>

## 第14章 常用 API（进阶）· 习题精讲

> 本章考点：Object（toString/equals/hashCode/clone 深浅克隆）、Objects、包装类装箱拆箱、StringBuilder/StringBuffer/StringJoiner、Math/System/Runtime、BigDecimal、传统日期（Date/SimpleDateFormat/Calendar）、JDK8 新日期（LocalDate/LocalTime/LocalDateTime/Instant/DateTimeFormatter/Period/Duration）。
> 编程题场景全部原创，请先自己动手写再对答案。

---

### 一、填空题

**1.** Object 类中 `equals()` 方法默认比较两个对象的______是否相同；它存在的意义是被子类______，以便按对象内容比较。

**【答案】** 地址；重写

**【解析】** Object 祖宗类中 equals 的本质就是 `==`（比地址）；String 等类重写后改为比内容。所以面试题"`==` 和 equals 的区别"：默认没区别，区别在于 equals 可被重写。
▶ 关联：String 的 equals 比较见第10章《常用API与综合案例》；Objects.equals 的防空写法见本章第三节、第9章。

**2.** 对象克隆需要让类实现______标记接口（该接口是空接口）；浅克隆中，引用类型属性的______和源对象相同，修改克隆对象的引用内容，源对象______（会/不会）跟着变。

**【答案】** `Cloneable`；地址值；会

**【解析】** 浅克隆只复制对象本身和基本类型属性，引用类型属性复制的是地址（"地址一样，名字不一样"）；深克隆要在重写的 clone 中对引用字段再克隆一次。
▶ 关联：引用类型地址共享（双引用一改全改）在第6章数组、第7章对象内存图中已反复出现。

**3.** 8 种基本类型中，int 的包装类是______，char 的包装类是______；把字符串 `"129"` 转成 int 用______方法，把 int 转成字符串可用______方法。

**【答案】** `Integer`；`Character`；`Integer.parseInt(String)`；`Integer.toString(int)`（或 `String.valueOf`）

**【解析】** 包装类把基本类型包装成对象，用于集合、泛型等只能放对象的场景；Java 5 起支持自动装箱/拆箱。注意 parseInt 返回基本类型 int，valueOf 返回包装类（再自动拆箱）。
▶ 关联：`ArrayList<Integer>` 存整数见第10章；泛型不支持基本类型见第13章泛型。

**4.** 解决浮点运算失真要用______类；创建对象推荐使用______静态方法而不是 `new BigDecimal(double)`；除法除不尽时必须调用带"保留位数 + ______"三个参数的 divide，否则抛 ArithmeticException。

**【答案】** `BigDecimal`；`BigDecimal.valueOf(...)`；舍入模式（`RoundingMode.HALF_UP` 四舍五入）

**【解析】** `0.1 + 0.2` 在 double 下是 `0.30000000000000004`；`new BigDecimal(0.1)` 会把这个失真值原样带入，`valueOf(0.1)` 或字符串构造才精确。
▶ 关联：浮点数精度问题在第2章基本类型、第3章运算符已埋下伏笔。

**5.** SimpleDateFormat 中，把日期转成字符串用______方法，把字符串解析回日期用______方法；解析时模式字符串必须与目标字符串的格式______。

**【答案】** `format`；`parse`；完全一致

**【解析】** 模式字母：yyyy 年、MM 月、dd 日、HH 时（24小时制）、mm 分、ss 秒。格式不匹配会抛 ParseException。parse 需要处理异常（第16章会学）。
▶ 关联：异常与 try-catch 见第16章《异常与List集合》。

**6.** JDK8 新日期 API 中，只含年月日的是______，只含时分秒的是______，两者都含的是 LocalDateTime；新日期对象都是______对象，修改方法（with/plus/minus）会返回______，原对象不变。

**【答案】** `LocalDate`；`LocalTime`；不可变；新对象

**【解析】** 传统 Date/Calendar 是可变对象、线程不安全；JDK8 新日期类不可变、线程安全、可精确到纳秒。所以 `ld.plusDays(10)` 必须接收返回值才看得到变化。
▶ 关联：String 不可变性同理，见第10章。

---

### 二、选择题

**1.** 关于 `==` 和 `equals()`，下列说法正确的是（　）

A. 两者永远完全等价
B. `==` 比较地址；equals 默认也是比地址，但可以被子类重写为比较内容
C. 重写 equals 后，`==` 也会自动变成比较内容
D. equals 只能比较基本类型

**【答案】** B

**【解析】** Object 中 equals 的源码就是 `==`；String、包装类等重写后比内容。但重写 equals 改变不了 `==` 的行为——`new` 出来的两个内容相同对象，`s1 == s2` 永远是 false（地址不同）。
▶ 关联：字符串常量池中 `==` 与 equals 的各种 true/false 判断见第10章。

**2.** 关于浅克隆，下列说法正确的是（　）

A. 浅克隆会把引用类型属性指向的对象也复制一份
B. 浅克隆后，修改克隆对象的引用类型属性内容，源对象会跟着改变
C. 浅克隆不需要实现 Cloneable 接口
D. 浅克隆后两个对象的地址相同

**【答案】** B

**【解析】** 浅克隆复制基本类型属性值，引用类型属性只复制地址（两个引用指向同一个对象）。深克隆则要对引用字段单独再克隆。克隆出的是新对象，地址不同。
▶ 关联：引用类型传值/共享地址见第6章数组内存、第7章对象内存图。

**3.** 计算 `0.1 + 0.2` 并要求得到精确结果 0.3，正确写法是（　）

A. `new BigDecimal(0.1).add(new BigDecimal(0.2))`
B. `0.1 + 0.2`
C. `BigDecimal.valueOf(0.1).add(BigDecimal.valueOf(0.2))`
D. `(double)(0.1 + 0.2)`

**【答案】** C

**【解析】** `new BigDecimal(double)` 接收的是已经失真的二进制近似值，不推荐；`valueOf(double)` 内部走字符串转换，结果精确。
▶ 关联：包装类 valueOf/parseXxx 见本章第四节。

**4.** 关于 StringBuilder 和 StringBuffer，下列说法正确的是（　）

A. 两者都是可变字符串容器，StringBuilder 线程不安全、速度快，StringBuffer 线程安全
B. StringBuffer 拼接效率比 StringBuilder 更高
C. StringBuilder 是不可变字符串
D. 单线程环境下应优先使用 StringBuffer

**【答案】** A

**【解析】** StringBuffer 的方法加了 synchronized 保证线程安全，但有性能开销；不涉及多线程时用 StringBuilder 更快。多线程概念见第21章。
▶ 关联：String 用 + 拼接底层会 new StringBuilder 产生临时对象，见第10章；synchronized 见第21章《特殊文件日志与多线程》。

**5.** 下列关于 JDK8 新日期 API 的说法，错误的是（　）

A. LocalDate 只包含年月日，不包含时分秒
B. LocalDateTime 的 plusDays/withYear 等方法会修改对象本身
C. 新日期类都是不可变对象、线程安全
D. Instant 可以精确到纳秒，推荐代替 Date

**【答案】** B

**【解析】** 新日期类不可变：plus/with/minus 都返回新对象，原对象不变（必须用变量接收返回值）。这与 String 的不可变性是同一种设计。
▶ 关联：可变 vs 不可变对比 Calendar（可变）与 String（不可变）。

**6.** 已知 `String s = "12";`，下列输出结果正确的是（　）

```java
System.out.println(s + 1);
System.out.println(Integer.parseInt(s) + 1);
```

A. 121 和 13
B. 13 和 13
C. 121 和 121
D. 编译报错

**【答案】** A

**【解析】** `s + 1` 中 s 是字符串，+ 做字符串拼接得 "121"；parseInt 把 "12" 转成整数 12，再加 1 得 13。
▶ 关联：字符串拼接规则（+ 遇到字符串变拼接）见第3章运算符。

**7.** 要把字符串 `"2026年09月05日"` 解析成日期，SimpleDateFormat 的模式应写为（　）

A. `yyyy-MM-dd`
B. `yyyy年MM月dd日`
C. `yyyy/MM/dd`
D. 任意模式都能自动识别

**【答案】** B

**【解析】** parse 要求模式与字符串逐字符对应（连汉字、分隔符都要一致），否则抛 ParseException。
▶ 关联：JDK8 中对应的 DateTimeFormatter 同样要求模式一致，见本章第十节。

---

### 三、判断题

**1.** 重写 equals 方法时，通常也应该重写 hashCode 方法。（　）

**【答案】** 正确。

**【解析】** 重写 equals 让两个对象逻辑上相等；重写 hashCode 让它们在哈希容器（HashMap、HashSet）中落在同一个位置。只重写 equals 不重写 hashCode，两个"相等"对象可能被集合当成两个元素。
▶ 关联：hashCode 在哈希表中的作用见第17章《Set与Map集合》。

**2.** `new BigDecimal(0.1)` 可以精确表示 0.1。（　）

**【答案】** 错误。

**【解析】** double 字面量 0.1 本身已经是失真的近似值，new BigDecimal(double) 会原样接收这一长串近似小数；要用 `BigDecimal.valueOf(0.1)` 或 `new BigDecimal("0.1")`。

**3.** SimpleDateFormat 是线程安全的，可以定义为 static 成员在多线程中共享。（　）

**【答案】** 错误。

**【解析】** 传统日期类（Date、Calendar、SimpleDateFormat）都是线程不安全的；多线程环境应用 JDK8 的 DateTimeFormatter（线程安全）。
▶ 关联：线程安全问题与 synchronized 见第21章。

**4.** Calendar 是不可变对象，调用 add 方法后原日历对象保持不变。（　）

**【答案】** 错误。

**【解析】** Calendar 是**可变**对象：`now.add(Calendar.DAY_OF_YEAR, 100)` 直接修改 now 本身；JDK8 的 LocalDate 等才是不可变对象（修改返回新对象）。

**5.** `Objects.equals(s1, s2)` 中即使 s1 为 null 也不会抛空指针异常。（　）

**【答案】** 正确。

**【解析】** 源码是 `(a == b) || (a != null && a.equals(b))`，a 为 null 时短路返回 false，安全。直接写 `s1.equals(s2)` 且 s1 为 null 时会抛 NullPointerException。
▶ 关联：逻辑运算符短路特性见第3章；空指针异常见第7/16章。

---

### 四、简答题

**1.** 简述 `==` 和 `equals()` 的区别；为什么重写 equals 时通常要一起重写 hashCode？

**【答案】**
- `==`：基本类型比值，引用类型比地址；
- equals：Object 中默认就是 `==`（比地址），但可以被子类重写为比较内容（String、包装类已重写）；
- 重写 equals 后两个对象逻辑相等，但哈希容器（HashSet/HashMap）先按 hashCode 分桶，若 hashCode 不同会被存到不同位置，导致"相等对象"被当成两个。所以约定：equals 相等的对象，hashCode 必须相等，两者要一起重写（IDE 可自动生成）。

**【解析】** 记忆：equals 管"逻辑相等"，hashCode 管"哈希位置"，逻辑相等的对象必须在同一位置。
▶ 关联：哈希表去重原理（先看 hashCode 再看 equals）见第17章。

**2.** 浅克隆和深克隆有什么区别？如何在代码中实现深克隆？

**【答案】**
- 浅克隆：基本类型属性复制值，引用类型属性复制地址——克隆对象与源对象的引用属性指向同一个对象，改一个另一个跟着变；
- 深克隆：引用类型属性指向的对象也复制一份，两者互不影响；
- 实现：类实现 Cloneable、重写 clone，先 `super.clone()` 完成浅克隆，再对引用类型字段单独克隆：
```java
@Override
protected Object clone() throws CloneNotSupportedException {
    Goods g = (Goods) super.clone();
    g.tags = tags.clone();   // 引用字段再克隆一次
    return g;
}
```

**【解析】** String 属性虽然也是引用类型，但它不可变，无需深克隆；需要深克隆的是数组、集合、可变对象。
▶ 关联：数组复制 `arr.clone()` 与第6章数组反转中的新数组法思想一致。

**3.** 传统日期类有哪些缺点？JDK8 新日期 API 主要有哪些类，各自负责什么？

**【答案】**
- 传统类缺点：设计不合理（Date 月份从 0 开始等）、很多方法已淘汰；Date/Calendar 是可变对象；SimpleDateFormat 线程不安全；只能精确到毫秒。
- JDK8 新 API：
  - `LocalDate`：年月日、星期；
  - `LocalTime`：时分秒纳秒；
  - `LocalDateTime`：年月日时分秒（可与前两者互转）；
  - `Instant`：时间戳（秒 + 纳秒），推荐代替 Date；
  - `DateTimeFormatter`：线程安全的格式化器，代替 SimpleDateFormat；
  - `Period`：两个 LocalDate 的间隔（年月日）；`Duration`：两个时间的间隔（时分秒纳秒）；
  - `ZoneId/ZonedDateTime`：时区。
- 共性：不可变、线程安全、精确到纳秒；get 取信息、with 改、plus 加、minus 减、of 指定、isBefore/isAfter 比较。

**【解析】** 开发中新代码优先用 JDK8 新 API；老项目维护中仍会见到 Date/SimpleDateFormat，所以两套都要会。
▶ 关联：线程安全概念见第21章；时间毫秒值 currentTimeMillis 见本章 System 一节。

---

### 五、代码阅读题

**1.** 写出运行结果。

```java
public class WrapperTest {
    public static void main(String[] args) {
        String p1 = "19";
        String p2 = "2.5";
        System.out.println(p1 + 1);
        System.out.println(Integer.parseInt(p1) + 1);
        System.out.println(Double.parseDouble(p2) + 0.5);
        Integer boxed = Integer.valueOf("8");
        int unboxed = boxed + 2;
        System.out.println(unboxed);
    }
}
```

**【答案】**
```
191
20
3.0
10
```

**【解析】**
- `p1 + 1`：字符串拼接 → "191"；
- `parseInt("19") + 1`：整数 19 + 1 = 20；
- `parseDouble("2.5") + 0.5`：2.5 + 0.5 = 3.0（double 运算结果带小数）；
- `Integer.valueOf("8")` 装箱为 Integer，`+ 2` 时自动拆箱为 int 8，8 + 2 = 10。
▶ 关联：+ 拼接规则见第3章；自动装箱/拆箱见本章第四节。

**2.** 写出运行结果。

```java
System.out.println(Math.ceil(4.0001));
System.out.println(Math.floor(4.999));
System.out.println(Math.round(3.5));
System.out.println(Math.round(2.4));
System.out.println(Math.max('a', 'b'));
System.out.println(Math.pow(2, 5));
```

**【答案】**
```
5.0
4.0
4
2
98
32.0
```

**【解析】**
- ceil 向上取整：4.0001 → 5.0（ceil(4.0) 才是 4.0）；
- floor 向下取整：4.999 → 4.0；
- round 四舍五入：3.5 → 4，2.4 → 2；
- `Math.max('a','b')`：char 参与运算取编码值（'a'=97，'b'=98），max(int,int) 返回 98；
- pow(2,5)：2 的 5 次方 = 32.0（返回 double）。
▶ 关联：char 取编码值参与运算见第2/3章；向上取整思想在第5章循环练习中也常用到。

**3.** 写出运行结果。

```java
BigDecimal a = BigDecimal.valueOf(0.1);
BigDecimal b = BigDecimal.valueOf(0.2);
System.out.println(a.add(b));
System.out.println(BigDecimal.valueOf(100).divide(
        BigDecimal.valueOf(3), 2, RoundingMode.HALF_UP));
System.out.println(a.multiply(b));
System.out.println(a.add(b).doubleValue());
```

**【答案】**
```
0.3
33.33
0.02
0.3
```

**【解析】**
- valueOf 创建的 BigDecimal 精确，0.1 + 0.2 = 0.3；
- 100 / 3 除不尽，保留 2 位四舍五入 → 33.33（不指定精度会抛 ArithmeticException）；
- 0.1 × 0.2 = 0.02 精确；
- doubleValue() 转回基本类型 double 输出 0.3。
▶ 关联：舍入与精确计算是金融/计费类业务的基本功，可结合第21章日志打印计费结果。

**4.** 写出运行结果，注意不可变性。

```java
LocalDate today = LocalDate.of(2026, 9, 5);
LocalDate later = today.plusDays(10);
System.out.println(today);
System.out.println(later);
LocalDate changed = today.withYear(2099);
System.out.println(today.getYear());
System.out.println(changed.getYear());
```

**【答案】**
```
2026-09-05
2026-09-15
2026
2099
```

**【解析】** plusDays/withYear 都返回新对象，today 本身始终是 2026-09-05——这与 String 拼接后原字符串不变完全一致。若写成 `today.plusDays(10);` 不接收返回值，则看不到任何变化。
▶ 关联：String 不可变性见第10章。

**5.** 写出运行结果。

```java
class Order implements Cloneable {
    String name;
    double[] prices;

    Order(String name, double[] prices) {
        this.name = name;
        this.prices = prices;
    }

    @Override
    protected Object clone() throws CloneNotSupportedException {
        return super.clone();   // 浅克隆
    }
}

Order o1 = new Order("午餐", new double[]{20.0, 30.0});
Order o2 = (Order) o1.clone();
o2.prices[0] = 99.0;
System.out.println(o1.prices[0]);
System.out.println(o1 == o2);
```

**【答案】**
```
99.0
false
```

**【解析】** super.clone() 是浅克隆：o2 的 prices 数组与 o1 指向同一个数组，改 o2.prices[0] 后 o1 也变成 99.0（浅克隆的典型坑）；但两个对象地址不同，`==` 为 false。改成深克隆只需在 clone 中加一行 `o2.prices = o2.prices.clone();`。
▶ 关联：数组地址共享见第6章；深克隆写法见本章编程题 6。

---

### 六、编程题（共 6 题，由易到难）

#### 编程题 1（基础）：运单费用文本解析

**需求：** 系统从运单文本中读到三个费用字符串 `"12.5"`、`"8.0"`、`"6.5"`，请用包装类方法把它们转成数值并求合计；再把流水号字符串 `"1024"` 转成整数并算出下一单流水号；最后把流水号转成字符串拼接出运单号 `"SF1024"`。

**参考代码：**

```java
public class FeeParser {
    public static void main(String[] args) {
        String[] feeTexts = {"12.5", "8.0", "6.5"};
        double total = 0;
        for (String text : feeTexts) {
            total += Double.parseDouble(text);   // 字符串 → double
        }
        System.out.println("三单运费合计：" + total + " 元");

        String numText = "1024";
        int num = Integer.parseInt(numText);     // 字符串 → int
        System.out.println("下一单流水号：" + (num + 1));

        String numStr = Integer.toString(num);   // int → 字符串
        System.out.println("运单号：SF" + numStr);
    }
}
```

**运行结果：**
```
三单运费合计：27.0 元
下一单流水号：1025
运单号：SF1024
```

**【解析】** 控制台、文件、网络读到的数据最初都是字符串，`parseXxx` 是把文本变数值的入口；数值变文本用 `toString`/`String.valueOf` 或直接和字符串拼接。
▶ 关联：Scanner 录入字符串与数值见第3/4章；文件中读取文本见第19/20章 IO 流。

#### 编程题 2（基础）：聚餐 AA 账单（BigDecimal）

**需求：** 聚餐消费 200 元，会员享 88 折。请用 BigDecimal 精确计算：折后总价；3 人 AA 每人应付多少（除不尽保留 2 位小数，四舍五入）。

**参考代码：**

```java
import java.math.BigDecimal;
import java.math.RoundingMode;

public class BillSplit {
    public static void main(String[] args) {
        BigDecimal total = BigDecimal.valueOf(200);        // 消费总额
        BigDecimal discount = new BigDecimal("0.88");      // 88 折（字符串构造精确）

        BigDecimal memberPrice = total.multiply(discount); // 乘法
        System.out.println("会员折后总价：" + memberPrice + " 元");

        // 除法：除不尽必须指定保留位数和舍入模式
        BigDecimal each = memberPrice.divide(BigDecimal.valueOf(3), 2, RoundingMode.HALF_UP);
        System.out.println("每人应付：" + each + " 元");

        System.out.println("（约 " + each.doubleValue() + " 元/人）");
    }
}
```

**运行结果：**
```
会员折后总价：176.00 元
每人应付：58.67 元
（约 58.67 元/人）
```

**【解析】** 200 × 0.88 = 176.00；176 ÷ 3 = 58.666…，HALF_UP 四舍五入保留两位为 58.67。金额计算严禁用 double 直接做除法/乘法。
▶ 关联：浮点失真原理见第2/3章；异常 ArithmeticException 与第16章异常体系呼应。

#### 编程题 3（基础）：购物小票拼接（StringBuilder + StringJoiner）

**需求：** 顾客点了三个菜（农家小炒肉 28、番茄蛋汤 12、米饭 2）。用 StringJoiner 拼出商品清单（顿号分隔），用 StringBuilder 拼出整张小票（含逐行菜品和合计）。

**参考代码：**

```java
import java.util.StringJoiner;

public class Receipt {
    public static void main(String[] args) {
        String[] items = {"农家小炒肉", "番茄蛋汤", "米饭"};
        double[] prices = {28.0, 12.0, 2.0};

        // StringJoiner：自动加分隔符和前后缀
        StringJoiner joiner = new StringJoiner("、", "本次购买商品：", "。");
        for (String item : items) {
            joiner.add(item);
        }
        System.out.println(joiner);

        // StringBuilder：频繁追加用可变容器，支持链式调用
        StringBuilder sb = new StringBuilder();
        sb.append("====== 用餐小票 ======\n");
        double total = 0;
        for (int i = 0; i < items.length; i++) {
            sb.append(i + 1).append(". ")
              .append(items[i]).append("：")
              .append(prices[i]).append(" 元\n");
            total += prices[i];
        }
        sb.append("----------------------\n");
        sb.append("合计：").append(total).append(" 元\n");
        sb.append("======================");
        System.out.println(sb);
    }
}
```

**运行结果：**
```
本次购买商品：农家小炒肉、番茄蛋汤、米饭。
====== 用餐小票 ======
1. 农家小炒肉：28.0 元
2. 番茄蛋汤：12.0 元
3. 米饭：2.0 元
----------------------
合计：42.0 元
======================
```

**【解析】** 有固定分隔符/前后缀的拼接用 StringJoiner 最简洁；自由格式的逐行拼接用 StringBuilder 链式 append。二者都是可变容器，避免 String 用 + 反复产生临时对象。
▶ 关联：StringBuilder 扩容与 + 拼接底层原理见第10章；数组遍历见第6章。

#### 编程题 4（中等）：会员生日提醒（JDK8 新日期）

**需求：** 给定今天日期和会员的生日（月、日），计算会员今年生日日期；若今年生日已过（含今天正好生日的特殊情况单独提示），则算明年的生日；输出距离生日还有几个月零几天。

**参考代码：**

```java
import java.time.LocalDate;
import java.time.Period;

public class BirthdayReminder {
    public static void daysUntilBirthday(LocalDate today, int month, int day) {
        LocalDate thisYear = today.withMonth(month).withDayOfMonth(day);
        if (thisYear.equals(today)) {
            System.out.println("今天就是会员生日，记得送祝福！");
            return;
        }
        // 今年生日已过 → 顺延到明年
        LocalDate birthday = thisYear.isBefore(today) ? thisYear.plusYears(1) : thisYear;
        Period p = Period.between(today, birthday);
        System.out.println("距离生日还有 " + p.getMonths() + " 个月零 "
                + p.getDays() + " 天（" + birthday + "）");
    }

    public static void main(String[] args) {
        LocalDate today = LocalDate.of(2026, 9, 5);
        daysUntilBirthday(today, 12, 20);  // 12月20日
        daysUntilBirthday(today, 7, 1);    // 7月1日（今年已过）
        daysUntilBirthday(today, 9, 5);    // 今天
    }
}
```

**运行结果：**
```
距离生日还有 3 个月零 15 天（2026-12-20）
距离生日还有 9 个月零 26 天（2027-07-01）
今天就是会员生日，记得送祝福！
```

**【解析】** withMonth/withDayOfMonth 基于今天替换月日得到今年生日（不可变，返回新对象）；Period.between 把间隔分解为"几个月零几天"。
▶ 关联：分支判断见第5章；不可变对象特性同 String（第10章）。

#### 编程题 5（中等）：优惠券有效期校验（SimpleDateFormat）

**需求：** 优惠券有效期为 `2026-09-01 00:00:00` 到 `2026-09-10 23:59:59`，用户在 `2026-09-05 12:30:00` 下单。用 SimpleDateFormat 解析时间后统一转毫秒值判断是否可用，并格式化当前时间输出核销记录。

**参考代码：**

```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class CouponValidity {
    public static void main(String[] args) throws ParseException {
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");

        Date start = sdf.parse("2026-09-01 00:00:00");
        Date end = sdf.parse("2026-09-10 23:59:59");
        Date useTime = sdf.parse("2026-09-05 12:30:00");

        // 日期比较统一转毫秒值
        long t = useTime.getTime();
        if (t >= start.getTime() && t <= end.getTime()) {
            System.out.println("优惠券在有效期内，核销成功");
        } else {
            System.out.println("优惠券已过期或未生效，核销失败");
        }

        System.out.println("核销时间：" + sdf.format(new Date()));
    }
}
```

**运行结果（前两行固定，最后一行为运行时当前时间）：**
```
优惠券在有效期内，核销成功
核销时间：2026-09-05 20:xx:xx
```

**【解析】** 日期比较的通用套路：format/parse 负责字符串与日期互转，比较大小一律转 getTime() 毫秒值（数值比较最简单可靠）。parse 要抛出/处理 ParseException。
▶ 关联：if 判断见第5章；异常处理见第16章；毫秒值起点（1970-01-01）与 System.currentTimeMillis 同源。

#### 编程题 6（进阶）：商品类综合（equals/hashCode/深克隆/toString）

**需求：** 设计商品类 Goods（名称 name、价格 price、标签数组 tags），要求：
1. 重写 toString 返回商品完整信息；
2. 重写 equals/hashCode：两个商品名称、价格、标签内容都相同即视为同一商品（数组内容比较用 Arrays.equals）；
3. 实现深克隆：克隆后修改新商品的标签，原商品不受影响；
4. 测试：两个内容相同的商品 `==` 为 false、equals 为 true、hashCode 相等；深克隆后改标签互不影响。

**参考代码：**

```java
import java.util.Arrays;
import java.util.Objects;

public class Goods implements Cloneable {
    private String name;
    private double price;
    private String[] tags;

    public Goods(String name, double price, String[] tags) {
        this.name = name;
        this.price = price;
        this.tags = tags;
    }

    @Override
    public String toString() {
        return "Goods{name='" + name + "', price=" + price
                + ", tags=" + Arrays.toString(tags) + "}";
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Goods goods = (Goods) o;
        return Double.compare(goods.price, price) == 0
                && Objects.equals(name, goods.name)
                && Arrays.equals(tags, goods.tags);   // 数组比内容
    }

    @Override
    public int hashCode() {
        int result = Objects.hashCode(name);
        result = 31 * result + Double.hashCode(price);
        result = 31 * result + Arrays.hashCode(tags);
        return result;
    }

    @Override
    protected Object clone() throws CloneNotSupportedException {
        Goods g = (Goods) super.clone();   // 浅克隆
        g.tags = tags.clone();            // 引用字段（数组）单独再克隆 → 深克隆
        return g;
    }

    public static void main(String[] args) throws CloneNotSupportedException {
        Goods g1 = new Goods("机械键盘", 299.0, new String[]{"办公", "外设"});
        Goods g2 = new Goods("机械键盘", 299.0, new String[]{"办公", "外设"});

        System.out.println(g1 == g2);            // false：地址不同
        System.out.println(g1.equals(g2));       // true：内容相同
        System.out.println(g1.hashCode() == g2.hashCode()); // true

        Goods g3 = (Goods) g1.clone();
        g3.tags[0] = "游戏";   // 修改克隆对象的标签
        System.out.println(g1); // 原对象标签不变（深克隆）
        System.out.println(g3);
    }
}
```

**运行结果：**
```
false
true
true
Goods{name='机械键盘', price=299.0, tags=[办公, 外设]}
Goods{name='机械键盘', price=299.0, tags=[游戏, 外设]}
```

**【解析】** 本题串联本章三大考点：
- toString 重写让打印对象看到内容而非地址（默认 `类名@哈希值`）；
- equals + hashCode 成对重写，数组用 Arrays.equals/Arrays.hashCode 比较内容；
- 深克隆 = super.clone() 后对引用字段 tags 再 clone 一次。
▶ 关联：toString/equals 重写动机见第8章 Object 入门；hashCode 的用途见第17章哈希表；Cloneable 是标记接口，与第23章注解/接口知识呼应。

---

### 本章自测清单

- [ ] 能说出 toString/equals/hashCode/clone 各自的作用和重写场景
- [ ] 能解释 `==` 与 equals 的区别、equals 与 hashCode 的配对约定
- [ ] 能动手实现深克隆（引用字段再克隆）
- [ ] 能写出 8 种基本类型与包装类的对应关系，熟练用 parseInt/valueOf/toString
- [ ] 能说出 StringBuilder 与 StringBuffer 的区别，会用 StringJoiner
- [ ] 能用 BigDecimal.valueOf 创建对象、用带舍入模式的 divide 做除法
- [ ] 能用 SimpleDateFormat 完成 format/parse，并统一转毫秒值比较时间
- [ ] 能说出传统日期类的缺点，会用 LocalDate/LocalDateTime 的 get/with/plus/minus/of/isBefore
- [ ] 会用 Period/Duration 计算时间间隔，知道 Instant/DateTimeFormatter 的优势

---

<div style="page-break-after: always;"></div>

## 第十五章 Lambda、算法与正则表达式 · 习题精讲

> 习题覆盖全章：Arrays 工具类与对象排序、Lambda 表达式、四种方法引用、冒泡/选择/二分查找、正则表达式校验/提取/替换/分割。
> 所有题目场景均为原创（歌单排序、快递单号、工单提取、气温排序、图书查找），未使用笔记中的学生排序、手机号邮箱校验等原案例。

---

### 一、填空题

**1.** Lambda 表达式是 JDK ______ 开始新增的语法形式，它的作用是简化 ______ 的代码写法。

**【答案】** 8；函数式接口的匿名内部类

**【解析】** Lambda 是 JDK 8 随 Stream、函数式接口一起引入的语法糖。它不能简化所有匿名内部类，只能简化"函数式接口"（接口中只有一个抽象方法）的匿名内部类。
▶ 关联：第9章《面向对象高级（下）》首次接触 Lambda 入门，本章系统学习其规则；第18章《Stream 与 File》的 Stream 流大量使用 Lambda。

**2.** 函数式接口的定义是：必须是一个 ______，且接口中只有 ______ 个抽象方法。

**【答案】** 接口；一

**【解析】** 两个条件缺一不可：抽象类不能用 Lambda；接口里有两个及以上抽象方法时，编译器无法判断 Lambda 实现的是哪个方法，也不能用。接口中可以有 default、static 方法，不影响它是函数式接口。
▶ 关联：第9章接口的 default/static 方法为函数式接口演进提供了基础。

**3.** 对象数组排序有两种方案：让元素类实现 ______ 接口并重写 ______ 方法（规则写死在类上）；或者调用 `Arrays.sort(arr, 排序器)` 传入 ______ 接口的实现对象（规则灵活，推荐）。

**【答案】** `Comparable<T>`；`compareTo`；`Comparator<T>`

**【解析】** 直接对对象数组调用 `Arrays.sort(arr)` 会报 `ClassCastException: Xxx cannot be cast to Comparable`，因为 sort 不知道对象"谁大谁小"。Comparable 方案把规则写在类里，一个类只能有一种默认规则；Comparator 方案在调用时临时给规则，想用什么规则就传什么排序器，实体类不用实现任何接口，更灵活。
▶ 关联：第9章多态——`Comparator` 接口接收其匿名实现/Lambda 就是多态的应用；第13章泛型——`Comparable<Student>` 中的泛型避免强转。

**4.** 二分查找（折半查找）的前提条件是数组必须 ______；查找失败（目标不存在）时返回 ______。

**【答案】** 有序（元素按升序/降序排列）；-1

**【解析】** 二分查找每一步用中间元素和目标比较，从而排除一半数据，这依赖"有序"才能判断目标在左半还是右半。无序数组只能用基本查找（从头到尾）。找不到目标时约定返回 -1（索引不可能为 -1）。
▶ 关联：第6章《数组》的遍历是基本查找；第17章 TreeSet/TreeMap 底层红黑树也是"有序"思想的延伸。

**5.** 正则表达式中 `\d` 表示 ______，等价于字符类 ______；但在 Java 字符串里反斜杠是转义字符，所以要写成 ______。

**【答案】** 数字字符（0-9）；`[0-9]`；`"\\d"`

**【解析】** 正则本身写 `\d`，但 Java 字符串中 `\` 用来转义（如 `\n`），一个 `\` 无法表示正则的反斜杠，必须双写 `\\`。同理 `\w`（单词字符）写 `"\\w"`、`\s`（空白字符）写 `"\\s"`。
▶ 关联：第2章《Java 基础语法》的字符与转义；第19章《字符集与字节流》中字符编码的思想与 `\w` 只认 ASCII 单词字符（不含中文）相呼应。

**6.** 方法引用的标志性符号是 ______；静态方法引用的格式是 ______，实例方法引用的格式是 ______。

**【答案】** `::`；`类名::静态方法名`；`对象名::实例方法名`

**【解析】** 方法引用是对 Lambda 的进一步简化：当 Lambda 体里只是调用一个已有方法、且前后参数形式一致时，可以直接"引用"这个方法。另有特定类型方法引用 `类型::实例方法`（第一个参数是调用者）和构造器引用 `类名::new`。
▶ 关联：第18章 Stream 终结方法中 `System.out::println`、`Student::new` 等方法引用随处可见。

---

### 二、选择题

**1.** 下列接口中，可以使用 Lambda 表达式创建其匿名内部类对象的是（　）。

A. 接口中有两个抽象方法
B. 接口中没有抽象方法，只有 default 方法
C. 接口中只有一个抽象方法，另有两个 default 方法
D. 抽象类，类中只有一个抽象方法

**【答案】** C

**【解析】** Lambda 的两个硬条件：必须是接口；有且仅有一个抽象方法。A 有两个抽象方法不行；B 没有抽象方法，Lambda 不知道实现什么；D 是抽象类不是接口，不行。default 方法有方法体、不算抽象方法，所以 C 中"一个抽象方法 + 两个 default"仍是函数式接口。
▶ 关联：第9章 JDK8 接口 default 方法——default 不破坏函数式接口特性。

**2.** 关于 Lambda 的省略规则，下列说法**错误**的是（　）。

A. 参数类型可以省略
B. 只有一个参数时，省略类型后小括号 `()` 也可以省略
C. 方法体只有一行代码时，可以省略大括号 `{}` 和分号
D. 方法体只有一行 `return` 语句时，可以省略大括号但必须保留 `return` 关键字

**【答案】** D

**【解析】** 三条省略规则：参数类型可省；仅一个参数时 `()` 可省；方法体只有一行时 `{}` 和分号可省，**如果这行是 return 语句，return 也必须一起去掉**。例如 `(a,b) -> { return a - b; }` 省略后是 `(a, b) -> a - b`，保留 return 反而编译报错。
▶ 关联：第15章方法引用是在 Lambda 省略形式基础上的进一步简化。

**3.** 对学生身高（double 类型）做升序排序，Comparator 中正确的比较写法是（　）。

A. `return (int)(o1.getHeight() - o2.getHeight());`
B. `return Double.compare(o1.getHeight(), o2.getHeight());`
C. `return o1.getHeight() - o2.getHeight();`
D. `return o1.getHeight() > o2.getHeight();`

**【答案】** B

**【解析】** double 相减结果是小数，强转 int 会丢失精度（如 1.75 - 1.70 = 0.05，强转成 0，误判为相等），C 编译都通不过（double 不能作 int 返回），D 返回类型错误。包装类提供静态 `compare` 方法专门解决此问题：`Double.compare(a, b)` 返回负/0/正，无精度损失。int 比较推荐 `Integer.compare` 还能防相减溢出。
▶ 关联：第14章《常用 API》包装类；第3章《运算符》隐式转换与精度损失。

**4.** 下列 `matches` 判断的结果，正确的一组是（　）。

```java
"a3c".matches("\\w{3}")      // ①
"abc".matches("\\w?")        // ②
"".matches("\\w*")           // ③
"徐".matches("\\w")          // ④
```

A. ①true ②true ③true ④true
B. ①true ②false ③true ④false
C. ①true ②false ③false ④true
D. ①false ②false ③true ④false

**【答案】** B

**【解析】** ① `\w{3}` 正好 3 个单词字符，a3c 是 3 个 → true；② `\w?` 表示 0 或 1 个，abc 是 3 个 → false；③ `\w*` 表示 0 个或多个，空串是 0 个 → true；④ `\w` 等价 `[a-zA-Z_0-9]`，**不包含中文**，"徐" → false。注意 `? * +` 三个量词的区别：? 是 0~1 次，* 是 0~多次，+ 是 1~多次。
▶ 关联：本章正则字符类表；第19章字符集——中文不在 ASCII 单词字符范围内。

**5.** 二分查找中，计算中间索引能防止整数溢出的写法是（　）。

A. `int mid = (left + right) / 2;`
B. `int mid = left + (right - left) / 2;`
C. `int mid = right - left / 2;`
D. `int mid = left / 2 + right;`

**【答案】** B

**【解析】** 当 left 和 right 都接近 int 最大值（约 21 亿）时，`left + right` 可能超过 int 范围溢出成负数。`left + (right - left) / 2` 数学上等价但不会溢出，是工业界标准写法。C、D 算出来的不是中点。
▶ 关联：第2章基本类型 int 的取值范围；第3章运算符优先级（先除后加）。

**6.** 关于选择排序的"优化写法"（记录最小值索引），下列说法正确的是（　）。

A. 每轮比较次数比冒泡排序少一半
B. 一轮内无论发现多少次更小值，只记录索引，**一轮结束最多交换一次**
C. 优化后时间复杂度从 O(n²) 变为 O(n)
D. 优化后不再需要内层循环

**【答案】** B

**【解析】** 基础选择排序每发现更小值就交换一次，一轮可能交换多次；优化写法用 `minIndex` 记住当前最小值位置，内层循环只比较不交换，一轮走完后最多交换一次，减少了交换次数。比较次数没变（仍是 O(n²)），内层循环依然存在。
▶ 关联：第5章《流程控制语句》嵌套循环；第6章数组 temp 交换变量是排序的基础动作。

---

### 三、判断题

**1.** 只要是匿名内部类，都可以改写为 Lambda 表达式。（　）

**【答案】** ✗ 错误

**【解析】** 只有函数式接口（接口 + 唯一抽象方法）的匿名内部类才能用 Lambda。抽象类的匿名内部类（如 `new Animal(){...}`）、有多个抽象方法的接口都不能简化。
▶ 关联：第9章匿名内部类；本章 2.2 节使用条件。

**2.** 使用 `Comparator` 排序器方案时，被排序的实体类必须实现 `Comparable` 接口，否则编译报错。（　）

**【答案】** ✗ 错误

**【解析】** 这正是 Comparator 方案的优点：排序规则由外部排序器提供，实体类不需要实现任何接口、不需要任何改动。需要实现 Comparable 的是"单参数 `Arrays.sort(arr)`"那种方案。
▶ 关联：第13章泛型——`Comparator<Song>` 泛型指定比较的元素类型。

**3.** 二分查找在无序数组上也能正确工作，只是速度慢一些。（　）

**【答案】** ✗ 错误

**【解析】** 二分查找依赖"中间元素比目标小→目标在右半"这样的推断，无序时这个推断不成立，查找结果不可靠（可能漏掉真实存在的目标）。无序数组只能从头到尾基本查找。
▶ 关联：第6章数组遍历；第17章 TreeSet 有序集合。

**4.** Java 字符串中写正则 `\d` 时必须写成 `"\\d"`，因为反斜杠在字符串中是转义字符。（　）

**【答案】** ✓ 正确

**【解析】** Java 字符串语法里 `\` 用于转义（`\n`、`\t`），要表示一个字面反斜杠得写 `\\`，所以正则规则 `\d{3}` 在 Java 代码里是 `"\\d{3}"`。
▶ 关联：第2章字符与字符串字面量；本章 5.3 节预定义字符。

---

### 四、简答题

**1.** 对比说明 `Comparable` 与 `Comparator` 两种对象排序方案的区别和选择。

**【答案】**

| 对比项 | Comparable | Comparator |
| --- | --- | --- |
| 位置 | 规则写在实体类上（`implements Comparable<T>`） | 规则写在调用处的排序器对象中 |
| 方法 | 重写 `compareTo(T o)` | 重写 `compare(T o1, T o2)` |
| 规则数量 | 一个类只有一种默认排序规则 | 想按什么排序就传什么排序器，可随时切换 |
| 实体类改动 | 需要修改实体类源码 | 实体类不用实现任何接口 |
| 适用 | 排序规则单一、固定 | 多种排序需求（推荐） |

返回值约定相同：负数表示前者小（排前面）、0 表示相等、正数表示前者大（排后面）；升序 `Integer.compare(o1, o2)`，降序交换参数位置。小数比较用 `Double.compare`/`Integer.compare`，不要直接相减。

**【解析】** 记忆口诀：Comparable 是"我自己会比较"（类自带能力），Comparator 是"请个裁判来比较"（外部工具）。实际开发中实体类往往来自第三方 jar 不能改源码，Comparator 更实用；配合 Lambda 后代码极简：`Arrays.sort(songs, (a,b) -> Integer.compare(b.plays, a.plays))`。
▶ 关联：第9章多态与接口；第13章泛型；第15章 Lambda 省略写法。

**2.** 简述冒泡排序的思想，并说明 n 个元素需要比较几轮、每轮比较多少次。

**【答案】**
- 思想：每一轮从头到尾相邻两个元素比较，顺序不对就交换，每轮结束把当前最大值"冒泡"到本轮末尾；
- 轮数：n 个元素比较 **n-1 轮**（最后一轮只剩一个元素，无需再比）；
- 第 i 轮（i 从 0 开始）比较 **n-1-i 次**（末尾 i 个元素已经排好，不用再比）；
- 内层判断条件 `arr[j] > arr[j+1]` 为升序，改成 `<` 为降序；
- 时间复杂度 O(n²)，适合小数据量、锻炼编程思维。

**【解析】** 冒泡排序外层控制轮数 `i < arr.length - 1`，内层 `j < arr.length - 1 - i`，这两个边界是考试和面试高频考点。选择排序与其结构相似但"每轮选最小的放到前面"。
▶ 关联：第5章嵌套循环；第6章数组；本章选择排序、二分查找都是算法思维训练。

**3.** 列出方法引用的四种形式及各自使用场景。

**【答案】**

| 形式 | 语法 | 使用场景 |
| --- | --- | --- |
| 静态方法引用 | `类名::静态方法` | Lambda 体只是调用一个静态方法，参数形式一致 |
| 实例方法引用 | `对象名::实例方法` | Lambda 体只是调用某个对象的实例方法（先 new 对象） |
| 特定类型方法引用 | `类型::实例方法` | Lambda 第一个参数是方法调用者，其余参数是入参，如 `String::compareToIgnoreCase` |
| 构造器引用 | `类名::new` | Lambda 体只是在 new 对象，参数形式一致 |

**【解析】** 方法引用不是必须掌握的"新能力"，它只是让符合条件的 Lambda 更短。判断能否引用的关键：Lambda 体里是否"只调用一个已有方法"且"参数正好对得上"。不符合条件时老老实实写 Lambda。
▶ 关联：第18章 Stream 中 `list.forEach(System.out::println)`、`map(Student::getName)` 大量使用；第9章 Lambda 基础。

---

### 五、代码阅读题

**1.** 阅读歌单排序代码，写出输出结果。

```java
class Song {
    private String name;
    private int plays;          // 播放量（万次）
    public Song(String name, int plays) { this.name = name; this.plays = plays; }
    public int getPlays() { return plays; }
    public String toString() { return name + "(" + plays + "万)"; }
}

public class SongRank {
    public static void main(String[] args) {
        Song[] songs = {
            new Song("晴天", 900),
            new Song("稻香", 1200),
            new Song("七里香", 600),
            new Song("夜曲", 1200)
        };
        Arrays.sort(songs, (a, b) -> Integer.compare(b.getPlays(), a.getPlays()));
        System.out.println(Arrays.toString(songs));
    }
}
```

**【答案】**
```
[稻香(1200万), 夜曲(1200万), 晴天(900万), 七里香(600万)]
```

**【解析】** `Integer.compare(b.plays, a.plays)` 参数顺序是 b 在前 a 在后，表示**降序**：播放量大的排前面。1200 的两首歌（稻香、夜曲）在前，排序算法（TimSort）是稳定的，播放量相同时保持它们在原数组中的相对顺序，所以稻香仍在夜曲前面；然后是晴天 900、七里香 600。
▶ 关联：本章 Comparator 返回值约定；第9章多态——sort 第二参数接收 Comparator 接口的 Lambda 实现。

**2.** 阅读快递单号校验代码，写出 5 个输出。

```java
// 规则：顺丰单号以 SF 开头，后面紧跟 12 位数字，总长 14 位
public static boolean checkExpressNo(String no) {
    return no != null && no.matches("SF\\d{12}");
}

System.out.println(checkExpressNo("SF123456789012"));   // ①
System.out.println(checkExpressNo("SF12345678901"));    // ②
System.out.println(checkExpressNo("sf123456789012"));   // ③
System.out.println(checkExpressNo("SF1234567890123"));  // ④
System.out.println(checkExpressNo("SF12345678901A"));   // ⑤
```

**【答案】** ① true　② false　③ false　④ false　⑤ false

**【解析】**
- ① `SF` + `123456789012`（12 位数字），完全匹配 → true；
- ② SF 后只有 11 位数字，不满足 `{12}` → false；
- ③ `sf` 小写，规则中 `SF` 区分大小写 → false（要忽略大小写可加 `(?i)`）；
- ④ SF 后 13 位数字，`{12}` 要求正好 12 位 → false；
- ⑤ 含字母 A，`\d` 只匹配数字 → false。

`matches` 要求**整个字符串**完全匹配规则，不是"包含"即可。
▶ 关联：本章字符类与数量词；`(?i)` 忽略大小写规则。

**3.** 阅读二分查找代码，推演在数组中查找 60 的完整过程并写出返回值。

```java
int[] arr = {10, 20, 30, 40, 50, 60, 70};

public static int binarySearch(int[] arr, int target) {
    int left = 0, right = arr.length - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (target < arr[mid])      right = mid - 1;
        else if (target > arr[mid]) left = mid + 1;
        else return mid;
    }
    return -1;
}
```

**【答案】** 返回 **5**。推演：

| 轮次 | left | right | mid | arr[mid] | 比较 | 动作 |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | 0 | 6 | 3 | 40 | 60 > 40 | left = 4 |
| 2 | 4 | 6 | 5 | 60 | 60 == 60 | 返回 5 |

若查找 25（不存在）：第1轮 mid=3(40)>25 → right=2；第2轮 mid=1(20)<25 → left=2；第3轮 mid=2(30)>25 → right=1；此时 left(2) > right(1)，循环结束返回 -1。

**【解析】** 循环条件必须是 `left <= right`：两指针重合时还剩最后一个元素没比较，`<` 会漏掉它。`mid` 防溢出写法见选择题第 5 题。
▶ 关联：第5章 while 循环；第6章数组索引。

**4.** 阅读特定类型方法引用代码，写出输出结果。

```java
String[] titles = {"java", "Spring", "hadoop", "Docker", "linux"};
Arrays.sort(titles, String::compareToIgnoreCase);
System.out.println(Arrays.toString(titles));
```

**【答案】**
```
[Docker, hadoop, java, linux, Spring]
```

**【解析】** `String::compareToIgnoreCase` 是特定类型的方法引用：Lambda 形式为 `(o1, o2) -> o1.compareToIgnoreCase(o2)`，第一个参数 o1 是方法调用者、o2 是入参，符合"类型::实例方法"的引用条件。忽略大小写后按字母表顺序：D(docker) < h(hadoop) < j(java) < l(linux) < S(spring)。若用默认 `Arrays.sort(titles)`，大写字母编码值小于小写，会排成 `[Docker, Spring, hadoop, java, linux]`（大写在前）。
▶ 关联：本章 3.3 节特定类型方法引用；第10章 String 的 `compareToIgnoreCase` 方法。

---

### 六、编程题（5 道，由易到难）

#### 编程题 1（基础）：歌单排序器

**需求：** 定义歌曲类 `Song`（歌名、播放量万次、时长秒），把 4 首歌存入数组，分别完成两种排序并输出：① 按播放量**降序**；② 按时长**升序**。要求使用 `Arrays.sort` + Lambda 形式的 Comparator，实体类不实现任何接口。

**【参考代码】**

```java
import java.util.Arrays;

class Song {
    private String name;
    private int plays;      // 播放量（万次）
    private int duration;   // 时长（秒）

    public Song(String name, int plays, int duration) {
        this.name = name;
        this.plays = plays;
        this.duration = duration;
    }
    public int getPlays() { return plays; }
    public int getDuration() { return duration; }
    public String toString() {
        return name + "(播放" + plays + "万," + duration + "秒)";
    }
}

public class SongRankDemo {
    public static void main(String[] args) {
        Song[] songs = {
            new Song("晴天", 900, 270),
            new Song("稻香", 1200, 223),
            new Song("七里香", 600, 299),
            new Song("夜曲", 1200, 231)
        };

        // ① 播放量降序：b 在前 a 在后
        Arrays.sort(songs, (a, b) -> Integer.compare(b.getPlays(), a.getPlays()));
        System.out.println("按播放量降序：");
        for (Song s : songs) System.out.println("  " + s);

        // ② 时长升序：a 在前 b 在后
        Arrays.sort(songs, (a, b) -> Integer.compare(a.getDuration(), b.getDuration()));
        System.out.println("按时长升序：");
        for (Song s : songs) System.out.println("  " + s);
    }
}
```

**【运行结果】**
```
按播放量降序：
  稻香(播放1200万,223秒)
  夜曲(播放1200万,231秒)
  晴天(播放900万,270秒)
  七里香(播放600万,299秒)
按时长升序：
  稻香(播放1200万,223秒)
  夜曲(播放1200万,231秒)
  晴天(播放900万,270秒)
  七里香(播放600万,299秒)
```

**【思路讲解】**
1. 实体类 Song 用 private 字段 + 构造器 + getter + toString，是标准 JavaBean（第7章规范）；
2. Comparator 的 Lambda `(a, b) -> 返回值`，compare 参数顺序决定升降序：`compare(a, b)` 升序、`compare(b, a)` 降序；
3. int 比较用 `Integer.compare` 防溢出；若比较身高/价格等 double 用 `Double.compare`。

▶ 关联：第7章 JavaBean 封装；第9章多态与接口；第13章泛型 `Comparator<Song>`。

---

#### 编程题 2（基础）：快递单号格式校验

**需求：** 快递柜录入快递单号，规则为：以大写 `SF` 开头，后面必须是 12 位数字（总长 14 位）。写校验方法，对一批单号输出是否合法。

**【参考代码】**

```java
public class ExpressNoChecker {
    public static void main(String[] args) {
        String[] nos = {
            "SF123456789012",   // 合法
            "SF12345678901",    // 数字只有11位
            "sf123456789012",   // 小写开头
            "SF1234567890123",  // 数字13位
            "YT888866665555",   // 不是SF开头
            "SF12345678901A"    // 含字母
        };
        for (String no : nos) {
            System.out.println(no + " -> " + (check(no) ? "合法" : "不合法"));
        }
    }

    // SF 开头 + 正好 12 位数字
    public static boolean check(String no) {
        return no != null && no.matches("SF\\d{12}");
    }
}
```

**【运行结果】**
```
SF123456789012 -> 合法
SF12345678901 -> 不合法
sf123456789012 -> 不合法
SF1234567890123 -> 不合法
YT888866665555 -> 不合法
SF12345678901A -> 不合法
```

**【思路讲解】**
1. `matches` 要求整串完全匹配：`SF` 是字面量前缀，`\\d{12}` 表示正好 12 个数字；
2. Java 字符串中 `\d` 必须双写成 `\\d`；
3. 加 `no != null` 防空指针；如果规则要放宽大小写，可改成 `(?i)sf\\d{12}`。

▶ 关联：本章正则字符类/数量词；第16章空指针异常防护。

---

#### 编程题 3（中等）：客服日志提取工单号

**需求：** 客服系统日志是一段文本，工单号规则为 `GD` 开头紧跟 8 位数字（如 GD20260901）。用 `Pattern` + `Matcher` 把日志中所有完整工单号提取出来输出；编号不完整的（如 GD2026）不能提取。

**【参考代码】**

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class OrderExtractor {
    public static void main(String[] args) {
        String log = "2026-09-05 客服小王处理工单 GD20260901，客户反馈快递延误；"
                   + "同日工单 GD20260902 已归档；备注 GD2026 编号不完整不计入；"
                   + "次日新增工单 GD20260903 待跟进。";

        // 1、把正则封装成 Pattern 对象
        Pattern pattern = Pattern.compile("GD\\d{8}");
        // 2、获取匹配器
        Matcher matcher = pattern.matcher(log);
        // 3、find() 循环查找，group() 取本次匹配内容
        while (matcher.find()) {
            System.out.println("提取到工单：" + matcher.group());
        }
    }
}
```

**【运行结果】**
```
提取到工单：GD20260901
提取到工单：GD20260902
提取到工单：GD20260903
```

**【思路讲解】**
1. `matches` 是"整串校验"，从大段文本中**查找/爬取**内容必须用 Pattern/Matcher 两步走；
2. `find()` 找到下一个匹配返回 true，`group()` 返回本次匹配到的子串，循环到找不到为止；
3. `GD2026` 只有 4 位数字，不满足 `{8}`，自动被跳过。

▶ 关联：本章 5.5 节正则提取；第22章网络编程中爬取网页数据也用同样手法。

---

#### 编程题 4（中等）：手写冒泡排序——一周气温排序

**需求：** 不允许调用 `Arrays.sort`，手写冒泡排序把一周气温（double）按**升序**排列后输出。

**【参考代码】**

```java
import java.util.Arrays;

public class TempBubbleSort {
    public static void main(String[] args) {
        double[] temps = {26.5, 23.0, 28.1, 24.6, 30.2, 25.0};

        // 外层：n-1 轮
        for (int i = 0; i < temps.length - 1; i++) {
            // 内层：每轮比较 n-1-i 次
            for (int j = 0; j < temps.length - 1 - i; j++) {
                if (temps[j] > temps[j + 1]) {   // 升序：前大后小就交换
                    double t = temps[j];
                    temps[j] = temps[j + 1];
                    temps[j + 1] = t;
                }
            }
        }
        System.out.println("升序排列后：" + Arrays.toString(temps));
    }
}
```

**【运行结果】**
```
升序排列后：[23.0, 24.6, 25.0, 26.5, 28.1, 30.2]
```

**【思路讲解】**
1. 两个循环边界是核心：外层 `i < length - 1` 控制 n-1 轮，内层 `j < length - 1 - i` 因为末尾 i 个已排好；
2. 相邻元素比较用 `temps[j]` 和 `temps[j+1]`，交换借助第三个变量 t（第6章 temp 交换法）；
3. 想排成降序只需把 `>` 改成 `<`。

▶ 关联：第5章嵌套循环；第6章数组遍历与 temp 交换；本章算法思想。

---

#### 编程题 5（挑战）：二分查找图书架位

**需求：** 图书馆书架上的图书编号按升序排列。手写二分查找方法，传入有序编号数组和目标编号，返回所在索引；找不到返回 -1。测试查找 509 和 999。

**【参考代码】**

```java
public class BookBinarySearch {
    public static void main(String[] args) {
        int[] bookIds = {101, 205, 308, 412, 509, 620, 733, 841};

        int pos1 = binarySearch(bookIds, 509);
        System.out.println("509 的架位索引：" + pos1);       // 4

        int pos2 = binarySearch(bookIds, 999);
        System.out.println("999 的架位索引：" + pos2);       // -1
    }

    public static int binarySearch(int[] arr, int target) {
        int left = 0;
        int right = arr.length - 1;

        while (left <= right) {                 // <= ：重合位置还要再比一次
            int mid = left + (right - left) / 2; // 防溢出写法
            if (target < arr[mid]) {
                right = mid - 1;                // 目标小，去左半找
            } else if (target > arr[mid]) {
                left = mid + 1;                 // 目标大，去右半找
            } else {
                return mid;                     // 找到
            }
        }
        return -1;                              // left > right：不存在
    }
}
```

**【运行结果】**
```
509 的架位索引：4
999 的架位索引：-1
```

**【思路讲解】**
1. 查找 509：left=0/right=7 → mid=3（412）<509 → left=4；left=4/right=7 → mid=5（620）>509 → right=4；left=4/right=4 → mid=4（509）命中，返回 4；
2. 查找 999：目标始终偏大，left 不断右移直到 left > right，返回 -1；
3. 二分查找每步排除一半，8 个元素最多比较 3 次（log₂8），而基本查找最坏要 8 次——数据量越大优势越明显。

▶ 关联：第5章 while 循环与边界条件；第6章数组；第17章 TreeSet 有序集合的查找思想。

---

<div style="page-break-after: always;"></div>

## 第十六章 异常处理与 List 集合 · 习题精讲

> 习题覆盖全章：异常体系（Error/Exception、运行时/编译时异常）、throws 与 try-catch、多 catch 顺序、自定义异常；集合分类、Collection 方法与三种遍历、List 特有方法、ArrayList/LinkedList 底层原理、边遍历边删除。
> 题目场景均为原创（书单管理、借书超限、书架下架、食堂排队、图书系统），未使用笔记中的电影遍历、删除 b 元素、子弹栈、排队购票等原案例。

---

### 一、填空题

**1.** Java 异常体系的根类是 `java.lang.` ______，它有两个子类：代表系统级严重错误的 ______ 和代表程序问题的 ______。

**【答案】** `Throwable`；`Error`；`Exception`

**【解析】** Error 是 JVM 级别的严重问题（如栈溢出 `StackOverflowError`、内存不足 `OutOfMemoryError`），不能靠代码处理，程序员一般不管；Exception 才是程序中可处理的异常。
▶ 关联：第19章《字符集与字节流》的 `IOException`、第23章反射方法上声明的异常都属于 Exception 体系。

**2.** `Exception` 分两大类：`RuntimeException` 及其子类称为 ______ 异常，编译阶段不报错、运行时才出现；其余称为 ______ 异常，编译阶段就必须处理。

**【答案】** 运行时；编译时

**【解析】** 空指针、数组越界、算术异常、类型转换异常都是运行时异常（编译器"信任"你）；日期解析 `ParseException`、IO 流的 `IOException` 是编译时异常（编译器"拦着你"，必须 throws 或 try-catch）。
▶ 关联：第6章数组越界 `ArrayIndexOutOfBoundsException`、第9章 `ClassCastException` 都是运行时异常的具体体现。

**3.** 关键字 ______ 用在方法签名上，声明方法可能抛出异常交给调用者；关键字 ______ 用在方法体内部，手动抛出一个异常对象。

**【答案】** `throws`；`throw`

**【解析】** 形式对比：`public void setAge(int age) throws AgeException { ... throw new AgeException("年龄非法"); }`。throws 后面跟异常类型（可多个，逗号分隔），throw 后面跟异常对象。
▶ 关联：第19章 IO 流方法 `read()` 声明 `throws IOException` 就是编译时异常上抛的典型。

**4.** 多个 catch 块捕获不同异常时，异常类型必须按"______ 到 ______"的顺序书写：先写具体的子类异常，父类异常（如 `Exception`）必须写在 ______。

**【答案】** 小；大；最后

**【解析】** 如果把 `catch (Exception e)` 写在最前面，后面的具体异常永远没有机会匹配（子类 is-a 父类），编译器直接报错。一次异常最终只执行第一个匹配上的 catch 块。
▶ 关联：第8章继承——"子类 is-a 父类"的多态关系决定了 catch 的匹配顺序。

**5.** `Collection` 是单列集合的祖宗接口，它规定了 add、remove、contains、size、toArray 等方法，但**没有** ______ 方法，原因是 Set 集合没有 ______，无法按位置获取元素。

**【答案】** `get`；索引

**【解析】** Collection 必须同时对 List 和 Set 通用，而 Set 无序无索引，所以祖宗接口不能定义 get。要按索引取元素必须用 List 类型接收对象。
▶ 关联：第10章 ArrayList 入门使用的 get；第17章 Set/Map 集合体系。

**6.** ArrayList 底层基于 ______ 实现，无参构造时先创建长度为 ______ 的数组，添加第一个元素时创建长度为 ______ 的数组，存满后按 ______ 倍扩容；LinkedList 底层基于 ______ 实现。

**【答案】** 数组；0；10；1.5；双链表

**【解析】** 数组支持首地址+索引随机访问，所以 ArrayList 查询快、中间增删要移动元素所以慢；双链表节点在内存中不连续、靠 prev/next 地址串联，查询要从头找所以慢，首尾增删只需改指针所以快。若 addAll 一批元素 1.5 倍放不下，新长度按实际需要定（如 21）。
▶ 关联：第6章数组（定长、连续内存）；第10章 ArrayList 入门；LinkedList 模拟队列/栈对应第21章线程等待队列的思想。

---

### 二、选择题

**1.** 下列异常中，属于**编译时异常**（不处理就编译报错）的是（　）。

A. `NullPointerException`
B. `ArrayIndexOutOfBoundsException`
C. `ParseException`
D. `ArithmeticException`

**【答案】** C

**【解析】** 日期解析 `SimpleDateFormat.parse()` 声明抛出 `ParseException`，属于编译时异常，必须 throws 或 try-catch。其余三个都是 `RuntimeException` 的子类，编译不报错。记忆：空指针、越界、算术、类型转换"四大运行时异常"。
▶ 关联：第14章《常用 API》SimpleDateFormat 日期解析；第16章异常分类。

**2.** 要定义一个"借书数量超限"的**编译时异常**，自定义异常类应该（　）。

A. `class BorrowException extends RuntimeException`
B. `class BorrowException extends Exception`
C. `class BorrowException extends Error`
D. `class BorrowException implements Exception`

**【答案】** B

**【解析】** 继承 `Exception`（且不是 RuntimeException 子类）= 编译时异常，方法内 throw 它时签名必须 `throws` 声明；继承 `RuntimeException` = 运行时异常，无需声明。异常类必须用 extends 继承（Exception 是类不是接口），所以 D 错；继承 Error 语义错误。
▶ 关联：第8章继承语法；本章 7.1/7.2 自定义异常。

**3.** 在增强 for 循环中直接调用集合的 remove 方法删除元素，运行结果是（　）。

A. 正常删除，程序结束
B. 抛出 `ConcurrentModificationException`（并发修改异常）
C. 抛出 `NullPointerException`
D. 编译报错

**【答案】** B

**【解析】** 增强 for 底层是迭代器 Iterator。循环中调用 `list.remove(s)` 绕过迭代器直接改集合，迭代器下次取元素时发现集合被"非法"修改，为保护数据一致性抛出并发修改异常。正确做法：迭代器自己的 `iterator.remove()`、`removeIf`、或 fori 配合 i--/倒序。
▶ 关联：第15章 Lambda——`removeIf(s -> 条件)` 是最简洁的解法。

**4.** 下列方法中，属于 LinkedList **特有**（List 接口通用方法之外）的是（　）。

A. `add(E e)`
B. `get(int index)`
C. `addFirst(E e)`
D. `size()`

**【答案】** C

**【解析】** `addFirst/addLast/getFirst/getLast/removeFirst/removeLast` 六个首尾操作方法是 LinkedList 基于双链表提供的特有方法，ArrayList 没有。add、get、size 是 List 系列共有方法。
▶ 关联：用 `addLast` 入队 + `removeFirst` 出队可模拟队列（先进先出）；`addFirst` 压栈 + `removeFirst` 弹栈可模拟栈（先进后出）。

**5.** `list.removeIf(...)` 方法接收的参数类型是（　）。

A. `Comparator<T>`
B. `Consumer<T>`
C. `Predicate<T>`
D. `Function<T, R>`

**【答案】** C

**【解析】** `removeIf(Predicate<? super E> filter)` 中 Predicate 是函数式接口，唯一方法 `boolean test(T t)`：对每个元素调用 test，返回 true 就删除。Lambda 写法 `list.removeIf(s -> s.startsWith("【下架】"))`。Consumer 用于 forEach（有参无返），Comparator 用于排序。
▶ 关联：第15章 Lambda 与函数式接口；第18章 Stream 的 filter 同样基于 Predicate。

**6.** 关于 List 系列集合的特点，描述正确的是（　）。

A. 无序、不重复、无索引
B. 有序、可重复、有索引
C. 有序、不重复、有索引
D. 无序、可重复、无索引

**【答案】** B

**【解析】** List（ArrayList、LinkedList）：存取有序、元素可重复、有索引（所以有 get/set/add(index) 等索引方法）。"无序、不重复、无索引"是 HashSet 的特点，别记反。
▶ 关联：第17章 HashSet/LinkedHashSet/TreeSet 的特点对比。

---

### 三、判断题

**1.** 出现 `OutOfMemoryError`（内存溢出）时，可以用 try-catch 捕获后让程序恢复正常。（　）

**【答案】** ✗ 错误

**【解析】** Error 是系统级严重问题，代表 JVM 自身资源耗尽，不是代码逻辑能补救的，try-catch 也没有意义。异常处理针对的是 Exception 体系。
▶ 关联：第21章多线程中栈溢出风险与递归（第18章）的关系。

**2.** 一段代码可能发生多种异常时，可以写多个 catch 块，一次异常会依次执行所有匹配的 catch。（　）

**【答案】** ✗ 错误

**【解析】** 一次异常最终**只执行第一个匹配上的** catch 块，执行完就跳到 try-catch 之后继续运行，不会进入其他 catch。多个 catch 之间是"多选一"关系。
▶ 关联：第5章 switch 分支"多选一+break"的思想类似。

**3.** 集合中存储自定义对象时，实际存的是对象的地址值；通过集合外的引用修改对象内容，集合里看到的内容也会变。（　）

**【答案】** ✓ 正确

**【解析】** 集合里装的是引用（地址），外部引用和集合元素指向堆中同一个对象，改的是同一块内存。但若让外部引用 `= new 新对象()`，集合里存的旧地址不受影响。
▶ 关联：第6章数组双引用"一改全改"；第7章对象内存图；第9章多态。

**4.** LinkedList 根据索引查询元素比 ArrayList 更快，因为链表不需要连续内存。（　）

**【答案】** ✗ 错误

**【解析】** 说反了。链表内存不连续，查第 i 个元素必须从头节点顺着 next 一个个数；数组靠"首地址 + 索引"一步定位。所以 **ArrayList 查询快、LinkedList 首尾增删快**。
▶ 关联：第6章数组内存连续的特性；本章 ArrayList/LinkedList 底层原理。

---

### 四、简答题

**1.** 异常的两种处理方式 throws 和 try-catch 分别在什么场景使用？为什么？

**【答案】**
- **底层方法用 throws 往上抛**：工具方法/底层方法往往不知道异常发生后该怎么向用户交代（比如解析日期失败，该提示什么？底层不知道业务上下文），所以只管抛给调用者；
- **顶层方法（如 main）用 try-catch 捕获处理**：main 直接面对用户，必须捕获并给出友好提示（"系统繁忙请稍后重试"），不能再往上抛——抛给 JVM 的后果是打印一堆红色异常栈并终止程序。

调用链示例：main → test01 → test02 → test03（底层 parse 抛异常），异常沿调用链反向向上传递，直到被某个 try-catch 接住；一直没人接才由 JVM 处理。

**【解析】** throws 是"甩锅"，try-catch 是"兜底"。编译时异常二者必选其一，否则编译不通过；运行时异常语法上可以不处理，但良好的顶层设计仍建议捕获关键异常。
▶ 关联：第4章方法调用栈——异常沿栈反向传播与方法弹栈顺序一致；第19章 IO 操作的异常处理。

**2.** 用普通 for 循环边遍历边删除 List 元素，为什么会删不干净？给出三种正确写法。

**【答案】**
- **问题原因**：删除索引 i 的元素后，后面的元素整体前移一位，紧跟的同值元素移到了索引 i；但循环变量 i 已经自增到 i+1，下一次检查 i+1 位置，跳过了移到 i 位置的元素。
- **写法一：删除后 i--**，下次循环还检查当前索引；
- **写法二：倒序遍历**（从 size-1 到 0），元素前移只影响已检查过的索引；
- **写法三（推荐）：迭代器的 `remove()`** 或 JDK8 的 `removeIf`，内部指针会正确回退。
- 禁止：增强 for 中直接调集合 remove（抛并发修改异常）。

**【解析】** `removeIf(s -> 条件)` 一行代码最简洁；需要在删除时做其他操作时用迭代器。本题是集合章节面试高频题。
▶ 关联：第5章循环变量的执行流程；第15章 Lambda/Predicate；第17章 Map 删除同理。

**3.** 从底层结构、性能特点、适用场景三方面对比 ArrayList 与 LinkedList。

**【答案】**

| 对比项 | ArrayList | LinkedList |
| --- | --- | --- |
| 底层 | 数组（内存连续） | 双链表（节点不连续，prev + item + next） |
| 查询 | 快：首地址+索引直接定位 | 慢：从头节点依次找 |
| 中间增删 | 慢：元素要移动；满了还要扩容拷贝 | 较快：改相邻节点指针 |
| 首尾增删 | 一般 | 快：有 addFirst/removeLast 等专用方法 |
| 特有场景 | 随机查询、数据量不大 | 频繁首尾增删；模拟队列、栈 |
| 扩容 | 0→10→1.5 倍 | 无需扩容，节点按需创建 |

**【解析】** 开发中 90% 场景用 ArrayList（查询远多于增删、且末尾 add 并不慢）；LinkedList 在需要队列/栈数据结构时使用。
▶ 关联：第6章数组；第4章方法栈（栈结构）；第21章等待队列思想。

---

### 五、代码阅读题

**1.** 写出下列代码的输出结果。

```java
public static void main(String[] args) {
    System.out.println("开始");
    try {
        int[] arr = {1, 2, 3};
        System.out.println(arr[1]);
        System.out.println(arr[5]);       // 越界
        System.out.println("try 块结束");
    } catch (ArrayIndexOutOfBoundsException e) {
        System.out.println("捕获：索引越界");
    }
    System.out.println("程序继续执行");
}
```

**【答案】**
```
开始
2
捕获：索引越界
程序继续执行
```

**【解析】** 异常发生在 `arr[5]`：try 块中该行之后的"try 块结束"**不再执行**（直接跳到匹配的 catch）；catch 执行完后，try-catch 之后的"程序继续执行"正常输出——这正是 try-catch 的价值：程序不崩溃、能继续。
▶ 关联：第6章数组越界异常；本章 try-catch 执行流程。

**2.** 书架上有连续两本待处理书，下列代码想删除所有书名等于"下架书"的书，写出实际输出并说明问题。

```java
ArrayList<String> shelf = new ArrayList<>();
shelf.add("Java入门");
shelf.add("下架书");
shelf.add("下架书");
shelf.add("Python入门");

for (int i = 0; i < shelf.size(); i++) {
    if (shelf.get(i).equals("下架书")) {
        shelf.remove(i);
    }
}
System.out.println(shelf);
```

**【答案】**
```
[Java入门, 下架书, Python入门]
```
还剩一本"下架书"，删不干净。

**【解析】** 推演：i=0 是 Java入门，不动；i=1 是下架书，删除后元素前移 → 集合变为 `[Java入门, 下架书, Python入门]`，第二本下架书移到了索引 1；i 自增为 2，检查索引 2 是 Python入门——索引 1 上的下架书被跳过。正确写法见简答题第 2 题（i--、倒序、removeIf）。
▶ 关联：第5章 for 循环变量变化；本章边遍历边删除专题。

**3.** 食堂餐盘按摞存放，写出下列代码的输出。

```java
LinkedList<String> plates = new LinkedList<>();
plates.addFirst("盘子1");
plates.addFirst("盘子2");
plates.addFirst("盘子3");
System.out.println("栈顶：" + plates.getFirst());
System.out.println("取走：" + plates.removeLast());
System.out.println("剩余：" + plates);
```

**【答案】**
```
栈顶：盘子3
取走：盘子1
剩余：[盘子3, 盘子2]
```

**【解析】** 三次 addFirst 后链表为 `[盘子3, 盘子2, 盘子1]`（每次插头部）；getFirst 取头部 → 盘子3；removeLast 删尾部 → 盘子1；剩下 `[盘子3, 盘子2]`。addFirst/removeFirst 配对模拟栈（先进后出，最后摞上的盘子最先被拿走）；addLast/removeFirst 配对模拟队列（先进先出）。
▶ 关联：第4章方法调用栈（压栈/弹栈）；第21章线程栈。

**4.** 写出下列代码的输出结果。

```java
Collection<Book> books = new ArrayList<>();
Book b1 = new Book("三体", 3);
books.add(b1);
b1.setCount(5);                                  // 通过外部引用修改对象

Book b2 = new Book("活着", 2);
books.add(b2);
b2 = new Book("平凡的世界", 1);                  // 引用改指向新对象

for (Book b : books) {
    System.out.println(b.getName() + "：" + b.getCount() + " 本");
}
// Book 为标准 JavaBean：name、count 字段
```

**【答案】**
```
三体：5 本
活着：2 本
```

**【解析】** 集合里存的是地址：`b1.setCount(5)` 改的是堆中同一个对象，集合里看到的三体变成 5；而 `b2 = new Book(...)` 只是让 b2 这个**引用变量**指向新对象，集合中存的还是旧地址（活着，2 本），新对象"平凡的世界"没有被 add 进集合，不输出。
▶ 关联：第6章数组双引用；第7章对象内存图与 JavaBean。

---

### 六、编程题（5 道，由易到难）

#### 编程题 1（基础）：心愿书单增删改查

**需求：** 用 `ArrayList<String>` 管理心愿书单：添加 4 本书 → 在索引 1 位置插入"算法导论" → 修改索引 0 的书名 → 删除索引 3 的书（打印被删书名）→ 遍历输出最终书单和总数量。

**【参考代码】**

```java
import java.util.ArrayList;
import java.util.List;

public class WishList {
    public static void main(String[] args) {
        List<String> books = new ArrayList<>();
        books.add("Java入门");
        books.add("数据结构");
        books.add("操作系统");
        books.add("计算机网络");

        books.add(1, "算法导论");                 // 指定索引插入
        System.out.println("插入后：" + books);

        String old = books.set(0, "Java从入门到精通"); // 修改，返回被改元素
        System.out.println("被替换的旧书名：" + old);

        String removed = books.remove(3);         // 按索引删除，返回被删元素
        System.out.println("被删除的书：" + removed);

        System.out.println("最终书单：");
        for (int i = 0; i < books.size(); i++) {  // List 有索引，可以用 fori
            System.out.println("  " + (i + 1) + ". " + books.get(i));
        }
        System.out.println("共 " + books.size() + " 本");
    }
}
```

**【运行结果】**
```
插入后：[Java入门, 算法导论, 数据结构, 操作系统, 计算机网络]
被替换的旧书名：Java入门
被删除的书：操作系统
最终书单：
  1. Java从入门到精通
  2. 算法导论
  3. 数据结构
  4. 计算机网络
共 4 本
```

**【思路讲解】**
1. `add(index, e)` 插入后原位置及后面的元素后移；`set(index, e)` 修改并返回旧值；`remove(index)` 删除并返回被删元素——这三个是 List 有索引才有的方法；
2. 删除前书单为 `[Java从入门到精通, 算法导论, 数据结构, 操作系统, 计算机网络]`，索引 3 正是"操作系统"。

▶ 关联：第10章 ArrayList 入门；第6章数组索引思想。

---

#### 编程题 2（基础）：自定义异常——借书超限

**需求：** 图书馆规定一张借书证最多借 5 本。定义**运行时异常** `BorrowLimitException`，借书方法中超过 5 本时抛出异常（携带提示信息）；main 中连续借 6 本书，用 try-catch 捕获后程序继续输出"借阅流程结束"。

**【参考代码】**

```java
// 自定义运行时异常：继承 RuntimeException
class BorrowLimitException extends RuntimeException {
    public BorrowLimitException() {}
    public BorrowLimitException(String message) {
        super(message);          // 把提示信息传给父类，getMessage() 可取到
    }
}

class LibraryCard {
    private int borrowed = 0;    // 已借数量

    public void borrow(String bookName) {
        if (borrowed >= 5) {
            throw new BorrowLimitException(
                "借书数量不能超过5本，当前已借 " + borrowed + " 本，无法再借《" + bookName + "》");
        }
        borrowed++;
        System.out.println("成功借阅《" + bookName + "》，当前已借 " + borrowed + " 本");
    }
}

public class LibraryTest {
    public static void main(String[] args) {
        LibraryCard card = new LibraryCard();
        String[] books = {"三体", "活着", "围城", "白夜行", "平凡的世界", "万历十五年"};
        try {
            for (String b : books) {
                card.borrow(b);
            }
        } catch (BorrowLimitException e) {
            System.out.println("借阅被拒绝：" + e.getMessage());
        }
        System.out.println("借阅流程结束");   // 捕获后程序继续
    }
}
```

**【运行结果】**
```
成功借阅《三体》，当前已借 1 本
成功借阅《活着》，当前已借 2 本
成功借阅《围城》，当前已借 3 本
成功借阅《白夜行》，当前已借 4 本
成功借阅《平凡的世界》，当前已借 5 本
借阅被拒绝：借书数量不能超过5本，当前已借 5 本，无法再借《万历十五年》
借阅流程结束
```

**【思路讲解】**
1. 自定义异常两步：写类继承 RuntimeException（运行时）/Exception（编译时），提供无参和带 message 的有参构造器（有参构造调 super(message)）；
2. `throw new XxxException(提示)` 在方法体内抛出对象；运行时异常方法签名不用 throws；
3. main 用 try-catch 兜底，异常被捕获后"借阅流程结束"照常输出，程序不崩溃。

▶ 关联：第7章构造器与 super；第8章继承；本章异常处理流程。

---

#### 编程题 3（中等）：批量清理下架图书

**需求：** 书架集合中有若干书名，下架书以 `【下架】` 开头。分别用**迭代器 remove** 和 **removeIf + Lambda** 两种方式清理（写两个方法各演示一次），输出清理后的书架。

**【参考代码】**

```java
import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

public class ShelfCleaner {
    public static void main(String[] args) {
        List<String> shelf1 = new ArrayList<>(List.of(
                "Java入门", "【下架】旧版JSP教程", "数据结构", "【下架】Flash宝典", "操作系统"));
        cleanByIterator(shelf1);
        System.out.println("迭代器清理后：" + shelf1);

        List<String> shelf2 = new ArrayList<>(List.of(
                "Java入门", "【下架】旧版JSP教程", "数据结构", "【下架】Flash宝典", "操作系统"));
        cleanByRemoveIf(shelf2);
        System.out.println("removeIf清理后：" + shelf2);
    }

    // 方式一：迭代器自己的 remove
    public static void cleanByIterator(List<String> shelf) {
        Iterator<String> it = shelf.iterator();
        while (it.hasNext()) {
            String book = it.next();
            if (book.startsWith("【下架】")) {
                it.remove();        // 用迭代器的删除，指针正确回退
            }
        }
    }

    // 方式二：removeIf + Lambda（最简洁）
    public static void cleanByRemoveIf(List<String> shelf) {
        shelf.removeIf(book -> book.startsWith("【下架】"));
    }
}
```

**【运行结果】**
```
迭代器清理后：[Java入门, 数据结构, 操作系统]
removeIf清理后：[Java入门, 数据结构, 操作系统]
```

**【思路讲解】**
1. `List.of(...)` 创建的是不可变集合，不能直接删，所以用 `new ArrayList<>(List.of(...))` 包一层可变集合；
2. 迭代器循环三步：`iterator()` 拿迭代器 → `hasNext()` 判断 → `next()` 取值，删除必须调 `it.remove()` 而不是 `shelf.remove(...)`；
3. `removeIf` 的 Lambda 参数是 Predicate：返回 true 的元素被批量删除，内部已处理好指针问题。

▶ 关联：第15章 Lambda 与 Predicate 函数式接口；第10章 String 的 startsWith 方法；第18章 Stream filter。

---

#### 编程题 4（中等）：食堂取餐排队叫号

**需求：** 用 LinkedList 模拟食堂取餐排队：同学 A、B、C 先来排队（入队）；叫号让 A 取餐离开；这时同学 D 到达排队；再叫号让下一位取餐；输出当前排队队列。要求体现队列"先进先出"。

**【参考代码】**

```java
import java.util.LinkedList;

public class CanteenQueue {
    public static void main(String[] args) {
        LinkedList<String> queue = new LinkedList<>();

        // 入队：排到队尾
        queue.addLast("同学A");
        queue.addLast("同学B");
        queue.addLast("同学C");
        System.out.println("排队情况：" + queue);

        // 出队：队首取餐离开
        System.out.println(queue.removeFirst() + " 取餐离开");

        // 新来的同学排到队尾
        queue.addLast("同学D");
        System.out.println("同学D 到达排队：" + queue);

        System.out.println(queue.removeFirst() + " 取餐离开");
        System.out.println("当前排队：" + queue);
    }
}
```

**【运行结果】**
```
排队情况：[同学A, 同学B, 同学C]
同学A 取餐离开
同学D 到达排队：[同学B, 同学C, 同学D]
同学B 取餐离开
当前排队：[同学C, 同学D]
```

**【思路讲解】**
1. 队列特征是先进先出（FIFO）：入队用 `addLast`（加队尾），出队用 `removeFirst`（删队首）；
2. A 离开后队列是 [B, C]，D 入队变 [B, C, D]，再叫号 B 离开，剩 [C, D]；
3. 对比：栈（先进后出）用 `addFirst` 压栈 + `removeFirst` 弹栈，两个操作都在头部。

▶ 关联：第4章方法栈（压栈弹栈）；第21章多线程的等待队列；本章 LinkedList 首尾方法。

---

#### 编程题 5（综合）：班级图书角管理系统

**需求：** 用 `ArrayList<Book>` 实现图书角管理：Book 为 JavaBean（书名、作者、价格）。功能：① 添加图书；② 按书名查找图书（找到打印信息，找不到提示"馆藏中没有这本书"）；③ 按书名删除图书；④ 展示全部图书与总价。菜单用 while(true)+switch 搭建，用户输入 0 退出。

**【参考代码】**

```java
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

class Book {
    private String name;
    private String author;
    private double price;

    public Book() {}
    public Book(String name, String author, double price) {
        this.name = name;
        this.author = author;
        this.price = price;
    }
    public String getName() { return name; }
    public double getPrice() { return price; }
    public String toString() {
        return "《" + name + "》 作者：" + author + "，价格：" + price + " 元";
    }
}

class BookManager {
    private final List<Book> books = new ArrayList<>();   // 程序运行期间一直用这一个集合

    public void add(Book b) { books.add(b); }

    public void findByName(String name) {
        for (Book b : books) {
            if (b.getName().equals(name)) {     // 字符串内容比较用 equals
                System.out.println("找到：" + b);
                return;                          // 找到直接结束方法
            }
        }
        System.out.println("馆藏中没有《" + name + "》这本书");
    }

    public void removeByName(String name) {
        for (int i = 0; i < books.size(); i++) {
            if (books.get(i).getName().equals(name)) {
                Book removed = books.remove(i); // 按索引删除并接住被删对象
                System.out.println("已下架：" + removed);
                return;
            }
        }
        System.out.println("删除失败，没有《" + name + "》");
    }

    public void showAll() {
        if (books.isEmpty()) {
            System.out.println("图书角是空的");
            return;
        }
        double total = 0;
        for (Book b : books) {
            System.out.println(b);
            total += b.getPrice();
        }
        System.out.println("共 " + books.size() + " 本，总价 " + total + " 元");
    }
}

public class BookCorner {
    public static void main(String[] args) {
        BookManager manager = new BookManager();
        manager.add(new Book("三体", "刘慈欣", 59.0));
        manager.add(new Book("活着", "余华", 35.0));

        Scanner sc = new Scanner(System.in);
        while (true) {
            System.out.println("\n1-添加 2-查找 3-删除 4-展示全部 0-退出");
            int cmd = sc.nextInt();
            sc.nextLine();                       // 吃掉换行，防止 nextLine 读空
            switch (cmd) {
                case 1:
                    System.out.print("书名："); String name = sc.nextLine();
                    System.out.print("作者："); String author = sc.nextLine();
                    System.out.print("价格："); double price = sc.nextDouble();
                    manager.add(new Book(name, author, price));
                    System.out.println("添加成功");
                    break;
                case 2:
                    System.out.print("要查找的书名：");
                    manager.findByName(sc.nextLine());
                    break;
                case 3:
                    System.out.print("要删除的书名：");
                    manager.removeByName(sc.nextLine());
                    break;
                case 4:
                    manager.showAll();
                    break;
                case 0:
                    System.out.println("再见");
                    return;                      // 结束 main
                default:
                    System.out.println("没有这个功能");
            }
        }
    }
}
```

**【思路讲解】**
1. **分层思想**：Book 只装数据（JavaBean），BookManager 封装集合和操作（第7章实体类/操作类分工），main 只负责菜单交互；
2. **集合只创建一次**：用 `final` 成员变量持有，所有操作共用同一个集合，不能写在循环里（否则每轮新建、数据丢失）；
3. **查找套路**：遍历 + equals 比较书名，命中就打印并 return，循环结束没 return 说明不存在——这是"信号位/提前返回"思想；
4. **删除套路**：按索引删除用 `books.remove(i)`（第10章 remove(int) 返回被删元素），删除后立即 return，避免索引移动问题；
5. **Scanner 混用陷阱**：nextInt 后 nextLine 会读到残留换行，先调一次 `sc.nextLine()` 吃掉；
6. 菜单框架 `while(true) + switch + return` 是第5章流程控制的综合应用。

▶ 关联：第5章 switch/while 菜单；第7章 JavaBean 与类设计；第9章多态（List 引用接收 ArrayList）；第10章 ArrayList 增删改查；第15章 Lambda（本例查找删除还可用 removeIf 简化）。

---

<div style="page-break-after: always;"></div>

## 第17章 Set 与 Map 集合·习题精讲

> 题型：填空、选择、判断、简答、代码阅读、编程（5 道，由易到难）。
> 所有编程题为原创业务场景（快递网点、会员足迹、派件统计等），考点与笔记一致。

---

### 一、填空题

**1.** Set 系列集合的总体特点是：______、______、______。

**【答案】** 无序、不重复、无索引。

**【解析】** 无序指添加顺序与取出顺序不一致；不重复指相同元素只能存一个；无索引指没有 `get(int index)` 方法，不能按索引取值。注意三个实现类有差异：`LinkedHashSet` 有序、`TreeSet` 可排序，但"不重复、无索引"是所有 Set 的共性。
▶ 关联：第16章《异常与List集合》中 List 恰好相反——有序、可重复、有索引，选择集合时按这三点对照需求。

**2.** JDK 8 开始，哈希表的结构是 ______ + ______ + ______；HashMap/HashSet 底层数组默认长度为 ______，默认负载因子为 ______，当存入元素超过 ______ 个时按 ______ 倍扩容。

**【答案】** 数组、链表、红黑树；16；0.75；12；2。

**【解析】** 扩容阈值 = 容量 × 负载因子 = 16 × 0.75 = 12，即存第 13 个元素时扩容，新数组长度约为旧数组 2 倍，元素要重新计算位置搬入。链表转红黑树还有附加条件：链表长度 ≥ 8 **且**数组长度 ≥ 64；树节点退化到 ≤ 6 时转回链表。
▶ 关联：第16章 ArrayList 扩容是 1.5 倍且无负载因子概念，注意对比记忆。

**3.** 想让 HashSet 对"内容相同的两个不同对象"去重，必须重写对象的 ______ 和 ______ 两个方法（IDEA 中可用 Alt + Insert 自动生成）。

**【答案】** `hashCode()`、`equals()`。

**【解析】** 底层先用 hashCode 算落点：内容相同的对象必须算出相同哈希值才会落到同一位置；落到同一位置后再用 equals 比较，返回 true 才认定重复。默认实现都按地址比较，所以不重写就无法按内容去重。
▶ 关联：第14章《常用API》讲过 Object 类的这两个方法，重写时 `hashCode` 用参与比较的属性计算、`equals` 比较相同属性，二者必须同时重写。

**4.** Map 的三种遍历方式分别是：______、______、______。

**【答案】** 键找值（`keySet()` + `get()`）、键值对 Entry（`entrySet()` + `getKey()`/`getValue()`）、Lambda（`forEach`）。

**【解析】** 方式一先拿全部键的 Set 再逐个 get；方式二把每个键值对看成 Entry 对象整体遍历，最符合面向对象思想；方式三是 JDK8 的 `map.forEach((k,v) -> ...)`，底层就是方式二。
▶ 关联：第15章《Lambda算法与正则》学过 Lambda 与 BiConsumer，forEach 的参数就是 BiConsumer。

**5.** 自定义对象要存入 TreeSet 排序，两种方式：让类实现 ______ 接口并重写 ______ 方法（this 大于参数对象返回______数、小于返回______数、相等返回______）；或者调用 TreeSet 有参构造器传入 ______ 比较器对象。

**【答案】** `Comparable<T>`、`compareTo`、正整、负整、0；`Comparator`。

**【解析】** compareTo 返回 0 表示两元素"相等"，TreeSet 会判定重复而不存入——所以比较规则必须把所有属性都比到，否则同年龄不同姓名的对象会被误删。Comparator 方式类本身不用改动，更灵活，推荐使用。
▶ 关联：第15章 Arrays.sort 与 Collections.sort 用的也是这两个接口，规则完全一致。

---

### 二、选择题

**1.** 下列关于 HashSet 的说法，正确的是（　）。

A. 元素按添加顺序取出　B. 可以通过 `get(2)` 取第三个元素　C. 同一个元素重复 add 只会存一份　D. 底层基于数组实现，查询慢

**【答案】** C。

**【解析】** HashSet 无序（A 错）、无索引没有 get 方法（B 错）、底层是哈希表，增删改查都快（D 错）；重复元素靠 hashCode+equals 判定后被拦截，C 正确。
▶ 关联：要"保序去重"选 LinkedHashSet，要"排序去重"选 TreeSet，见本章选择表。

**2.** HashMap 中，链表转换为红黑树的条件是（　）。

A. 链表长度达到 8 立即转换　B. 链表长度 ≥ 8 且数组长度 ≥ 64　C. 数组长度达到 16　D. 元素个数达到 12

**【答案】** B。

**【解析】** 链表长度 ≥ 8 但数组长度 < 64 时，只扩容不树化——因为红黑树维护成本高，节点少时链表更快；数组扩容后哈希重新分布，链表自然变短。这是"用最低成本解决问题"的设计。
▶ 关联：红黑树节点退化到 ≤ 6 时转回链表，8 和 6 之间留了缓冲带，防止频繁树化/退化。

**3.** 关于 Map 集合，下列说法错误的是（　）。

A. 键不允许重复，值可以重复　B. 键重复时再次 put 会覆盖旧值　C. HashMap 允许 null 键和 null 值　D. Map 的特点由值决定，键只是附属

**【答案】** D。

**【解析】** 说反了：Map 系列集合的特点全部由**键**决定——HashMap 键无序、LinkedHashMap 键有序、TreeMap 键可排序，值只是附属品。Set 的底层其实就是 Map，Set 只取键、不要值。

**4.** 可变参数 `public static double avg(double... nums)` 的说法，错误的是（　）。

A. 方法内部 nums 本质是一个 double 数组　B. 可以不传参数调用 `avg()`　C. 一个方法可以写两个可变参数　D. 可变参数必须放在形参列表最后

**【答案】** C。

**【解析】** 一个形参列表中只能有一个可变参数且必须在最后（C 错）；它本质就是数组，可用 `nums.length`、可以传 0 个参数（收到空数组），但直接传 null 会在遍历时抛 NullPointerException。

**5.** 下列代码运行结果是（　）。

```java
Map<String, Integer> map = new TreeMap<>();
map.put("orange", 3);
map.put("apple", 1);
map.put("banana", 2);
map.put("apple", 5);
System.out.println(map);
```

A. `{orange=3, apple=5, banana=2}`　B. `{apple=5, banana=2, orange=3}`　C. `{apple=1, banana=2, orange=3}`　D. 报异常

**【答案】** B。

**【解析】** TreeMap 按键的自然顺序升序排列，字符串按首字符编码：a < b < o；`apple` 第二次 put 是覆盖，值变为 5。所以输出 `{apple=5, banana=2, orange=3}`。
▶ 关联：键的排序规则与 TreeSet 完全相同（底层同一套红黑树）。

**6.** Collections 工具类的方法，作用描述错误的是（　）。

A. `addAll(list, a, b, c)` 批量添加　B. `shuffle(list)` 随机打乱顺序　C. `sort(list)` 对对象集合按自然顺序排序，无需任何前提　D. `sort(list, comparator)` 可按比较器规则排序

**【答案】** C。

**【解析】** `sort(list)` 要求元素自身实现 Comparable 接口（Integer、String 已实现）；自定义对象直接 `sort(students)` 会抛 ClassCastException，必须传 Comparator 比较器。
▶ 关联：第16章讲过 List 排序，第15章 Arrays.sort 同理。

---

### 三、判断题

**1.** Set 集合提供了 `get(int index)` 方法，可以按索引获取元素。（　）

**【答案】** ✗ 错误。

**【解析】** Set 无索引，没有 get 方法，遍历只能用迭代器、增强 for 或 forEach。"按索引取值"是 List 的专利。

**2.** 向 HashMap 中 put 一个已存在的键，程序会抛出异常。（　）

**【答案】** ✗ 错误。

**【解析】** 键重复不报错，而是用新值**覆盖**旧值，put 返回被覆盖的旧值。这与 Set"重复元素存不进去"行为不同，注意区分。

**3.** 递归方法没有出口，最终会抛出 StackOverflowError。（　）

**【答案】** ✓ 正确。

**【解析】** 方法不断压栈却永远不弹栈，栈内存被压满后抛栈溢出错误。递归必须有出口且每次调用向出口靠近。
▶ 关联：StackOverflowError 属于 Error 体系，详见第16章《异常与List集合》的异常体系；递归专题在第18章。

**4.** TreeSet 中存入 Integer 元素，默认按数值升序排列；存入 String 元素，默认按字符编码升序排列。（　）

**【答案】** ✓ 正确。

**【解析】** Integer、String 都实现了 Comparable：数字按大小，字符串逐字符比较编码（大写字母编码小于小写，所以 `"A" < "a"`）。

---

### 四、简答题

**1.** 简述 HashSet 存入一个元素时的底层判定过程，并说明它为什么能"去重"。

**【答案】**
1. 把元素封装成节点，调用元素的 `hashCode()` 算出哈希值，与数组长度做类似求余运算得到落点索引；
2. 该位置为 null：直接存入；
3. 该位置已有元素：调用 `equals()` 比较——返回 false（不相等）挂成链表（JDK8 尾插法），返回 true（相等）判定重复，不存入；
4. 链表长度 ≥ 8 且数组长度 ≥ 64 时转红黑树。

**【解析】** "去重"靠两道关卡：哈希值决定落点（内容相同的对象必须重写 hashCode 使哈希值相同才会相遇），equals 决定是否真的相等。两者都用默认实现（按地址）时，内容相同的两个 new 出来的对象地址不同，会被当成两个元素——所以自定义对象必须同时重写两个方法。
▶ 关联：HashMap 存键值对时过程完全相同，只是比较的是**键**，相等时用新值覆盖旧值。

**2.** Comparable 与 Comparator 两种排序方式有什么区别？compareTo/compare 返回值的含义是什么？

**【答案】**
- Comparable：类自己实现的"默认排序规则"，类要 `implements Comparable<T>` 并重写 `compareTo(T o)`， intrusive（侵入类本身）；
- Comparator：调用集合/工具类时临时传入的比较器对象，重写 `compare(o1, o2)`，类不用改动，更灵活，推荐；
- 返回值规则相同：负整数表示前者应排在前面（更小），正整数表示后者排前面，返回 0 表示两者相等（TreeSet/TreeMap 中判为重复，不存入）。

**【解析】** 实战建议：compare 中优先用 `Integer.compare(a, b)`、`Double.compare(a, b)` 而不是直接相减，避免整数溢出；多字段排序时 res 为 0 就继续比下一个字段，全部比完仍为 0 才是真重复。

**3.** 为什么说"Set 系列集合的底层就是 Map"？HashMap 和 HashSet 有什么关系？

**【答案】** HashSet 底层就是一个 HashMap：add 元素时把元素作为**键**存入 Map，值用一个固定的 Object 占位对象。因为 Map 的键天然无序、不重复、无索引，Set 直接复用了这套机制。同理 LinkedHashSet 底层是 LinkedHashMap，TreeSet 底层是 TreeMap。

**【解析】** 理解这层关系后，Set 的所有特点都可以从 Map 的键推导，HashMap 的哈希表、扩容、树化机制讲一遍，Set 和 Map 就都掌握了。
▶ 关联：第18章 Stream 的 `collect(Collectors.toSet())`、`toMap()` 收集结果时，去重原理也回到 hashCode+equals。

---

### 五、代码阅读题

**1.** 阅读代码，写出输出结果。

```java
HashSet<String> set = new HashSet<>();
set.add("北京");
set.add("上海");
set.add("北京");
set.add("广州");
set.add(null);
System.out.println(set.size());
System.out.println(set.contains("上海"));
```

**【答案】**
```
4
true
```

**【解析】** "北京"添加两次只存一份；HashSet 允许存一个 null（HashMap 允许 null 键），所以元素是 北京、上海、广州、null 共 4 个，`size()` 为 4；contains 判断"上海"存在返回 true。输出顺序不要求（无序）。

**2.** 阅读代码，写出两个 TreeSet 的输出。

```java
TreeSet<Integer> ts1 = new TreeSet<>();
Collections.addAll(ts1, 30, 5, 18, 5, 22, 1);
System.out.println(ts1);

TreeSet<String> ts2 = new TreeSet<>();
Collections.addAll(ts2, "banana", "Apple", "apple", "Cherry");
System.out.println(ts2);
```

**【答案】**
```
[1, 5, 18, 22, 30]
[Apple, Cherry, apple, banana]
```

**【解析】** Integer 按数值升序、5 重复只存一个。字符串逐字符比编码：大写字母 A=65、C=67 都小于小写 a=97、b=98，所以大写开头的词排最前，顺序为 Apple、Cherry、apple、banana。

**3.** 阅读代码，写出输出结果。

```java
Map<String, Integer> map = new HashMap<>();
map.put("张三", 80);
map.put("李四", 90);
map.put("王五", 70);
map.put("张三", 95);
System.out.println(map.size());
System.out.println(map.get("张三"));
System.out.println(map.getOrDefault("赵六", -1));
map.remove("王五");
System.out.println(map.containsKey("王五"));
```

**【答案】**
```
3
95
-1
false
```

**【解析】** "张三"第二次 put 覆盖旧值（95），键值对总数仍是 3；getOrDefault 在键不存在时返回默认值 -1，避免返回 null；remove 后 containsKey 为 false。

**4.** 下面 Student 类的 compareTo 只比较了年龄，往 TreeSet 中存入 3 个对象，输出 size 是多少？说明原因。

```java
class Student implements Comparable<Student> {
    String name; int age;
    Student(String name, int age) { this.name = name; this.age = age; }
    @Override
    public int compareTo(Student o) {
        return this.age - o.age;   // 只按年龄比较
    }
    public String toString() { return name + ":" + age; }
}

TreeSet<Student> ts = new TreeSet<>();
ts.add(new Student("张三", 18));
ts.add(new Student("李四", 18));
ts.add(new Student("王五", 20));
System.out.println(ts.size());
```

**【答案】** `2`。

**【解析】** "张三"和"李四"年龄都是 18，compareTo 返回 0，TreeSet 认为二者是"同一个元素"，李四被丢弃。这就是比较规则没写全的典型坑——必须在 res 为 0 时继续比姓名等其他属性：

```java
int res = this.age - o.age;
if (res == 0) res = this.name.compareTo(o.name);
return res;
```

▶ 关联：HashSet 去重靠 hashCode+equals，TreeSet 去重靠 compareTo/compare 返回 0，两套机制不要混淆。

---

### 六、编程题（共 5 题，由易到难）

#### 编程题 1（基础）：快递揽收城市去重

**需求**：快递站点一天内揽收了一批包裹，每个包裹有收件城市。统计今天一共寄往了多少个**不同的城市**（重复城市只算一次），并输出这些城市。

**参考代码**：

```java
import java.util.*;

public class Task1 {
    public static void main(String[] args) {
        ArrayList<String> cities = new ArrayList<>();
        Collections.addAll(cities,
                "武汉", "长沙", "武汉", "郑州", "长沙", "西安", "武汉", "郑州");

        // HashSet 去重：相同城市只存一个
        HashSet<String> distinct = new HashSet<>(cities);

        System.out.println("今日寄达城市数：" + distinct.size());
        System.out.println("城市列表：" + distinct);
    }
}
```

**运行结果**（顺序可能不同）：
```
今日寄达城市数：4
城市列表：[武汉, 长沙, 郑州, 西安]
```

**讲解**：把 List 直接传给 HashSet 构造器即可批量去重，这是"单列数据去重"最简洁的写法。HashSet 无序，输出顺序不固定属正常。
▶ 关联：若要求城市按**首次出现顺序**输出，把 HashSet 换成 LinkedHashSet 即可（见编程题 3）。

#### 编程题 2（基础）：包裹运费排行榜

**需求**：定义包裹类 Package（单号 id、重量 weight（kg）、运费 fee（元））。把若干包裹存入集合，要求**按运费从高到低排序**输出；运费相同时按重量从高到低排序；全部信息相同才视为重复。使用 TreeSet + Comparator 实现。

**参考代码**：

```java
import java.util.*;

class Package {
    private String id;
    private double weight;
    private double fee;

    public Package(String id, double weight, double fee) {
        this.id = id;
        this.weight = weight;
        this.fee = fee;
    }
    public String getId() { return id; }
    public double getWeight() { return weight; }
    public double getFee() { return fee; }
    public String toString() {
        return "包裹" + id + "(重量" + weight + "kg, 运费" + fee + "元)";
    }
}

public class Task2 {
    public static void main(String[] args) {
        TreeSet<Package> ts = new TreeSet<>(new Comparator<Package>() {
            @Override
            public int compare(Package o1, Package o2) {
                // 运费降序
                int res = Double.compare(o2.getFee(), o1.getFee());
                // 运费相同按重量降序
                if (res == 0) res = Double.compare(o2.getWeight(), o1.getWeight());
                // 还相同按单号升序兜底，保证不同包裹不会被误判重复
                if (res == 0) res = o1.getId().compareTo(o2.getId());
                return res;
            }
        });

        ts.add(new Package("SF001", 2.5, 18.0));
        ts.add(new Package("SF002", 1.0, 12.0));
        ts.add(new Package("SF003", 5.0, 18.0));
        ts.add(new Package("SF004", 0.5, 8.0));
        ts.add(new Package("SF001", 2.5, 18.0)); // 完全重复，不存入

        for (Package p : ts) {
            System.out.println(p);
        }
    }
}
```

**运行结果**：
```
包裹SF001(重量2.5kg, 运费18.0元)
包裹SF003(重量5.0kg, 运费18.0元)
包裹SF002(重量1.0kg, 运费12.0元)
包裹SF004(重量0.5kg, 运费8.0元)
```

**讲解**：降序的技巧是比较时把 o2 写前面（`Double.compare(o2.getFee(), o1.getFee())`）；多字段排序每一级 res 为 0 就继续比下一级；最后用单号兜底，避免两个"运费重量碰巧相同但其实是不同包裹"被误删——对应代码阅读题 4 的坑。

#### 编程题 3（中等）：会员浏览足迹

**需求**：电商 App 记录会员浏览商品的足迹。要求：重复浏览同一商品时**只保留第一次浏览的位置**（保序、去重），最后按浏览先后顺序输出足迹，并统计浏览了多少个不同商品。

**参考代码**：

```java
import java.util.*;

public class Task3 {
    public static void main(String[] args) {
        String[] views = {"手机壳", "蓝牙耳机", "手机壳", "充电宝", "蓝牙耳机", "数据线"};

        // LinkedHashSet：双链表记录添加顺序，同时去重
        LinkedHashSet<String> footprints = new LinkedHashSet<>();
        for (String v : views) {
            footprints.add(v);  // 重复添加自动忽略，且不会改变已有顺序
        }

        System.out.println("浏览足迹（按先后顺序）：");
        int i = 1;
        for (String item : footprints) {
            System.out.println(i++ + ". " + item);
        }
        System.out.println("共浏览了 " + footprints.size() + " 个不同商品");
    }
}
```

**运行结果**：
```
浏览足迹（按先后顺序）：
1. 手机壳
2. 蓝牙耳机
3. 充电宝
4. 数据线
共浏览了 4 个不同商品
```

**讲解**：LinkedHashSet = 哈希表（去重快）+ 双链表（记录顺序），"保序去重"场景首选。注意重复 add 已存在元素时，元素位置**不变**（不会被挪到最后）。

#### 编程题 4（中等）：快递员派件量排行榜

**需求**：系统记录了一天内所有包裹的派件员工号（一个 List，重复出现表示该员工派了多件）。用 Map 统计每个快递员的派件数，输出派件王（派件最多的员工）及其件数。

**参考代码**：

```java
import java.util.*;

public class Task4 {
    public static void main(String[] args) {
        // 模拟派件流水：每个元素是一个包裹对应的派件员工号
        List<String> deliveries = new ArrayList<>();
        Collections.addAll(deliveries,
                "E01", "E02", "E01", "E03", "E01", "E02", "E03", "E03", "E02", "E03", "E01");

        // 统计：键=工号，值=派件数
        Map<String, Integer> countMap = new HashMap<>();
        for (String emp : deliveries) {
            // 写法一：containsKey 判断
            if (countMap.containsKey(emp)) {
                countMap.put(emp, countMap.get(emp) + 1);
            } else {
                countMap.put(emp, 1);
            }
            // 写法二（更简洁）：countMap.merge(emp, 1, Integer::sum);
        }
        System.out.println("派件统计：" + countMap);

        // 找派件王：遍历 entrySet，边遍历边比较
        String king = null;
        int max = -1;
        for (Map.Entry<String, Integer> entry : countMap.entrySet()) {
            if (entry.getValue() > max) {
                max = entry.getValue();
                king = entry.getKey();
            }
        }
        System.out.println("派件王是：" + king + "，共派件 " + max + " 件");
    }
}
```

**运行结果**（HashMap 顺序不固定，但派件王确定）：
```
派件统计：{E01=4, E02=3, E03=4}
派件王是：E01，共派件 4 件
```

**讲解**：这是"单列流水 → 双列统计"的经典套路：第一次出现 put 1，之后 get 出来 +1 再 put；`merge(k, 1, Integer::sum)` 一行等价于整个 if-else。找最大值用"打擂台"：假设 max 为 -1，遍历中遇到更大的就更新。注意 E01 和 E03 同为 4 件时，代码记录先遍历到的那个，业务上可并列。
▶ 关联：第18章学完 Stream 后，这种统计可以用 `collect(groupingBy(..., counting()))` 一行完成，但底层思想完全相同。

#### 编程题 5（综合）：省—网点层级查询

**需求**：快递公司按省份管理网点，每个省份下有多个网点（网点类 Outlet：编号、名称、地址）。要求：
1. 用集合嵌套存储"省份 → 该省网点列表"；
2. 录入湖北、湖南两省的网点数据；
3. 查询并输出"湖北省"的所有网点名称与地址；
4. 输出全国一共有多少个网点。

**参考代码**：

```java
import java.util.*;

class Outlet {
    private String code;
    private String name;
    private String address;

    public Outlet(String code, String name, String address) {
        this.code = code;
        this.name = name;
        this.address = address;
    }
    public String getName() { return name; }
    public String getAddress() { return address; }
    public String toString() { return name + "（" + address + "）"; }
}

public class Task5 {
    public static void main(String[] args) {
        // Map 的值是一个 List：集合嵌套
        Map<String, List<Outlet>> network = new HashMap<>();

        List<Outlet> hb = new ArrayList<>();
        Collections.addAll(hb,
                new Outlet("HB01", "武汉光谷网点", "武汉市洪山区"),
                new Outlet("HB02", "宜昌东山网点", "宜昌市西陵区"),
                new Outlet("HB03", "襄阳樊城网点", "襄阳市樊城区"));
        network.put("湖北省", hb);

        List<Outlet> hn = new ArrayList<>();
        Collections.addAll(hn,
                new Outlet("HN01", "长沙雨花网点", "长沙市雨花区"),
                new Outlet("HN02", "株洲天元网点", "株洲市天元区"));
        network.put("湖南省", hn);

        // 查询湖北省的网点
        System.out.println("===== 湖北省网点 =====");
        List<Outlet> result = network.get("湖北省");
        if (result != null) {
            for (Outlet o : result) {
                System.out.println(o.getName() + " —— " + o.getAddress());
            }
        }

        // 统计全国网点总数：遍历所有值（List），累加 size
        int total = 0;
        for (List<Outlet> list : network.values()) {
            total += list.size();
        }
        System.out.println("全国网点总数：" + total);

        // 补充：forEach 遍历整个嵌套结构
        network.forEach((province, outlets) ->
                System.out.println(province + "有 " + outlets.size() + " 个网点"));
    }
}
```

**运行结果**：
```
===== 湖北省网点 =====
武汉光谷网点 —— 武汉市洪山区
宜昌东山网点 —— 宜昌市西陵区
襄阳樊城网点 —— 襄阳市樊城区
全国网点总数：5
湖北省有 3 个网点
湖南省有 2 个网点
```

**讲解**：集合嵌套的读法——`Map<String, List<Outlet>>` 就是"键找值，值还是个集合"，先 get 拿到 List 再按第16章 List 的方式遍历。统计总数时遍历 `values()`，每个值是一个 List，累加其 size。查询结果可能为 null（省份不存在），先判空再遍历是好习惯。
▶ 关联：这种"分组"结构在第18章可用 Stream 的 `groupingBy` 自动生成；嵌套集合的泛型声明依赖第13章《面向对象进阶三》的泛型知识。

---

<div style="page-break-after: always;"></div>

## 第18章 Stream 流、File 类与递归·习题精讲

> 题型：填空、选择、判断、简答、代码阅读、编程（5 道，由易到难）。
> 所有编程题为原创业务场景（外卖订单、骑手排名、歌单、目录体检等），考点与笔记一致。

---

### 一、填空题

**1.** Stream 流的使用固定分三步：______、______、______；其中 ______ 方法调用后流就关闭，不能再继续链式调用。

**【答案】** 获取流、中间操作（链式加工）、终结操作；终结方法。

**【解析】** 中间方法（filter、sorted、map 等）返回值仍是 Stream，可以继续链式调用；终结方法（forEach、count、collect 等）不返回流，调用后流关闭。Stream 只是操作数据的**手段**，最终要用 collect/toArray 收集回集合或数组才是**目的**。
▶ 关联：Stream 大量配合 Lambda 使用，Lambda 语法见第15章《Lambda算法与正则》。

**2.** Map 集合不能直接获取 Stream 流，需要先转成单列视图：获取所有键用 ______、获取所有值用 ______、获取所有键值对用 ______。

**【答案】** `keySet()`、`values()`、`entrySet()`。

**【解析】** 三者分别得到 `Set<K>`、`Collection<V>`、`Set<Map.Entry<K,V>>`，再调 `.stream()`。单列集合直接 `集合.stream()`；数组用 `Arrays.stream(arr)` 或 `Stream.of(arr)`。
▶ 关联：这三个方法来自第17章 Map 的常用方法，Stream 章节是它们的典型应用场景。

**3.** Stream 的中间方法中，过滤用 ______、排序用 ______、只保留前 n 个用 ______、跳过前 n 个用 ______、加工转换类型用 ______、去重用 ______。

**【答案】** `filter`、`sorted`、`limit`、`skip`、`map`、`distinct`。

**【解析】** filter 的 lambda 返回 true 保留、false 拦截；map 的 lambda 返回值就是进入新流的数据（可把 Student 流转成 String 名字流）；distinct 去重对象时依赖对象的 hashCode 和 equals，实体类要重写这两个方法。
▶ 关联：distinct 的去重原理与第17章 HashSet 完全一致。

**4.** File 对象只能操作文件/文件夹本身，不能 ______；创建单级目录用 ______ 方法、创建多级目录用 ______ 方法；delete 方法只能删除文件或 ______ 文件夹。

**【答案】** 读写文件内容（内容要用 IO 流）；`mkdir()`；`mkdirs()`；空的。

**【解析】** mkdir 遇到父目录不存在会失败返回 false，mkdirs 会自动创建父目录；delete 删非空文件夹返回 false、不会递归删除；createNewFile 创建空文件、父路径不存在会抛 IOException。
▶ 关联：文件**内容**的读写正是第19、20章 IO 流的内容，File 只负责"文件本身"。

**5.** 递归算法的三要素是：______、______、______；递归没有出口会导致方法不断压栈，最终抛出 ______ 错误。

**【答案】** 递归公式（把大问题拆成同形式小问题）、递归终结点/出口、递归方向必须走向终结点；`StackOverflowError`（栈溢出）。

**【解析】** 以阶乘为例：公式 `f(n)=f(n-1)*n`、出口 `f(1)=1`、方向是 n 每次减 1 不断靠近出口。执行时先一路压栈（向下传递），命中出口后再依次弹栈返回（向上回归）。

---

### 二、选择题

**1.** 下列 Stream 方法中，属于**终结方法**的是（　）。

A. filter　B. sorted　C. count　D. map

**【答案】** C。

**【解析】** count 返回 long 类型的统计结果，不再是 Stream；filter/sorted/map 都返回 Stream 可继续链式调用。常见终结方法还有 forEach、max、min、collect、toArray。

**2.** Stream 的 `max(Comparator)` 方法返回的类型是（　）。

A. 集合中的元素类型　B. Optional 类型，需要再调 `.get()` 取出　C. boolean　D. long

**【答案】** B。

**【解析】** 因为流可能为空（没有最大值），max/min 把结果包在 `Optional<T>` 中返回，用 `.get()` 取出元素；count 才返回 long。
▶ 关联：Optional 是 JDK8 配合 Stream 引入的容器类，用于避免空指针。

**3.** 关于 File 类，下列说法错误的是（　）。

A. File 对象既可以表示文件也可以表示文件夹　B. `length()` 返回文件的字节个数　C. File 可以直接读取文件中的文本内容　D. 推荐用 `File.separator` 拼接跨平台路径

**【答案】** C。

**【解析】** File 不能读写内容，内容读写要靠 IO 流（第19、20章）。Windows 路径分隔符是 `\`（Java 中写 `\\`），Linux/Mac 是 `/`，用 File.separator 拼接可跨平台。

**4.** 调用 `listFiles()` 时，下列哪种情况返回值不是 `null`（　）。

A. 主调对象是一个文件　B. 路径不存在　C. 主调是一个空文件夹　D. 文件夹无访问权限

**【答案】** C。

**【解析】** 空文件夹返回一个**长度为 0 的 File 数组**（不是 null）；文件、路径不存在、无权限才返回 null。所以遍历前要同时判 null 和长度 0，避免空指针。

**5.** 下面递归方法执行 `f(4)` 的结果是（　）。

```java
public static int f(int n) {
    if (n == 1) return 1;
    return n + f(n - 1);
}
```

A. 4　B. 10　C. 24　D. 栈溢出

**【答案】** B。

**【解析】** 这是求 1+2+...+n 的和：f(4) = 4 + f(3) = 4 + 3 + f(2) = 4+3+2+f(1) = 4+3+2+1 = 10。出口 n==1 返回 1，方向 n-1 走向出口，三要素齐全。（24 是阶乘 `n * f(n-1)` 的结果，注意区分加号和乘号。）

**6.** 关于 `Collectors.groupingBy`，下列说法错误的是（　）。

A. 可以按对象的某个属性把元素分成若干组　B. 配合 `Collectors.counting()` 可以分组计数　C. 分组结果是一个 List　D. 配合 `averagingDouble` 可以分组求平均值

**【答案】** C。

**【解析】** groupingBy 的结果是 **Map**：键是分组属性的值，值是该组元素组成的 List（或下游收集器的统计结果）。分组计数返回 `Map<键类型, Long>`。

---

### 三、判断题

**1.** Stream 流调用终结方法之后，还可以继续对同一个流调用 filter 等中间方法。（　）

**【答案】** ✗ 错误。

**【解析】** 终结方法调用后流就关闭了，再次操作会抛 `IllegalStateException`。需要重新获取流。

**2.** `File f = new File("test.txt"); f.mkdirs();` 可以用来创建一个多级文本文件。（　）

**【解析】** ✗ 错误。mkdirs 创建的是**文件夹（目录）**，不是文件；创建文件用 createNewFile。名字叫 test.txt 但用 mkdirs 创建出来的是一个名为 test.txt 的文件夹。

**3.** 递归方法既可以"方法自己调用自己"（直接递归），也可以通过调用其他方法、其他方法再调回来实现（间接递归）。（　）

**【答案】** ✓ 正确。

**【解析】** 两种形式都属于递归，无论哪种都必须有出口并向出口靠近，否则同样栈溢出。

**4.** `sorted()` 无参版本按自然顺序升序排序，要求元素实现 Comparable 接口；自定义对象可以用 `sorted(比较器)` 指定规则。（　）

**【答案】** ✓ 正确。

**【解析】** 与第17章 TreeSet/Collections.sort 的排序规则一致：数字按大小、字符串按编码，自定义对象要么实现 Comparable，要么传入 Comparator。降序就在比较器里调换两个参数的位置。

---

### 四、简答题

**1.** 简述 Stream 流的完整使用步骤，并说明中间方法和终结方法的区别。

**【答案】**
1. **获取流**：单列集合调 `stream()`；Map 先 keySet/values/entrySet 再 stream；数组用 `Arrays.stream()` 或 `Stream.of()`；
2. **中间操作**：filter、sorted、limit、skip、map、distinct 等，返回值仍是 Stream，可链式调用；
3. **终结操作**：forEach、count、max、min、collect、toArray 等，调用后流关闭。

**区别**：中间方法"加工数据、返回新流"，可以串多个；终结方法"产出最终结果（遍历/统计/收集），不再返回流"。开发中最终一般用 collect 把结果收集回 List/Set/Map——流是手段，集合才是目的。
▶ 关联：collect 的 toSet/toMap 去重原理见第17章；函数式接口（Predicate、Function、Consumer）见第15章。

**2.** 分别说明 `listFiles()` 在以下情况的返回值：①路径不存在；②主调是一个文件；③空文件夹；④有内容的文件夹；⑤无权限访问。为什么遍历前必须判空？

**【答案】**
- ①路径不存在、②主调是文件、⑤无权限：返回 `null`；
- ③空文件夹：返回长度为 0 的 File 数组；
- ④有内容的文件夹：返回包含所有**一级**文件和文件夹的 File 数组（隐藏文件也包含，但不递归进入子文件夹）。

判空原因：返回 null 时直接写 `for (File f : files)` 会抛 NullPointerException。标准写法是先判 `files == null || files.length == 0` 再遍历。
▶ 关联：这个判空在递归遍历目录（编程题 5）中是递归出口的一部分。

**3.** 什么是递归？写出递归三要素，并以"求 1~n 的和"为例说明压栈、弹栈的执行过程。

**【答案】** 递归是方法直接或间接调用自身的算法。三要素：①递归公式（大问题拆成同形式小问题）；②终结点/出口；③每次调用都向出口靠近。

求和 `sum(n) = n + sum(n-1)`，出口 `sum(1)=1`。以 sum(4) 为例：
- 压栈（向下传递）：main → sum(4) 等 sum(3) → sum(3) 等 sum(2) → sum(2) 等 sum(1) → sum(1) 命中出口返回 1；
- 弹栈（向上回归）：sum(2)=2+1=3 → sum(3)=3+3=6 → sum(4)=4+6=10，回到 main 输出 10。

缺出口或方向不收敛，栈帧无限压入，栈内存满后抛 StackOverflowError。
▶ 关联：方法栈"压栈/弹栈"的内存机制在第4章《方法》中讲过，递归是它的综合应用。

---

### 五、代码阅读题

**1.** 写出下列代码的输出。

```java
List<Integer> list = new ArrayList<>(List.of(12, 5, 8, 100, 3, 66));
list.stream().filter(i -> i >= 10).sorted().forEach(System.out::println);
```

**【答案】**
```
12
66
100
```

**【解析】** filter 保留 ≥10 的：12、100、66；sorted 无参按自然顺序升序：12、66、100；`System.out::println` 是方法引用，等价于 `x -> System.out.println(x)`。
▶ 关联：方法引用语法见第15章。

**2.** 写出输出结果。

```java
List<Integer> list = new ArrayList<>(List.of(3, 9, 1, 7, 20));
long c = list.stream().filter(i -> i > 5).count();
int max = list.stream().max(Integer::compare).get();
long skipped = list.stream().skip(2).count();
System.out.println(c + "," + max + "," + skipped);
```

**【答案】** `3,20,3`

**【解析】**
- 大于 5 的是 9、7、20，count = 3；
- max 最大值 20（Optional 包装，.get() 取出）；
- skip(2) 跳过前两个（3、9），剩 1、7、20 共 3 个。
注意每次统计都重新获取了流（三个独立的 stream() 调用），这是正确的——流不能复用。

**3.** 已知订单类 Order 有城市 city 和金额 amount 两个属性，下列分组统计输出什么？

```java
List<Order> orders = new ArrayList<>(List.of(
        new Order("武汉", 30.0),
        new Order("武汉", 50.0),
        new Order("长沙", 40.0)));

Map<String, Long> cnt = orders.stream()
        .collect(Collectors.groupingBy(Order::getCity, Collectors.counting()));
System.out.println(cnt);

Map<String, Double> avg = orders.stream()
        .collect(Collectors.groupingBy(Order::getCity,
                Collectors.averagingDouble(Order::getAmount)));
System.out.println(avg);
```

**【答案】**
```
{武汉=2, 长沙=1}
{武汉=40.0, 长沙=40.0}
```

**【解析】** groupingBy 第一参数是"分组键怎么取"（按城市），第二参数是下游收集器：counting 计数（武汉两单、长沙一单），averagingDouble 求平均（武汉 (30+50)/2=40.0，长沙 40.0）。`Order::getCity` 是方法引用。

**4.** 找出下面代码的问题并说明后果。

```java
public static void printAll(File dir) {
    File[] files = dir.listFiles();
    for (File f : files) {
        System.out.println(f.getAbsolutePath());
    }
}
// 调用：printAll(new File("D:/某文件.txt"));
```

**【答案】** `listFiles()` 的主调是一个**文件**（或路径不存在、无权限时），返回 `null`，对 null 做增强 for 遍历直接抛 `NullPointerException`。

**修复**：遍历前先判空——

```java
File[] files = dir.listFiles();
if (files == null || files.length == 0) {
    return;
}
for (File f : files) { ... }
```

**【解析】** 这正是 listFiles 返回值规则的实战意义；递归遍历目录时，这个判空同时充当递归出口（见编程题 5）。

---

### 六、编程题（共 5 题，由易到难）

#### 编程题 1（基础）：大额订单筛选

**需求**：外卖系统有一批订单金额（元）。用 Stream 完成：①筛选出金额满 30 元的订单；②按金额升序输出；③统计满 30 元的订单数量。

**参考代码**：

```java
import java.util.*;
import java.util.stream.Collectors;

public class Task1 {
    public static void main(String[] args) {
        List<Double> amounts = new ArrayList<>(List.of(18.5, 32.0, 25.0, 66.0, 30.0, 12.8));

        // ① 筛选 + ②排序 + 收集到新集合
        List<Double> bigOrders = amounts.stream()
                .filter(a -> a >= 30)
                .sorted()
                .collect(Collectors.toList());
        System.out.println("满30元订单（升序）：" + bigOrders);

        // ③统计数量（count 返回 long）
        long count = amounts.stream().filter(a -> a >= 30).count();
        System.out.println("满30元订单数：" + count);
    }
}
```

**运行结果**：
```
满30元订单（升序）：[30.0, 32.0, 66.0]
满30元订单数：3
```

**讲解**：filter 的 lambda 是保留条件；sorted 无参自然升序；collect(toList()) 把流收集回 List——体现"流是手段、集合是目的"。count 是终结方法，返回 long。

#### 编程题 2（基础）：骑手配送时长排名

**需求**：骑手类 Rider（姓名 name、配送时长 minutes）。用 Stream 完成：①找出配送时长最短的 3 名骑手（升序取前 3）；②找出最慢的 2 名骑手（降序取前 2，或升序 skip 掉前面的）。

**参考代码**：

```java
import java.util.*;
import java.util.stream.Collectors;

class Rider {
    private String name;
    private int minutes;
    public Rider(String name, int minutes) { this.name = name; this.minutes = minutes; }
    public String getName() { return name; }
    public int getMinutes() { return minutes; }
    public String toString() { return name + "(" + minutes + "分钟)"; }
}

public class Task2 {
    public static void main(String[] args) {
        List<Rider> riders = new ArrayList<>(List.of(
                new Rider("小赵", 28),
                new Rider("小钱", 22),
                new Rider("小孙", 35),
                new Rider("小李", 25),
                new Rider("小周", 40)));

        // ① 时长升序（越快越靠前），取前 3
        List<Rider> fastest = riders.stream()
                .sorted(Comparator.comparingInt(Rider::getMinutes))
                .limit(3)
                .collect(Collectors.toList());
        System.out.println("配送最快的3名：" + fastest);

        // ② 时长降序取前 2（最慢）
        List<Rider> slowest = riders.stream()
                .sorted(Comparator.comparingInt(Rider::getMinutes).reversed())
                .limit(2)
                .collect(Collectors.toList());
        System.out.println("配送最慢的2名：" + slowest);
    }
}
```

**运行结果**：
```
配送最快的3名：[小钱(22分钟), 小李(25分钟), 小赵(28分钟)]
配送最慢的2名：[小周(40分钟), 小孙(35分钟)]
```

**讲解**：对象排序用 `Comparator.comparingInt(类名::getter)` 最简洁，`.reversed()` 反转成降序；limit(3) 保留前 3 个。注意排序和 limit 的顺序——必须先 sorted 再 limit，取到的才是极值。
▶ 关联：Comparator 排序规则与第15、17章一致；方法引用 `Rider::getMinutes` 见第15章。

#### 编程题 3（中等）：歌单歌手去重

**需求**：歌单里每首歌是一个 Song 对象（歌名 title、歌手 singer）。用 Stream 完成：①提取所有歌手名字；②去重；③输出歌手名单和歌手人数。

**参考代码**：

```java
import java.util.*;
import java.util.stream.Collectors;

class Song {
    private String title;
    private String singer;
    public Song(String title, String singer) { this.title = title; this.singer = singer; }
    public String getSinger() { return singer; }
}

public class Task3 {
    public static void main(String[] args) {
        List<Song> songs = new ArrayList<>(List.of(
                new Song("晴天", "周杰伦"),
                new Song("稻香", "周杰伦"),
                new Song("红豆", "王菲"),
                new Song("匆匆那年", "王菲"),
                new Song("李白", "李荣浩")));

        // map：把 Song 流转成歌手名字的 String 流；distinct 去重
        List<String> singers = songs.stream()
                .map(Song::getSinger)
                .distinct()
                .collect(Collectors.toList());

        System.out.println("歌手名单：" + singers);
        System.out.println("歌手人数：" + singers.size());

        // 也可以直接收集到 Set（自动去重）
        Set<String> singerSet = songs.stream().map(Song::getSinger).collect(Collectors.toSet());
        System.out.println("用 Set 收集：" + singerSet);
    }
}
```

**运行结果**：
```
歌手名单：[周杰伦, 王菲, 李荣浩]
歌手人数：3
用 Set 收集：[周杰伦, 王菲, 李荣浩]
```

**讲解**：map 的作用是"换流的类型"——Song 流经过 `map(Song::getSinger)` 变成 String 流；distinct 按内容去重（String 已重写 hashCode/equals）。若去重的是自定义对象，记得在实体类重写这两个方法。collect(toSet()) 则一步完成收集+去重。
▶ 关联：Set 去重原理见第17章。

#### 编程题 4（中等）：按城市统计订单

**需求**：订单类 Order（城市 city、金额 amount）。用 Stream + groupingBy 完成：①统计每个城市的订单数量；②统计每个城市的平均客单价；③输出订单量最多的城市。

**参考代码**：

```java
import java.util.*;
import java.util.stream.Collectors;

class Order {
    private String city;
    private double amount;
    public Order(String city, double amount) { this.city = city; this.amount = amount; }
    public String getCity() { return city; }
    public double getAmount() { return amount; }
}

public class Task4 {
    public static void main(String[] args) {
        List<Order> orders = new ArrayList<>(List.of(
                new Order("武汉", 30.0),
                new Order("武汉", 50.0),
                new Order("武汉", 40.0),
                new Order("长沙", 25.0),
                new Order("长沙", 35.0)));

        // ① 分组计数
        Map<String, Long> countMap = orders.stream()
                .collect(Collectors.groupingBy(Order::getCity, Collectors.counting()));
        System.out.println("各城市订单数：" + countMap);

        // ② 分组求平均金额
        Map<String, Double> avgMap = orders.stream()
                .collect(Collectors.groupingBy(Order::getCity,
                        Collectors.averagingDouble(Order::getAmount)));
        System.out.println("各城市平均客单价：" + avgMap);

        // ③ 订单数最多的城市（对计数结果再求 max）
        String topCity = countMap.entrySet().stream()
                .max(Map.Entry.comparingByValue())
                .get().getKey();
        System.out.println("订单量最多的城市：" + topCity);
    }
}
```

**运行结果**：
```
各城市订单数：{武汉=3, 长沙=2}
各城市平均客单价：{武汉=40.0, 长沙=30.0}
订单量最多的城市：武汉
```

**讲解**：groupingBy(分组键, 下游收集器) 是分组统计的核心：counting 计数、averagingDouble 求平均。第③问对分组后的 Map 再次转流，用 `max(Map.Entry.comparingByValue())` 找值最大的键。这道题串联了第17章 Map 遍历和本章 Stream 统计。

#### 编程题 5（综合）：文件夹体检 + 递归统计目录大小

**需求**：写一个工具，对指定文件夹做"体检"：
1. 列出该文件夹下所有**一级**内容的名称，并区分是文件还是文件夹；
2. 统计一级内容中文件个数、文件夹个数；
3. 用**递归**统计整个文件夹（含所有子文件夹）的总大小（字节数）。

**参考代码**：

```java
import java.io.File;

public class Task5 {
    public static void main(String[] args) {
        File dir = new File("D:\\test");  // 改成你机器上的真实文件夹路径

        if (!dir.exists() || !dir.isDirectory()) {
            System.out.println("路径不存在或不是文件夹：" + dir);
            return;
        }

        File[] files = dir.listFiles();
        // listFiles 判空：文件/不存在/无权限返回 null，空文件夹返回长度 0 数组
        if (files == null || files.length == 0) {
            System.out.println("文件夹为空或无法访问");
            return;
        }

        int fileCount = 0, dirCount = 0;
        System.out.println("===== 一级内容 =====");
        for (File f : files) {
            if (f.isFile()) {
                fileCount++;
                System.out.println("[文件] " + f.getName() + "，" + f.length() + " 字节");
            } else {
                dirCount++;
                System.out.println("[文件夹] " + f.getName());
            }
        }
        System.out.println("一级内容：文件 " + fileCount + " 个，文件夹 " + dirCount + " 个");

        long total = totalSize(dir);
        System.out.println("整个文件夹总大小（含子文件夹）：" + total + " 字节");
    }

    /**
     * 递归统计目录总大小
     * 公式：目录大小 = 目录下每个一级内容的大小之和
     *   - 一级内容是文件：加 length()
     *   - 一级内容是文件夹：加 totalSize(子文件夹)（递归）
     * 出口：files 为 null/空（叶子目录）返回 0；文件不进入递归
     */
    public static long totalSize(File file) {
        if (file.isFile()) {
            return file.length();   // 文件：直接返回自身大小
        }
        File[] children = file.listFiles();
        if (children == null || children.length == 0) {
            return 0;               // 空文件夹或无权限：大小为 0（递归出口）
        }
        long sum = 0;
        for (File child : children) {
            sum += totalSize(child); // 是文件夹就继续递归进去
        }
        return sum;
    }
}
```

**运行结果**（示例，取决于实际目录）：
```
===== 一级内容 =====
[文件] a.txt，128 字节
[文件] b.jpg，102400 字节
[文件夹] sub
一级内容：文件 2 个，文件夹 1 个
整个文件夹总大小（含子文件夹）：105600 字节
```

**讲解**：
- 第一、二问用 listFiles + isFile/isDirectory 区分类型，遍历前必须判空；
- 递归统计大小的三要素：公式"目录大小 = 所有一级内容大小之和"（文件用 length、文件夹递归）、出口"文件返回 length / 空目录返回 0"、方向"每次进入子文件夹，层级加深但必然到达叶子文件"；
- totalSize 对文件直接返回 length 不再深入，对文件夹才递归，这保证了递归一定会终止——文件夹树是有限深度的，不会像无出口递归那样栈溢出。

▶ 关联：File 的路径/判断方法是本章第 2 节内容；同样的递归骨架稍作改造就能做"递归搜索文件"（找到名字匹配的文件输出路径）、"递归打印目录树"（每层加缩进）；文件内容的读写要等第19、20章 IO 流。

---

<div style="page-break-after: always;"></div>

## 第19章 字符集与字节流·习题精讲

> 题型：填空、选择、判断、简答、代码阅读、编程（6 道，由易到难）。
> 所有编程题场景均为原创（快递面单、歌单备份、快递柜日志、运单上传等），考点与笔记一致。

---

### 一、填空题

**1.** 在 UTF-8 编码中，一个汉字占 ______ 个字节；在 GBK 编码中，一个汉字占 ______ 个字节；英文字母在两种编码中都占 ______ 个字节。

**【答案】** 3；2；1

**【解析】** UTF-8 是可变长编码（1~4 字节），汉字 3 字节；GBK 汉字 2 字节；两者都兼容 ASCII，英文数字 1 字节。记不住字节数就无法判断乱码原因和数组长度。
▶ 关联：本章编码结论是第 20 章「字符流读 GBK 文件乱码」的直接原因。

**2.** `FileInputStream` 的 `read()` 方法每次读取 1 个字节，读到文件末尾时返回 ______；`read(byte[] buffer)` 方法的返回值表示 ______，读到末尾返回 ______。

**【答案】** -1；本次实际读取到的字节个数；-1

**【解析】** 注意 `read()` 返回的是字节的码表值（int），不是字符本身，打印中文要 `(char)` 强转；`read(byte[])` 返回的是"本次装了多少个"，数组容量不等于实际读取数。
▶ 关联：第 20 章字符流 `read(char[])` 的返回值规则与此完全一致。

**3.** 创建 `FileOutputStream` 时，构造方法第二个参数传 ______ 表示追加模式（不清空原内容）；不传则默认 ______ 原文件内容。

**【答案】** true；清空（覆盖）

**【解析】** `new FileOutputStream(path)` 每次写入前先清空文件；`new FileOutputStream(path, true)` 在末尾续写。日志类需求必须用追加模式。

**4.** IO 流类名有命名规律：字节流的类名以 ______ 结尾，字符流的类名以 ______ 结尾。

**【答案】** Stream；Reader / Writer

**【解析】** 如 `FileInputStream`/`FileOutputStream` 是字节流；`FileReader`/`FileWriter` 是字符流。看到类名就能判断派系。
▶ 关联：第 22 章网络编程的 `Socket.getInputStream()` 返回字节流，因为网络传输的是字节。

**5.** JDK 7 及以后推荐使用 try-with-resources 释放资源，能放进 `try (...)` 里的资源类都必须实现 ______ 接口，该接口保证资源有 ______ 方法可被自动调用。

**【答案】** AutoCloseable；close()

**【解析】** try 退出时（无论正常还是异常）自动调用 close()，省去 finally 判空关闭。
▶ 关联：第 20 章所有字符流、缓冲流、对象流都实现了该接口，所以都能放进 try()。

**6.** 把字符转成字节叫 ______，把字节转回字符叫 ______；两者使用的字符集不一致就会出现 ______。

**【答案】** 编码（Encode）；解码（Decode）；乱码

**【解析】** Java 中 `getBytes()` 编码、`new String(bytes)` 解码，都可传字符集名参数。

---

### 二、选择题

**1.** 执行 `byte[] b = "I爱Y".getBytes();`（平台默认 UTF-8），数组 `b` 的长度是：

A. 3　　B. 4　　C. 5　　D. 6

**【答案】** C

**【解析】** I 占 1 字节、爱 占 3 字节、Y 占 1 字节，共 5 个字节。UTF-8 汉字 3 字节是关键。

**2.** 接上题，若改为 `"I爱Y".getBytes("GBK")`，数组长度是：

A. 3　　B. 4　　C. 5　　D. 6

**【答案】** B

**【解析】** GBK 中爱 只占 2 字节：1+2+1=4。

**3.** 下列哪种文件不能用字节流复制？

A. 图片 .jpg　　B. 视频 .mp4　　C. 压缩包 .zip　　D. 以上都能用字节流复制

**【答案】** D

**【解析】** 字节流以字节为单位，可以操作**所有类型**文件；字符流才只能操作纯文本。复制图片/视频必须用字节流（字符流会破坏二进制数据）。

**4.** 关于 `readAllBytes()`，下列说法正确的是：

A. 是 JDK 8 提供的方法
B. 一次性读取文件全部字节，适合超大文件
C. 一次性读取全部字节，不会读到半个汉字，但文件过大可能内存溢出
D. 返回值是读取到的字节个数

**【答案】** C

**【解析】** readAllBytes() 是 JDK 11+ 方法，返回 byte[]（不是个数），整体转字符串不乱码，但大文件会撑爆内存，所以大文件仍应用缓冲区边读边写。

**5.** 用字节数组缓冲区复制文件时，写出循环正确的写法是：

A. `fos.write(bytes);`
B. `fos.write(bytes, 0, len);`
C. `fos.write(bytes, 0, bytes.length);`
D. `fos.write(len);`

**【答案】** B

**【解析】** 最后一次读取通常装不满数组，若写整个数组（A/C），会把数组里上一次残留的旧数据也写进目标文件，导致文件尾部多出垃圾字节。必须只写本次读到的前 len 个字节。

**6.** 程序创建了 `FileOutputStream("D:/a/b.txt")` 但还没来得及 write 就抛异常终止，关于目标文件说法正确的是：

A. 文件不存在，因为没写成功
B. 文件存在且内容完整
C. 文件存在但大小是 0 字节（创建输出流时已自动建空文件）
D. 会自动删除

**【答案】** C

**【解析】** 创建输出流对象时若文件不存在会**立即自动创建空文件**，随后异常终止没写入，留下 0 字节文件——这是"复制成功的假象"，判断复制是否成功要看目标文件大小是否与源文件一致。

**7.** `new FileOutputStream("waybill.txt")` 后连续执行 `write(97)`、`write(98)`，文件中显示的内容是：

A. 9798　　B. ab　　C. 179　　D. 乱码

**【答案】** B

**【解析】** write(int b) 写出的是字节 97、98，按码表对应字符 a、b 存入文件。

---

### 三、判断题

**1.** 字节流只能复制二进制文件（图片、视频），不能复制文本文件。（　）

**【答案】** 错误

**【解析】** 字节流可以复制**任意类型**文件，包括文本。只是逐字节读取中文时会因读到半个汉字而在"读取并显示"时乱码；单纯复制（读字节→写字节）不解析字符，不会乱码。

**2.** `fis.read()` 读到的第一个字节若对应字母 'a'，方法返回字符 'a' 本身。（　）

**【答案】** 错误

**【解析】** read() 返回 int 类型的码表值 97，不是字符 'a'；直接拼接打印是数字，需要 `(char)` 强转才显示字母。

**3.** 用 `new FileOutputStream(path)` 写文件时，如果目标文件原本不存在，程序会自动创建该文件。（　）

**【答案】** 正确

**【解析】** 输出流创建时自动建文件（但父目录必须存在，否则抛 FileNotFoundException）。

**4.** try-with-resources 的 `try ()` 里可以放入任意 Java 对象。（　）

**【答案】** 错误

**【解析】** 只能放实现了 AutoCloseable 接口的资源对象（流等），普通对象没有 close() 方法、无法自动释放。

**5.** 用 `read(byte[] bytes)` 读取后，直接 `new String(bytes)` 转字符串是最稳妥的写法。（　）

**【答案】** 错误

**【解析】** 数组最后一次可能没读满，未填充位置是空字符/残留数据，直接转字符串会带出多余内容。必须用 `new String(bytes, 0, len)` 只转换本次读到的 len 个字节。

---

### 四、简答题

**1.** 什么是编码、解码？为什么会乱码？英文数字为什么一般不乱码？

**【答案】**
- 编码：字符 → 字节（`getBytes()`）；解码：字节 → 字符（`new String(bytes)`）。
- 乱码根本原因：**编码用的字符集和解码用的字符集不一致**（如用 GBK 编码、用 UTF-8 解码），字节按错误规则拼接成了别的字符。
- 英文数字不乱码：因为绝大多数字符集（GBK、UTF-8）都兼容 ASCII，英文字母的编码在各字符集中完全相同。

**【解析】** 解决乱码的核心原则只有一条：读写双方约定相同字符集。这也是第 20 章转换流存在的意义。

**2.** 字节流和字符流有什么区别？分别适合什么场景？

**【答案】**

| 对比项 | 字节流 | 字符流 |
| --- | --- | --- |
| 数据单位 | 字节 | 字符 |
| 类名结尾 | Stream | Reader / Writer |
| 可操作文件 | 所有类型（文本/图片/视频/压缩包） | 仅纯文本（.txt/.java 等） |
| 中文处理 | 逐字节读会读到半个汉字 | 自动按编码拼字符，不乱码 |

- 复制**任意文件**（尤其图片、视频、音频）→ 字节流；
- 只读写**纯文本**且涉及中文显示 → 字符流（第 20 章）。

**【解析】** 方向（输入/输出）以内存为基准：读进来是输入流，写出去是输出流。

**3.** 为什么流用完必须关闭？try-with-resources 相比 finally 有什么好处？

**【答案】**
- 流会占用操作系统文件资源，不关闭会导致资源泄漏、文件被占用无法删除等。
- JDK7 前用 finally 关闭：流变量必须在 try 外声明、finally 中还要逐个判空（防止流没创建成功就 close 导致空指针），代码繁琐。
- try-with-resources：资源声明在 `try ()` 中，无论正常结束还是抛异常，JVM 都会自动调用 close()，代码简洁且不会漏关。前提是资源实现 AutoCloseable。

---

### 五、代码阅读题

**1.** 阅读代码，写出两段打印结果（平台默认 UTF-8）：

```java
String data = "I爱Y";
byte[] a = data.getBytes();
System.out.println(a.length);                 // ①
System.out.println(Arrays.toString(a));       // ②
byte[] b = data.getBytes("GBK");
System.out.println(b.length);                 // ③
```

**【答案】**
① `5`
② `[73, -25, -120, -79, 89]`
③ `4`

**【解析】** UTF-8：I=73，爱=三字节 -25,-120,-79（字节首位为 1 时 Java 显示为负数），Y=89，共 5 个。GBK：爱=两字节 -80,-82，共 4 个。负数是因为字节最高位为 1 表示这是个多字节字符的组成部分。

**2.** 下面复制文件的代码有两处问题，找出并说明后果：

```java
FileInputStream fis = new FileInputStream("src/song.mp3");
FileOutputStream fos = new FileOutputStream("backup/song.mp3");
byte[] bytes = new byte[1024];
while (true) {
    int len = fis.read(bytes);
    if (len == -1) break;
    fos.write(bytes);          // 问题行
}
fis.close();
fos.close();
```

**【答案】**
- 问题一：`fos.write(bytes)` 写了整个数组，应改为 `fos.write(bytes, 0, len)`。后果：最后一次读不满 1024 字节时，数组尾部残留上一轮的数据被一并写入，目标文件比源文件大、尾部有垃圾内容（对 mp3 可能导致播放异常）。
- 问题二：没有用 try-with-resources/finally，若中途抛异常，close() 执行不到，流资源泄漏。

**【解析】** 这是字节流复制最经典的扣分点：读用 len 判断，写也必须用 len 限定长度。

**3.** 某文本文件内容为 `中`（UTF-8 编码，3 字节），用如下代码读取并打印，输出什么？为什么？

```java
FileInputStream fis = new FileInputStream("f.txt");
int b;
while ((b = fis.read()) != -1) {
    System.out.print((char) b);
}
```

**【答案】** 输出 3 个乱码字符（类似 `ä¸­`），而不是"中"。

**【解析】** read() 每次只读 1 个字节，把 UTF-8 汉字的 3 个字节各自当成一个独立字符强转，等于把一个汉字拆成了三分之一×3，必然乱码。逐字节读只适合英文/二进制；读中文文本应整体 `readAllBytes()` 转字符串，或用第 20 章字符流。

**4.** 已知文件 `log.txt` 原有内容 `A`，程序连续运行两次，每次执行：

```java
FileOutputStream fos = new FileOutputStream("log.txt", true);
fos.write("B".getBytes());
fos.close();
```

两次运行后文件内容是什么？若把构造参数的 true 去掉呢？

**【答案】**
- 追加模式（true）：第一次后 `AB`，第二次后 `ABB`。
- 去掉 true（默认覆盖）：每次运行都先清空再写，第一次后 `B`，第二次后还是 `B`。

**【解析】** true 控制不清空、续写；无 true 则每次覆盖。日志累加场景必须用 true。

---

### 六、编程题

#### 编程题 1（基础）：生成快递电子面单

**需求**：快递公司需要把一张电子面单信息写入文件 `waybill.txt`。面单内容为三行文本（用字节流写出）：
```
SF1234567890
张三
北京市海淀区中关村大街1号
```
请用 `FileOutputStream` 把上述内容写入文件（字符串用 `getBytes()` 转字节数组，行间写换行符 `\r\n`）。

**【参考代码】**

```java
public class WaybillWriter {
    public static void main(String[] args) {
        try (FileOutputStream fos = new FileOutputStream("waybill.txt")) {
            fos.write("SF1234567890".getBytes());
            fos.write("\r\n".getBytes());
            fos.write("张三".getBytes());
            fos.write("\r\n".getBytes());
            fos.write("北京市海淀区中关村大街1号".getBytes());
            System.out.println("面单已生成");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**【思路讲解】**
1. 字节流写字节，字符串必须先 `getBytes()` 编码成字节数组——这正是本章"编码"的实际应用；
2. 字节流不会自动换行，手动写 `"\r\n".getBytes()`（Windows 换行）；
3. 用 try-with-resources 自动关闭流，不用手写 finally。

**运行结果**：项目下生成 waybill.txt，打开为三行面单信息。
▶ 关联：写文本用字节流需要自己处理换行和编码，第 20 章的 FileWriter 提供了更方便的 `write(String)`。

#### 编程题 2（基础）：歌单文件备份

**需求**：把下载的歌曲文件 `song.mp3` 备份到 `backup/song_backup.mp3`。要求用字节数组缓冲区**边读边写**（不能用 readAllBytes），并统计复制耗时。

**【参考代码】**

```java
public class SongBackup {
    public static void main(String[] args) {
        long start = System.currentTimeMillis();
        try (
            FileInputStream fis = new FileInputStream("song.mp3");
            FileOutputStream fos = new FileOutputStream("backup/song_backup.mp3")
        ) {
            byte[] buffer = new byte[1024];
            int len;
            while ((len = fis.read(buffer)) != -1) {
                fos.write(buffer, 0, len);   // 关键：只写本次读到的 len 个字节
            }
            System.out.println("备份完成");
        } catch (Exception e) {
            e.printStackTrace();
        }
        long end = System.currentTimeMillis();
        System.out.println("耗时：" + (end - start) + "ms");
    }
}
```

**【思路讲解】**
1. 歌曲是二进制文件，必须用字节流（字符流会破坏数据）；
2. 边读边写是大文件标准做法：1KB 缓冲区循环搬运，内存占用恒定；
3. `write(buffer, 0, len)` 保证最后一批不写脏数据；
4. 两个流都放进 try() 自动关闭。
▶ 关联：第 20 章会给字节流再包一层缓冲流（BufferedInputStream）进一步提速。

#### 编程题 3（中等）：快递柜存取日志（追加模式）

**需求**：快递柜每次存件、取件都要往 `locker.log` 追加一条记录（不能覆盖历史记录）。记录格式如：
```
[存件] 柜号A-12 运单SF7788 时间2026-09-05 10:20
[取件] 柜号A-12 运单SF7788 时间2026-09-05 18:05
```
请编写方法 `void log(String action, String lockerNo, String waybillNo)`，调用两次模拟一次存件、一次取件，两条记录都追加到同一文件。

**【参考代码】**

```java
public class LockerLog {
    public static void main(String[] args) {
        log("存件", "A-12", "SF7788");
        log("取件", "A-12", "SF7788");
    }

    public static void log(String action, String lockerNo, String waybillNo) {
        // 第二个参数 true：追加模式，不清空历史日志
        try (FileOutputStream fos = new FileOutputStream("locker.log", true)) {
            String time = java.time.LocalDateTime.now()
                                .toString().replace('T', ' ').substring(0, 16);
            String record = "[" + action + "] 柜号" + lockerNo
                    + " 运单" + waybillNo + " 时间" + time + "\r\n";
            fos.write(record.getBytes());
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**【思路讲解】**
1. 日志必须**追加**，构造器第二参数固定写 true；
2. 每次调用都开关一次流稍显频繁，真实项目常用一个长期打开的流或日志框架（第 21 章 Logback）；
3. 这里字节流写中文没问题（写的是 getBytes 后的字节），读取显示时才需关心编码。
▶ 关联：第 21 章的日志技术（SLF4J/Logback）就是这种需求的工业级方案。

#### 编程题 4（中等）：面单批量上传并保留原文件名

**需求**：模拟上传：把 `uploads/` 目录下的一个文件（路径由用户输入）复制到 `server/` 目录，要求目标文件名与源文件**完全一致（含后缀）**，不能写死。提示：用 `Paths.get(路径).getFileName()` 截取文件名。

**【参考代码】**

```java
import java.nio.file.Paths;
import java.util.Scanner;

public class WaybillUpload {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入要上传的文件路径：");
        String srcPath = sc.next();

        // 截取真实文件名（自动适配 \ 和 /）
        String fileName = Paths.get(srcPath).getFileName().toString();

        try (
            FileInputStream fis = new FileInputStream(srcPath);
            FileOutputStream fos = new FileOutputStream("server/" + fileName)
        ) {
            byte[] buffer = new byte[1024];
            int len;
            while ((len = fis.read(buffer)) != -1) {
                fos.write(buffer, 0, len);
            }
            System.out.println("上传完成，服务器保存为：server/" + fileName);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**【思路讲解】**
1. 目标文件名若写死成 `1.txt`，上传 .jpg/.pdf 时文件名后缀全错；用 Paths.getFileName() 从源路径取出"带后缀的文件名"，跨平台（Windows `\`、Linux `/`）都正确；
2. 复制逻辑同编程题 2；
3. 相比手写 `substring(lastIndexOf("\\"))`，Path 方案不用考虑分隔符差异。

#### 编程题 5（综合）：快递网点数据迁移（含异常保护）

**需求**：把网点旧数据目录下的 `data.dat` 迁移到新目录 `newdb/data.dat`。要求：
1. 用 try-with-resources 管理两个流；
2. 迁移完成后在控制台打印"迁移成功"；
3. 若源文件不存在等异常，打印"迁移失败：xxx"且不能让程序崩溃、不能泄漏流资源。

**【参考代码】**

```java
public class DataMigration {
    public static void main(String[] args) {
        try (
            FileInputStream fis = new FileInputStream("olddb/data.dat");
            FileOutputStream fos = new FileOutputStream("newdb/data.dat")
        ) {
            byte[] buffer = new byte[1024];
            int len;
            while ((len = fis.read(buffer)) != -1) {
                fos.write(buffer, 0, len);
            }
            System.out.println("迁移成功");
        } catch (Exception e) {
            System.out.println("迁移失败：" + e.getMessage());
        }
        // try-with-resources 保证无论成功失败，两个流都已关闭
    }
}
```

**【思路讲解】**
1. 资源全部放进 try()，即使读的过程中抛异常，两个流也会被自动 close——这正是相对 finally 写法的优势（不用判空、不会漏关）；
2. catch 捕获 Exception 兜底，程序不崩溃；
3. 注意若 newdb 目录不存在，FileOutputStream 会抛 FileNotFoundException，实际项目应先用第 18 章 File 类的 mkdirs() 建好目录。
▶ 关联：目录创建见第 18 章 File；异常处理体系见第 16 章。

#### 编程题 6（提高）：文本编码体检工具

**需求**：编写程序，读入一个文本文件的全部字节，分别用 UTF-8 和 GBK 解码成两个字符串打印出来，观察哪个不乱码，从而判断文件的真实编码。

**【参考代码】**

```java
public class EncodingCheck {
    public static void main(String[] args) {
        try (FileInputStream fis = new FileInputStream("unknown.txt")) {
            byte[] all = fis.readAllBytes();      // JDK11+ 一次读完
            String asUtf8 = new String(all, "UTF-8");
            String asGbk = new String(all, "GBK");
            System.out.println("按 UTF-8 解码：");
            System.out.println(asUtf8);
            System.out.println("按 GBK 解码：");
            System.out.println(asGbk);
            System.out.println("哪个显示正常中文，文件就是哪种编码");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**【思路讲解】**
1. 同一份字节用不同字符集解码，正确的那个显示正常中文、错误的那个乱码——直观验证"编码解码必须一致"；
2. 用 readAllBytes() 整体读取避免半个汉字问题（小文件适用）；
3. 这正是第 20 章转换流 `InputStreamReader(fis, "GBK")` 的原理：指定正确字符集解码。
▶ 关联：确认真实编码后，第 20 章用 InputStreamReader 指定 GBK 读取即可彻底解决乱码。

---

### 本章自测清单

- [ ] 能说出 ASCII/GBK/UTF-8 中英文各占几个字节
- [ ] 能区分 read()、read(byte[])、readAllBytes() 的返回值和适用场景
- [ ] 能正确写出字节数组缓冲区复制文件的循环（write(bytes,0,len)）
- [ ] 理解追加模式 true、输出流自动建文件、0 字节文件假象
- [ ] 会用 Paths.getFileName() 截取文件名
- [ ] 能说出 try-with-resources 的好处和 AutoCloseable 的作用

---

<div style="page-break-after: always;"></div>

## 第20章 字符流、缓冲流与 IO 高级流·习题精讲

> 题型：填空、选择、判断、简答、代码阅读、编程（6 道，由易到难）。
> 所有编程题场景均为原创（快递评价、歌词歌单、网点配置转码、会员存档、聊天记录、日志重定向），考点与笔记一致。

---

### 一、填空题

**1.** `FileWriter` 写出数据后，必须调用 ______ 方法刷新或调用 ______ 方法关闭，数据才会真正写入文件；其中 ______ 之后流还能继续写，______ 之后不能再写。

**【答案】** flush()；close()；flush 刷新；close 关闭

**【解析】** 字符流底层有缓冲区，数据先存在内存，不刷新/关闭文件里看不到内容。flush 把缓冲区数据冲到文件后流仍可用；close 会先 flush 再关闭，关闭后再写抛异常。

**2.** 缓冲流底层自带一个大小为 ______ 的缓冲数组（约 ______ KB），通过减少与磁盘的交互次数来提高性能；缓冲流不能单独使用，必须 ______。

**【答案】** 8192 字节/字符；8；包装（依赖）原始流

**【解析】** "读时一次囤 8KB、写时攒满 8KB 再运走"。创建缓冲流时要传入对应的原始流对象。

**3.** `BufferedReader` 新增了按行读取的方法 ______，读到文件末尾返回 ______（注意不是 -1）；`BufferedWriter` 新增了跨平台换行方法 ______。

**【答案】** readLine()；null；newLine()

**【解析】** readLine 返回 String，所以末尾标志是 null；newLine() 自动根据操作系统写 `\r\n` 或 `\n`，比手写换行符更通用。

**4.** FileReader 默认只能按 ______ 编码读取文件，读取 GBK 文件会乱码；需要用转换流 ______ 包装字节输入流并指定字符集来解决。

**【答案】** UTF-8；InputStreamReader

**【解析】** 输出方向对应的是 OutputStreamWriter（控制写出用什么编码）。

**5.** 对象要能被序列化，其类必须实现标记接口 ______；不想被序列化的敏感成员变量用 ______ 修饰，反序列化后该字段为 ______。

**【答案】** Serializable；transient；默认值（引用类型为 null）

**【解析】** Serializable 是空接口（标记接口），不实现会抛 NotSerializableException。

**6.** 序列化用 ______ 流的 writeObject 方法，反序列化用 ______ 流的 readObject 方法；readObject 返回类型是 ______，需要强转回真实类型。

**【答案】** ObjectOutputStream；ObjectInputStream；Object

---

### 二、选择题

**1.** 关于 `flush()` 和 `close()`，下列说法正确的是：

A. flush 后流就不能再写数据了
B. close 关闭流时会先自动刷新缓冲区
C. 只要调用了 write，数据立即写入文件，无需 flush/close
D. flush 会关闭底层文件

**【答案】** B

**【解析】** close() 内部会先 flush() 再释放资源；flush 只冲数据不关流，之后还能继续写。

**2.** `BufferedReader.readLine()` 读到文件末尾时返回：

A. -1　　B. 空字符串 ""　　C. null　　D. 抛出异常

**【答案】** C

**【解析】** readLine 返回字符串对象，末尾标志是 null（-1 是字节/字符 read() 方法的结束标志）。所以循环写法是 `while ((line = br.readLine()) != null)`。

**3.** 要读取一个 GBK 编码的文本文件且不乱码，正确的流包装顺序是：

A. `new BufferedReader(new FileReader("a.txt"))`
B. `new BufferedReader(new InputStreamReader(new FileInputStream("a.txt"), "GBK"))`
C. `new InputStreamReader(new FileReader("a.txt"), "GBK")`
D. `new FileReader("a.txt", "GBK")`

**【答案】** B

**【解析】** 思路：先拿原始字节输入流 FileInputStream → 用 InputStreamReader 按文件真实编码 GBK 转成字符流 → 再包 BufferedReader 用 readLine。FileReader 写死 UTF-8，无法指定编码。

**4.** 会员类 `Member implements Serializable` 中 `private transient String password;`，序列化后再反序列化，password 的值是：

A. 原密码　　B. null　　C. 空字符串 ""　　D. 反序列化直接报错

**【答案】** B

**【解析】** transient 字段不参与序列化，反序列化时给默认值；String 是引用类型，默认 null（若是 int 则为 0）。

**5.** 打印流执行 `ps.println(97); ps.write(97);`，文件中对应内容是：

A. 97 和 97　　B. a 和 a　　C. 97 和 a　　D. a 和 97

**【答案】** C

**【解析】** println(97) 把 97 当成数据"打印成文本"，写出 "97"；write(97) 写的是字节 97，按码表显示为字符 a。

**6.** 关于数据流 DataOutputStream/DataInputStream，下列说法错误的是：

A. 可以把数据连同类型一起写出
B. 属于字节流
C. 读取顺序可以和写入顺序不同，会自动匹配类型
D. 读取顺序和类型必须与写入时一一对应

**【答案】** C

**【解析】** 数据流按写入顺序存储，读取必须顺序、类型完全一致，否则读乱或抛 EOFException。

**7.** 下列关于缓冲流的说法，错误的是：

A. BufferedInputStream 包装 InputStream
B. 缓冲流可以脱离原始流单独 new 出来使用
C. 缓冲流靠 8KB 缓冲区减少磁盘交互
D. BufferedReader 比 FileReader 多了 readLine() 功能

**【答案】** B

**【解析】** 缓冲流是处理流，构造方法必须传入一个原始流，不能单独使用。

---

### 三、判断题

**1.** 字符流可以用来读取图片、视频等二进制文件。（　）

**【答案】** 错误

**【解析】** 字符流只能操作纯文本文件。图片视频必须用字节流，字符流按字符解码二进制数据会破坏内容。

**2.** `close()` 方法在关闭流之前会先自动刷新缓冲区。（　）

**【答案】** 正确

**【解析】** 所以正常关闭后数据不会丢；但如果只 write 既不 flush 也不 close 就退出程序，缓冲区数据会丢失。

**3.** 被 static 修饰的静态变量和被 transient 修饰的变量都不会被序列化。（　）

**【答案】** 正确

**【解析】** 序列化保存的是对象的实例状态；静态变量属于类不属于对象，不随对象序列化；transient 是显式标记实例字段不参与序列化。

**4.** 缓冲流之所以更快，是因为它改变了数据内容、压缩了文件。（　）

**【答案】** 错误

**【解析】** 缓冲流不改变数据，只是通过 8KB 缓冲区"批量读写"减少与磁盘交互的次数来提速。

**5.** FileWriter 写出文本时会自动换行。（　）

**【答案】** 错误

**【解析】** 不会自动换行，需手动写 `"\r\n"`（Windows）/`"\n"`，或用 BufferedWriter 的 newLine()。

---

### 四、简答题

**1.** 为什么字符流读中文不会乱码，而字节流逐字节读中文会乱码？FileWriter 写出后为什么要 flush？

**【答案】**
- 字节流 read() 每次只读 1 个字节，UTF-8 汉字占 3 字节，被拆成三次读、各当成一个字符，出现乱码；字符流以字符为单位，底层自动按编码把字节拼成完整字符，所以不乱码。
- 字符流写出时数据先进内存缓冲区，没有立即落盘；flush() 把缓冲区数据强制写入文件，close() 也会先 flush。不刷新不关闭，文件里看不到内容。

**【解析】** 字符流 = 字节流 + 编码解码，这是它与字节流的本质区别。
▶ 关联：编码规则（UTF-8 汉字 3 字节）来自第 19 章。

**2.** 缓冲流为什么能提高读写性能？BufferedReader/BufferedWriter 各新增了什么方法？

**【答案】**
- 原理：缓冲流内部维护 8KB（8192）缓冲数组。读时一次性从磁盘读 8KB 囤起来，程序从内存数组取；写时先攒到数组，满了再一次性写盘。大大减少了与磁盘的交互次数（磁盘 IO 是速度瓶颈）。
- BufferedReader 新增 `readLine()`：读一行文本，末尾返回 null。
- BufferedWriter 新增 `newLine()`：写一个跨平台换行符。

**3.** 一个类的对象想被序列化，需要满足哪些条件？序列化有哪些注意事项？

**【答案】**
- 类必须实现 `java.io.Serializable` 标记接口（空接口），否则抛 NotSerializableException；
- 成员变量的类型也建议可序列化（基本类型和 String 等都已实现）；
- 敏感字段用 `transient` 修饰则不序列化，反序列化后为默认值；
- 静态变量不随对象序列化；
- 建议手动声明 `serialVersionUID`，否则类结构改动后反序列化会因版本号不一致报错。

**【解析】** 标记接口（Serializable、Cloneable）没有方法，只用于给 JVM"打标签"。

---

### 五、代码阅读题

**1.** 下面代码希望把三行评价写入文件，运行后打开文件可能看到什么？问题出在哪？

```java
FileWriter fw = new FileWriter("review.txt");
fw.write("快递员很准时");
fw.write("包装完好");
fw.write("态度热情");
// 没有调用任何刷新或关闭
```

**【答案】** 文件可能是空的（内容还在缓冲区没落盘）；即使有内容也全挤在一行。两个问题：① 没有 flush/close，数据可能丢失；② 没有写换行符，三句连成一行。

**【解析】** 正确做法：每句后 `fw.write("\r\n")` 换行，最后 `fw.close()`（或用 try-with-resources 自动关闭+刷新）。

**2.** 阅读序列化/反序列化代码，写出反序列化后打印的结果：

```java
class Member implements Serializable {
    String name;
    int age;
    transient String vipCode;
    static String site = "北京站";
    // 构造器：name, age, vipCode
}

Member m = new Member("王五", 28, "VIP888");
ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream("m.txt"));
oos.writeObject(m);
// 之后修改：Member.site = "上海站"; 再反序列化
ObjectInputStream ois = new ObjectInputStream(new FileInputStream("m.txt"));
Member back = (Member) ois.readObject();
System.out.println(back.name + "," + back.age + "," + back.vipCode + "," + back.site);
```

**【答案】** `王五,28,null,上海站`

**【解析】**
- name、age 正常序列化恢复：王五、28；
- vipCode 被 transient 修饰不参与序列化，反序列化为 null；
- site 是静态变量，属于类不随对象存储；反序列化读到的是当前方法区里静态变量的值"上海站"（序列化后被修改过）。

**3.** 下面代码用 BufferedReader 读文件，循环有什么问题？

```java
String line = br.readLine();
while (line != null) {
    System.out.println(line);
}
```

**【答案】** 死循环。readLine() 只在循环外调用了一次，读到第一行后 line 永远是那一行（非 null），循环体里没有再次读取，会无限打印第一行。

**【解析】** 正确写法是把读取放进循环条件：`while ((line = br.readLine()) != null) { System.out.println(line); }`，每轮重新读一行。

**4.** 数据流按如下顺序写入，读取时哪一行会出问题？

```java
dos.writeInt(100);
dos.writeBoolean(false);
dos.writeDouble(3.14);
// 读取代码：
System.out.println(dis.readInt());
System.out.println(dis.readDouble());   // ①
System.out.println(dis.readBoolean());  // ②
```

**【答案】** ① 处出错（读到的是用 boolean 写入的字节却按 double 解析，数据错乱，后续全乱，可能抛异常）。

**【解析】** 数据流必须按写入顺序、类型一一对应读取：先 readInt、再 readBoolean、最后 readDouble。顺序错了，字节按错误类型解析，结果全错。

---

### 六、编程题

#### 编程题 1（基础）：快递员评价录入

**需求**：把用户对快递员的三条评价逐行写入 `review.txt`（用 FileWriter），每条评价占一行；要求写完后数据确实落盘。三条评价：
```
准时送达，赞
包装完好
派件态度热情
```

**【参考代码】**

```java
public class ReviewWriter {
    public static void main(String[] args) {
        try (FileWriter fw = new FileWriter("review.txt")) {
            fw.write("准时送达，赞");
            fw.write("\r\n");
            fw.write("包装完好");
            fw.write("\r\n");
            fw.write("派件态度热情");
            fw.write("\r\n");
            System.out.println("评价已保存");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**【思路讲解】**
1. FileWriter 的 `write(String)` 可以直接写字符串，比字节流方便（不用 getBytes）；
2. 字符流不自动换行，手动写 `\r\n`；
3. 放进 try-with-resources，关闭时自动 flush，保证落盘。
▶ 关联：相比第 19 章字节流写字面单，字符流写中文文本更直接。

#### 编程题 2（中等）：歌词本整理（复制 + 转大写 + 加行号）

**需求**：把英文歌词文件 `lyrics.txt` 复制为 `lyrics_numbered.txt`，要求：所有字母转成大写，并且每行开头加上行号（格式 `1.`、`2.`…）。用 BufferedReader/BufferedWriter 完成。

**【参考代码】**

```java
public class LyricsFormatter {
    public static void main(String[] args) {
        try (
            BufferedReader br = new BufferedReader(new FileReader("lyrics.txt"));
            BufferedWriter bw = new BufferedWriter(new FileWriter("lyrics_numbered.txt"))
        ) {
            String line;
            int num = 1;
            while ((line = br.readLine()) != null) {
                bw.write(num + "." + line.toUpperCase());
                bw.newLine();
                num++;
            }
            System.out.println("歌词本整理完成");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**【思路讲解】**
1. readLine() 按行读（不含换行符），处理完用 newLine() 写回换行；
2. toUpperCase() 转大写，行号用计数器 num 拼接；
3. readLine 返回 null 结束循环，这是字符缓冲流最常用的模板。
▶ 关联：String 的 toUpperCase 是第 10 章常用 API。

#### 编程题 3（中等）：网点配置文件转码（GBK → UTF-8）

**需求**：老系统导出的网点配置 `config_gbk.txt` 是 GBK 编码，用普通 FileReader 读会乱码。请用转换流正确读取，并以 UTF-8 写出到 `config_utf8.txt`，完成转码。

**【参考代码】**

```java
public class ConfigConverter {
    public static void main(String[] args) {
        try (
            // 读：字节流 → 按 GBK 转成字符流 → 缓冲行读
            BufferedReader br = new BufferedReader(
                    new InputStreamReader(new FileInputStream("config_gbk.txt"), "GBK"));
            // 写：字节流 → 按 UTF-8 转成字符流 → 缓冲写（FileWriter 默认就是 UTF-8）
            BufferedWriter bw = new BufferedWriter(
                    new OutputStreamWriter(new FileOutputStream("config_utf8.txt"), "UTF-8"))
        ) {
            String line;
            while ((line = br.readLine()) != null) {
                bw.write(line);
                bw.newLine();
            }
            System.out.println("转码完成");
        } catch (Exception e) {
            e.printStackTrace();
        }
}
```

**【思路讲解】**
1. 转换流是"字节流 ↔ 字符流"的桥梁：InputStreamReader 把字节输入流按指定字符集解码成字符；OutputStreamWriter 把字符按指定字符集编码成字节输出；
2. 读 GBK 文件必须在 InputStreamReader 构造时传 "GBK"，这是解决乱码的关键；
3. 转码本质：用 GBK 解码读入 → 用 UTF-8 编码写出。
▶ 关联：乱码根源（编码解码不一致）见第 19 章。

#### 编程题 4（中等）：聊天记录按天追加

**需求**：聊天程序每收到一条消息，就把消息追加写入 `chat.log`（不能覆盖之前的记录），每条一行、带序号。用缓冲字符流 + 追加模式实现，写出一个 `appendChat(String msg)` 方法并模拟 3 条消息。

**【参考代码】**

```java
public class ChatLogger {
    public static void main(String[] args) {
        appendChat("你好，快递到哪了？");
        appendChat("已到达附近网点");
        appendChat("好的谢谢");
    }

    public static void appendChat(String msg) {
        // FileWriter 第二参数 true = 追加；再包缓冲流
        try (
            FileWriter fw = new FileWriter("chat.log", true);
            BufferedWriter bw = new BufferedWriter(fw)
        ) {
            bw.write(msg);
            bw.newLine();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**【思路讲解】**
1. 追加模式靠 FileWriter/FileOutputStream 构造参数 true，否则每次覆盖历史记录；
2. 缓冲流包在追加流外面，既保换行 newLine 又有性能；
3. try-with-resources 每次调用自动 flush+close，保证每条消息落盘。
▶ 关联：第 21 章的 Logback 日志框架就是这类需求的专业方案，还带时间戳和级别。

#### 编程题 5（综合）：会员档案序列化存档与读取

**需求**：
1. 定义会员类 `Member`（姓名、手机号、积分、登录密码），实现序列化接口，密码不参与序列化；
2. 把一个会员对象写入 `member.dat`（序列化）；
3. 再从文件读出该对象并打印（反序列化）。

**【参考代码】**

```java
import java.io.*;

class Member implements Serializable {
    private String name;
    private String phone;
    private int points;
    private transient String password;   // 密码不参与序列化

    public Member(String name, String phone, int points, String password) {
        this.name = name;
        this.phone = phone;
        this.points = points;
        this.password = password;
    }

    @Override
    public String toString() {
        return "Member{name='" + name + "', phone='" + phone
                + "', points=" + points + ", password='" + password + "'}";
    }
}

public class MemberArchive {
    public static void main(String[] args) {
        // 序列化：对象 → 文件
        try (ObjectOutputStream oos =
                     new ObjectOutputStream(new FileOutputStream("member.dat"))) {
            Member m = new Member("李雷", "13800001111", 3600, "secret123");
            oos.writeObject(m);
            System.out.println("会员档案已存档");
        } catch (Exception e) {
            e.printStackTrace();
        }

        // 反序列化：文件 → 对象
        try (ObjectInputStream ois =
                     new ObjectInputStream(new FileInputStream("member.dat"))) {
            Member back = (Member) ois.readObject();   // 返回 Object，需强转
            System.out.println("读取存档：" + back);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**【思路讲解】**
1. 类 implements Serializable 才能序列化（标记接口，无方法）；
2. password 用 transient 修饰，反序列化后为 null，保护敏感信息；
3. writeObject 写对象、readObject 读对象（返回 Object 要强转 Member）；
4. 对象流以"整个对象"为单位，比逐字段读写方便，常用于对象缓存、网络传输对象。
▶ 关联：第 22 章网络编程中对象也可通过 Socket 流直接传输。

#### 编程题 6（提高）：批量打印快递单（打印流 + 输出重定向）

**需求**：批量生成 5 张快递单文本，每张含单号和收件人。要求：
1. 用 PrintWriter 打印（利用 println 方便输出）；
2. 把原本输出到控制台的内容重定向到文件 `printjob.txt`（用 System.setOut）。

**【参考代码】**

```java
public class WaybillPrinter {
    public static void main(String[] args) {
        try (PrintStream ps = new PrintStream("printjob.txt")) {
            // 把系统标准输出重定向到打印流：之后所有 System.out 内容写入文件
            System.setOut(ps);
            String[] receivers = {"张三", "李四", "王五", "赵六", "孙七"};
            for (int i = 1; i <= 5; i++) {
                System.out.println("====== 快递单 " + i + " ======");
                System.out.println("单号：SF" + (100000 + i));
                System.out.println("收件人：" + receivers[i - 1]);
                System.out.println("------------------");
            }
            System.out.println("全部打印任务已生成到 printjob.txt");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**【思路讲解】**
1. 打印流 PrintStream/PrintWriter 的特点是"打印啥就是啥"，println 直接输出文本，不用管字节/字符转换；
2. `System.setOut(打印流)` 把标准输出重定向，此后 System.out.println 的内容不再显示在控制台，而是写入文件——这正是早期"把控制台日志存文件"的做法；
3. 打印流只有输出流没有输入流。
▶ 关联：项目上线后用日志框架（第 21 章）替代这种手工重定向，更规范。

---

### 本章自测清单

- [ ] 会用 FileReader/FileWriter 读写文本，记得 flush/close 和换行
- [ ] 能说出缓冲流 8KB 原理，会用 readLine()/newLine()
- [ ] 会用 InputStreamReader/OutputStreamWriter 指定字符集解决 GBK 乱码
- [ ] 理解 println 与 write 的区别、System.setOut 重定向
- [ ] 掌握序列化三要素：Serializable、transient、readObject 强转
- [ ] 知道数据流读取顺序必须与写入一致

---

<div style="page-break-after: always;"></div>

## 第21章 特殊文件、日志技术与多线程·习题精讲

> 本章三大板块：Properties 属性文件与 XML 解析（Dom4j）、Logback 日志框架、多线程（三种创建方式、线程安全与同步、等待唤醒、线程池、六种状态）。
> 做题前先回忆本章主线：**配置文件解决"参数硬编码"问题，日志解决"println 无法持久化"问题，多线程解决"并发执行效率"问题——而多线程一引入共享数据，就必须用同步保证安全。**

---

### 一、填空题

**1.** Properties 本质上是一个 ______ 集合，但它的核心作用是代表属性文件；用 ______ 方法把属性文件加载进内存，用 ______ 方法根据键取值，把键值对写回文件用 ______ 方法。

**【答案】** Map；`load(Reader/InputStream)`；`getProperty(String key)`；`store(Writer/OutputStream, 注释)`

**【解析】** Properties 是 Map 接口的实现类，键值都是 String。读取流程固定为"new Properties() → load(文件流) → getProperty(键)"；写出用 store，默认**覆盖**原文件。属性文件中键不能重复、值可以重复，行尾不要加分号或多余空格（会被算进值里）。
▶ 关联：第17章《Set与Map集合》讲 Map 体系，Properties 就是 Hashtable 的子类；第20章《字符流与IO综合》中 Properties 常配合文件流使用。

**2.** 使用 Dom4j 解析 XML 时，______ 是解析器对象，______ 代表整个 XML 文档，______ 代表标签（元素），______ 代表属性；获取根元素用 ______ 方法。

**【答案】** `SAXReader`；`Document`；`Element`；`Attribute`；`getRootElement()`

**【解析】** DOM 思想把 XML 的每个组成部分都看成对象：解析流程是 `new SAXReader() → read(路径) 得到 Document → getRootElement() 得到根 Element → elements()/element() 取子元素 → getText()/elementText() 取文本、attributeValue() 取属性值。
▶ 关联：第23章《单元测试、反射、注解与代理》中反射也是"把类的组成部分看成对象"（Class/Constructor/Method/Field），思想一脉相承。

**3.** Logback 的五个日志级别从低到高依次是 ______ < ______ < info < ______ < error；记录规则是：只有级别 ______ 配置文件中设置的级别，才会被记录。

**【答案】** trace；debug；warn；大于或等于

**【解析】** 例如 `<root level="info">` 时，trace、debug 不输出，info/warn/error 输出；设为 warn 时只剩 warn、error。级别是"阈值"不是"开关"——高于阈值的全部放行。
▶ 关联：日志框架基于 **SLF4J** 门面接口实现（Logback 是 SLF4J 的实现），这种"接口+实现"的解耦思想同第9章《面向对象高级（下）》的接口多态。

**4.** Logback 配置文件 logback.xml 必须放在 ______ 目录下；日志对象通过 `LoggerFactory.______(类名.class)` 获取；输出日志到文件用 ______ appender，输出到控制台用 ______ appender。

**【答案】** src；`getLogger`；FILE；CONSOLE

**【解析】** 三个 jar 包（slf4j-api、logback-core、logback-classic）放入 lib 并 Add as Library 后，logback.xml 必须复制到 **src 目录**下才能被自动加载，放别处不生效。Logger 一般声明为 `public static final Logger LOG = LoggerFactory.getLogger(当前类.class);`。
▶ 关联：第23章注解 JUnit 的 `@Test` 方法也要求在特定目录/规范下才被框架识别，框架配置都有"约定优于配置"的位置要求。

**5.** Java 创建线程的三种方式：① ______（重写 run 方法，缺点是不能再继承其他类）；② ______（任务对象交给 Thread，扩展性强但无返回值）；③ ______ + ______（有返回值，通过 get() 取结果）。

**【答案】** 继承 Thread 类；实现 Runnable 接口；实现 Callable 接口；FutureTask

**【解析】** 方式三的 call() 方法有返回值且可以抛出异常，Callable 对象要先包装成 FutureTask，再交给 Thread，最后 `futureTask.get()` 取结果——get() 有**阻塞**特点，线程没执行完当前代码会等。
▶ 关联：Runnable、Callable 都是接口，第9章学过接口；Lambda 简化 Runnable 写法用到第15章《Lambda算法与正则》的函数式接口知识。

**6.** 线程的默认名称格式是 ______；获取当前正在执行的线程对象用 ______ 方法；让当前线程睡眠指定毫秒数用 ______ 方法；让一个线程等待另一个线程执行完毕用 ______ 方法。

**【答案】** `Thread-索引`（如 Thread-0）；`Thread.currentThread()`；`Thread.sleep(毫秒)`；`join()`

**【解析】** 给线程起名可以用 setName() 或 `new Thread(任务, "名字")` 构造器。注意 sleep 是静态方法、操作的是"当前线程"；join 只能**间接**影响顺序（让某线程先跑完），**没有任何方法能强行控制线程的整体执行先后**，CPU 调度抢占式。
▶ 关联：第22章《网络编程》的多客户端服务器中，主线程 accept 到一个客户端就 new 一条线程处理，用的正是本章的线程技术。

**7.** 线程同步的三种方式是 ______、______、______；其中 Lock 是显式锁，需要手动调用 ______ 加锁、______ 释放锁（建议放在 finally 中）。

**【答案】** 同步代码块（synchronized(锁对象){}）；同步方法（synchronized 修饰方法）；Lock 锁（ReentrantLock）；`lock()`；`unlock()`

**【解析】** 同步代码块/方法是隐式锁，自动加锁释放；Lock 更灵活可控。实例同步方法的隐式锁是 **this**，静态同步方法的隐式锁是 **类名.class**。
▶ 关联：第17章中边遍历边删除集合会触发并发修改异常，本质也是"多个操作方修改共享数据"，和线程安全同源。

**8.** ThreadPoolExecutor 构造器的七个参数依次是：核心线程数、______、临时线程空闲时间、时间单位、______、线程工厂、______；默认拒绝策略是 ______。

**【答案】** 最大线程数；任务队列（阻塞队列 BlockingQueue）；拒绝策略；AbortPolicy

**【解析】** 临时线程创建条件：核心线程全忙 + 队列已满 + 线程数未达 maximumPoolSize。拒绝时机：核心和临时线程全忙 + 队列也满。四种策略：AbortPolicy（抛异常，默认）、CallerRunsPolicy（由提交任务的线程自己 run）、DiscardPolicy（静默丢弃，不推荐）、DiscardOldestPolicy（丢最老任务）。
▶ 关联：线程池中线程执行的任务常用 Runnable/Callable，配合第15章 Lambda 写法 `executor.execute(() -> {...})`。

**9.** Java 线程的六种状态（定义在 Thread.State 枚举中）：NEW、______、BLOCKED、______、TIMED_WAITING、TERMINATED；其中调用 wait() 无参方法会进入 ______ 状态，调用 sleep(毫秒) 进入 ______ 状态。

**【答案】** RUNNABLE；WAITING；WAITING；TIMED_WAITING

**【解析】** NEW 是创建未 start；RUNNABLE 是可运行（可能正在跑也可能在等 CPU 时间片）；BLOCKED 是等 synchronized 锁；WAITING 是无限等待（wait()/join()）；TIMED_WAITING 是计时等待（sleep(ms)/wait(ms)）；TERMINATED 是 run 结束。注意 wait 被唤醒后**若锁被抢走会先进 BLOCKED**，拿到锁才回 RUNNABLE。
▶ 关联：第3.8 节等待唤醒中 wait 释放锁、sleep 不释放锁，这个区别直接决定状态流转路径。

**10.** wait()、notify()、notifyAll() 是 ______ 类的方法，调用时必须在 ______ 代码块中、并且由 ______ 来调用。

**【答案】** Object；同步（synchronized）；锁对象

**【解析】** 任何对象都能当锁，所以等待唤醒方法定义在 Object 中。不在同步块中调用 wait 会抛 IllegalMonitorStateException。wait() 会**释放锁并等待**，被 notifyAll 唤醒后重新抢锁。
▶ 关联：sleep 定义在 Thread 中且不释放锁，wait 定义在 Object 中且释放锁——这是高频面试对比题。

---

### 二、选择题

**1.** 对一个已经调用过 start() 的线程对象再次调用 start()，结果是？

A. 正常启动第二条线程
B. 抛出 IllegalThreadStateException
C. 编译报错
D. 什么都不发生

**【答案】** B

**【解析】** 一个 Thread 对象只能 start 一次：start 后线程状态从 NEW 变为 RUNNABLE，再次 start 时状态已不是 NEW，JVM 抛出 IllegalThreadStateException。想再跑一次任务要 new 新的 Thread 对象。
▶ 关联：线程六种状态（本章 3.11）中 NEW 是"一次性"的，TERMINATED 之后也不能复活。

**2.** 在线程任务类中直接调用 `run()` 方法而不是 `start()`，下列说法正确的是？

A. 会新开一条线程执行 run
B. run 被当作普通方法在当前线程同步执行，相当于单线程
C. 编译报错
D. 会抛运行时异常

**【答案】** B

**【解析】** start() 的作用是向 JVM 注册一条新线程、由 JVM 在合适时机调用 run()；直接调 run() 只是普通对象的普通方法调用，代码在当前线程（如 main）里顺序执行，没有并发效果。
▶ 关联：这是多线程第一高频面试题，配合"主线程任务不要放在 start 之前"一起理解。

**3.** logback.xml 中 `<root level="warn">`，则下列日志语句会输出的有？
`LOG.trace("a"); LOG.debug("b"); LOG.info("c"); LOG.warn("d"); LOG.error("e");`

A. a b c d e
B. d e
C. c d e
D. e

**【答案】** B

**【解析】** 记录规则：级别 ≥ 配置级别才输出。warn 阈值下，trace/debug/info 全部被过滤，只有 warn(d)、error(e) 输出。
▶ 关联：生产环境通常设 info 或 warn，调试时设 debug/trace——不改代码只改配置文件，这正是日志技术相比 println 的核心优势（本章 2.1）。

**4.** 关于 Properties 属性文件，下列说法**错误**的是？

A. 文件中每一行是一个键值对，键和值用 `=` 隔开
B. 键不能重复，值可以重复
C. 行尾习惯性加个分号不影响使用
D. `#` 开头的行是注释

**【答案】** C

**【解析】** 行尾的分号、空格会被当成**值的一部分**原样读入，例如 `age=18;` 读出来是 `"18;"`，后续转数字就会出错。属性文件里不要写分号。
▶ 关联：第14章《常用API》中 Integer.parseInt 遇到非数字字符串会抛 NumberFormatException，这个坑常和 Properties 读取连在一起考。

**5.** 关于 XML 语法，下列说法正确的是？

A. 一个 XML 文件可以有多个根标签
B. 标签可以不成对出现，只要名字写对
C. XML 中只能有一个根标签，标签必须正确嵌套
D. 标签名必须用 XML 规定好的关键字

**【答案】** C

**【解析】** XML 可扩展指标签名可以自定义（`<locker>`、`<package>` 都行），但语法严格：单根标签、标签成对、正确嵌套；`<`、`&` 等特殊字符要用实体字符（`&lt;`、`&amp;`）或放进 CDATA 区。
▶ 关联：第22章网络编程中 XML 可作为网络传输的数据格式（淘宝查顺丰运单的例子）。

**6.** 关于 Callable + FutureTask 方式与 Runnable 方式的区别，正确的是？

A. Callable 的 call() 方法没有返回值
B. Runnable 的 run() 方法可以声明抛出 Exception
C. Callable 的 call() 方法有返回值，且可以声明抛出异常
D. FutureTask 的 get() 方法会立即返回 null

**【答案】** C

**【解析】** Runnable.run() 无返回值、不能声明受检异常；Callable.call() 有泛型返回值、可以 throws Exception。get() 是**阻塞**的：线程没跑完，当前线程停在 get() 处等待。
▶ 关联：第14章包装类的泛型参数 `<String>` 写法与第13章泛型相通；线程池提交 Callable 用 submit() 返回 Future（本章 3.9.4）。

**7.** 关于 sleep() 和 wait()，下列说法**错误**的是？

A. sleep 是 Thread 类的静态方法，wait 是 Object 类的方法
B. sleep 睡眠期间不释放锁，wait 等待期间会释放锁
C. sleep 时间到了自动继续；wait 需要被 notify/notifyAll 唤醒
D. wait() 可以在任何地方直接调用

**【答案】** D

**【解析】** wait() 必须在 synchronized 同步块中、由锁对象调用，否则抛 IllegalMonitorStateException——因为 wait 的语义是"释放这把锁并等待"，没有锁就无从释放。sleep 则不需要锁，任何地方都能睡。
▶ 关联：wait 释放锁 → 状态进 WAITING；sleep 不释放锁 → 进 TIMED_WAITING（本章状态转换图）。

**8.** 线程池配置：核心线程 3、最大线程 5、任务队列容量 5，拒绝策略为默认策略。一次提交 12 个任务（每个任务执行很久），下列说法正确的是？

A. 12 个任务全部正常执行
B. 3 个核心线程执行，5 个进队列，2 个开临时线程，剩下 2 个触发拒绝策略抛异常
C. 直接创建 12 条线程
D. 任务全部进队列排队

**【答案】** B

**【解析】** 任务调度顺序：核心线程（3 个）→ 任务队列（5 个，累计 8）→ 临时线程（最大 5-核心 3 = 2 个，累计 10）→ 仍有剩余（12-10=2）触发拒绝策略。默认 AbortPolicy 抛 RejectedExecutionException。
▶ 关联：若换成 CallerRunsPolicy，第 11、12 个任务会由提交任务的 main 线程亲自执行；DiscardPolicy 则静默丢弃。这是线程池最高频的计算题。

**9.** 关于同步锁对象的选择，正确的是？

A. 只要对象唯一，随便 new 一个 Object 当锁就最安全
B. 锁对象可以每次进入方法时 new 一个
C. 建议用共享资源本身作为锁；实例方法可用 this，静态场景用 类名.class
D. 字符串字面量可以随便当锁，没有任何风险

**【答案】** C

**【解析】** 锁必须所有线程共享同一个对象（每次 new 一把锁等于没锁）；但也不能随便选无关的唯一对象——锁范围过大会拖累无关线程，建议直接用共享资源当锁。实例同步方法隐式锁是 this（多任务对象时锁不住），静态同步方法隐式锁是类名.class（全局唯一）。
▶ 关联：第8/11章权限与 static 知识解释了为什么类名.class 全局唯一（字节码对象加载一次）。

**10.** Dom4j 解析时，根元素下有 3 个同名 `<package>` 子标签，调用 `root.element("package")` 获取到的是？

A. 全部 3 个
B. 第 1 个
C. 最后 1 个
D. 抛异常

**【答案】** B

**【解析】** element("标签名") 获取单个子元素，多个同名时**默认取第一个**；要取全部用 elements() 得到 List 再遍历，或 elements("package") 取同名全部。
▶ 关联：第16章 List 集合的 get(索引) 操作在这里直接使用，解析结果常封装进 ArrayList<JavaBean>（第10章 JavaBean 规范）。

---

### 三、判断题

**1.** 调用线程对象的 run() 方法就可以启动一条新线程。（　）

**【答案】** ✗ 错误

**【解析】** 启动新线程必须调 start()，由 JVM 调用底层资源创建线程并回调 run()；直接调 run() 只是当前线程里的普通方法调用，串行执行。
▶ 关联：选择题第 2 题同源，多线程入门第一大误区。

**2.** 线程在 synchronized 同步块中调用 sleep() 睡眠时，会释放手中的锁。（　）

**【答案】** ✗ 错误

**【解析】** sleep 抱着锁睡觉——睡眠期间不释放任何锁，其他线程仍然进不来；会释放锁的是 wait()。这也是 sleep 和 wait 最核心的区别之一。
▶ 关联：所以 sleep 放在同步块里要谨慎，长时间睡眠会让其他线程干等；wait 则用于等待唤醒协作（本章 3.8）。

**3.** 同步代码块的锁对象只要是唯一的就行，随便 new 一个与业务无关的 Object 也完全没问题。（　）

**【答案】** ✗ 错误

**【解析】** 笔记明确指出：锁对象必须唯一，但**不能随便选一个无关的唯一对象**——锁范围过大可能影响其他无关线程的执行，建议直接用共享资源作为锁对象。
▶ 关联：锁的粒度是并发编程的重要权衡：锁太粗影响并发效率，锁太细又锁不住。

**4.** 线程池的核心线程数设置得越大，程序效率就越高。（　）

**【答案】** ✗ 错误

**【解析】** 线程数过多会导致 CPU 频繁切换上下文、内存占用增大，反而降低性能；线程池的意义之一正是**控制**并发线程数量。合理线程数要根据任务类型（CPU 密集型接近核数，IO 密集型可更多）和压测结果确定。
▶ 关联：本章 3.10 并发与并行——CPU 核心数有限，线程靠轮询并发执行，线程太多切换成本吞噬收益。

**5.** wait() 方法可以在普通方法中直接调用，不需要 synchronized。（　）

**【答案】** ✗ 错误

**【解析】** wait/notify/notifyAll 必须在同步块中由锁对象调用，否则抛 IllegalMonitorStateException。因为它们的语义就是操作"锁"：wait 释放锁并等待，notify 唤醒等待这把锁的线程。
▶ 关联：第16章异常体系中 IllegalMonitorStateException 是运行时异常，不强制捕获，但一写就错。

**6.** logback.xml 配置文件放在项目根目录下就能被 Logback 自动加载。（　）

**【答案】** ✗ 错误

**【解析】** logback.xml 必须放在 **src 目录**下（编译后会复制到类路径根），放项目根目录或其他位置框架识别不到，日志配置不生效。
▶ 关联：第23章 JUnit 等框架同样依赖类路径（classpath）加载资源，这是 Java 框架的通用约定。

**7.** XML 文件中 `<age>18 < 20</age>` 这样写完全合法。（　）

**【答案】** ✗ 错误

**【解析】** 裸写的 `<` 会被解析器误认为标签开头导致解析错误，必须写成实体字符 `18 &lt; 20`，或整段放进 `<![CDATA[ ... ]]>` 数据区。
▶ 关联：CDATA 区常用于在 XML 中嵌入代码片段；实体字符五个（&lt; &gt; &amp; &apos; &quot;）要记牢。

---

### 四、简答题

**1.** 请列表对比三种线程创建方式的步骤、优点和缺点。

**【答案】**

| 方式 | 步骤 | 优点 | 缺点 |
| --- | --- | --- | --- |
| 继承 Thread 类 | 子类继承 Thread → 重写 run() → new 对象 → start() | 编码最简单 | 已继承 Thread，**不能再继承其他类**，扩展性差 |
| 实现 Runnable 接口 | 实现 Runnable 重写 run() → new 任务对象 → new Thread(任务) → start() | 只实现接口，**可继续继承类、实现接口**，扩展性强；同一任务对象可交多个线程共享 | 需多建任务对象；run() **无返回值** |
| Callable + FutureTask | 实现 Callable\<T\> 重写 call() → 包装成 FutureTask → 交给 Thread → start() → get() 取结果 | 扩展性强，**有返回值**，call 可抛异常 | 编码稍复杂；get() 阻塞 |

**【解析】** 记忆主线：Thread 方式胜在简单、Runnable 胜在解耦（任务和线程分离）、Callable 胜在有结果。实战中 Runnable/Lambda 最常用，需要返回结果（如子线程算总和）用 Callable。
▶ 关联：Runnable 和 Callable 都是函数式接口（只有一个抽象方法），所以都能用第15章的 Lambda 简化：`new Thread(() -> {...}).start()`。

**2.** 线程安全问题产生的条件是什么？有哪三种解决方式？锁对象如何选择？

**【答案】**

产生的三个条件（**同时满足**才会出问题）：
1. 存在多个线程同时执行；
2. 同时访问同一个共享资源；
3. 存在修改该共享资源的操作。

三种解决方式：
1. **同步代码块**：`synchronized(锁对象){ 核心代码 }`，锁范围最小、最灵活；
2. **同步方法**：synchronized 修饰整个方法，写法简洁；实例方法锁是 this，静态方法锁是 类名.class；
3. **Lock 锁**：`ReentrantLock` 对象，手动 lock()/unlock()，unlock 放 finally 保证异常也释放。

锁对象选择：必须是多线程共享的同一个对象；建议直接用**共享资源本身**当锁；实例方法中可用 this（前提多线程用同一任务对象）；静态场景用 类名.class（全局唯一）。

**【解析】** 同步思想是"化并发为串行"：加锁后同一时刻只有一个线程操作共享资源，牺牲少量效率换取数据正确。典型案例：夫妻两人同时取同一个账户 10 万，不加锁可能各取走 10 万、余额变 -10 万。
▶ 关联：第17章 Collections.synchronizedXxx、第21章线程池中的共享任务，凡是"多线程+共享+修改"三要素齐备就要考虑同步；第16章并发修改异常是单线程版的"边读边改"问题。

**3.** 请从所属类、是否释放锁、使用前提、唤醒方式四个角度对比 sleep() 和 wait()。

**【答案】**

| 对比项 | sleep(long ms) | wait() / wait(ms) |
| --- | --- | --- |
| 所属类 | Thread 类的静态方法 | Object 类的方法 |
| 是否释放锁 | **不释放锁**（抱着锁睡） | **释放锁**（交出锁并等待） |
| 使用前提 | 任意位置都可调用 | 必须在 synchronized 同步块中、由锁对象调用 |
| 醒来方式 | 睡眠时间到自动醒来 | 无参 wait 需 notify/notifyAll 唤醒；带参 wait 超时自动醒或被提前唤醒 |
| 用途 | 暂停当前线程一会儿 | 线程间协作（生产者消费者等待唤醒） |

**【解析】** 两者都让线程暂停（sleep 进 TIMED_WAITING，无参 wait 进 WAITING），但设计目的完全不同：sleep 是"我歇会儿"，锁不撒手；wait 是"条件不满足，你们先弄，弄好叫我"，主动交锁。
▶ 关联：wait 被唤醒后不一定直接运行——锁若被别的线程抢走，先进 BLOCKED 等锁，拿到锁才回 RUNNABLE（本章状态转换图）。

**4.** 简述线程池的工作原理：任务提交后的调度顺序、临时线程何时创建、何时拒绝，以及使用线程池的好处。

**【答案】**

工作原理：线程池内部维护一组**工作线程**和一个**任务队列**。任务提交后：
1. 有空闲核心线程 → 核心线程直接执行；
2. 核心线程全忙 → 新任务进入任务队列排队；
3. 队列也满了 → 创建**临时线程**（线程数未超过最大线程数时）；
4. 核心线程 + 临时线程全忙、队列也满 → 执行**拒绝策略**。

临时线程空闲超过 keepAliveTime 会被回收；线程执行完任务不销毁，回池等待复用。

好处：① 复用线程，避免频繁创建/销毁的巨大开销；② 控制最大并发线程数，防止线程过多拖垮系统；③ 提供队列缓冲和拒绝策略，提升系统韧性。

**【解析】** 计算题套路（核心 c、最大 m、队列 q）：前 c 个任务核心线程做，接下来 q 个进队列，再接下来 (m-c) 个开临时线程，超出 c+q+(m-c)=m+q 的任务被拒绝。Executors 的 newFixedThreadPool/newSingleThreadExecutor/newCachedThreadPool 底层都是 ThreadPoolExecutor，但因无界队列或无线程上限有 OOM 风险，生产推荐直接用 ThreadPoolExecutor 显式配置；定时任务用 newScheduledThreadPool。
▶ 关联：execute(Runnable) 无返回值，submit(Callable) 返回 Future 可 get() 结果——呼应 Callable 方式；第22章多线程服务器中线程池用于控制同时接入的客户端数量。

---

### 五、代码阅读题

**1. 日志级别过滤**

logback.xml 中配置为 `<root level="info">`，执行以下代码，控制台会输出哪几行？

```java
public class OrderTest {
    public static final Logger LOG = LoggerFactory.getLogger(OrderTest.class);

    public static void main(String[] args) {
        LOG.trace("追踪：进入 main 方法");
        LOG.debug("调试：准备下单");
        LOG.info("业务：订单创建成功，订单号 SF1001");
        LOG.warn("警告：库存仅剩 2 件");
        try {
            int price = Integer.parseInt("abc");
        } catch (NumberFormatException e) {
            LOG.error("错误：价格解析失败", e);
        }
    }
}
```

**【答案】** 输出 3 行：
- info：业务：订单创建成功，订单号 SF1001
- warn：警告：库存仅剩 2 件
- error：错误：价格解析失败（后附异常堆栈）

trace、debug 两行不输出。

**【解析】** 阈值 info 下，级别 ≥ info 的日志才记录：info/warn/error 放行，trace/debug 过滤。注意 error 可以携带异常对象 `LOG.error("消息", e)`，会把堆栈一并打印。
▶ 关联：把 level 改成 trace 则 5 行全输出，改成 error 则只剩最后一行——无需改代码、改配置即可控制，这就是日志框架的价值。

**2. start 与 run 的区别**

```java
public class BikeTask extends Thread {
    @Override
    public void run() {
        for (int i = 1; i <= 3; i++) {
            System.out.println(Thread.currentThread().getName()
                    + " 配送第 " + i + " 单");
        }
    }
}

public class Test {
    public static void main(String[] args) {
        BikeTask t1 = new BikeTask();
        t1.setName("骑手小王");
        BikeTask t2 = new BikeTask();
        t2.setName("骑手小李");

        t1.run();
        t2.run();
    }
}
```

问：运行结果有什么特点？如果把两个 `run()` 都改成 `start()`，结果又有什么特点？

**【答案】** 调 run() 时：代码在 **main 主线程**中同步执行，打印的线程名是 `main`（不是骑手小王），且**严格顺序**输出——main 配送 1、2、3 单（t1 的任务），再 main 配送 1、2、3 单（t2 的任务），共 6 行，set 设置的名字完全没体现。

改成 start() 后：两条新线程真正启动，打印线程名是"骑手小王""骑手小李"，两个名字的输出**交错出现、每次运行顺序可能不同**（CPU 抢占调度）。

**【解析】** 易错点：直接调 run() 只是普通方法调用，执行它的是 main 线程，所以 `Thread.currentThread().getName()` 拿到的是 main；线程对象 t1/t2 的 name 字段虽然设置了，但没有新线程去使用它。对比中可以体会：start() 才会向 JVM 注册新线程并由新线程回调 run()。
▶ 关联：currentThread() 的语义是"当前正在执行的线程"；实现 Runnable 方式中任务对象不是线程、根本没有 getName()，必须 Thread.currentThread().getName()——笔记 3.5 节特别强调了这一点。

**3.** 两个任务对象导致同步失效

```java
public class MilkTeaShop implements Runnable {
    private int cups = 100; // 限量奶茶 100 杯

    public synchronized void sell() {
        if (cups > 0) {
            System.out.println(Thread.currentThread().getName()
                    + " 卖出 1 杯，剩余 " + (--cups) + " 杯");
        }
    }

    @Override
    public void run() {
        while (cups > 0) {
            sell();
        }
    }
}

public class Test {
    public static void main(String[] args) {
        new Thread(new MilkTeaShop(), "美团窗口").start();
        new Thread(new MilkTeaShop(), "饿了么窗口").start();
    }
}
```

问：这段代码能保证不超卖吗？为什么？如何修改？

**【答案】** **不能保证**，可能超卖（剩余数出现错乱、两个窗口卖出超过 100 杯）。

原因：同步方法 sell() 的隐式锁是 **this**，而这里两个线程传入了**两个不同的 MilkTeaShop 对象**——两把不同的锁，各锁各的，互斥失效；而且 cups 是实例变量，两个对象各自有一份 cups=100，连共享资源都不是同一份。

修改方案（任选其一）：
1. 两个线程共用同一个任务对象：`MilkTeaShop shop = new MilkTeaShop(); new Thread(shop, "美团窗口"); new Thread(shop, "饿了么窗口");`——同一把 this 锁、同一份 cups；
2. 把 sell() 改成 **static synchronized**（隐式锁变为 MilkTeaShop.class，全局唯一），cups 也加 static；
3. 用同步代码块 `synchronized (MilkTeaShop.class) { ... }`。

**【解析】** 本题连环两坑：① 锁对象不唯一（两个 this）；② 数据不共享（两个 cups）。生产中推荐方案 1 的"共享任务对象"或方案 2 的静态同步。这正是笔记强调"实例同步方法默认锁 this，不同任务对象会有两把锁"的原因。
▶ 关联：第3.7.2 节锁对象选择建议——静态场景用类名.class；对比记忆：同步代码块 `synchronized(Obj)` 锁什么由括号里写什么决定，最直观。

**4. 线程池任务调度计算**

```java
ThreadPoolExecutor pool = new ThreadPoolExecutor(
        2,                                  // 核心 2
        4,                                  // 最大 4
        2, TimeUnit.DAYS,
        new ArrayBlockingQueue<>(3),        // 队列容量 3
        Executors.defaultThreadFactory(),
        new ThreadPoolExecutor.CallerRunsPolicy()
);

for (int i = 1; i <= 8; i++) {
    final int id = i;
    pool.execute(() -> {
        System.out.println(Thread.currentThread().getName() + " 处理任务" + id);
        try { Thread.sleep(3000); } catch (InterruptedException e) { e.printStackTrace(); }
    });
}
```

问：8 个任务分别由哪些线程执行？会抛拒绝异常吗？

**【答案】** 容量拆解：核心线程 2 个 + 队列 3 个 + 临时线程（4-2=2）个 = 最多同时接纳 **7** 个任务。第 8 个任务超出容量，触发拒绝策略。

调度明细：
- 任务 1、2 → 两个核心线程（pool-1-thread-1、pool-1-thread-2）立即执行；
- 任务 3、4、5 → 进入队列排队；
- 任务 6、7 → 创建两个临时线程（pool-1-thread-3、pool-1-thread-4）执行；
- 任务 8 → 触发 CallerRunsPolicy：**由提交任务的 main 线程亲自调用 run() 执行**（打印 main 处理任务8），不抛异常。

不会抛异常（CallerRunsPolicy 是"降级为提交者自己执行"）；若用默认 AbortPolicy 则任务 8 抛 RejectedExecutionException。

**【解析】** 调度顺序铁律：核心 → 队列 → 临时 → 拒绝。临时线程执行的是**最新提交**的任务（6、7 插队），队列里的 3、4、5 要等有线程空闲后按先来先服务执行。CallerRunsPolicy 的背压效果：main 线程被拉去干活，提交速度自然变慢，是一种优雅限流。
▶ 关联：把队列容量改成 5，则 2+5=7 个任务都在核心+队列容量内（核心跑 2、队列排 5），第 8 个才开临时线程——参数的微小变化改变调度路径，这是经典计算题套路。

**5. 等待唤醒流程分析**

```java
public class Locker {
    public static final Object lock = new Object();
    public static boolean hasPackage = false; // 快递柜里有没有包裹
}

// 快递员线程
synchronized (Locker.lock) {
    System.out.println("快递员：投递包裹");
    Locker.hasPackage = true;
    Locker.lock.notifyAll();
}

// 取件人线程（先启动）
synchronized (Locker.lock) {
    if (!Locker.hasPackage) {
        System.out.println("取件人：没包裹，等待");
        Locker.lock.wait();
    }
    System.out.println("取件人：取走包裹");
}
```

问：两条线程的完整协作流程是什么？wait() 在这里起到哪两个作用？

**【答案】** 流程：
1. 取件人先抢到锁，发现 hasPackage=false，打印"没包裹，等待"，调用 wait()；
2. wait() 做两件事：① **释放 lock 锁**（否则快递员永远进不来）；② 当前线程进入 **WAITING** 状态；
3. 快递员拿到锁，投递包裹、hasPackage=true，调用 notifyAll() 唤醒等待 lock 的线程；
4. 快递员同步块结束释放锁；
5. 取件人被唤醒后**重新抢锁**，抢到后从 wait() 处继续执行，打印"取走包裹"。

wait 的两个作用：释放锁 + 让当前线程等待；notifyAll 的作用：唤醒等待同一把锁的线程（唤醒后还要重新抢锁，抢不到先进 BLOCKED）。

**【解析】** 这是生产者-消费者模型的最小骨架：共享标志位 + 唯一锁 + wait/notifyAll。为什么用 notifyAll 而不是 notify：多个等待线程时 notify 只随机醒一个，可能唤醒的不是需要的那类线程；notifyAll 唤醒全部，由条件判断决定谁继续。
▶ 关联：if 判断条件在更严谨的写法中要用 while（防止被唤醒后条件已被其他线程改变），这是 wait/notify 的经典进阶陷阱；状态流转 WAITING → 抢锁成功 RUNNABLE / 抢锁失败 BLOCKED。

---

### 六、编程题（共 7 题，由易到难）

#### 编程题 1（基础）：读取驿站配置文件

**需求**：驿站系统有配置文件 `station.properties`，内容如下。编写程序加载该文件，打印全部配置，并根据键单独读取营业时间和客服电话。

```properties
# 驿站配置
stationName = 幸福里驿站
openTime = 08:00
closeTime = 22:00
servicePhone = 95338
boxCount = 48
```

**参考代码**：

```java
import java.io.FileReader;
import java.util.Properties;
import java.util.Set;

public class StationConfigTest {
    public static void main(String[] args) throws Exception {
        // 1. 创建 Properties 对象
        Properties prop = new Properties();
        // 2. 加载配置文件
        prop.load(new FileReader("station.properties"));

        // 3. 打印全部键值对
        System.out.println(prop);

        // 4. 获取所有键并遍历
        Set<String> keys = prop.stringPropertyNames();
        for (String key : keys) {
            System.out.println(key + " = " + prop.getProperty(key));
        }

        // 5. 根据键单独取值
        System.out.println("营业时间：" + prop.getProperty("openTime")
                + " ~ " + prop.getProperty("closeTime"));
        System.out.println("客服电话：" + prop.getProperty("servicePhone"));

        // 6. 修改配置并写回文件（覆盖）
        prop.setProperty("boxCount", "56");
        prop.store(new java.io.FileWriter("station.properties"), "更新格口数量");
    }
}
```

**思路讲解**：
- Properties 操作固定四步：new → load → getProperty/stringPropertyNames →（需要时）store；
- store 第二参数是注释，会写到文件头部；store 默认**覆盖**原文件；
- 配置文件中文乱码时，把文件另存为 UTF-8 编码即可。

**运行结果**：控制台先输出 `{servicePhone=95338, boxCount=48, ...}`，再逐行打印每个键值对，最后打印营业时间 `08:00 ~ 22:00`、电话 `95338`；文件中 boxCount 更新为 56。

▶ 关联：第17章 Map 的遍历思想（keySet + get）在这里体现为 stringPropertyNames + getProperty；第20章 FileReader/FileWriter 是字符流基础。

---

#### 编程题 2（基础）：奶茶店点单日志改造

**需求**：奶茶店点单程序原本用 System.out.println 输出信息。请改用 Logback 记录：点单成功记 info、配料售罄记 warn、下单异常记 error。要求输出 trace/debug/info/warn/error 五个级别各一条，体会级别过滤。

**参考代码**（logback.xml 放 src 下，level 自行调整测试）：

```java
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class MilkTeaOrder {
    public static final Logger LOG = LoggerFactory.getLogger(MilkTeaOrder.class);

    public static void main(String[] args) {
        LOG.trace("追踪：进入 main 方法");
        LOG.debug("调试：开始接待顾客");

        String drink = "珍珠奶茶";
        boolean bobaSoldOut = false;

        LOG.info("顾客点单成功：{} 一杯", drink);

        if (bobaSoldOut) {
            LOG.warn("警告：珍珠已售罄，推荐替换为椰果");
        } else {
            LOG.info("珍珠库存正常，继续出餐");
        }

        try {
            int sugar = Integer.parseInt("全糖"); // 模拟异常输入
        } catch (NumberFormatException e) {
            LOG.error("错误：甜度参数解析失败，请检查收银系统", e);
        }
    }
}
```

**思路讲解**：
- Logger 固定写法：`public static final Logger LOG = LoggerFactory.getLogger(当前类.class);`，包名必须是 org.slf4j；
- 五个级别按严重程度选用：trace 追踪、debug 调试、info 业务正常信息、warn 警告但程序还能跑、error 错误（可携带异常对象）；
- `{}` 是 SLF4J 的占位符，比字符串拼接更优雅。

**运行结果**：level=info 时输出 info 两行 + error 一行（trace/debug 过滤）；把配置改成 trace 则 5 类日志全部出现。

▶ 关联：对比 println 三大弊端（只能控制台、不能存文件、取消要改源码）理解日志优势；异常对象 e 传给 error 用的是第16章异常体系的知识。

---

#### 编程题 3（基础）：共享单车骑行——三种创建方式

**需求**：共享单车骑行 App 要统计骑行数据，分别用三种方式实现：
1. 继承 Thread：每辆车骑行 3 次，打印骑行了多少米；
2. 实现 Runnable：同一个骑行任务交给 3 个用户线程并发骑行；
3. Callable + FutureTask：子线程计算总里程并返回，主线程用 get() 取回。

**参考代码**：

方式一：

```java
public class BikeThread extends Thread {
    @Override
    public void run() {
        for (int i = 1; i <= 3; i++) {
            System.out.println(getName() + " 骑行第 " + i + " 段，累计 " + (i * 500) + " 米");
        }
    }
}
// 测试：new BikeThread().start();
```

方式二：

```java
public class RideTask implements Runnable {
    @Override
    public void run() {
        for (int i = 1; i <= 3; i++) {
            System.out.println(Thread.currentThread().getName()
                    + " 正在骑行，第 " + i + " 段路");
        }
    }
}
// 测试：
RideTask task = new RideTask();
new Thread(task, "用户张三").start();
new Thread(task, "用户李四").start();
new Thread(task, "用户王五").start();
```

方式三：

```java
import java.util.concurrent.Callable;
import java.util.concurrent.FutureTask;

public class DistanceTask implements Callable<Integer> {
    @Override
    public Integer call() {
        int total = 0;
        for (int i = 1; i <= 5; i++) {
            total += 300; // 每段 300 米
            System.out.println(Thread.currentThread().getName()
                    + " 骑过第 " + i + " 段，当前累计 " + total + " 米");
        }
        return total; // 返回总里程
    }
}
// 测试：
FutureTask<Integer> ft = new FutureTask<>(new DistanceTask());
new Thread(ft, "骑行统计线程").start();
System.out.println("主线程等待结果...");
System.out.println("本次骑行总里程：" + ft.get() + " 米"); // get 阻塞直到结果返回
```

**思路讲解**：
- 方式一直接 getName()（线程对象本身）；方式二必须 Thread.currentThread().getName()（任务对象不是线程）；
- 方式三 call() 的泛型 Integer 就是返回值类型，get() 会阻塞主线程直到子线程算完；
- 观察方式二的输出：三个用户的输出交错出现，且每次运行顺序不同。

**运行结果**：方式三最后打印 `本次骑行总里程：1500 米`，且这行一定在子线程 5 段输出之后（get 阻塞保证）。

▶ 关联：Runnable/Callable 都是函数式接口，可用第15章 Lambda 改写为 `new Thread(() -> {...}).start()`；FutureTask.get() 的阻塞语义在第22章网络编程接收数据时也会遇到。

---

#### 编程题 4（中等）：限量奶茶秒杀——线程安全与同步

**需求**：某品牌奶茶限量 100 杯，美团、饿了么两个窗口同时售卖。先用不加锁的写法观察超卖现象，再用**同步代码块**修复，最后改为**同步方法**和 **Lock 锁**两个版本。

**参考代码（问题版本 + 修复版本）**：

```java
public class SeckillShop implements Runnable {
    private int cups = 100; // 共享库存

    @Override
    public void run() {
        while (true) {
            sell();
            if (cups <= 0) break;
        }
    }

    // 修复版：同步代码块，锁用共享资源所在对象 this（两个线程共用同一个 shop 对象）
    public void sell() {
        synchronized (this) {
            if (cups > 0) {
                System.out.println(Thread.currentThread().getName()
                        + " 卖出 1 杯，剩余 " + (--cups) + " 杯");
            }
        }
    }
}
// 测试：必须共用同一个任务对象
// SeckillShop shop = new SeckillShop();
// new Thread(shop, "美团窗口").start();
// new Thread(shop, "饿了么窗口").start();
```

同步方法版（等价写法）：

```java
public synchronized void sell() {   // 隐式锁 this
    if (cups > 0) {
        System.out.println(Thread.currentThread().getName()
                + " 卖出 1 杯，剩余 " + (--cups) + " 杯");
    }
}
```

Lock 锁版（推荐 unlock 放 finally）：

```java
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

public class SeckillShop implements Runnable {
    private int cups = 100;
    private final Lock lock = new ReentrantLock();

    public void sell() {
        lock.lock();
        try {
            if (cups > 0) {
                System.out.println(Thread.currentThread().getName()
                        + " 卖出 1 杯，剩余 " + (--cups) + " 杯");
            }
        } finally {
            lock.unlock(); // 保证异常时也释放锁
        }
    }

    @Override
    public void run() {
        while (cups > 0) {
            sell();
        }
    }
}
```

**思路讲解**：
- 安全三条件齐备：2 个线程 + 共享 cups + `--cups` 修改操作，不加锁必然超卖；
- 判断和自减必须包在**同一个**同步块内（锁的是"判断+扣减"整段原子操作），只锁 --cups 没用；
- 两个线程必须共用同一个 shop 对象（this 才是同一把锁）；
- Lock 版 unlock 放 finally：卖货过程中哪怕抛异常锁也能释放，避免死锁。

**运行结果**：修复后剩余数从 99 严格递减到 0，不会出现负数或同号重复；两个窗口交替卖但总数恰好 100。

▶ 关联：本题三种锁写法覆盖本章 3.7 全部内容；若用两个不同任务对象测试 this 锁会复现代码阅读题 3 的失效场景；第22章多客户端服务器共享数据时同样要加锁。

---

#### 编程题 5（中等）：充电桩调度——线程池 + Lock 统计

**需求**：充电站有若干充电桩，用线程池处理车辆充电任务：核心线程 2、最大线程 4、队列容量 3，拒绝策略 CallerRunsPolicy。提交 8 辆车的充电任务，每辆车充电时占用一个空闲桩（用 Lock 保护空闲桩计数），打印占用与释放过程。

**参考代码**：

```java
import java.util.concurrent.*;
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

public class ChargingStation {
    private int freePiles = 3; // 3 个空闲充电桩
    private final Lock lock = new ReentrantLock();

    public void charge(String car) {
        lock.lock();
        try {
            if (freePiles > 0) {
                freePiles--;
                System.out.println(Thread.currentThread().getName()
                        + "： " + car + " 开始充电，空闲桩剩余 " + freePiles);
            } else {
                System.out.println(Thread.currentThread().getName()
                        + "： " + car + " 暂无空闲桩（理论上不应发生，队列已限流）");
                return;
            }
        } finally {
            lock.unlock();
        }

        try {
            Thread.sleep(2000); // 模拟充电时长
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        lock.lock();
        try {
            freePiles++;
            System.out.println(Thread.currentThread().getName()
                    + "： " + car + " 充电完成离开，空闲桩 " + freePiles);
        } finally {
            lock.unlock();
        }
    }

    public static void main(String[] args) {
        ChargingStation station = new ChargingStation();
        ThreadPoolExecutor pool = new ThreadPoolExecutor(
                2, 4,
                60, TimeUnit.SECONDS,
                new ArrayBlockingQueue<>(3),
                Executors.defaultThreadFactory(),
                new ThreadPoolExecutor.CallerRunsPolicy()
        );

        for (int i = 1; i <= 8; i++) {
            final String car = "京A" + (1000 + i);
            pool.execute(() -> station.charge(car));
        }

        pool.shutdown(); // 等全部任务完成后关闭线程池
    }
}
```

**思路讲解**：
- freePiles 是多线程共享的修改型数据，占用/释放两段操作都要加 Lock，unlock 放 finally；
- 容量 2+3+2=7，第 8 个任务触发 CallerRunsPolicy——观察输出中会有一行是 **main 线程**亲自执行的充电任务；
- shutdown() 平滑关闭（等队列任务跑完）；shutdownNow() 立即关闭并返回未执行任务列表。

**运行结果**：pool-1-thread-1~4 处理大部分车辆，第 8 辆由 main 处理；空闲桩数量在 0~3 间变化且不会出现负数。

▶ 关联：把拒绝策略换成 AbortPolicy 会看到 RejectedExecutionException；换成 DiscardPolicy 第 8 辆静默消失——对比四种策略的差异（本章 3.9.2）。

---

#### 编程题 6（进阶）：快递柜投递与取件——等待唤醒机制

**需求**：模拟快递柜：快递员（生产者）往柜子里投递包裹，取件人（消费者）取件。柜子最多放 1 个包裹：柜满时快递员等待，柜空时取件人等待。用 wait/notifyAll 实现协作，共完成 5 次投递-取件循环。

**参考代码**：

```java
// 共享柜
public class Locker {
    public static final Object lock = new Object();
    public static boolean hasPackage = false; // 柜中是否有包裹
    public static int count = 0;              // 已完成的取件数
}

// 快递员（生产者）
public class Courier implements Runnable {
    @Override
    public void run() {
        while (true) {
            synchronized (Locker.lock) {
                if (Locker.count >= 5) break;
                if (Locker.hasPackage) {
                    try {
                        Locker.lock.wait(); // 柜子满，等待取件人取走
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                } else {
                    System.out.println("快递员：投递包裹 No." + (Locker.count + 1));
                    Locker.hasPackage = true;
                    Locker.lock.notifyAll(); // 通知取件人
                }
            }
        }
    }
}

// 取件人（消费者）
public class Customer implements Runnable {
    @Override
    public void run() {
        while (Locker.count < 5) {
            synchronized (Locker.lock) {
                if (!Locker.hasPackage) {
                    try {
                        Locker.lock.wait(); // 没包裹，等待快递员投递
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                } else {
                    Locker.count++;
                    System.out.println("取件人：取走包裹 No." + Locker.count);
                    Locker.hasPackage = false;
                    Locker.lock.notifyAll(); // 通知快递员可以投下一个
                }
            }
        }
    }
}

// 测试
public class LockerTest {
    public static void main(String[] args) {
        new Thread(new Courier(), "快递员").start();
        new Thread(new Customer(), "取件人").start();
    }
}
```

**思路讲解**：
- 三个要素：唯一锁对象（Locker.lock）、共享状态标志（hasPackage）、wait/notifyAll 配对；
- wait 一定在循环/条件判断中使用、由锁对象调用；操作完状态后 notifyAll 唤醒对方；
- 严谨写法中条件判断推荐用 **while** 而非 if（防止被虚假唤醒或唤醒后条件已变），本例单生产者单消费者 if 可用，多消费者场景必须 while。

**运行结果**：严格交替输出"快递员投递 No.1 → 取件人取走 No.1 → 投递 No.2 → ……"，共 5 轮后取件人线程结束。

▶ 关联：这就是第22章 TCP 通信中"服务端等待客户端发数据、客户端等待服务端响应"协作模型的基础；wait 释放锁的特性保证对方能进入同步块。

---

#### 编程题 7（综合）：Dom4j 解析快递柜 XML 配置

**需求**：快递柜部署信息用 XML 描述。请用 Dom4j 解析文件，把每个柜机封装为 LockerDevice 对象存入 ArrayList 并遍历输出；同时统计格口总数。

XML 文件 `lockers.xml`：

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<lockerList>
    <locker id="L001" vip="true">
        <address>幸福里小区东门</address>
        <boxes>48</boxes>
    </locker>
    <locker id="L002" vip="false">
        <address>科创园 B 座大堂</address>
        <boxes>72</boxes>
    </locker>
    <locker id="L003" vip="true">
        <address>地铁 2 号线 C 口</address>
        <boxes>36</boxes>
    </locker>
</lockerList>
```

**参考代码**：

```java
import org.dom4j.Attribute;
import org.dom4j.Document;
import org.dom4j.Element;
import org.dom4j.io.SAXReader;

import java.util.ArrayList;
import java.util.List;

public class LockerDevice {
    private String id;
    private boolean vip;
    private String address;
    private int boxes;

    public LockerDevice() {}

    public LockerDevice(String id, boolean vip, String address, int boxes) {
        this.id = id;
        this.vip = vip;
        this.address = address;
        this.boxes = boxes;
    }

    @Override
    public String toString() {
        return "柜机编号：" + id + "，地址：" + address
                + "，格口数：" + boxes + "，VIP 柜：" + (vip ? "是" : "否");
    }
}

class LockerParseTest {
    public static void main(String[] args) throws Exception {
        // 1. 创建解析器，读成 Document
        SAXReader saxReader = new SAXReader();
        Document document = saxReader.read("lockers.xml");

        // 2. 获取根元素
        Element root = document.getRootElement();

        // 3. 获取所有一级子元素 <locker>
        List<Element> lockerEls = root.elements();

        // 4. 遍历封装
        ArrayList<LockerDevice> list = new ArrayList<>();
        int totalBoxes = 0;
        for (Element el : lockerEls) {
            String id = el.attributeValue("id");                 // 属性
            String vip = el.attributeValue("vip");
            String address = el.elementText("address");         // 子标签文本
            String boxes = el.elementText("boxes");

            LockerDevice device = new LockerDevice(
                    id, Boolean.parseBoolean(vip),
                    address, Integer.parseInt(boxes));
            list.add(device);
            totalBoxes += Integer.parseInt(boxes);
        }

        // 5. 遍历输出
        for (LockerDevice d : list) {
            System.out.println(d);
        }
        System.out.println("柜机总数：" + list.size() + "，格口总数：" + totalBoxes);
    }
}
```

**思路讲解**：
- Dom4j 解析固定套路：SAXReader → Document → getRootElement → elements 遍历；
- 属性用 attributeValue("属性名")，子标签文本用 elementText("标签名")（等价于 element("x").getText()）；
- XML 中布尔、数字都是文本，需用 Boolean.parseBoolean / Integer.parseInt 转换；
- 每个 `<locker>` 对应一个 JavaBean 对象——这就是 XML 数据到 Java 对象的映射思想。

**运行结果**：

```
柜机编号：L001，地址：幸福里小区东门，格口数：48，VIP 柜：是
柜机编号：L002，地址：科创园 B 座大堂，格口数：72，VIP 柜：否
柜机编号：L003，地址：地铁 2 号线 C 口，格口数：36，VIP 柜：是
柜机总数：3，格口总数：156
```

▶ 关联：JavaBean 封装规范（私有字段 + 构造器 + get/set + toString）来自第7章《面向对象基础》；ArrayList 遍历来自第10/16章；这种"配置文件描述数据、程序解析成对象"的模式在第22章网络传输结构化数据、第23章框架解析注解配置中反复出现。

---

### 本章自测清单

- [ ] 能独立写出 Properties 的 load/getProperty/store 流程，知道键不能重复、行尾不写分号
- [ ] 能说出 XML 语法四规则（单根、成对、嵌套、实体字符/CDATA），会用 Dom4j 解析并封装 JavaBean
- [ ] 能说清日志五个级别和过滤规则，会获取 Logger、打不同级别日志
- [ ] 能手写三种线程创建方式并说出优缺点
- [ ] 能解释 start 与 run 的区别、sleep 与 wait 的区别
- [ ] 能判断线程安全三条件，会用三种同步方式，锁对象选择正确
- [ ] 能手算线程池任务调度（核心→队列→临时→拒绝），说出四种拒绝策略
- [ ] 能说出六种线程状态及典型转换路径
- [ ] 能写出 wait/notifyAll 生产者消费者骨架

---

<div style="page-break-after: always;"></div>

## 第22章 网络编程·习题精讲

> 做题建议：网络编程的题分两类——概念题（三要素、UDP/TCP 区别）靠背，编程题靠"流程"：UDP 是"打包→发送/接收→拆包"，TCP 是"先起服务端→accept 等连接→拿 IO 流收发"。编程题都可以在本机用 127.0.0.1 跑通。

### 一、填空题

1. 网络编程三要素是 ______、______、______。

**【答案】** IP 地址；端口；协议。

**【解析】** IP 地址定位网络上的主机（`InetAddress` 表示），端口定位主机上的具体应用程序，协议规定数据传输规则。三者缺一不可。
▶ 关联：IP 地址对象的获取见本章 InetAddress；协议在传输层分 UDP/TCP 两种。

2. 端口是一个 16 位二进制数，范围是 ______；自己开发的程序一般使用 ______ 段端口。

**【答案】** 0 ~ 65535；注册端口（1024 ~ 49151）。

**【解析】** 0~1023 是周知端口（HTTP 占 80、FTP 占 21），49152~65535 是动态端口。我们自己写服务端绑定端口时选 1024~49151 之间、且本机未被占用的端口，否则报 `BindException: Address already in use`。
▶ 关联：第21章多线程中服务端要为每个客户端服务，端口只绑定一次。

3. UDP 协议的特点是 ______、______；每个数据包大小限制在 ______ 以内。

**【答案】** 无连接；不可靠；64KB。

**【解析】** UDP 发送方不管对方在不在线、不确认、不重传，所以快但不可靠；数据按包发，一包含收发双方 IP、端口和数据，限 64KB。语音通话、直播用 UDP。
▶ 关联：对比 TCP 见下一题与简答题。

4. TCP 保证可靠传输的三个步骤是 ______、______、______。

**【答案】** 三次握手建立连接；传输数据进行确认；四次挥手断开连接。

**【解析】** 三次握手确认双方收发能力都正常（全双工），传输中确认/重传保证数据不丢，四次挥手确保双方数据都发完再断。TCP 面向连接、可靠，网页、文件下载、支付都用 TCP。
▶ 关联：TCP 编程核心类是 `Socket`/`ServerSocket`，数据通过第19/20章学的 IO 流传输。

5. UDP 广播使用的目标地址是 ______，并且需要先调用 ______ 方法手动开启广播。

**【答案】** 255.255.255.255；`socket.setBroadcast(true)`。

**【解析】** 向 255.255.255.255 发数据，同网段所有监听该端口的程序都能收到；默认广播不开启，不调 setBroadcast 直接发可能抛异常。若路由器屏蔽广播，可改用网段广播地址（如 192.168.1.255）。

### 二、选择题

1. 下列关于 IP 地址的说法，错误的是（ ）
A. `127.0.0.1` 和 `localhost` 都代表本机
B. `192.168.x.x` 是常见的内网（局域网）地址
C. IPv6 地址共 128 位，分 8 段用冒号分隔
D. 一台设备联网后可以没有 IP 地址，只要端口正确就能通信

**【答案】** D

**【解析】** IP 是设备在网络上的唯一标志，没有 IP 就无法被定位，端口是依附于主机上的程序的，二者不是替代关系。A、B、C 均为笔记原文。
▶ 关联：`InetAddress.getByName("域名")` 可以把域名解析成 IP 对象。

2. UDP 编程中，接收方解析数据时，用来获取本次实际收到字节数的方法是（ ）
A. `packet.getData()`
B. `packet.getLength()`
C. `packet.getPort()`
D. `socket.receive()`

**【答案】** B

**【解析】** `getData()` 返回整个 64KB 缓冲数组（后面是空字节），`getLength()` 返回本次实际收到的字节数，所以正确写法是 `new String(data, 0, len)`。漏掉 len 会把缓冲里的空白也拼进字符串。`getPort()` 拿的是发送方端口。
▶ 关联：这和第19章字节流 `read(bytes)` 返回实际读取长度是同一个思想。

3. 关于 TCP 编程，下列说法正确的是（ ）
A. 必须先启动客户端，再启动服务端
B. 服务端 `accept()` 方法在没有客户端连接时会立即返回 null
C. 必须先启动服务端，客户端连接的端口要和服务端绑定的端口一致
D. TCP 数据通过 DatagramPacket 对象传输

**【答案】** C

**【解析】** 先起服务端、再起客户端，否则客户端抛 `Connection refused: connect`；`accept()` 是阻塞方法，没有连接会一直等；TCP 用 Socket/ServerSocket + IO 流，DatagramPacket 是 UDP 的类。
▶ 关联：第21章讲过阻塞的概念——wait/sleep 会停住线程，accept 同样阻塞。

4. TCP 多发多收场景下，服务端为什么不能用 `is.readAllBytes()` 读消息？（ ）
A. readAllBytes 只能读文本文件
B. readAllBytes 会等连接关闭才返回全部数据，无法实时处理每条消息
C. readAllBytes 一次最多读 1024 字节
D. readAllBytes 是 UDP 专用方法

**【答案】** B

**【解析】** readAllBytes 要读到流末尾（-1）才返回，而 TCP 连接一直开着、客户端在循环发消息，服务端就永远等不到流末尾，表现为"一条都收不到，断开瞬间全出来"。多发多收要用 `read(byte[])` 循环读。
▶ 关联：第19章字节流里 readAllBytes 适合一次性读完整个文件，不适合长连接实时通信。

5. 下列场景与协议的搭配，最合理的是（ ）
A. 视频直播 —— TCP
B. 微信文字消息/支付 —— TCP
C. 文件下载 —— UDP
D. 语音通话 —— TCP

**【答案】** B

**【解析】** 追求实时、允许少量丢包的场景（直播、语音）用 UDP，效率高；要求数据准确完整的场景（网页、支付、文件下载、消息）用 TCP。笔记结论：实际上现在基本都使用 TCP。

6. 服务端要同时服务多个 TCP 客户端，正确做法是（ ）
A. 为每个客户端 new 一个 ServerSocket
B. 主线程循环 accept，每接到一个 Socket 就交给一个新线程处理
C. 一个 Socket 对象轮流给多个客户端用
D. 让客户端排队，一个服务完再 accept 下一个

**【答案】** B

**【解析】** ServerSocket 只创建一次、绑定一个端口；主线程死循环 accept，每接到一个 Socket 就 `new Thread(new MyRunnable(socket)).start()`，否则主线程在处理第一个客户端时无法 accept 第二个。
▶ 关联：这正是第21章多线程的典型应用——Runnable 任务携带 Socket 数据。

### 三、判断题

1. UDP 发送数据前必须先和接收方建立连接，否则发送失败。（ ）

**【答案】** 错误。

**【解析】** UDP 是无连接协议，发送方不管对方是否在线直接发包，收不到也不报错；TCP 才需要三次握手建立连接。这是 UDP"不可靠"的根源。

2. TCP 通信中，服务端绑定的端口号和客户端连接时写的端口号必须一致。（ ）

**【答案】** 正确。

**【解析】** 服务端 `new ServerSocket(9999)` 注册 9999 端口，客户端 `new Socket("127.0.0.1", 9999)` 必须连同一个端口，就像打电话要拨对分机号；客户端自己的端口由系统分配，不需要关心。

3. 一台计算机上两个网络程序可以使用相同的端口号，只要协议不同就行。（ ）

**【答案】** 错误。

**【解析】** 笔记明确：一台设备中不能出现两个程序端口号相同，否则会出错（端口冲突，BindException）。端口的作用就是唯一标记正在运行的程序。

4. 服务端用线程处理多个客户端时，每个子线程持有自己的那个 Socket 对象。（ ）

**【答案】** 正确。

**【解析】** accept 每接到一个连接返回一个独立 Socket，把它传给 Runnable 的成员变量，子线程只和自己的客户端通信，互不干扰。共享同一个 Socket 会导致消息串台。
▶ 关联：Socket 作为对象通过构造方法传给线程任务，和第21章"两个线程卖各自的票"传数据方式一致。

### 四、简答题

1. 从连接、可靠性、效率、数据量、典型场景五个方面对比 UDP 和 TCP。

**【答案】**
| 对比项 | UDP | TCP |
| --- | --- | --- |
| 连接 | 无连接，发包前不建立连接 | 面向连接，三次握手建连 |
| 可靠性 | 不可靠（不确认、不重传） | 可靠（确认、重传机制） |
| 效率 | 高 | 相对低（握手/确认有开销） |
| 数据量 | 单包限 64KB | 连接中可传大量数据 |
| 典型场景 | 语音通话、视频直播 | 网页、文件下载、支付 |

**【解析】** 记忆抓手：UDP"快而糙"——像广播喇叭，喊完不管；TCP"稳而慢"——像打电话，先接通（握手）再说话，挂断要道别（挥手）。核心 API 也要对应记：UDP 是 DatagramSocket+DatagramPacket，TCP 是 Socket+ServerSocket+IO 流。
▶ 关联：TCP 收发数据用的就是第19/20章的字节流/字符流。

2. 简述 TCP 三次握手和四次挥手各自的目的。

**【答案】** 三次握手目的：确认通信双方发送和接收消息的能力都正常（全双工），保证连接可靠建立；四次挥手目的：确保双方的数据收发都已经完成，再断开连接，避免数据丢失。

**【解析】** 握手不是形式主义——TCP 要在不可靠的网络信道上实现可靠传输，必须先确认"我能发给你、你能发给我"。挥手要四次是因为连接是全双工的，两个方向的数据要各自关闭。
▶ 关联：理解"面向连接"后就明白为什么 TCP 代码里必须先有 ServerSocket 等连接。

3. 画出（或文字描述）TCP 服务端同时服务多个客户端的程序结构。

**【答案】** 主线程：`new ServerSocket(端口)` → `while(true)` 循环 → `Socket socket = ss.accept()` 阻塞等连接 → 接到后 `new Thread(new 处理任务(socket)).start()` → 继续 accept。子线程任务类：实现 Runnable，成员变量存 Socket，run 方法中获取输入流、循环 `read` 读取并处理该客户端消息，异常时提示客户端离开。

**【解析】** 关键点有三个：① ServerSocket 只创建一次；② accept 在循环里反复调用；③ 每个 Socket 交给独立线程，主线程不做业务处理。这样多个客户端可以并发和服务端通信。
▶ 关联：这是第21章"线程创建方式二（实现 Runnable）"在网络场景的直接应用。

### 五、代码阅读题

1. 下面 UDP 接收端代码运行后，打印出的消息末尾带了一串空白，可能是什么原因？

```java
DatagramSocket socket = new DatagramSocket(8888);
byte[] bytes = new byte[1024 * 64];
DatagramPacket packet = new DatagramPacket(bytes, bytes.length);
socket.receive(packet);
String res = new String(packet.getData());   // 问题在这一行
System.out.println("收到：" + res);
```

**【答案】** `new String(packet.getData())` 把整个 64KB 缓冲数组都转成了字符串，数组后半部分是空字节。应改为：

```java
int len = packet.getLength();
String res = new String(packet.getData(), 0, len);
```

**【解析】** getData 返回的是接收容器，不是实际数据长度；getLength 才是本次收到的真实字节数。这是 UDP 接收代码最高频的错误。
▶ 关联：和字节流 `int len = is.read(bytes); new String(bytes, 0, len)` 完全同构（第19章）。

2. 阅读 TCP 服务端代码，指出两处问题并说明后果。

```java
public static void main(String[] args) throws Exception {
    ServerSocket ss = new ServerSocket(9999);
    while (true) {
        Socket socket = ss.accept();
        InputStream is = socket.getInputStream();
        byte[] bytes = new byte[1024];
        int len;
        while ((len = is.read(bytes)) != -1) {
            System.out.println(new String(bytes, 0, len));
        }
    }
}
```

**【答案】**
① 主线程在 while 循环里直接读取客户端数据：处理第一个客户端期间（read 阻塞等待），主线程无法回到 accept，第二个客户端连不上（表现为"第一个客户端能用，后面的全卡住"）。应把每个 Socket 交给子线程处理。
② 没有关闭/异常处理：客户端断开后 read 返回 -1 或抛异常，若不处理可能影响后续循环（应在子线程 try-catch，客户端离开时打印提示）。

**【解析】** 这正是笔记"多客户端实现"一节要解决的问题：accept 和业务处理必须解耦。
▶ 关联：修复方式即简答题3的线程模型，用到第21章 Runnable。

3. 下面广播客户端代码在同网段其他机器上收不到消息，找出原因。

```java
DatagramSocket socket = new DatagramSocket();
byte[] bytes = "学校通知：今天下午四点放假".getBytes();
DatagramPacket packet = new DatagramPacket(bytes, bytes.length,
        InetAddress.getByName("255.255.255.255"), 8888);
socket.send(packet);
socket.close();
```

**【答案】** 缺少 `socket.setBroadcast(true);`，广播默认不开启，不开启直接向广播地址发送会失败或被丢弃。在 send 之前加上该方法即可。另外若路由器屏蔽全局广播，可改为本网段广播地址（如 192.168.1.255）。

**【解析】** 广播地址写对了（255.255.255.255），但开关没打开——这是广播题的固定考点。

### 六、编程题

#### 编程题 1（基础）：驿站取件通知（UDP 单播）

**需求：** 驿站服务端启动后等待接收；快递员客户端发送一条取件通知"取件码 8-3-126，包裹已到驿站"。服务端收到后打印消息和发送方 IP、端口。

**【答案】**

客户端（发送方）：

```java
import java.net.*;

public class CourierClient {
    public static void main(String[] args) throws Exception {
        DatagramSocket socket = new DatagramSocket();
        byte[] bytes = "取件码 8-3-126，包裹已到驿站".getBytes();
        DatagramPacket packet = new DatagramPacket(
                bytes, bytes.length,
                InetAddress.getLocalHost(), 9527);
        socket.send(packet);
        System.out.println("取件通知已发送");
        socket.close();
    }
}
```

服务端（接收方）：

```java
import java.net.DatagramPacket;
import java.net.DatagramSocket;

public class StationServer {
    public static void main(String[] args) throws Exception {
        DatagramSocket socket = new DatagramSocket(9527);
        byte[] bytes = new byte[1024 * 64];
        DatagramPacket packet = new DatagramPacket(bytes, bytes.length);
        System.out.println("驿站等待通知...");
        socket.receive(packet);
        String msg = new String(packet.getData(), 0, packet.getLength());
        System.out.println("收到通知：" + msg);
        System.out.println("来自：" + packet.getAddress().getHostAddress()
                + " 端口：" + packet.getPort());
        socket.close();
    }
}
```

（注意：上面 `1 java.net.DatagramSocket;` 应为 `import java.net.DatagramSocket;`，这是故意留给你找的笔误——import 关键字不能少。）

**【解析】** UDP 四步固定套路：客户端 new Socket → 数据打成 DatagramPacket（数据、长度、目标 IP、端口）→ send → close；服务端 new Socket(端口) → new Packet(缓冲数组) → receive 阻塞 → 用 getLength 截取真实长度。先启动服务端再运行客户端。
▶ 关联：中文跨机器乱码时可用 `getBytes(StandardCharsets.UTF_8)` 并在接收端 `new String(data,0,len,StandardCharsets.UTF_8)`，字符集知识见第19章。

#### 编程题 2（基础）：InetAddress 网络小工具

**需求：** 写一个工具方法，打印本机主机名和 IP；再查询"www.baidu.com"的 IP，并判断 5 秒内能否连通。

**【答案】**

```java
import java.net.InetAddress;

public class NetTool {
    public static void main(String[] args) throws Exception {
        InetAddress local = InetAddress.getLocalHost();
        System.out.println("本机名：" + local.getHostName());
        System.out.println("本机IP：" + local.getHostAddress());

        InetAddress baidu = InetAddress.getByName("www.baidu.com");
        System.out.println("百度主机名：" + baidu.getHostName());
        System.out.println("百度IP：" + baidu.getHostAddress());
        System.out.println("5秒内是否连通：" + baidu.isReachable(5000));
    }
}
```

**【解析】** 三个核心方法：getLocalHost 拿本机、getByName(域名/IP/主机名) 拿任意主机、isReachable(毫秒) 相当于程序版 ping。这些方法都声明了异常，main 上 throws Exception 即可。
▶ 关联：getByName 返回的 InetAddress 对象正好可以作为 DatagramPacket/Socket 的目标地址参数。

#### 编程题 3（中等）：校园广播通知（UDP 一对多）

**需求：** 广播站客户端向全网段广播一条放假通知；所有启动着的接收端（可开多个）都能同时收到。

**【答案】**

广播发送端：

```java
import java.net.*;

public class BroadcastStation {
    public static void main(String[] args) throws Exception {
        DatagramSocket socket = new DatagramSocket();
        socket.setBroadcast(true);   // 必须手动开启广播
        byte[] bytes = "校园广播：今天 16:00 提前放假，请各班关好门窗".getBytes();
        DatagramPacket packet = new DatagramPacket(
                bytes, bytes.length,
                InetAddress.getByName("255.255.255.255"), 9527);
        socket.send(packet);
        System.out.println("广播已发出");
        socket.close();
    }
}
```

接收端（复制多份运行）：

```java
import java.net.*;

public class BroadcastReceiver {
    public static void main(String[] args) throws Exception {
        DatagramSocket socket = new DatagramSocket(9527);
        byte[] bytes = new byte[1024 * 64];
        DatagramPacket packet = new DatagramPacket(bytes, bytes.length);
        System.out.println("班级广播待命...");
        socket.receive(packet);
        System.out.println("收到广播：" + new String(packet.getData(), 0, packet.getLength()));
        socket.close();
    }
}
```

**【解析】** 广播与单播的唯一区别：目标 IP 改 255.255.255.255 + setBroadcast(true)；服务端代码不变，多个接收端绑定同一端口各自收一份。想持续接收多条，把 receive 放进 while(true)。
▶ 关联：多接收端"一份数据多处收到"是 UDP 无连接特性的直接体现。

#### 编程题 4（中等）：快递状态查询（TCP 一问一答）

**需求：** 客户端发送一个快递单号，服务端查询后返回状态（用 Map 预置 3 个单号的状态），客户端打印结果后断开。

**【答案】**

服务端：

```java
import java.io.*;
import java.net.*;
import java.util.*;

public class ExpressServer {
    public static void main(String[] args) throws Exception {
        Map<String, String> db = new HashMap<>();
        db.put("SF1001", "已揽收，运输中");
        db.put("SF1002", "派送中，快递员：张师傅");
        db.put("SF1003", "已签收");

        ServerSocket ss = new ServerSocket(9999);
        Socket socket = ss.accept();

        BufferedReader br = new BufferedReader(
                new InputStreamReader(socket.getInputStream()));
        PrintStream ps = new PrintStream(socket.getOutputStream());

        String no = br.readLine();
        String status = db.getOrDefault(no, "查无此单");
        ps.println(status);

        ps.close();
        br.close();
        socket.close();
        ss.close();
    }
}
```

客户端：

```java
import java.io.*;
import java.net.Socket;
import java.util.Scanner;

public class ExpressClient {
    public static void main(String[] args) throws Exception {
        Socket socket = new Socket("127.0.0.1", 9999);
        BufferedReader br = new BufferedReader(
                new InputStreamReader(socket.getInputStream()));
        PrintStream ps = new PrintStream(socket.getOutputStream());

        System.out.print("请输入快递单号：");
        String no = new Scanner(System.in).nextLine();
        ps.println(no);
        System.out.println("查询结果：" + br.readLine());

        br.close();
        ps.close();
        socket.close();
    }
}
```

**【解析】** TCP 一问一答的关键是用"行流"配合：BufferedReader.readLine 等一行、PrintStream.println 发一行（自带换行，对端 readLine 才能读到）。这里用字符流包装字节流，即第20章的转换流 InputStreamReader。
▶ 关联：getOrDefault 是第17章 Map 的常用方法；readLine/println 配合是第20章缓冲流知识。

#### 编程题 5（进阶）：多线程外卖点餐服务器（TCP 多发多收）

**需求：** 多个顾客客户端可以同时连接服务器，每个顾客可以连续发送菜品名点餐，输入 exit 结束。服务器每收到一条就打印"来自 xx 的订单：xx"，并能同时接待所有顾客。

**【答案】**

服务端主线程 + 任务类：

```java
import java.net.*;

public class OrderServer {
    public static void main(String[] args) throws Exception {
        ServerSocket ss = new ServerSocket(1088);
        while (true) {
            System.out.println("等待顾客连接...");
            Socket socket = ss.accept();
            new Thread(new OrderTask(socket)).start();
        }
    }
}
```

```java
import java.io.*;
import java.net.Socket;

public class OrderTask implements Runnable {
    private Socket socket;

    public OrderTask(Socket socket) {
        this.socket = socket;
    }

    @Override
    public void run() {
        try {
            String addr = socket.getRemoteSocketAddress().toString();
            System.out.println(addr + " 顾客进店");
            BufferedReader br = new BufferedReader(
                    new InputStreamReader(socket.getInputStream()));
            String dish;
            while ((dish = br.readLine()) != null) {
                System.out.println("来自 " + addr + " 的订单：" + dish);
            }
        } catch (Exception e) {
            System.out.println("一位顾客离开：" + socket.getRemoteSocketAddress());
        }
    }
}
```

客户端（可启动多个）：

```java
import java.io.*;
import java.net.Socket;
import java.util.Scanner;

public class CustomerClient {
    public static void main(String[] args) throws Exception {
        Socket socket = new Socket("127.0.0.1", 1088);
        PrintStream ps = new PrintStream(socket.getOutputStream());
        Scanner sc = new Scanner(System.in);
        while (true) {
            System.out.print("点菜（exit 结束）：");
            String dish = sc.nextLine();
            if ("exit".equals(dish)) break;
            ps.println(dish);
        }
        ps.close();
        socket.close();
    }
}
```

**【解析】** 这是网络编程的集大成写法：① 主线程只 accept；② 每个 Socket 包进 Runnable 交线程；③ 子线程用 readLine 循环收，客户端断开时 readLine 返回 null（或异常）结束；④ println 发一行对端 readLine 读一行。启动一个服务端、多个客户端即可看到并发接待效果。
▶ 关联：Runnable 带数据（Socket）是第21章写法；字符流包装是第20章；多线程并发是第21章核心；循环+exit 退出是第5章结构。

---

<div style="page-break-after: always;"></div>

## 第23章 单元测试、反射、注解与动态代理·习题精讲

> 做题建议：本章四个主题是 JavaSE 的"框架预科"。抓住四条主线：JUnit 测方法、反射解剖类（Class→Constructor→Field→Method）、注解打标记+反射解析、动态代理用接口做增强。反射代码多抛 Exception，main/test 上直接 throws 即可。

### 一、填空题

1. JUnit 测试方法必须满足三个条件：______、______、______，并且要加 ______ 注解。

**【答案】** 公共（public）；无参；无返回值（void）；`@Test`。

**【解析】** 框架通过反射调用测试方法（第23章反射），所以必须 public、无参、void，再用 @Test 标记。@BeforeEach 做准备、@AfterEach 做清理，@BeforeAll/@AfterAll 全局一次且必须 static。

2. 获取 Class 对象的三种方式是 ______、______、______。

**【答案】** `类名.class`；`Class.forName("全类名")`；`对象.getClass()`。

**【解析】** 第一种编译期已知类，第二种最常用（配置文件里写全类名字符串，运行期加载，框架核心），第三种已有对象时使用。三种方式拿到的是同一个 Class 对象（一个类加载后只有一份字节码）。
▶ 关联：getClass 是第8章 Object 类的方法；forName 字符串驱动正是"反射做框架"的基础。

3. 反射访问私有成员时，必须先调用 ______ 方法，作用是 ______。

**【答案】** `setAccessible(true)`；暴力反射（取消权限检查，允许访问私有成员）。

**【解析】** getDeclaredConstructor/Field/Method 能拿到私有成员，但直接 newInstance/get/set/invoke 会抛 IllegalAccessException；setAccessible(true) 后才能操作。注意 getDeclaredXxx 拿本类全部声明（含私有），getXxx 只拿 public（含继承的）。

4. 自定义注解使用 ______ 关键字声明；两个常用元注解中，______ 限定注解能写在哪些位置，______ 限定注解存活范围。

**【答案】** `@interface`；`@Target`；`@Retention`。

**【解析】** @Target 的值如 ElementType.TYPE（类）、METHOD（方法）、FIELD（字段）；@Retention 要让反射读到必须写 RetentionPolicy.RUNTIME。注解属性写法是"类型 属性名() [default 默认值]"，特殊属性名 value 在只有一个属性时使用可省略属性名。
▶ 关联：@Test、@Override 都是现成注解，@Override 保留策略是 SOURCE（编译期检查即可）。

5. JDK 动态代理通过 ______ 方法创建代理对象，它的三个参数分别是 ______、______、______。

**【答案】** `Proxy.newProxyInstance`；类加载器（当前类.class.getClassLoader()）；代理要实现的接口数组（new Class[]{接口.class}）；InvocationHandler（调用处理器，写增强逻辑）。

**【解析】** JDK 动态代理基于接口：被代理对象必须实现接口，代理对象也实现同一接口，所以能强转成接口类型。每次调用代理方法都会进入 InvocationHandler 的 invoke 方法，在里面写前置增强、method.invoke(源对象, args) 调原方法、后置增强。
▶ 关联：method.invoke 就是反射的 Method 调用，代理是反射的综合应用。

### 二、选择题

1. 下列关于在 main 方法里做测试的弊端，说法错误的是（ ）
A. 一个方法抛异常会中断 main，后面的方法测不到
B. 无法自动生成测试报告，要人工观察
C. main 方法不能调用其他类的方法
D. 测试代码和业务代码混在一起，方法间互相影响

**【答案】** C

**【解析】** main 当然可以调用其他类的方法，这正是测试的方式；弊端是没有隔离性、没有自动报告。JUnit 的每个 @Test 方法独立运行，一个失败不影响其他，绿/红报告自动生成。

2. 断言 `Assertions.assertEquals(预期值, 实际值, 提示)` 的作用是（ ）
A. 方法抛异常时打印提示
B. 比较预期与实际，不一致就断言失败（红色）
C. 只在方法返回 null 时报错
D. 输出实际值到控制台

**【答案】** B

**【解析】** 没有断言时，测试只看"抛不抛异常"，方法逻辑算错（如该返回最大索引却返回长度）也会绿灯。断言比对预期值和实际返回值，不一致抛 AssertionError 使测试变红，第三个参数是失败提示。

3. 已有 `Parcel p = new Parcel();`，下列获取 Class 对象的写法错误的是（ ）
A. `Class c1 = Parcel.class;`
B. `Class c2 = Class.forName("com.itheima.Parcel");`
C. `Class c3 = p.getClass();`
D. `Class c4 = p.new Class();`

**【答案】** D

**【解析】** Class 对象不能 new 构造，三种合法方式见填空第2题。Class.forName 要写全类名（包名+类名），写错抛 ClassNotFoundException。

4. 反射执行一个有参有返回值的方法 `int sum(int a, int b)`，正确写法是（ ）
A. `Method m = c.getMethod("sum"); m.invoke(obj);`
B. `Method m = c.getDeclaredMethod("sum", int.class, int.class); m.setAccessible(true); int r = (int) m.invoke(obj, 2, 3);`
C. `Method m = c.getDeclaredMethod("sum"); int r = m.invoke(obj, 2, 3);`
D. `int r = c.invoke("sum", 2, 3);`

**【答案】** B

**【解析】** getDeclaredMethod 第一个参数是方法名，后面是可变参数——形参类型列表，用于定位重载方法；invoke 第一个参数是对象，后面是实参；invoke 返回 Object，基本类型会被装箱，需要强转回 int。私有方法别忘 setAccessible(true)。
▶ 关联：参数类型列表定位方法，和第4章方法重载"方法名+参数列表"唯一确定一个方法是同一道理。

5. 自定义注解希望在程序运行时能被反射读取，@Retention 必须写成（ ）
A. RetentionPolicy.SOURCE
B. RetentionPolicy.CLASS
C. RetentionPolicy.RUNTIME
D. 不写 @Retention 也行

**【答案】** C

**【解析】** SOURCE 只在源码中存在（编译丢弃，如 @Override）；CLASS 存活到 class 文件但运行期不可见；RUNTIME 一直存活到运行时，反射 getDeclaredAnnotation/isAnnotationPresent 才能读到。

6. 关于 JDK 动态代理，下列说法正确的是（ ）
A. 任何类都能被 JDK 代理，不需要接口
B. 代理对象和被代理对象实现相同接口，调用代理方法会进入 InvocationHandler.invoke
C. invoke 方法里不能调用原对象的方法，否则会死循环
D. 代理对象是直接 new 出来的被代理类的子类对象

**【答案】** B

**【解析】** JDK 代理基于接口：Proxy.newProxyInstance 运行期生成一个实现了指定接口的代理类对象；每次方法调用都进入 invoke，参数 method 是被调方法、args 是实参；在 invoke 内用 `method.invoke(源对象, args)` 回调原方法，这不是递归，不会死循环。A、D 描述的是 CGLIB 代理（子类代理），不在本章范围。
▶ 关联：接口约定方法见第9/12章；回调原方法用的是反射 Method.invoke。

### 三、判断题

1. @BeforeEach 注解的方法在整个测试类运行期间只执行一次。（ ）

**【答案】** 错误。

**【解析】** @BeforeEach/@AfterEach 是每个 @Test 方法执行前后各执行一次（n 个测试方法就执行 n 次），适合每个测试都要做的准备/清理；全局只执行一次的是 @BeforeAll/@AfterAll，且方法必须 static。
▶ 关联：这和第21章"每个任务前准备、后清理"的思路一致，只是触发时机由框架控制。

2. 反射可以访问类的私有成员，说明反射破坏了封装性。（ ）

**【答案】** 正确。

**【解析】** setAccessible(true) 可以绕过 private 权限检查读取/修改私有字段、调用私有方法，所以说反射破坏封装性。这不是鼓励乱访问，而是给框架提供通用能力（如 ORM 框架给私有字段赋值）。

3. 注解本身会直接影响程序的运行逻辑，不加解析代码也能起作用。（ ）

**【答案】** 错误。

**【解析】** 注解只是"标记"，本身不改变任何代码逻辑；必须有程序（通常通过反射）去检测注解并根据注解信息决定行为，如模拟 JUnit 中 isAnnotationPresent 判断后才 invoke。@Override 之所以有效，是编译器在帮你检查。

4. 动态代理中，InvocationHandler 的 invoke 方法返回 null 时，如果原方法有返回值，调用处会收到 null（或对应默认值拆箱异常）。

**【答案】** 正确。

**【解析】** invoke 的返回值会原样返回给代理方法的调用者。增强时如果忘了 `return method.invoke(源对象, args)` 而是返回 null，引用类型方法收到 null，int 等基本类型方法拆箱时抛 NullPointerException。所以通用写法是把原方法返回值接住并 return。

### 四、简答题

1. 简述反射的概念、学习反射的四步以及反射的主要用途。

**【答案】** 反射是加载类并以编程方式解剖类中各种成分（构造器、成员变量、方法）的机制。四步：① 获取 Class 对象（类名.class / Class.forName / 对象.getClass）；② 获取构造器 Constructor（getDeclaredConstructor，newInstance 创建对象）；③ 获取成员变量 Field（getDeclaredField，get/set 读写值）；④ 获取成员方法 Method（getDeclaredMethod，invoke 执行）。私有成员均需 setAccessible(true)。用途：获取并操作类的全部成分；破坏封装做通用访问；最重要的是做框架——主流框架都基于反射实现通用功能。

**【解析】** 记忆主线：Class 是"类的图纸"，Constructor 造对象、Field 摸属性、Method 调方法。getDeclaredXxx 拿本类全部（含私有），暴力反射后操作。
▶ 关联：反射创建对象本质还是走构造器（第7章）；invoke 调方法要传对象和实参（第4章方法调用）。

2. 自定义一个能在运行时解析的注解，需要注意哪几点？如何解析方法上的注解？

**【答案】** ① 用 @interface 声明；② 用元注解 @Target 指定可标注位置（TYPE/METHOD/FIELD 等）；③ 用 @Retention(RetentionPolicy.RUNTIME) 保证运行时存活；④ 属性用"类型 名() [default 值]"声明，只有一个 value 属性时使用可省略名。解析方法注解：先拿到 Class 对象 → getDeclaredMethods 遍历 Method → method.isAnnotationPresent(注解.class) 判断是否存在 → method.getDeclaredAnnotation(注解.class) 取出注解对象 → 调用属性方法读内容。

**【解析】** 指导思想是笔记原话："要解析谁上面的注解，就先拿到谁"——解析类拿 Class、解析方法拿 Method、解析字段拿 Field，它们都实现了 AnnotatedElement 接口。
▶ 关联：Class/Method/Field 全部来自反射，注解解析是反射的应用。

3. 什么是动态代理？代理对象的 invoke 方法中 typically 包含哪三部分逻辑？为什么说 JDK 动态代理必须基于接口？

**【答案】** 动态代理：程序运行期动态生成一个代理对象，代替原对象处理方法调用，把日志、耗时、权限、事务等额外逻辑（增强）从业务类中抽离统一处理。invoke 中三部分：前置增强（如记录开始时间、校验权限）→ `Object result = method.invoke(源对象, args)` 调用原方法 → 后置增强（如记录结束时间、打印日志），最后 return result。基于接口的原因：Proxy.newProxyInstance 生成的代理类通过实现指定接口来"拥有和原对象相同的方法"，所以源对象必须实现接口，代理对象才能被强转成该接口类型调用。

**【解析】** 代理解决的痛点：计时/日志等横切逻辑写进每个业务方法会大量冗余；交给代理后业务类只关心核心功能。
▶ 关联：接口多态（第9/12章）保证代理能替换原对象；method.invoke 是反射（本章第二节）。

### 五、代码阅读题

1. 下列代码运行后打印什么？

```java
public class Parcel {
    public static void main(String[] args) throws Exception {
        Class c1 = Parcel.class;
        Class c2 = Class.forName("Parcel");
        Class c3 = new Parcel().getClass();
        System.out.println(c1 == c2);
        System.out.println(c2 == c3);
        System.out.println(c3.getName());
        System.out.println(c3.getSimpleName());
    }
}
```

**【答案】**
```
true
true
Parcel
Parcel
```

**【解析】** 一个类被类加载器加载后，方法区/元空间中只有一份 Class 对象，三种方式拿到的是同一个对象，所以 == 比较为 true。getName 返回全类名（含包名，这里默认包所以就是 Parcel），getSimpleName 返回纯类名。
▶ 关联：Class 对象唯一，和第7章 static 成员全类一份的"方法区存储"思想呼应。

2. 下面反射代码运行报 IllegalAccessException，原因是什么？怎么改？

```java
Field fee = c.getDeclaredField("fee");
fee.set(parcel, 20.0);
```

**【答案】** fee 是私有字段，getDeclaredField 能拿到它，但直接 set 会因权限检查抛 IllegalAccessException。在 set 之前加一行：

```java
fee.setAccessible(true);
```

**【解析】** "拿得到"和"用得了"是两回事：Declared 系列方法能看到私有成员，但操作前必须暴力反射。构造器 newInstance、方法 invoke 私有成员同理。

3. 阅读代理代码，写出调用 `orderProxy.pay("SF1001")` 时的控制台输出顺序。

```java
OrderService proxy = (OrderService) Proxy.newProxyInstance(
    ProxyTest.class.getClassLoader(),
    new Class[]{OrderService.class},
    (p, method, args) -> {
        System.out.println("[日志] 开始执行：" + method.getName());
        long start = System.currentTimeMillis();
        Object r = method.invoke(orderService, args);
        System.out.println("[日志] " + method.getName() + " 耗时"
                + (System.currentTimeMillis() - start) + "ms");
        return r;
    });
```

假设原方法 pay 内部打印 `支付成功：SF1001`。

**【答案】**
```
[日志] 开始执行：pay
支付成功：SF1001
[日志] pay 耗时0ms（或个位数毫秒）
```

**【解析】** 执行顺序固定：前置增强 → method.invoke 进入原方法（打印"支付成功"）→ 回到 invoke 继续后置增强 → 返回。原方法输出夹在两行日志中间，这就是"环绕增强"。method.getName() 反射拿到方法名 pay。
▶ 关联：Lambda 实现 InvocationHandler 是第15章 Lambda 的应用（函数式接口）。

4. 注解定义如下，解析方法打印注解内容时却得到 null，最可能缺了什么？

```java
@Target(ElementType.METHOD)
public @interface Audit {
    String value();
}
// 解析处：Audit a = method.getDeclaredAnnotation(Audit.class); // 得到 null
```

**【答案】** 缺少 `@Retention(RetentionPolicy.RUNTIME)`。默认保留策略下注解运行期不可见，getDeclaredAnnotation 返回 null。补上：

```java
@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
public @interface Audit {
    String value();
}
```

**【解析】** 这是注解解析第一高频错误：注解要被反射读到，必须存活到运行时。

### 六、编程题

#### 编程题 1（基础）：快递费工具类的 JUnit 测试

**需求：** 已有快递费计算工具类 `ExpressFee`：首重 1kg 内 12 元，超出部分每 kg 5 元（不足 1kg 按 1kg 算）。请为它编写 JUnit 测试类：用 @BeforeEach 打印"用例开始"，@AfterEach 打印"用例结束"；写 3 个 @Test 方法分别测试 0.5kg（12 元）、1kg（12 元）、3.2kg（12+3×5=27 元，超出 2.2kg 按 3kg），并用断言校验。

**【答案】**

```java
public class ExpressFee {
    public static double calc(double weight) {
        if (weight <= 1.0) {
            return 12.0;
        }
        int extra = (int) Math.ceil(weight - 1.0); // 向上取整
        return 12.0 + extra * 5.0;
    }
}
```

```java
import org.junit.jupiter.api.*;

public class ExpressFeeTest {

    @BeforeEach
    public void before() {
        System.out.println("用例开始");
    }

    @AfterEach
    public void after() {
        System.out.println("用例结束");
    }

    @Test
    public void testLessThan1() {
        Assertions.assertEquals(12.0, ExpressFee.calc(0.5), "首重内计费错误");
    }

    @Test
    public void testExactly1() {
        Assertions.assertEquals(12.0, ExpressFee.calc(1.0), "1kg 计费错误");
    }

    @Test
    public void testOverweight() {
        // 3.2kg：超出 2.2kg，ceil 后 3kg，12 + 3*5 = 27
        Assertions.assertEquals(27.0, ExpressFee.calc(3.2), "续重计费错误");
    }
}
```

**【解析】** 测试方法三要素：public、无参、void + @Test；断言三参数（预期、实际、失败提示）让结果可自动判定；@BeforeEach/@AfterEach 每个用例前后都跑，3 个用例会看到 3 次"用例开始/结束"。Math.ceil 向上取整对应"不足 1kg 按 1kg"。
▶ 关联：Math.ceil 见第14章；测试独立、互不影响是 JUnit 相比 main 测试的核心优势。

#### 编程题 2（基础）：暴力反射读取私有包裹信息

**需求：** Parcel 类（快递单号、重量、寄件人）字段全部私有且只有有参构造器。不允许修改 Parcel 类，用反射创建对象并把三个字段值打印出来。

**【答案】**

```java
import java.lang.reflect.Constructor;
import java.lang.reflect.Field;

public class Parcel {
    private String no;
    private double weight;
    private String sender;

    private Parcel(String no, double weight, String sender) {
        this.no = no;
        this.weight = weight;
        this.sender = sender;
    }
}
```

```java
public class ReflectTest {
    public static void main(String[] args) throws Exception {
        Class<Parcel> c = Parcel.class;

        // 1. 暴力获取有参构造器并创建对象
        Constructor<Parcel> con =
                c.getDeclaredConstructor(String.class, double.class, String.class);
        con.setAccessible(true);
        Parcel p = con.newInstance("SF1001", 2.5, "王小明");

        // 2. 遍历所有私有字段，暴力读取
        Field[] fields = c.getDeclaredFields();
        for (Field f : fields) {
            f.setAccessible(true);
            System.out.println(f.getName() + " = " + f.get(p));
        }
    }
}
```

运行结果：
```
no = SF1001
weight = 2.5
sender = 王小明
```

**【解析】** 套路固定：getDeclaredConstructor(形参类型...) 定位构造器 → setAccessible → newInstance(实参...)；getDeclaredFields 拿全部字段 → 逐个 setAccessible → f.get(对象) 读值。字段名通过 f.getName() 动态获得，这就是"通用"的含义——换个类这段遍历代码照样能用。
▶ 关联：构造器传参顺序按定义来（第7章构造器）；private 封装被反射绕过（本节判断题2）。

#### 编程题 3（中等）：配置文件驱动创建对象

**需求：** 写一个"通知发送器"框架：配置文件 config.properties 里写 `senderClassName=SmsSender`，程序读取该配置，用反射创建对应发送器对象并调用其 send(String) 方法。再准备 SmsSender（短信）和 EmailSender（邮件）两个实现，改配置文件不改代码就能切换通知方式。

**【答案】**

```java
public interface Sender {
    void send(String message);
}

public class SmsSender implements Sender {
    @Override
    public void send(String message) {
        System.out.println("[短信] " + message);
    }
}

public class EmailSender implements Sender {
    @Override
    public void send(String message) {
        System.out.println("[邮件] " + message);
    }
}
```

config.properties：
```properties
senderClassName=EmailSender
```

```java
import java.io.FileReader;
import java.lang.reflect.Constructor;
import java.lang.reflect.Method;
import java.util.Properties;

public class SenderFramework {
    public static void main(String[] args) throws Exception {
        // 1. 读配置
        Properties prop = new Properties();
        prop.load(new FileReader("config.properties"));
        String className = prop.getProperty("senderClassName");

        // 2. 反射加载类、创建对象
        Class<?> c = Class.forName(className);
        Constructor<?> con = c.getDeclaredConstructor();
        Object sender = con.newInstance();

        // 3. 反射调用 send 方法
        Method send = c.getDeclaredMethod("send", String.class);
        send.invoke(sender, "您的包裹已签收");
    }
}
```

**【解析】** 这就是框架的核心思想：代码里不写死 new SmsSender()，类名来自配置文件，Class.forName 运行期加载，想换通知方式只改 properties。反射拿到的是 Object，调方法用 Method.invoke；因为两个实现都有 send 方法（接口约定），反射调用不会因为换类而失效。
▶ 关联：Properties 读取见第21章；接口多态见第9章；Class.forName 字符串驱动是所有 MVC/ORM 框架的雏形。

#### 编程题 4（中等）：@Audit 审计注解与解析

**需求：** 自定义注解 `@Audit("操作说明")`，只能标在方法上、运行时存活。业务类有下单、查询、退款三个方法，其中下单和退款加注解。编写解析程序：扫描业务类所有方法，凡是加了 @Audit 的，调用它并打印"审计日志：操作说明"。

**【答案】**

定义注解：

```java
import java.lang.annotation.*;

@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
public @interface Audit {
    String value();
}
```

业务类：

```java
public class OrderService {
    @Audit("用户下单")
    public void createOrder(String orderNo) {
        System.out.println("创建订单：" + orderNo);
    }

    public void queryOrder(String orderNo) {
        System.out.println("查询订单：" + orderNo);
    }

    @Audit("用户退款")
    public void refund(String orderNo) {
        System.out.println("订单退款：" + orderNo);
    }
}
```

解析并触发：

```java
import java.lang.reflect.Method;

public class AuditFramework {
    public static void main(String[] args) throws Exception {
        OrderService service = new OrderService();
        Class<?> c = service.getClass();

        for (Method m : c.getDeclaredMethods()) {
            if (m.isAnnotationPresent(Audit.class)) {
                Audit audit = m.getDeclaredAnnotation(Audit.class);
                System.out.println("审计日志 >>> " + audit.value());
                m.setAccessible(true);
                // 有参方法反射调用时传演示参数
                m.invoke(service, "SF" + System.nanoTime());
                System.out.println("-------------------");
            }
        }
    }
}
```

**【解析】** 三段式：@interface + @Target(METHOD) + @Retention(RUNTIME) 定义；isAnnotationPresent 判断；getDeclaredAnnotation 取出后 audit.value() 读注解属性。queryOrder 没注解被跳过——注解本身不做任何事，是反射解析让它"生效"。
▶ 关联：这正是笔记"模拟 JUnit"的换皮版（@MyTest→@Audit），思想完全一致：标记→扫描→反射触发。

#### 编程题 5（进阶）：动态代理给订单服务加权限校验与耗时统计

**需求：** OrderInterface 接口有 placeOrder（下单）、cancelOrder（取消）、queryOrder（查询）三个方法。要求：用 JDK 动态代理生成代理对象——调用下单、取消前先校验是否已登录（未登录抛 SecurityException 提示），查询不需要登录；每个方法执行后打印耗时。

**【答案】**

```java
public interface OrderInterface {
    void placeOrder(String orderNo);
    void cancelOrder(String orderNo);
    void queryOrder(String orderNo);
}
```

```java
public class OrderManager implements OrderInterface {
    @Override
    public void placeOrder(String orderNo) {
        System.out.println("下单成功：" + orderNo);
    }
    @Override
    public void cancelOrder(String orderNo) {
        System.out.println("取消订单：" + orderNo);
    }
    @Override
    public void queryOrder(String orderNo) {
        System.out.println("查询结果：" + orderNo + " 运输中");
    }
}
```

代理工具类：

```java
import java.lang.reflect.*;

public class OrderProxyUtil {
    public static OrderInterface createProxy(OrderInterface target, boolean loggedIn) {
        return (OrderInterface) Proxy.newProxyInstance(
                OrderProxyUtil.class.getClassLoader(),
                new Class[]{OrderInterface.class},
                new InvocationHandler() {
                    @Override
                    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
                        String name = method.getName();

                        // 前置增强：写操作需要登录
                        if ((name.equals("placeOrder") || name.equals("cancelOrder"))
                                && !loggedIn) {
                            throw new SecurityException("未登录，无权执行：" + name);
                        }

                        long start = System.currentTimeMillis();
                        Object result = method.invoke(target, args);   // 调原方法
                        long end = System.currentTimeMillis();
                        System.out.println("[耗时] " + name + " 用了 " + (end - start) + "ms");
                        return result;
                    }
                });
    }

    public static void main(String[] args) {
        OrderInterface guest = createProxy(new OrderManager(), false);
        OrderInterface member = createProxy(new OrderManager(), true);

        guest.queryOrder("SF1001");        // 未登录可查询
        member.placeOrder("SF1002");       // 登录后下单
        try {
            guest.cancelOrder("SF1001");   // 未登录取消 → 抛异常
        } catch (SecurityException e) {
            System.out.println("拦截到：" + e.getMessage());
        }
    }
}
```

运行结果：
```
查询结果：SF1001 运输中
[耗时] queryOrder 用了 0ms
下单成功：SF1002
[耗时] placeOrder 用了 0ms
拦截到：未登录，无权执行：cancelOrder
```

**【解析】** 代理三参数：类加载器、接口数组、InvocationHandler；invoke 内通过 method.getName() 区分方法做差异化增强（权限只拦写操作）；method.invoke(target, args) 是固定的"放行到原对象"写法，返回值要原样 return。权限判断、耗时统计这些横切逻辑全部集中在代理里，OrderManager 业务类干干净净——这就是 Spring AOP 的底层原理。
▶ 关联：接口与实现分离（第9章）、反射 invoke（本章第二节）、异常抛出与 try-catch（第16章）、System.currentTimeMillis 计时（第14章）。

---
