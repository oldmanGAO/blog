---
title: Java 学习笔记（完整版）
subtitle: ''
date: '2026-09-08T08:33:29+08:00'
lastmod: '2026-09-10T09:44:47+08:00'
draft: false
authors: []
description: java基础
tags:
- java笔记
categories:
- 技术
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

##  Java 学习笔记（完整版）

> 本文件由 `合并笔记.py` 将 23 个分章笔记与练习附录自动合并而成，
> 内容与分章文件一致；如需修改，请改分章文件后重新运行脚本。

![图片](https://oldergao.github.io/blog-images/images/2026/09/e89592046fb9bb0d.png)


共 24 章，涵盖 JavaSE 基础与进阶全部知识点。

## 目录

- **第一部分 · Java 基础**
  - [第1章 Java开发环境与IDEA](#第1章-java开发环境与idea)
  - [第2章 Java基础语法](#第2章-java基础语法)
  - [第三章 运算符](#第三章-运算符)
  - [第四章 方法](#第四章-方法)
  - [第五章 流程控制语句](#第五章-流程控制语句)
  - [第六章 数组](#第六章-数组)
  - [第七章：面向对象基础](#第七章面向对象基础)
  - [第八章 面向对象高级（上）：继承、Object、final、抽象类与模板模式](#第八章-面向对象高级上继承objectfinal抽象类与模板模式)
  - [第九章 面向对象高级（下）：接口、多态、代码块、内部类与 Lambda](#第九章-面向对象高级下接口多态代码块内部类与-lambda)
  - [第10章 常用 API（String、StringBuilder、ArrayList）与综合案例](#第10章-常用-apistringstringbuilderarraylist与综合案例)

- **第二部分 · JavaSE 进阶**
  - [第十一章 面向对象进阶（一）：static 与继承](#第十一章-面向对象进阶一static-与继承)
  - [第十二章 面向对象进阶（二）：多态、final、抽象类与接口](#第十二章-面向对象进阶二多态final抽象类与接口)
  - [第十三章 面向对象进阶（三）](#第十三章-面向对象进阶三)
  - [第十四章 常用 API](#第十四章-常用-api)
  - [第十五章 常见API、Lambda表达式、常见算法与正则表达式](#第十五章-常见apilambda表达式常见算法与正则表达式)
  - [第16章 异常处理与 List 集合](#第16章-异常处理与-list-集合)
  - [第17章 Set 与 Map 集合](#第17章-set-与-map-集合)
  - [第18章 JDK8 新特性：Stream 流、File 类与递归](#第18章-jdk8-新特性stream-流file-类与递归)
  - [第19章 字符集与字节流](#第19章-字符集与字节流)
  - [第20章 字符流、缓冲流与 IO 高级流](#第20章-字符流缓冲流与-io-高级流)
  - [第二十一章 特殊文件、日志技术与多线程](#第二十一章-特殊文件日志技术与多线程)
  - [第22章 网络编程](#第22章-网络编程)
  - [第23章 单元测试、反射、注解与动态代理](#第23章-单元测试反射注解与动态代理)

- **附 录**
  - [附录 A 练习题与参考答案](#附录-a-练习题与参考答案)

---

# 第一部分 · Java 基础

<div style="page-break-after: always;"></div>

## 第1章 Java开发环境与IDEA

### 课程导览：AI 新时代为什么学 Java

**AI（Artificial Intelligence，人工智能）大模型**是指具有极大规模、高度复杂性和强大能力的人工智能系统。围绕大模型的工作方向主要有：

- **开发大模型**：开发大模型本身、打造智能产品；
- **微调大模型**：用行业数据训练、优化大模型；
- **应用大模型**：信息检索、内容分析、内容生成、辅助编程（自动补全代码、生成代码片段等）。

无论哪种方向，都需要大量的软件系统来支撑，而 Java 正是企业级后台开发的主力语言。本课程为 **Java SE 基础篇**，学习路线为：Java 开发环境搭建 → IDEA 开发工具 → Java 基础语法 → 面向对象思想（封装、继承、多态、抽象类、接口），打好基础后再进入 JavaEE 企业级开发。

### 1.1 Java语言简介

Java 是由 James Gosling（詹姆斯·高斯林）于 1995 年在 Sun 公司开发的计算机高级编程语言，2009 年 Sun 公司被 Oracle（甲骨文）公司收购。高斯林 1955 年出生于加拿大，1977 年获卡尔加里大学计算机学士学位，1983 年获卡内基梅隆大学计算机博士学位，被誉为"**Java 之父**"。

#### 学习 Java 能做什么

Java 基本上什么都能做，主要用于**企业级应用开发**，常见方向：

| 方向 | 典型例子 |
| --- | --- |
| 桌面应用开发 | IDEA、Eclipse 等开发工具本身就是 Java 写的 |
| 企业级应用开发 | 微服务、大型互联网应用（Java 最主要的方向） |
| 移动应用开发 | Android 手机应用 |
| 服务器系统 | 各类应用的后台服务 |
| 大数据开发 | Hadoop 等大数据技术栈 |
| 游戏开发 | 我的世界（MineCraft） |

#### Java 三大技术平台

| 平台 | 全称 | 用途 |
| --- | --- | --- |
| JavaSE | Java Standard Edition（标准版） | 桌面应用开发，是整个 Java 技术体系的基础 |
| JavaEE | Java Enterprise Edition（企业版） | 企业级互联网应用开发（网站、后台系统等） |
| JavaME | Java Micro Edition（微型版） | 嵌入式、小型设备开发，已被淘汰，了解即可 |

学习路线：第一、二阶段先学 **JavaSE 打基础**，随后学习 JavaEE 做企业级开发。

### 1.2 JDK、JRE 与 JVM

开发 Java 程序必须先安装好 **JDK**（Java Development Kit，Java 开发工具包）。三者关系：

- **JVM**（Java Virtual Machine，Java 虚拟机）：真正运行 Java 程序的地方。
- **JRE**（Java Runtime Environment，Java 运行环境）：包含 JVM 和运行 Java 程序所需的核心类库，只能运行程序，不能开发。
- **JDK**（Java Development Kit，Java 开发工具包）：包含 JRE 以及编译、运行、调试等开发工具（javac、java 等），是 Java 开发的完整工具集。

关系：**JDK > JRE > JVM**。安装 JDK 后，就可以用 javac 编译代码、用 java 运行程序，并使用丰富的 Java 类库开发应用。

### 1.3 JDK 的下载与安装

#### 版本选择

JDK 版本很多，应选择**带有 LTS（Long Term Support，长期支持）标识的版本**。JDK 8、11、17、21 都是 LTS 版本，目前很多企业还在使用 JDK 8 / JDK 11；本课程为学习新技术使用 **JDK 21**。

#### 下载与安装

- 下载地址：<https://www.oracle.com>（在 Downloads 中选择对应操作系统的 JDK 21 安装包）。
- 安装建议：**安装路径不要带中文、不要带空格**（例如 `D:\soft\Java\jdk-21`），傻瓜式下一步安装即可。
- 检测是否安装成功：打开命令行输入 `java -version` 和 `javac -version`，都能显示版本号即成功。

#### javac、java 工具

JDK 安装目录下的 `bin` 文件夹中有两个核心工具：

- `javac.exe`：**编译工具**，把 `.java` 源文件翻译成 `.class` 字节码文件。
- `java.exe`：**运行工具**，启动 JVM 执行字节码。

我们写的 Java 程序是高级语言，计算机硬件不能直接识别，必须先经 javac 编译翻译，再由 java 执行，才能驱动机器干活。

### 1.4 常用 DOS 命令

javac、java 工具需要在 DOS 命令行中操作。

**打开方式**：按下 `Win + R`，在运行框中输入 `cmd`，回车。

常用命令：

| 命令 | 作用 |
| --- | --- |
| `盘符名:`（如 `d:`） | 切换盘符 |
| `dir` | 列出当前目录下的文件和文件夹 |
| `cd 目录名` | 进入指定目录（如 `cd Desktop`） |
| `cd ..` | 回退到上一级目录 |
| `cd \` | 直接回到盘符根目录 |
| `cls` | 清屏 |
| `↑` / `↓` | 调出之前输入过的历史命令 |
| `exit` | 退出命令行窗口 |

提示：在文件夹的地址栏中直接输入 `cmd` 回车，可以在当前目录下打开命令行；按 Tab 键可以自动补全文件名。

### 1.5 第一个 Java 程序：HelloWorld

#### 开发三步曲

**第一步：编写代码**。新建记事本文件，将扩展名改为 `.java`（建议先放在 JDK 的 bin 目录下，便于初学操作）：

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("HelloWorld");
    }
}
```

**第二步：编译代码**。打开 DOS，进入 `HelloWorld.java` 所在目录，使用 javac 编译：

```bash
javac HelloWorld.java
```

编译成功后，目录下会生成 `HelloWorld.class` 字节码文件。

**第三步：运行代码**。使用 java 命令运行，**注意运行时不要带 .class 后缀**：

```bash
java HelloWorld
```

#### 代码详解

```java
// class 关键字用于定义一个类，HelloWorld 是类名
// public 是权限修饰符（后面会详细讲解），目前先理解为：要求类名必须和文件名一致
public class HelloWorld {
    // main 方法（主方法）是程序执行的入口点，写法固定
    public static void main(String[] args) {
        // 输出语句：打印小括号中的内容，字符串用双引号包裹
        System.out.println("HelloWorld");
    }
}
```

#### 常见错误

1. **Windows 文件扩展名没有勾选**：文件实际叫 `HelloWorld.java.txt`，需在"查看"中勾选"文件扩展名"。
2. **代码写了但忘记保存**（Ctrl+S），编译的还是旧内容。
3. **文件名和类名不一致**：public 修饰的类名必须与文件名完全一致。
4. **大小写错误、单词拼写错误、使用了中文符号、找不到 main 方法**：Java 严格区分大小写，所有标点必须是英文半角。
5. **括号不配对**：大括号、小括号必须成对出现。
6. **编译或执行工具使用不当**：编译用 `javac 文件名.java`（带后缀），运行用 `java 类名`（不带 .class）。

### 1.6 Java 程序执行原理与跨平台

#### 编程语言发展历程

计算机底层是硬件电路，通过通电（1）和不通电（0）表示数据，所以计算机只认识由 0 和 1 组成的**机器语言**（如 `00011100 00110101`）。编程语言经历了三个阶段：

| 阶段 | 特点 |
| --- | --- |
| 机器语言 | 直接用二进制 0、1 编写指令，最早期程序员的编程方式，难写难记 |
| 汇编语言 | 用简短的英文助记符代替二进制指令，比机器语言好记，但仍依赖具体硬件 |
| 高级语言 | 用接近人类自然语言的方式书写（Java、C、Python 等），再由编译/解释工具翻译成机器指令，简单易学、可移植性好 |

我们编写的 Java 代码属于高级编程语言，计算机无法直接识别，需要先**编译**成计算机能理解的机器指令才能执行：

```
.java 源文件  --javac编译-->  .class 字节码文件  --java启动JVM-->  执行
```

#### 跨平台原理

- **跨平台**：写好的 Java 程序可以在任意操作系统中运行，即"**一次编译，多处运行**"。
- **原理**：在不同的操作系统上安装对应版本的 JVM（Java 虚拟机），由 JVM 屏蔽底层操作系统的差异。字节码文件运行在 JVM 上，而不是直接运行在操作系统上。

注意：C/C++ 等语言编译后直接生成与平台相关的机器码，不能跨平台；Java 正是依靠 JVM 实现跨平台。

### 1.7 Path 与 JAVA_HOME 环境变量

#### Path 环境变量的作用

**Path 环境变量用于记住程序的路径，方便在命令行窗口的任意目录启动程序。**

工作原理：在命令行输入一个程序名（如 `qq`）时，系统会先在当前目录查找该程序，找不到就去 Path 环境变量记录的路径中逐个查找，找到就启动；都找不到则报错。

配置位置：**此电脑 → 属性 → 高级系统设置 → 高级 → 环境变量**。

验证方法：配置好后一路确定，重新打开一个 DOS 窗口，在任意目录输入程序名能启动即配置成功。

#### 配置 JDK 到 Path

较新的 JDK 安装时会自动把 javac、java 的路径配置到 Path 中（老版本 JDK 不会自动配置，必须手动配置）。无论是否自动配置，都**建议自己手动配置 Path 并额外配置 JAVA_HOME**（可先删除自动生成的 JDK 条目再手动添加）：

1. 删除自动生成的 JDK 相关 Path 条目。
2. 在 Path 中新增 JDK 的 bin 目录路径，例如：

```text
D:\soft\Java\jdk-21\bin
```

#### 推荐方式：JAVA_HOME + Path

后续课程中的其他开发工具（如 Maven、Tomcat、IDEA）需要通过查找 **JAVA_HOME** 来关联 JDK，因此推荐再配置一个 JAVA_HOME：

1. 新建系统变量：

```text
变量名：JAVA_HOME
变量值：D:\soft\Java\jdk-21
```

2. 在 Path 中通过 `%JAVA_HOME%` 引用：

```text
%JAVA_HOME%\bin
```

好处：以后 JDK 升级或换路径，只改 JAVA_HOME 一处即可。

3. 校验：重新打开 DOS，输入 `javac` 和 `java -version`，正常提示即配置成功。

### 1.8 IDEA 集成开发环境

#### IDE 概念

文本编辑工具（记事本、NotePad++、EditPlus、Sublime 等）编写代码时没有错误提醒、没有智能提示，还需要自己手动编译执行，功能不够强大。

**IDE**（Integrated Development Environment，集成开发环境）把代码编写、编译、执行、调试等多种功能综合到一起，支持智能代码提示、错误提醒、项目管理等。常见的 Java IDE 有 Eclipse、MyEclipse、IntelliJ IDEA、NetBeans 等，其中 **IDEA**（全称 IntelliJ IDEA）是目前使用最多、功能最强大的 Java 集成开发环境。

#### 下载与安装

- 下载地址：<https://www.jetbrains.com/zh-cn/idea/download/>
- 建议使用课程资料中的 2024.1 版本安装包，最新版本可能存在兼容问题。
- 安装时建议修改安装路径，**路径不要带中文**。
- IDEA 默认英文界面，看不习惯时可以暂时安装中文插件，但实际工作中都是英文界面，建议尽早适应英文。

IDEA 中的 Java 程序是**自动编译和执行**的，编译后的 class 文件在工程路径下的 `out` 文件夹中。

#### 项目结构：Project → Module → Package → Class

IDEA 中管理代码分四个层级，**必须按顺序创建**：

1. **Project（工程/项目）**：建议创建空项目（Empty Project），一个项目代表一套完整的代码体系。
2. **Module（模块）**：一个 Project 中可以创建多个 Module，便于按阶段（day01、day02……）管理代码。
3. **Package（包）**：一个 Module 中可以创建多个 Package。命名建议：**公司域名倒着写 + 技术名称**，如 `com.itheima.day01`，全小写。
4. **Class（类）**：一个 Package 中可以创建多个 Class。新建类时**只写类名，不加 .java 后缀**；类名遵循**首字母大写的驼峰命名**（如 `HelloWorld`）。

练习：创建一个 JavaSEProject，里面包含 day01~day09 九个模块，在 day01 模块中新建 `hello` 包，包里新建 `HelloWorld` 类，打印一行 "Hello World"。

> 说明：**Project、Module、Package 本质上都是文件夹**，作用是分门别类地管理类文件；Class 才是真正写代码的文件。实际开发中一个大型项目（如电商系统）会按业务划分模块（商品模块、搜索模块、购物车模块、订单模块），模块内部再按前端交互、业务逻辑、数据访问等分层建包管理。本基础篇只创建一个 Project，每天的代码新建一个 Module。

#### IDEA 常用快捷键

| 快捷键 | 作用 |
| --- | --- |
| `psvm` 或 `main` + 回车 | 快速生成 main 方法 |
| `sout` + 回车 | 快速生成输出语句 |
| `Ctrl + Alt + L` | 格式化代码 |
| `Alt + Shift + ↓` | 下移当前行 |
| `Alt + Shift + ↑` | 上移当前行 |
| `Alt + 回车` | 导入包、自动修正代码 |
| `Ctrl + N` | 搜索类 |
| `Ctrl + R` | 替换文本 |
| `Ctrl + F` | 查找文本 |
| `Shift + F6` | 重构 - 重命名（标识符会同步改名） |
| `Ctrl + X` | 剪切当前行（相当于删除行） |
| `Ctrl + D` | 复制当前行到下一行 |
| `Ctrl + /` | 单行注释（再按一次取消） |
| `Ctrl + Shift + /` | 多行注释（再按一次取消） |
| `Alt + 1` | 快速打开/关闭左侧工程界面 |
| `F2` | 快速定位到下一个错误位置 |
| `Ctrl + F12` | 查看当前文件的结构 |

补充：在设置中可以开启"按住 Ctrl + 鼠标滚轮改变字体大小"。

#### 界面设置

- **主题设置**：Settings → Appearance & Behavior → Appearance → Theme（如 Darcula 深色主题）。
- **字体设置**：Settings → Editor → Font，建议字号调到一页约显示 30 行代码为宜。
- **背景设置**：可设置自定义背景图片。

#### 类、模块、项目的增删改操作

**类文件**：

- 新建：在包上右键 New → Java Class。
- 删除：选中类按 Delete，或右键 Delete。
- 修改名称：选中类后按 `Shift + F6` 重命名（不要直接改文件名）。

**模块 Module**：

- 新建模块：File → New → Module。
- 删除模块：右键模块 → Remove Module（这只是从工程中移除，硬盘文件还在；要彻底删除需再去磁盘目录手动删除）。
- 修改模块：Project Structure（`Ctrl + Alt + Shift + S`）中可修改模块信息。
- 导入模块：先把模块文件夹复制到项目目录，再通过 File → Project Structure → Modules → + → Import Module 关联；若 JDK 版本不一致需按提示修改。操作较麻烦，更简单的做法是直接新建模块再把代码复制进去。

**项目 Project**：

- 新建：File → New → Projects。
- 打开/关闭：File → Open 打开已有工程；File → Close Project 关闭当前工程。
- 删除项目：直接删除磁盘上的项目文件夹即可。

### 1.9 本章小结

1. Java 是跨平台的高级语言，跨平台靠的是不同操作系统上安装对应的 **JVM**。
2. **JDK 包含 JRE 包含 JVM**；开发必须装 JDK，课程使用 JDK 21（LTS）。
3. 开发三步：编写 `.java` → `javac 文件名.java` 编译 → `java 类名` 运行（不带 .class）。
4. Path 环境变量让程序在任意目录都能启动；推荐配置 `JAVA_HOME` 再在 Path 中引用 `%JAVA_HOME%\bin`。
5. IDEA 中按 **Project → Module → Package → Class** 四级结构管理代码，类名大驼峰、包名全小写。

---

<div style="page-break-after: always;"></div>

## 第2章 Java基础语法

### 2.1 注释

注释是在程序指定位置添加的**说明性信息**，是对代码的一种解释。

**被注释的内容不会参与程序的编译和运行。**

Java 中注释分三种：

```java
// 单行注释

/*
    多行注释
*/

/**
    文档注释（可以被 javadoc 工具解析生成帮助文档，初学阶段了解即可）
*/
```

注释的使用示例：

```java
/*
    通过 class 关键字定义了一个类，类名称叫做 HelloWorld
    public 起到限制作用，限制类名称和文件名必须保持一致
*/
public class HelloWorld {
    // main（主方法）是程序执行的入口
    public static void main(String[] args) {
        System.out.println(123);
        System.out.println("HelloWorld");      // 输出语句，打印()中包裹的内容
    }
}
```

建议：今后如果某一句代码看了 10 秒还没看懂，就给它加注释。IDEA 中可用 `Ctrl + /` 添加/取消单行注释，`Ctrl + Shift + /` 添加/取消多行注释。

### 2.2 关键字

**关键字是被 Java 赋予了特殊含义的英文单词。**

例如：

- `public`：限制作用（限制类名与文件名一致）。
- `class`：用来定义类。
- `static`、`void`、`int` 等，后续课程会陆续学习。

注意：

1. 关键字已经被 Java 赋予了特殊含义，**我们不能把它们当作类名、变量名、方法名使用**。
2. 关键字在 IDEA 中会有特殊颜色高亮。
3. Java 关键字全部是小写的。

### 2.3 字面量

**字面量就是程序中直接写出来的、固定不变的值**，是 Java 中最基础的常量形式。可以理解成"写在代码里的具体数据"——不需要任何计算或变量引用，直接就表示一个确定的值。

学习字面量，就是学习生活中的各类数据在代码中如何书写：

| 字面量类型 | 书写方式 | 举例 |
| --- | --- | --- |
| 整数类型 | 直接写数字 | `23`、`-100` |
| 小数类型 | 直接写小数 |`185.1`、`3.14` |
| 字符串类型 | 用双引号括起来 | `"张三"`、`"HelloWorld"` |
| 字符类型 | 用单引号括起来，里面只能有一个字符 | `'男'`、`'A'`、`'0'` |
| 布尔类型 | 只有两个值 | `true`（真）、`false`（假） |
| 空类型 | `null` | 不能直接打印，含义后续讲解 |

示例：将个人信息展示在控制台

```java
public class ConstantDemo {
    /*
        字面量：生活中的数据在程序中的书写格式
        需求：将个人信息展示在控制台
              姓名(字符串)、年龄(整数)、性别(字符)、身高(小数)、婚姻状况(布尔)
     */
    public static void main(String[] args) {
        System.out.println("张三");        // 字符串
        System.out.println(23);            // 整数
        System.out.println(185.1);         // 小数
        System.out.println('男');          // 字符
        System.out.println(false);         // 布尔

        // System.out.println(null);       // null 不允许直接打印，具体含义后面讲解
    }
}
```

注意区分：**字符串用双引号 `" "`，字符用单引号 `' '`，且单引号里有且只能有一个字符**。

### 2.4 变量

#### 2.4.1 变量的概念

变量就是内存中的一块区域，可以理解成一个**盒子**，用来装程序要处理的数据。变量里装的数据是可以被替换的。

**定义格式**：

```java
数据类型 变量名 = 数据值;
```

例如：

```java
int num = 10;
```

变量通过**变量名**来使用：

```java
int age = 18;

System.out.println(age);        // 打印：18
age = 20;                       // 修改
System.out.println(age + 10);   // 计算：30
```

#### 2.4.2 变量的使用案例

需求：小哈的微信钱包中有 9.5 元，出门买冰棍花了 1.5 元，又在家族群抢红包抢到 0.35 元，求现在的余额。

```java
// 钱包的钱数是小数，需要用 double 定义变量
double money = 9.5;
// 买冰棍花了 1.5 元
money = money - 1.5;
System.out.println(money);      // 8.0
// 抢红包抢到 0.35 元
money = money + 0.35;
System.out.println(money);      // 8.35
```

#### 2.4.3 变量的注意事项

**1. 变量要先声明才能使用**

```java
int age = 18;
System.out.println(age);        // 正确
System.out.println(name);       // 错误：根本没有定义 name 变量
```

**2. 变量是什么类型，就必须装什么类型的数据**

```java
int age = 18;                   // 正确：int 存整数
int num = 12.3;                 // 错误：int 类型无法存储小数
```

**3. 变量只在自己所归属的大括号 `{}` 范围内有效**（作用域）

```java
int age = 18;
System.out.println(age);        // 正确，在 main 方法范围内

{
    int a = 10;
    System.out.println(a);      // 正确，a 在内层 { } 中有效
}

System.out.println(a);          // 错误：出了 { } 访问不到 a
System.out.println(age);        // 正确
```

**4. 同一个范围内，变量名不能重复**

```java
int age = 18;                   // 正确
{
    int a = 10;                 // 正确
}
{
    int a = 10;                 // 正确：这是另一个 { } 范围，不算重复
}
int age = 20;                   // 错误：main 方法中已经有 age 了
```

**5. 变量定义时可以不赋初始值，但使用时必须有值**

```java
int age;                        // 不报错：只是定义，没有使用
// System.out.println(age);     // 编译错误：变量中没有数据
age = 10;
System.out.println(age);        // 正确：age 里已经有值了
```

**6. 一条语句可以定义多个变量，中间用逗号分隔**

```java
int a = 10, b = 20, c = 30;
```

### 2.5 标识符

标识符就是给**类、方法、变量**等起名字的符号（自己起的名字）。

#### 2.5.1 命名规则（必须遵守，否则编译报错）

1. 由**数字、字母、下划线 `_`、美元符 `$`** 组成；
2. **不能以数字开头**；
3. **不能是关键字**；
4. **区分大小写**。

```java
// 合法标识符
age、name、_num、$money、a1、HelloWorld

// 非法标识符
1name       // 以数字开头
class       // 是关键字
na me       // 含空格
```

课堂练习：判断下面哪些名字不符合规则——`bj`、`b2`、`2b`、`class`、`_2b`、`#itheima`、`ak47`、`Class`、`helloworld`。

- 非法：`2b`（数字开头）、`class`（关键字）、`#itheima`（含 `#` 特殊符号）。
- 合法：`bj`、`b2`、`_2b`（下划线开头允许）、`ak47`、`helloworld`；
  特别注意 `Class` 是合法的——Java 区分大小写，`class` 是关键字而 `Class` 不是。

#### 2.5.2 命名规范（建议遵守，不报错但显得不专业）

1. **见名知意**：如 `age`、`name`、`money`，不要用 `a`、`b`、`c`。
2. **驼峰命名**：
   - **变量名、方法名**：小驼峰，第一个单词首字母小写，其余单词首字母大写，如 `maxAge`、`studentName`。
   - **类名**：大驼峰，每个单词首字母都大写，如 `HelloWorld`、`ConstantDemo`。

### 2.6 数据类型

#### 2.6.1 两大类数据类型

Java 中的数据类型分为两种：

1. **基本数据类型**：共 8 种，存的是真正的数据值。
2. **引用数据类型**：存的是地址值，如数组、类、接口、字符串 `String` 等。

#### 2.6.2 八种基本数据类型

| 数据类型 | 关键字 | 内存占用 | 取值范围 |
| --- | --- | --- | --- |
| 整数 | `byte` | 1 字节 | -128 ~ 127 |
| 整数 | `short` | 2 字节 | -32768 ~ 32767 |
| 整数 | `int`（默认） | 4 字节 | -2147483648 ~ 2147483647（约 ±21 亿，10 位数） |
| 整数 | `long` | 8 字节 | -9223372036854775808 ~ 9223372036854775807（19 位数） |
| 浮点数（小数） | `float` | 4 字节 | 1.401298e-45 ~ 3.402823e+38（单精度） |
| 浮点数（小数） | `double`（默认） | 8 字节 | 4.9e-324 ~ 1.797693e+308（双精度，精度更高） |
| 字符 | `char` | 2 字节 | 0 ~ 65535 |
| 布尔 | `boolean` | 1 字节 | `true`、`false` |

> 浮点数范围使用科学计数法表示：`e+38` 表示乘以 10 的 38 次方，`e-45` 表示乘以 10 的负 45 次方。日常开发只需记住"float 是单精度、double 是双精度，double 范围和精度都更大"。

使用思路：

1. **整数类型变量首选 `int`**；如果 int 装不下，换成 `long`，定义 long 变量时数值后要加 `L` 标识（建议大写，小写 l 容易和 1 混淆）。
2. **小数类型变量首选 `double`**；如果非要用 `float`，数值后要加 `F` 标识。

```java
long tel = 15612341234L;       // 超过 int 范围的整数，加 L
float height = 180.1F;         // float 字面量，加 F
double score = 99.5;           // 小数默认 double，直接写
```

#### 2.6.3 练习：定义变量描述个人信息

```java
public class VariableTest {
    public static void main(String[] args) {
        String name = "张三";       // 字符串：引用类型
        int age = 23;               // 整数
        char gender = '男';         // 字符
        double height = 180.1;      // 小数
        boolean flag = true;        // 布尔

        System.out.println(name);
        System.out.println(age);
        System.out.println(gender);
        System.out.println(height);
        System.out.println(flag);
    }
}
```

### 2.7 数据类型细节补充

**1. 所有整数默认是 int 类型**

```java
System.out.println(10);
// 整数 10 是一个字面量，但也是 Java 中的一份数据；是数据就有类型，整数默认 int
```

**2. 所有小数默认是 double 类型**

```java
System.out.println(12.3);
// 12.3 是一个字面量，小数默认 double 类型
```

这也解释了为什么 `float f = 12.3;` 会报错：12.3 默认是 double（8 字节），赋值给 4 字节的 float 可能损失精度，必须写成 `12.3F`。

**3. 字符类型 char 的取值范围是 0 ~ 65535**

原因：计算机只认识二进制，字符在底层也要用数值表示，这套"字符 ↔ 数值"的对应关系称为**编码表**。最早的编码表是 **ASCII**（American Standard Code for Information Interchange，美国信息交换标准代码），规定了英文字母、数字、符号对应的数值。例如字符 `'a'`：

```text
'a' ---> 二进制 01100001 ---> 十进制 97
```

所以 char 类型的变量也可以接收整数：

```java
char c = 97;        // 等价于 char c = 'a';
System.out.println(c);   // 打印结果是 a
```

这种写法了解即可，实际开发中都直接写字符本身。常见编码值记忆：`'A'` 是 65，`'a'` 是 97，`'0'` 是 48。（中文等更复杂字符的编码 GBK、UTF-8 等在后续 IO 流章节详细讲解。）

### 2.8 本章小结

1. 注释三种：单行 `//`、多行 `/* */`、文档 `/** */`，注释不参与编译运行。
2. 关键字是 Java 保留的、全小写的特殊单词，不能用作名字。
3. 字面量是代码里直接写出的值：字符串双引号、字符单引号（仅一个字符）、布尔只有 true/false。
4. 变量格式 `数据类型 变量名 = 值;`，先声明后使用、类型匹配、在所属 `{}` 内有效、同名不重复、使用前必须有值。
5. 标识符由字母、数字、`_`、`$` 组成，不能数字开头、不能是关键字；命名要见名知意、驼峰命名。
6. 8 种基本类型：整数首选 int（超范围用 long 加 L），小数首选 double（用 float 加 F），char 存单字符，boolean 存 true/false。

---

<div style="page-break-after: always;"></div>

## 第三章 运算符

**运算符**：对变量和常量（字面量）进行操作的符号。表达式则是用运算符把变量/常量连接起来、符合 Java 语法的式子。

Java 的运算符按功能可分为：算术运算符、赋值运算符、关系运算符、逻辑运算符、三元运算符，此外还有字符串拼接、自增自减以及运算过程中的类型转换规则。

---

### 一、算术运算符

#### 1. 基本语法

| 运算符 | 含义 |
| --- | --- |
| `+` | 加法（也可用于字符串拼接，见第二节） |
| `-` | 减法 |
| `*` | 乘法 |
| `/` | 除法，取商 |
| `%` | 取余（取模），取余数 |

#### 2. 注意事项

- `/` 和 `%` 的区别：两个数做除法时，`/` 取结果的**商**，`%` 取结果的**余数**。
- 整数相除只能得到整数；要想得到小数，必须有浮点数参与运算，或者让被除数先乘以 `1.0` 提升为浮点类型。

```java
System.out.println(5 / 2);        // 结果为 2
System.out.println(5 / 2.0);      // 结果为 2.5
System.out.println(1.0 * 5 / 2);  // 结果为 2.5

System.out.println(5 % 2);        // 结果为 1
System.out.println(4 % 2);        // 结果为 0
```

#### 3. 案例：数值拆分

**需求**：将数字 123 拆分出个位、十位、百位后打印在控制台。

**分析**：

- 个位：`数值 % 10`（123 除以 10，商 12 余 3）
- 十位：`数值 / 10 % 10`（123 / 10 得 12，12 % 10 得 2）
- 百位：`数值 / 10 / 10 % 10`（123 / 10 得 12，12 / 10 得 1，1 % 10 得 1）

**公式总结**：任意一位上的数字，都可以通过"先除到位、再对 10 取余"得到。

```java
个位 ：数值 % 10
十位 ：数值 / 10 % 10
百位 ：数值 / 100 % 10        // 等价于 数值 / 10 / 10 % 10
千位 ：数值 / 1000 % 10       // 等价于 数值 / 10 / 10 / 10 % 10
...
```

---

### 二、字符串拼接（+ 的特殊用法）

- `+` 号在 Java 中如果参与数学运算，就是加法运算。
- `+` 号与字符串运算时，用作**连接符**，不进行数学运算，而是进行字符串拼接，其结果依然是一个字符串。

```java
System.out.println("abc" + 12);   // abc12

int a = 6;
System.out.println("abc" + a);          // abc6
System.out.println(a + 5);              // 11
System.out.println("itheima" + a + 'a');// itheima6a（从左到右，字符串开头，全部拼接）
System.out.println(a + 'a' + "itheima");// 6+97=103，再拼接 → 103itheima
System.out.println(a + (5 + 6));        // 17（括号内先算加法）
```

> 执行顺序从左到右：一旦某一侧是字符串，`+` 就做拼接；两侧都是数值时才做加法。`char` 参与运算时使用编码表中的数值（如 `'a'` 为 97）。

**案例：短信验证码通知**——将验证码用变量保存，通过字符串拼接把整段通知内容打印到控制台，避免把验证码写死在字符串里。

---

### 三、自增自减运算符

#### 1. 概述

- 作用：让变量的值**加 1** 或**减 1**。
- `++` 和 `--` 既可以放在变量前面，也可以放在变量后面。

#### 2. 注意事项

- **自增自减运算符只能操作变量，不能操作字面量**。

```java
// System.out.println(10++); // 编译报错
int a = 10;
System.out.println(a++);     // 合法
```

- **避免在同一个表达式中多次使用**：复杂表达式中多次自增/自减虽然 Java 有明确规则，但可读性极差，容易出错。

```java
int a = 3;
int result = a++ + ++a; // 不建议这样写！
// 解析：a 初始为 3 → a++ 先取 3（a 变为 4）→ ++a 先让 a 变为 5（再取 5）→ 结果 = 3 + 5 = 8
```

#### 3. 书写位置的区别

- `++`/`--` 在前：**先自增/自减，再使用变量**。
- `++`/`--` 在后：**先使用变量原来的值，再自增/自减**。

##### 前缀形式（`++变量` / `--变量`）

先修改变量的值，再使用变量的新值。

```java
// 前缀递增
int a = 3;
int b = ++a; // 先让 a 加 1（a 变为 4），再将 4 赋给 b
System.out.println(a); // 4
System.out.println(b); // 4

// 前缀递减
int c = 5;
int d = --c; // 先让 c 减 1（c 变为 4），再将 4 赋给 d
System.out.println(c); // 4
System.out.println(d); // 4
```

##### 后缀形式（`变量++` / `变量--`）

先使用变量原来的值，再修改变量的值。

```java
// 后缀递增
int a = 3;
int b = a++; // 先将 a 的原值 3 赋给 b，再让 a 加 1（a 变为 4）
System.out.println(a); // 4
System.out.println(b); // 3

// 后缀递减
int c = 5;
int d = c--; // 先将 c 的原值 5 赋给 d，再让 c 减 1（c 变为 4）
System.out.println(c); // 4
System.out.println(d); // 5
```

#### 4. 面试题练习

试着写出以下代码的输出结果（答案要点：抓住"每行语句执行后变量的最新值"）：

```java
// 题1
int p = 4;
int q = p-- + 2;
System.out.println(p); // 3
System.out.println(q); // 6
```

```java
// 题2
int a = 1;
int b = 2;
int c = a++ + ++b;
// a++ 取 1（a 变为 2）；++b 先让 b 变为 3 再取 3；c = 1 + 3 = 4
System.out.println(a); // 2
System.out.println(b); // 3
System.out.println(c); // 4
```

```java
// 题3
int x = 3;
x++;
int y = 3;
++y;
System.out.println(x); // 4
System.out.println(y); // 4（单独成句时，前缀后缀效果相同）
```

```java
// 题4
int c = 10;
int d = 5;
int rs3 = c++ + ++c - --d - ++d + 1 + c--;
System.out.println(rs3);
System.out.println(c);
System.out.println(d);
```

---

### 四、类型转换

**类型转换**是将一种数据类型的值转换为另一种数据类型的过程。

Java 是**强类型语言**：每个变量和表达式都有明确的类型，且类型在编译期严格检查。不同类型的变量在赋值、运算或传递时必须满足类型兼容规则，否则编译报错。类型转换分为两种：

1. **隐式转换**（自动类型转换、运算过程中的隐式提升）
2. **强制类型转换**

#### 1. 隐式转换

##### （1）自动类型转换

- 把一个**取值范围小**的数值或变量，赋值给另一个**取值范围大**的变量。
- 不需要手动操作，JVM 自动完成。

> **核心规则**：小范围类型 → 大范围类型（"向上转型"）。两种类型兼容，且目标类型"容量"大于源类型时，JVM 自动转换，无需额外代码。
>
> 记忆：类型范围小的变量，可以直接赋值给类型范围大的变量。

```java
byte a = 12;   // 源类型：byte，占 1 个字节
int b = a;     // 目标类型：int，占 4 个字节，自动转换
System.out.println(b);
```

取值范围从小到大：`byte → short → int → long → float → double`，`char` 可提升为 `int`。

**补充：计算机中的存储单位**

- 内存（RAM）由无数个"存储单元"组成，每个单元存储 1 个二进制数字（0 或 1），称为 1 个**比特（bit）**。
- **8 个比特划分为 1 个字节（Byte）**，字节是计算机存储数据的最小"可寻址单位"。每个字节都有唯一编号，即**内存地址**（类似房间号），CPU 通过地址精准定位和操作数据。

```
地址：0x0001 → 存储字节：00001010（二进制，对应十进制 10）
地址：0x0002 → 存储字节：00000110（二进制，对应十进制 6）
```

##### （2）运算过程中的隐式转换

- 取值范围小的数据和取值范围大的数据一起运算时，小的会**先提升为大的类型**，再进行运算。
- **`byte`、`short`、`char` 三种类型的数据在运算时，都会先提升为 `int`，然后再运算**。
- `char` 类型参与运算时，使用的是编码表中对应的数值。

```java
public static void main(String[] args) {
    byte a = 10;
    byte b = 20;
    byte c = a + b; // 编译报错：a + b 已提升为 int，int 赋给 byte 需要强转
}
```

`char` 参与运算时取编码值，因此结果也是 `int`：

```java
int a = 1;
char b = 'a';        // 'a' 的编码值是 97
int c = a + b;       // char 提升为 int：1 + 97
System.out.println(c);   // 98
```

#### 2. 强制类型转换

- 把一个**取值范围大**的数值或变量，赋值给**取值范围小**的变量，不允许直接赋值，需要手动加强制转换。
- **格式**：`目标数据类型 变量名 = (目标数据类型) 被强转的数据;`
- **注意：强制转换有可能造成精度损失（数据丢失），使用时要考虑清楚。**

```java
public static void main(String[] args) {
    double a = 12.3;
    // int b = a;        // 编译报错
    int b = (int) a;     // 强制转换，b 的结果为 12（小数部分直接丢弃）
}
```

#### 3. 面试题

```java
byte b1 = 3;
byte b2 = 4;
byte b3 = b1 + b2;   // 是否有错？
```

**原因**：`b1` 和 `b2` 是两个 `byte` 类型数据，相加时会直接提升为 `int`，结果是 `int`。把 `int` 结果赋给 `byte` 变量属于"大的给小的赋值"，不能直接赋值。

**改正**：

```java
byte b3 = (byte)(b1 + b2);  // 方式1：强转
int b3 = b1 + b2;           // 方式2：用 int 接收
```

再看：

```java
byte b = 3 + 4;   // 这句不报错！
```

**原因**：Java 存在**字面量优化机制**（编译期常量折叠），`javac` 编译时就会完成 `3 + 4` 的运算，字节码文件中实际是 `byte b = 7;`，7 在 byte 范围内，所以合法。

---

### 五、赋值运算符

#### 1. 基本赋值运算符

- `=` 是赋值作用：把右侧的值赋给左侧的变量。

```java
int a = 10; // 先看 "=" 右边，把数据 10 赋给左边的变量 a 存储
```

#### 2. 扩展赋值运算符

| 运算符 | 等价写法 |
| --- | --- |
| `+=` | `a = a + b` |
| `-=` | `a = a - b` |
| `*=` | `a = a * b` |
| `/=` | `a = a / b` |
| `%=` | `a = a % b` |

- 扩展赋值运算符通过特殊书写方式实现数据的累加、累乘等操作。
- **重要特点：扩展赋值运算符自带强制类型转换。**

对比以下两段代码：

```java
// 代码1：编译报错
byte x = 10;
byte y = 30;
x = x + y;   // x + y 提升为 int，赋回 byte 需要强转
```

```java
// 代码2：正常运行
byte x = 10;
byte y = 30;
x += y;      // 等价于 x = (byte)(x + y)，内部自带强转
```

---

### 六、关系运算符

关系运算符用于比较两个操作数（变量、常量或表达式）之间的关系，**运算结果始终是布尔值 `boolean`**：关系成立为 `true`，不成立为 `false`。

| 运算符 | 含义 |
| --- | --- |
| `==` | 等于（比较基本类型时值相等即为 true） |
| `!=` | 不等于 |
| `>` | 大于 |
| `>=` | 大于等于 |
| `<` | 小于 |
| `<=` | 小于等于 |

```java
int a = 5;
int b = 2;
System.out.println(a > b);   // true
System.out.println(a >= b);  // true
System.out.println(a < b);   // false
System.out.println(a <= b);  // false
System.out.println(a == b);  // false
System.out.println(a != b);  // true
```

> 注意：`==` 是比较，`=` 是赋值，二者不要混淆。

---

### 七、逻辑运算符

逻辑运算符用于连接**布尔表达式**（返回 `boolean` 的表达式），最终结果也是 `boolean` 类型。即：把多个条件放在一起判断，返回 `true` 或 `false`。

#### 1. 普通逻辑运算符

| 运算符 | 含义 | 规则 |
| --- | --- | --- |
| `&` | 逻辑与 | 两边都为 true 才是 true |
| `\|` | 逻辑或 | 两边都为 false 才是 false |
| `!` | 逻辑非 | 对布尔值取反（一元运算符） |
| `^` | 逻辑异或 | 两边结果不同为 true，相同为 false |

**特点：`&` 和 `|` 无论左边结果如何，右边表达式一定会执行。**

```java
// 逻辑 &：右边一定会执行
int e = 1;
boolean result5 = (e > 2) & (++e > 0);
System.out.println(result5); // false
System.out.println(e);       // 2（++e 执行了）

// 逻辑 |：右边一定会执行
int f = 1;
boolean result6 = (f > 0) | (++f > 2);
System.out.println(result6); // true
System.out.println(f);       // 2（++f 执行了）

// 逻辑非
boolean c = true;
System.out.println(!c);  // false
boolean d = false;
System.out.println(!d);  // true

// 逻辑异或
boolean g = true, h = false;
System.out.println(g ^ h); // true（不同）
System.out.println(g ^ g); // false（相同）
System.out.println(h ^ h); // false（相同）
```

#### 2. 短路运算符

##### 短路与 `&&`

- 左右两个布尔表达式**同时为 `true`** 时，结果才为 `true`。
- **短路特性**：若左边为 `false`，右边表达式**不会执行**（直接返回 `false`）。

```java
int a = 1;
boolean result1 = (a > 2) && (++a > 0);
System.out.println(result1); // false
System.out.println(a);       // 1（左边为 false，++a 被短路，未执行）
```

##### 短路或 `||`

- 左右两个布尔表达式**有一个为 `true`**，结果就是 `true`。
- **短路特性**：若左边为 `true`，右边表达式**不会执行**（直接返回 `true`）。

```java
int b = 1;
boolean result2 = (b > 0) || (++b > 2);
System.out.println(result2); // true
System.out.println(b);       // 1（左边为 true，++b 被短路，未执行）
```

如果左边为 `false`，右边仍会执行：

```java
int b = 1;
boolean result2 = (b < 0) || (++b > 2);
System.out.println(result2); // false（左边为 false，右边执行：b 变为 2，2 > 2 不成立）
System.out.println(b);       // 2（++b 执行了）
```

> 开发中推荐使用 `&&` 和 `||`：既能得到正确结果，又能借助短路特性避免不必要的运算（甚至避免空指针等异常）。

---

### 八、三元运算符

三元运算符（条件运算符）是 Java 中唯一的**三目运算符**，根据条件的真假执行不同表达式并返回结果。

#### 1. 基本语法

```java
条件表达式 ? 表达式1 : 表达式2
```

#### 2. 执行逻辑

1. 先计算条件表达式（结果必须是 `boolean`）。
2. 条件为 `true` → 执行表达式 1，返回其结果。
3. 条件为 `false` → 执行表达式 2，返回其结果。

#### 3. 使用场景

**（1）简单的条件判断**

```java
int a = 10;
int b = 20;
int max = (a > b) ? a : b; // 返回较大的值
System.out.println(max);   // 20
```

**（2）不同类型的兼容场景**

```java
int score = 85;
String result = (score >= 60) ? "及格" : "不及格";
System.out.println(result); // 及格
```

> 注意：表达式 1 和表达式 2 的类型必须兼容，否则编译错误。
> 错误示例：`int x = (true) ? "abc" : 123;`（String 和 int 无法兼容）。

**（3）嵌套使用（不推荐过度嵌套，影响可读性）**

```java
int num = 5;
String desc = (num > 0) ? (num > 10 ? "大于10的正数" : "10以内的正数") : "非正数";
System.out.println(desc); // 10以内的正数
```

#### 4. 案例

**案例1：成绩判断**

```java
public static void main(String[] args) {
    int score = 90;
    String res = score >= 60 ? "成绩合格" : "成绩不合格";
    System.out.println(res);
}
```

**案例2：求三个数中的最大值**

```java
public static void main(String[] args) {
    int a = 10;
    int b = 20;
    int c = 60;
    // 1. 先找出前两个数的最大值
    int tempMax = a > b ? a : b;
    // 2. 再和第三个数比较
    int max = tempMax > c ? tempMax : c;
    System.out.println("最大值为：" + max); // 60
}
```

---

### 九、运算符优先级

表达式中的运算符按照优先级从高到低执行，同级则从左到右（个别运算符从右到左，如赋值）。

```java
public static void main(String[] args) {
    int a = 10;
    int b = 20;
    System.out.println(a > b || a < b && a > b);
}
```

- 需要记住：**短路与 `&&` 的优先级高于短路或 `||`**（上式等价于 `a > b || (a < b && a > b)`）。
- 实际开发中不必死记优先级表格——**合理使用小括号 `()` 明确运算顺序**，可读性最好。

```java
System.out.println(a > b || (a < b && a > b)); // 加括号，意图清晰
```

---

### 附：Scanner 键盘录入

`Scanner` 是 Java 5 引入的工具类，可以接收用户从键盘输入的多种数据类型（整数、浮点数、字符串等）。

#### 使用步骤

1. **导入类**：代码开头写 `import java.util.Scanner;`（否则要用全类名 `java.util.Scanner`）。
2. **创建对象**：`Scanner sc = new Scanner(System.in);`，`System.in` 表示输入源是键盘。
3. **调用方法接收数据**：

| 方法 | 接收类型 |
| --- | --- |
| `nextInt()` | 整数 int |
| `nextDouble()` | 小数 double |
| `next()` | 字符串（遇到空格/Tab 结束） |
| `nextLine()` | 字符串（读取整行，遇到回车结束） |

#### 示例

```java
import java.util.Scanner;

public class Test01 {
    public static void main(String[] args) {
        // 新建一个扫描器，接收用户输入
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入您要判断的非0数字");
        int n = sc.nextInt();
        // 用三元运算符判断正负
        String res = n > 0 ? "您输入的是一个正数" : "您输入的是一个负数";
        System.out.println(res);
    }
}
```

---

### 本章小结

- `/` 取商、`%` 取余；整数相除得整数，需要小数就让浮点数参与运算。
- `+` 遇到字符串变连接符；运算顺序从左到右。
- `++`/`--` 在前先变后用，在后先用后变；只能操作变量。
- 小范围类型可自动转大范围；大范围转小范围需强转，可能丢精度；`byte/short/char` 运算时先提升为 `int`。
- 扩展赋值运算符（`+=` 等）自带强转。
- 关系运算符结果是 `boolean`；逻辑运算符连接布尔表达式，推荐用短路的 `&&`、`||`。
- 三元运算符做二选一的判断，两个结果表达式类型要兼容。
- 优先级不必死记，用小括号明确顺序。

---

<div style="page-break-after: always;"></div>

## 第四章 方法

### 一、方法的概述和好处

**方法（函数）**：一段具有独立功能的代码块，**不调用就不执行**。

**使用方法的好处**：

1. 可以把挤在一起的臃肿代码按照功能分类管理，**提高可维护性**——某个功能出问题时，只需关注对应方法内部的代码。
2. **提高代码复用性**——需要多次使用某个功能时，只需多次调用方法，不必反复编写其中的代码。

例如一个"上架商品"的功能写成 `addGoods()` 方法后：功能出错只排查这个方法；要上架多次商品，多次调用即可。

---

### 二、方法的定义和调用

学习时按三种形式循序渐进：无参无返回值 → 有参数无返回值 → 带返回值。

#### 1. 无参无返回值方法

```java
// 定义
public static void 方法名() {
    方法体
}

// 调用：直接调用
方法名();
```

**案例：求两个整数的最大值**（方法内部自己定义数据）

```java
public static void main(String[] args) {
    getMax();
}

public static void getMax() {
    int a = 10;
    int b = 20;
    int max = a > b ? a : b;
    System.out.println("最大值为:" + max);
}
```

#### 2. 有参数无返回值方法

上面的 `getMax()` 只能求 10 和 20 的最大值，想求任意两个数就得写多个方法，没有真正实现复用。可以给方法设置**形参**，调用时传入**实参**。

```java
// 定义
public static void 方法名(形参1, 形参2) {
    方法体
}

// 调用
方法名(实参1, 实参2);
```

- **形参**（形式参数）：定义方法时声明的参数，相当于方法内的变量占位符。
- **实参**（实际参数）：调用方法时实际传入的数据。

**案例：求任意两个数中的最大值**

```java
public static void main(String[] args) {
    getMax(8, 29);
}

public static void getMax(int a, int b) {
    int max = a > b ? a : b;
    System.out.println("最大值为:" + max);
}
```

#### 3. 带返回值的方法

如果 **A 方法产生的数据，B 方法想要使用**，就需要定义带返回值的方法，把结果"带出来"交给调用者。

```java
// 定义
public static 数据类型 方法名(形参1, 形参2) {
    ...
    return 返回值;
}

// 调用：用变量接收返回结果
数据类型 结果变量名 = 方法名(实参1, 实参2);
```

**案例：求任意两个数中的最大值并返回**

```java
public class MethodTest {
    public static void main(String[] args) {
        int max = getMax(10, 20);      // 用变量接收返回值
        System.out.println("最大值为:" + max);
    }

    public static int getMax(int a, int b) {
        int max = a > b ? a : b;
        return max;                    // 把结果返回给调用处
    }
}
```

---

### 三、方法的通用定义格式

方法的定义格式实际上只有一种，前面三种形式是拆开循序渐进的学习路径。完整格式如下：

```java
修饰符 返回值类型 方法名(形参列表) {
    // 方法体（需要执行的功能代码）
    return 返回值; // 若返回值类型不是 void，必须有 return
}
```

各部分说明（可以用"面包店"类比记忆）：

- **修饰符**：现阶段统一使用 `public static`。
- **返回值类型**：方法执行后返回结果的类型。
  - 不需要返回结果用 `void`；
  - 需要 `return` 返回结果时必须指定具体类型（如 `int`、`String`），且 return 的数据类型必须与声明一致。
- **方法名**：自定义名字，遵循**小驼峰命名法**（首字母小写，后续单词首字母大写，如 `getSum`、`reverseArray`），要见名知意。
- **形参列表**：可以有多个，也可以没有；多个形参用逗号隔开，**形参不能给初始化值**。如 `(int a, int b)`；不需要参数时括号留空 `()`。
- **方法体**：花括号 `{}` 中实现具体功能的代码。
  - 返回值类型不是 `void` 时，必须用 `return` 返回对应类型的结果；
  - 返回值类型是 `void` 时，可以省略 `return`（也可以写 `return;` 提前结束方法）。

| 方法的组成 | 面包店类比 |
| --- | --- |
| 参数 | 制作材料（面粉、酵母、糖……） |
| 方法体 | 使用材料干活（搅拌、烘烤……） |
| 返回值 | 成品（面包） |

---

### 四、方法练习案例

**定义方法时做到"两个明确"**：

- **明确参数**：参数的类型和数量。
- **明确返回值类型**：操作完毕后是否有结果数据——有就写对应类型，没有就写 `void`。

**调用方法时**：

- `void` 类型的方法：直接调用即可。
- 非 `void` 类型的方法：推荐用变量接收调用结果；也可以直接调用（如 `add(10, 20);`），但返回的结果会丢失，没有意义。

**调用时的内存细节**：调用带参数的方法时，实参的值会赋给形参，形参作为方法内的局部变量随方法一起压入栈内存；方法弹栈后形参随即消失。例如 `getMax(10, 20)` 执行时，栈中的 `getMax` 方法里 `num1 = 10`、`num2 = 20`；再调用 `getMax(30, 40)` 时是一次全新的压栈，`num1 = 30`、`num2 = 40`，两次调用互不影响。

**需求1：计算两个小数的和**

```java
public class MethodTest1 {
    public static void main(String[] args) {
        double sum = getSum(11.1, 22.2);
        System.out.println("sum=" + sum);
    }

    /*
        1. 明确参数：double num1, double num2
        2. 明确返回值：double
     */
    public static double getSum(double num1, double num2) {
        return num1 + num2;
    }
}
```

**需求2：计算 3 个整数的最小值**

```java
public class MethodTest1 {
    public static void main(String[] args) {
        int min = getMin(20, 10, 30);
        System.out.println("min=" + min);
    }

    /*
        1. 明确参数：int num1, int num2, int num3
        2. 明确返回值：int
     */
    public static int getMin(int num1, int num2, int num3) {
        int tempMin = num1 < num2 ? num1 : num2;
        int min = tempMin < num3 ? tempMin : num3;
        return min;
    }
}
```

**需求3：打印用户的个人信息（姓名、年龄、身高、性别）**

```java
public class MethodTest1 {
    public static void main(String[] args) {
        printUserInfo("张三", 23, 180.1, '男');
    }

    /*
        1. 明确参数：String name, int age, double height, char gender
        2. 明确返回值：void
     */
    public static void printUserInfo(String name, int age, double height, char gender) {
        System.out.println("姓名为:" + name);
        System.out.println("年龄为:" + age);
        System.out.println("身高为:" + height);
        System.out.println("性别为:" + gender);
    }
}
```

---

### 五、方法在计算机中的执行原理

#### 1. 方法与栈内存

- 方法没有被调用时，存放在**方法区**的字节码文件中。
- 方法被调用时，需要进入**栈内存**中运行。
- 栈的特点是**先进后出**（后进先出）：方法被调用时依次"压栈"，执行完毕后依次"弹栈"清除，保证了方法调用结束后内存被及时回收，避免方法累积导致内存溢出。

以下面代码为例：

```java
public class Test {
    public static void main(String[] args) {
        A();
    }

    public static void A() {
        B();
    }
    public static void B() {
        C();
    }
    public static void C() {
        System.out.println("方法的调用流程");
    }
}
```

执行过程：

1. `main` 方法先压入栈内存运行；
2. 调用顺序（压栈）：`main → A → B → C`；
3. 执行与清除顺序（弹栈）：先执行完 `C` 并清除 → 再执行完 `B` 并清除 → 再执行完 `A` 并清除 → 最后回到 `main`，程序执行完毕，`main` 也弹栈清除。

即：**最先调用的方法最后结束，最后调用的方法最先结束**。

#### 2. 案例演示1

```java
public class Test {
    public static void main(String[] args) {
        System.out.println("开始");
        getMax();
        System.out.println("结束");
    }

    public static void getMax() {
        int num1 = 10;
        int num2 = 20;
        int max = num1 > num2 ? num1 : num2;
        System.out.println(max);
    }
}
```

输出顺序：`开始` → `20`（getMax 压栈执行后弹栈）→ `结束`。

#### 3. 案例演示2

```java
public class Demo2Method {
    public static void main(String[] args) {
        study();
    }

    public static void study() {
        eat();
        System.out.println("学习");
        sleep();
    }

    public static void eat() {
        System.out.println("吃饭");
    }

    public static void sleep() {
        System.out.println("睡觉");
    }
}
```

执行流程：`main` 压栈 → 调用 `study` 压栈 → `study` 中先调用 `eat`（压栈、打印"吃饭"、弹栈）→ 回到 `study` 打印"学习" → 调用 `sleep`（压栈、打印"睡觉"、弹栈）→ `study` 弹栈 → `main` 弹栈。

输出：

```text
吃饭
学习
睡觉
```

---

### 六、方法的注意事项

1. **方法不调用就不执行**。
2. **方法与方法之间是平级关系，不能嵌套定义**（不能在一个方法的方法体里再定义另一个方法）。
3. **方法的编写顺序和执行顺序无关**（执行顺序由调用顺序决定）。
4. 返回值类型为 `void` 表示没有返回值：可以省略 `return` 语句；如果写 `return`，后面不能跟具体数据（`return;` 仅表示提前结束方法）。
5. **`return` 语句下面不能再写代码**——一旦执行到 `return`，当前方法立即停止并返回，后续代码永远执行不到，属于无效代码，编译也会报错。

---

### 七、方法重载（Overload）

#### 1. 定义

一个类中，出现多个**方法名称相同**、但**形参列表不同**的方法，这些方法就称为方法重载。

```java
public class MethodOverLoad {
    public static void main(String[] args) {
        test();
        test(3);
    }

    public static void test() {
        System.out.println("---test1---");
    }

    public static void test(int a) {
        System.out.println("---test1---" + a);
    }
}
```

#### 2. 重载的判断规则

- 只要**方法名相同、形参列表不同**，就是方法重载；与修饰符、返回值类型是否相同无关（返回值类型不同不构成重载的区别条件）。
- **形参列表不同**指的是：形参的**个数、类型、顺序**不同，**不关心形参的名称**。

> 注意：同类型参数交换顺序不算重载（如 `(int a, int b)` 与 `(int b, int a)` 完全一样）；只有**不同类型**的参数顺序不同才算重载，如 `(int a, double b)` 和 `(double a, int b)`。

**判断练习**（判断下面每组方法是否构成重载）：

```java
// ① 仅返回值类型不同 —— 不是重载！参数列表完全一样，编译报错
public static void fn(int a) {}
public static int fn(int a) { return 1; }

// ② 参数类型不同 —— 是重载
public static void fn(int a) {}
public static int fn(double a) { return 1; }

// ③ 参数个数不同 —— 是重载
public static float fn(int a) { return 1; }
public static int fn(int a, int b) { return 1; }

// ④ 分别在两个类中 —— 不是重载！重载必须发生在同一个类中
class MethodDemo01 { public static void fn(int a) {} }
class MethodDemo02 { public static int fn(double a) { return 1; } }

// ⑤ 参数类型顺序不同 —— 是重载
public static void fn(int a, double b) {}
public static void fn(double a, int b) {}

// ⑥ 仅形参名字不同 —— 不是重载！(int a, double b) 和 (int c, double d) 本质一样
public static void fn(int a, double b) {}
public static void fn(int c, double d) {}
```

**重载的好处**：不用记忆过多繁琐的方法名字。JDK 中最常见的例子就是 `System.out.println()`：

```java
System.out.println(10);      // 调用参数为 int 的版本
System.out.println(10.1);    // 调用参数为 double 的版本
System.out.println(true);    // 调用参数为 boolean 的版本
System.out.println("字符串"); // 调用参数为 String 的版本
```

调用方法时，Java 虚拟机会根据传入参数的不同（个数、类型、顺序）自动区分调用哪个同名方法。

```java
public class MethodOverLoad {
    public static void main(String[] args) {
        System.out.println(add(1, 2));       // 调用两个 int 的版本
        System.out.println(add(1, 2, 3));    // 调用三个 int 的版本
        System.out.println(add(1.5, 2.5));  // 调用两个 double 的版本
        System.out.println(add(2, 3.5));    // 调用 int + double 的版本
    }

    // 1. 两个 int 相加
    public static int add(int a, int b) {
        return a + b;
    }

    // 2. 三个 int 相加（个数不同）
    public static int add(int a, int b, int c) {
        return a + b + c;
    }

    // 3. 两个 double 相加（类型不同）
    public static double add(double a, double b) {
        return a + b;
    }

    // 4. int 和 double 相加（类型顺序不同）
    public static double add(int a, double b) {
        return a + b;
    }

    // 5. double 和 int 相加（类型顺序不同）
    public static double add(double a, int b) {
        return a + b;
    }
}
```

#### 3. 应用场景

开发中经常需要为同一类业务提供多种解决方案，用方法重载来设计非常专业：调用时通过**参数的不同**来自动区分调用哪个方法。

**案例：武器发射系统**

需求：

1. 默认发射一枚武器；
2. 可以指定地区发射一枚武器；
3. 可以指定地区发射多枚武器。

```java
public class MethodOverLoad {
    public static void main(String[] args) {
        fire();
        fire("米国");
        fire("小日子", 10000);
    }

    private static void fire() {
        System.out.println("默认给岛国发射1枚武器");
    }

    private static void fire(String country) {
        System.out.println("给" + country + "发射1枚武器");
    }

    private static void fire(String country, int number) {
        System.out.println("给" + country + "发射" + number + "枚武器");
    }
}
```

---

### 附：IDEA 集成 AI 编程插件（通义灵码）

IDEA 可以集成 AI 辅助编程插件（如阿里巴巴通义灵码，官网 https://lingma.aliyun.com/lingma/download ），安装后可以根据注释自动生成方法代码，大幅提升编码效率。

但入门打基础阶段如果过度依赖 AI，会导致根基不稳、后续学习受阻。建议学习期间**暂时禁用 AI 插件**，等基础打牢后再开启使用。

---

### 本章小结

- 方法是具有独立功能的代码块，不调用不执行；好处是可维护性和复用性。
- 定义方法"两个明确"：明确参数（类型、个数）、明确返回值类型（有结果写类型，没有写 `void`）。
- 调用方式：`void` 方法直接调用；有返回值的方法推荐用变量接收。
- 方法运行在栈内存中：调用压栈、执行完弹栈，先进后出。
- 方法之间平级，不能嵌套定义；`return` 后不能写代码。
- 方法重载：同类中方法名相同、形参列表（个数/类型/顺序）不同；与返回值类型、形参名无关。

---

<div style="page-break-after: always;"></div>

## 第五章 流程控制语句

流程控制语句的作用是**控制程序代码的执行顺序**。程序中最经典的三种执行结构：

1. **顺序结构**：自上而下依次执行代码，遇到异常会停止后续代码的执行。
2. **分支结构**：根据条件选择对应的代码执行。
3. **循环结构**：控制某段代码重复执行。

---

### 一、顺序结构

顺序结构是程序默认的执行方式：代码从上到下依次执行，没有任何跳转或判断。它是所有程序的基础，大多数简单代码都遵循此结构。

```java
public class OrderDemo {
    public static void main(String[] args) {
        int a = 10;  // 第一步执行
        int b = 20;  // 第二步执行
        int sum = a + b;  // 第三步执行
        System.out.println(sum);  // 第四步执行（输出30）
    }
}
```

---

### 二、分支结构

分支结构用于**根据条件判断执行不同的代码块**，主要有 `if-else` 和 `switch-case` 两种。

#### 2.1 if-else 结构

根据判断条件（布尔表达式）的结果（`true` / `false`）执行不同分支。

##### 2.1.1 单分支 if

语法格式：

```java
if (条件表达式) {
    // 条件为true时执行的代码块
}
```

执行流程：首先判断条件表达式的结果，为 `true` 执行语句体，为 `false` 就不执行。

```java
public class IfDemo1 {
    public static void main(String[] args) {
        double score = 85.5;

        // 单分支：仅当分数>=60时提示成绩及格
        if (score >= 60) {
            System.out.println("恭喜，成绩及格了！");
        }
        System.out.println("程序结束了！");
    }
}
```

注意事项：if 语句中，如果大括号控制的只有一行代码，则大括号可以省略不写（但不推荐）。

```java
if (score >= 60) System.out.println("恭喜，成绩及格了！");
```

##### 2.1.2 双分支 if-else

语法格式：

```java
if (条件表达式) {
    // 条件为true时执行的代码块1
} else {
    // 否则执行的代码块2
}
```

执行流程：判断条件为 `true` 时执行代码块 1，否则执行 else 的代码块 2。

```java
public class IfDemo2 {
    public static void main(String[] args) {
        double score = 85.5;

        if (score >= 60) {
            System.out.println("恭喜，成绩及格了！");
        } else {
            System.out.println("没及格，好好努力吧~~~");
        }

        System.out.println("程序结束了！");
    }
}
```

##### 2.1.3 多分支 if-else if-else

语法格式：

```java
if (条件1) {
    // 条件1为true时执行
} else if (条件2) {
    // 条件1为false，条件2为true时执行
} else if (条件3) {
    // 条件2为false，条件3为true时执行
}
...
else {
    // 所有条件都为false时执行（可选）
}
```

执行流程：

- 先判断条件 1 的值，为 `true` 则执行语句体 1，分支结束；为 `false` 则判断条件 2；
- 条件 2 为 `true` 就执行语句体 2，分支结束；为 `false` 就继续判断条件 3；
- 以此类推；如果没有任何条件为 `true`，就执行 else 分支。

```java
// 判断一个int类型的数，是正数、负数还是零
int num = 5;
if (num > 0) {
    System.out.println("正数");
} else if (num < 0) {
    System.out.println("负数");
} else {
    System.out.println("零");
}
```

##### 2.1.4 案例练习

**案例 1：成绩判断**

需求：键盘录入考试成绩，根据成绩所在的区间，程序打印出不同的奖励机制（95~100 山地自行车一辆；90~94 游乐场玩一次；80~89 变形金刚玩具一个；80 以下胖揍一顿）。

分析：使用 Scanner 录入成绩并用变量 score 接收，使用 `if...else if...else` 组织逻辑。

```java
Scanner sc = new Scanner(System.in);
System.out.println("请输入考试成绩：");
int score = sc.nextInt();
if (score >= 95 && score <= 100) {
    System.out.println("山地自行车一辆");
} else if (score >= 90 && score <= 94) {
    System.out.println("游乐场玩一次");
} else if (score >= 80 && score <= 89) {
    System.out.println("变形金刚玩具一个");
} else {
    System.out.println("胖揍一顿");
}
```

**案例 2：密码校验**

需求：键盘录入用户名和密码，如果用户名为"小哈"、密码为"123456"，输出登录成功，否则输出用户名或密码有误。

分析：使用 Scanner 录入数据，使用 `if...else` 组织逻辑。

注意：字符串的比较比较特殊（应使用 `equals` 方法），后续课程介绍。

**案例 3：是否为会员**

需求：键盘输入数字，输入 1 是 VIP 会员，输入 2 是非 VIP 会员，其他数字提醒输入错误。使用 Scanner 录入命令，用 `if...else if...else` 组织逻辑。

##### 2.1.5 if 语句注意事项

1. if 语句中，如果大括号控制的只有一条语句，大括号可以省略不写（但不推荐，容易出错）。
2. if 语句的 `( )` 和 `{ }` 之间**不要写分号**——写了分号表示 if 体是空语句，后面的大括号代码会变成无条件执行。
3. if 语句的 `( )` 中必须产生 **boolean 类型**的结果（`true`/`false`），Java 不像 C 语言那样可以用 0/1 代替。

```java
// 错误示范：() 和 { 之间多了分号，if 实际控制的是空语句
if (score >= 60); {
    System.out.println("及格"); // 无论条件真假都会执行！
}
```

##### 2.1.6 面试点（结合 Debug 演示）

**连续写多个 if 和 if-else if-else 的区别是什么？**

- 连续写多个 if：所有的 if 语句都要判断一遍；
- `if-else if-else`：只需要匹配一个 `true`，后面的条件不再进行判断，效率更高。

#### 2.2 switch-case 分支结构

用于多值匹配的分支选择：根据表达式的值匹配 `case` 后的常量，执行对应代码块。

##### 2.2.1 语法格式与执行流程

```java
// 表达式类型：byte、short、int、char、枚举（JDK5+）、String（JDK7+）
switch (表达式) {
    case 值1:
        // 表达式等于常量1时执行
        break;  // 跳出switch（不写会"穿透"到下一个case）
    case 值2:
        // 表达式等于常量2时执行
        break;
    ...
    default:  // 所有case都不匹配时执行（可选）
        // 执行语句
        break;
}
```

执行流程：

- 先计算表达式的值，再拿着这个值去与 case 后的值匹配；
- 与哪个 case 匹配成功就执行哪个 case 块的代码，遇到 break 就跳出 switch；
- 如果全部 case 都不匹配，则执行 default 块的代码。

案例：用户输入 1-7 的整数，输出对应的星期几。

```java
Scanner sc = new Scanner(System.in);
System.out.println("请输入1~7之间的任意命令");
int num = sc.nextInt();
switch (num) {
    case 1:
        System.out.println("周一：埋头苦干，解决bug");
        break;
    case 2:
        System.out.println("周二：请求大牛程序员帮忙");
        break;
    case 3:
        System.out.println("周三：今晚啤酒、龙虾、小烧烤");
        break;
    case 4:
        System.out.println("周四：主动帮助新来的女程序解决bug");
        break;
    case 5:
        System.out.println("周五：今晚吃鸡");
        break;
    case 6:
        System.out.println("周六：与王婆介绍的小芳相亲");
        break;
    case 7:
        System.out.println("周日：郁郁寡欢、准备上班。");
        break;
    default:
        System.out.println("你输入的命令不符合要求，请输入1~7之间的数字！");
        break;
}
```

##### 2.2.2 注意事项

- 表达式类型只能是 `byte`、`short`、`int`、`char`；JDK5 开始支持枚举，JDK7 开始支持 `String`；**不支持 `double`、`float`、`long`**。
- case 给出的值不允许重复，且只能是**字面量**，不能是变量。
- 正常使用 switch 时不要忘记写 break，否则会出现**穿透现象**。

**if 与 switch 的选用**：

- `if` 适合条件是**区间判断**的情况（如成绩 90~94 分）；
- `switch` 适合条件是**比较值**的情况，代码更优雅、性能较好（直接按值跳转匹配）。

##### 2.2.3 switch 穿透性

当多个 case 分支的代码相同时，可以把相同的代码放到一个 case 块中，其他 case 块通过穿透性落到该 case 块执行，简化代码。

案例：输入月份（如"一月""二月"），输出对应季节（春 3-5 月，夏 6-8 月，秋 9-11 月，冬 12-2 月）。

```java
import java.util.Scanner;

public class SwitchSeasonDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入月份（如：一月、二月）：");
        String month = sc.next(); // 获取用户输入的字符串

        switch (month) {
            case "三月":
            case "四月":
            case "五月":
                // 多个case共用一个执行体（利用穿透性）
                System.out.println(month + "是春季");
                break;
            case "六月":
            case "七月":
            case "八月":
                System.out.println(month + "是夏季");
                break;
            case "九月":
            case "十月":
            case "十一月":
                System.out.println(month + "是秋季");
                break;
            case "十二月":
            case "一月":
            case "二月":
                System.out.println(month + "是冬季");
                break;
            default:
                System.out.println("输入错误！请输入正确的月份（如：一月）");
                break;
        }
    }
}
```

---

### 三、Debug 断点调试工具

**Debug** 是供程序员使用的程序调试工具，可以用来查看程序的执行流程，也可以追踪程序的执行过程来调试程序、定位问题。

Debug 调试又称为**断点调试**：断点（breakpoint）其实是一个标记，告诉 Debug 从标记的位置开始查看。

#### 3.1 使用步骤

1. **加断点**：在代码行号后面单击，出现红点即断点成功；再点一次红点可取消断点。
   - 断点加在想看的那一行（想看循环就加在循环体第一行）。
2. **以 Debug 方式运行**：右键选择 `Debug '类名.main()'`（或点击主方法旁的绿色虫子图标），程序运行到断点处会停下来。
3. **控制执行**（IDEA 常用按钮/快捷键）：

| 操作 | 快捷键 | 作用 |
| --- | --- | --- |
| Step Over（步过） | F8 | 程序向下执行一步，不进入方法内部 |
| Step Into（步入） | F7 | 进入当前行调用的方法内部查看 |
| Step Out（步出） | Shift+F8 | 跳出当前方法，回到调用处 |
| Resume Program（恢复） | F9 | 继续运行到下一个断点（没有断点则直接跑完） |
| Stop（结束） | Ctrl+F2 | 结束 Debug 模式 |

4. **观察窗口**：
   - **Variables（变量区）**：实时查看变量的变化过程；
   - **Frames（栈帧区）**：查看正在执行的方法（方法调用链）；
   - **Console（控制台）**：查看输出内容。

#### 3.2 Debug 的价值

- 循环执行了几次、每次变量怎么变，单步执行一目了然；
- 方法之间的调用顺序（谁调谁）可以在 Frames 窗口清楚看到；
- 程序结果不对时，用 Debug 逐行对比"自己以为的执行流程"和"真实执行流程"，很快就能定位错误。

---

### 四、循环结构

循环结构用于重复执行某段代码，直到满足终止条件。Java 提供三种循环：`for`、`while`、`do-while`。

#### 4.1 for 循环

适合**已知循环次数**的场景，结构清晰。

##### 4.1.1 语法格式

```java
for (初始化表达式; 循环条件; 迭代语句) {
    // 循环体（条件为true时执行）
}
```

- **初始化表达式**：声明循环计数器变量并赋初始值，**只执行 1 次**。变量名行业通用 `i`、`j`、`k`（index 的缩写）。
- **循环条件（条件判断表达式）**：必须是布尔值（true/false），是循环的"执行开关"，满足条件就执行，不满足就跳出。
- **迭代语句（步进表达式）**：循环体执行完毕后**必然执行**的代码，用于更新计数器，如 `i++`、`i+=2`、`i--`。
- **循环体**：被 `{}` 包裹的核心业务逻辑。循环体只有一行代码时 `{}` 可省略，但推荐永远写 `{}`。

##### 4.1.2 执行流程

初始化 → 判断条件（true 则执行循环体）→ 迭代 → 重复判断……

```java
// 输出3次HelloWorld
for (int i = 0; i < 3; i++) {
    System.out.println("Hello World");
}
```

执行步骤：

1. 初始化 `int i = 0`（只执行 1 次）；
2. 判断 `0 < 3` → true → 打印 HelloWorld；
3. 迭代 `i++` → i 变成 1；
4. 判断 `1 < 3` → true → 打印；
5. 迭代 → i 变成 2；
6. 判断 `2 < 3` → true → 打印；
7. 迭代 → i 变成 3；
8. 判断 `3 < 3` → false → 结束循环。

##### 4.1.3 案例练习

**案例 1：求和** —— 求 1-5 之间的数据和并输出。

```java
int sum = 0;
for (int i = 1; i <= 5; i++) {
    sum += i;
}
System.out.println("1~5的和是：" + sum); // 15
```

**案例 2：求奇数的和** —— 求 1-10 之间的奇数和并输出。

```java
int sum = 0;
for (int i = 1; i <= 10; i++) {
    if (i % 2 != 0) {
        sum += i;
    }
}
System.out.println("1~10的奇数和是：" + sum); // 25
```

**案例 3：模拟计时器** —— 设计方法 timer，先打印 1~3，再打印 3~1，最后 10 秒倒计时（"倒计时：10秒"……"倒计时：1秒"，结束打印"下课啦~~~"）。

```java
public static void timer() {
    System.out.println("------1~3------");
    for (int i = 1; i <= 3; i++) {
        System.out.println(i);
    }
    System.out.println("------3~1------");
    for (int i = 3; i >= 1; i--) {
        System.out.println(i);
    }
    System.out.println("------10秒倒计时下课------");
    for (int i = 10; i >= 1; i--) {
        System.out.println("倒计时：" + i + "秒");
    }
    System.out.println("下课啦~~~");
}
```

**案例 4：打印水仙花数** —— 设计方法 printNarcissisticNumber，输出所有"水仙花数"并统计个数。

水仙花数：一个三位数，其各位数字的立方和等于该数本身（如 153 = 1³ + 5³ + 3³）。示例：153、370、371、407。

提示：循环变量从 100 到 999；拆分百位（`num/100`）、十位（`num/10%10`）、个位（`num%10`）；计算立方和，等于自身则输出。

```java
public class Test {
    public static void main(String[] args) {
        printNarcissisticNumber();
    }

    private static void printNarcissisticNumber() {
        int count = 0; // 定义计数器
        for (int i = 100; i <= 999; i++) {
            int bai = i / 100;        // 百位
            int shi = i / 10 % 10;    // 十位
            int ge = i % 10;          // 个位
            int sum = bai * bai * bai
                    + shi * shi * shi
                    + ge * ge * ge;
            if (sum == i) {
                System.out.println(i);
                count++;
            }
        }
        System.out.println("100~999之间的水仙花数有：" + count + "个");
    }
}
```

##### 4.1.4 注意事项

1. 循环 `{ }` 中定义的变量，在**每一轮循环结束后**都会从内存中释放（下一轮重新定义）。
2. 循环 `( )` 中定义的变量，在**整个循环结束后**从内存中释放，循环外不能再使用。
3. 循环的 `( )` 和 `{ }` 之间**不要写分号**——写了分号表示循环体是空语句，后面大括号里的代码只执行一次，不再受循环控制。

```java
// 错误示范：() 和 { 之间多了分号
for (int i = 1; i <= 5; i++); {
    System.out.println("HelloWorld"); // 只会打印一次！
}
```

**编码思路积累**：

- 今后遇到"求 xxx 的和"类需求，立刻联想到**求和变量 `sum`**（循环外初始化为 0，循环中累加）；
- 遇到"统计 xxx 的个数"类需求，立刻联想到**计数器变量 `count`**（循环外初始化为 0，满足条件就 `count++`）。

#### 4.2 循环嵌套

##### 4.2.1 定义与特点

循环嵌套指**在一个循环的循环体中，完整地写了另一个循环**。外层的叫外层 for 循环，内层的叫内层 for 循环。

核心特点（重中之重）：**外循环控制行数，内循环控制列数**。

嵌套循环可以多层，但开发中最多用两层，三层及以上极少用（效率低）。

##### 4.2.2 语法格式与执行规律

```java
// 外层for循环
for (初始化外变量; 外循环条件; 外循环迭代) {
    // 内层for循环（是外层循环体的一部分）
    for (初始化内变量; 内循环条件; 内循环迭代) {
        // 内层循环体：真正要重复执行的核心代码
    }
}
```

核心执行规律：**外循环走 1 次，内循环跑完整 1 圈（执行全部次数）**。

完整步骤：

1. 执行外层循环的初始化表达式（只执行 1 次）；
2. 判断外层循环条件，为 `false` 则整个嵌套循环结束；为 `true` 则执行外层循环体；
3. 进入外层循环体后，执行内层循环的完整流程，直到内层条件为 `false`，内层循环彻底结束；
4. 内层循环结束后，执行外层循环的迭代表达式；
5. 回到步骤 2 重复判断，直到外层条件为 `false`，整个嵌套循环结束。

##### 4.2.3 案例

**案例 1：打印矩形** —— 打印 3 行 5 列的星号矩形。

```
*****
*****
*****
```

```java
public class Test1 {
    public static void main(String[] args) {
        // 外层循环：控制行数，打印3行
        for (int i = 1; i <= 3; i++) {
            // 内层循环：控制每行的列数，每行打印5个星号
            for (int j = 1; j <= 5; j++) {
                System.out.print("*"); // print 不换行，核心！
            }
            System.out.println(); // 内层循环结束后换行
        }
    }
}
```

**案例 2：打印直角三角形** —— 打印 5 行直角三角形。

与矩形的区别：**每行打印的星号数量和当前行数一致**（第 n 行打印 n 个星号），关键是内层条件 `j <= i`。

```java
public class Test2 {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= i; j++) { // 关键：j <= i
                System.out.print("*");
            }
            System.out.println(); // 换行
        }
    }
}
```

#### 4.3 while 循环

适合**循环次数不确定**的场景：先判断条件，条件为 `true` 才执行循环体。

##### 4.3.1 语法格式

```java
初始化变量;
while (循环条件) {
    循环体;  // 条件为 true 时执行的代码块
    迭代语句;
}
```

##### 4.3.2 执行流程

概括为"判断 → 执行 → 迭代自增 → 再判断"：

```java
int i = 0;
while (i < 3) {
    System.out.println("Hello World");
    i++;
}
System.out.println("循环结束！");
```

1. 循环开始，执行 `int i = 0`（一次）；
2. i=0，判断 `0 < 3` 为 true，进入循环体输出 HelloWorld，执行 `i++`；
3. i=1，判断 `1 < 3` 为 true，输出，`i++`；
4. i=2，判断 `2 < 3` 为 true，输出，`i++`；
5. i=3，判断 `3 < 3` 为 false，循环结束，输出"循环结束"。

##### 4.3.3 案例

**案例 1：累加求和** —— 计算 1 到 100 的和。

```java
int sum = 0;
int i = 1;
while (i <= 100) {
    sum += i;
    i++;
}
System.out.println("1~100的和是：" + sum); // 5050
```

**案例 2：水仙花数**（while 版本）

```java
int count = 0; // 计数器
int num = 100;
while (num <= 999) {
    int bai = num / 100;
    int shi = num / 10 % 10;
    int ge = num % 10;
    int sum = bai * bai * bai
            + shi * shi * shi
            + ge * ge * ge;
    if (sum == num) {
        System.out.println(num);
        count++;
    }
    num++; // 迭代自增，继续下一次循环
}
System.out.println("100~999之间的水仙花数有：" + count + "个");
```

**案例 3：折纸叠到珠穆朗玛峰的高度**

需求：珠峰高度 8848.86 米，一张纸厚度 0.1 毫米，每对折一次厚度 ×2，问折叠多少次能达到珠峰高度？

分析：单位要统一（0.1 毫米 = 0.0001 米）；核心规律是对折 n 次后厚度 = 初始厚度 × 2ⁿ。

```java
public static void main(String[] args) {
    double paperThickness = 0.0001; // 初始厚度 0.1毫米 = 0.0001米
    double zhuFengHeight = 8848.86; // 珠峰高度，单位米
    int count = 0; // 对折次数计数器

    while (paperThickness < zhuFengHeight) {
        paperThickness *= 2; // 对折一次，厚度翻倍
        count++;
    }

    System.out.println("对折次数：" + count + " 次");
    System.out.println("此时纸张厚度：" + paperThickness + " 米");
    System.out.println("超过珠峰高度：" + (paperThickness - zhuFengHeight) + " 米");
}
```

#### 4.4 do-while 循环

核心特点是**先执行循环体，后判断循环条件**，因此**循环体至少执行一次**。适用于"循环体必须先执行一次"的场景（如用户输入验证、菜单交互）。

语法格式（注意末尾的分号）：

```java
初始化语句;
do {
    循环体;   // 需要重复执行的代码块
    迭代语句;
} while (循环条件);  // 注意末尾的分号！
```

执行流程：

- 首先执行 do 后的循环体（**首次执行不判断条件**）；
- 执行迭代语句；
- 用新的值判断循环条件：为 true 继续执行循环体，为 false 立即停止。

```java
// 以下代码会打印一句 "你好AI智能体开发~~~"
public static void main(String[] args) {
    int i = 5;
    do {
        System.out.println("你好AI智能体开发~~~");
        i++;
    } while (i <= 5);
}
```

#### 4.5 三种循环的区别

- for 和 while：**先判断后执行**；do-while：**先执行后判断**。
- for 和 while 的执行流程一模一样，功能上无区别，for 能做的 while 也能做，反之亦然。
- 使用规范：**已知循环次数建议用 for；不清楚循环多少次建议用 while**。
- 其他区别：for 循环中控制循环的变量只在循环中使用；while 循环中控制循环的变量在循环后还可以继续使用。

```java
int num = 0;
while (num < 3) {
    System.out.println(num);
    num++;
}
System.out.println(num + 3); // 6，num 在循环外仍可使用

for (int i = 0; i < 3; i++) {
    System.out.println(i);
}
// System.out.println(i); // 报错：i 在循环外已释放，无法访问
```

#### 4.6 跳转关键字 break、continue

`break` 和 `continue` 都是用于**改变程序执行流程**的跳转语句，但作用场景和效果有本质区别。

形象理解（10 个大枣）：

- **break**：吃到第 3 个发现有虫子，剩余的枣全部放弃不吃了 —— 跳出并结束**当前所在循环**或 switch 语句。
- **continue**：吃到第 3 个发现有虫子，丢掉当前这个，继续吃其他的 —— 跳出当前循环的**当次**执行，直接进入下一次。

注意事项：

- break：只能用于结束所在循环，或结束所在 switch 分支的执行。
- continue：只能在循环中使用。
- **循环嵌套时，break/continue 默认只作用于内层循环**；如果想直接结束/跳过外层循环，可以给循环加**标号（label）**配合使用：

```java
outer:
for (int i = 1; i <= 5; i++) {
    for (int j = 1; j <= 5; j++) {
        if (j == 3) {
            break outer; // 直接结束外层循环（不写 outer 则只结束内层）
        }
        System.out.println(i + "-" + j);
    }
}
```

##### 4.6.1 break

立即终止当前所在的循环（for/while/do-while）或 switch-case 结构，跳出后执行该结构后面的代码。

示例：打印 1~10，打印到 6 就停止。

```java
public static void main(String[] args) {
    for (int i = 1; i <= 10; i++) {
        System.out.println("检查数字：" + i);
        if (i == 6) {
            System.out.println("找到目标~~~~~~~~：" + i);
            break; // 跳出当前for循环
        }
    }
    System.out.println("循环结束");
}
```

输出：

```
检查数字：1
检查数字：2
检查数字：3
检查数字：4
检查数字：5
检查数字：6
找到目标~~~~~~~~：6
循环结束
```

##### 4.6.2 continue

仅跳过当前循环迭代的剩余代码，直接进入下一次循环的判断（不会终止整个循环）。

示例：打印 1~10 中的奇数。

```java
public static void main(String[] args) {
    for (int i = 1; i <= 10; i++) {
        if (i % 2 == 0) {
            continue; // 偶数跳过，直接进入下一次循环
        }
        System.out.println(i);
    }
    System.out.println("循环结束");
}
```

输出：

```
1
3
5
7
9
循环结束
```

#### 4.7 return 关键字

`return` 是控制方法执行流程的核心关键字，作用是**结束当前方法的执行**，并（可选地）向调用者**返回一个值**。

- **终止方法执行**：一旦执行到 return，当前方法立即停止，后续代码不再执行。
- **返回值（可选）**：方法声明了返回类型（非 void）时，return 必须携带一个与返回类型匹配的值；void 方法中 return 可以不带值（仅用于终止方法）。

```java
public class Test {
    public static void main(String[] args) {
        chu(6, 2);
        chu(6, 0);
    }

    public static void chu(int a, int b) {
        // 除法不允许除数为0
        if (b == 0) {
            System.out.println("除数不能为0，请确认！");
            return; // 结束方法，不执行后面的代码
        }
        int res = a / b;
        System.out.println(a + " / " + b + " = " + res);
    }
}
```

#### 4.8 死循环

可以一直执行下去的循环，如果没有干预（break 等）不会停下来。

```java
// for 形式
for (;;) {
    System.out.println("Hello World1");
}

// while 经典写法
while (true) {
    System.out.println("Hello World2");
}

// do-while 形式
do {
    System.out.println("Hello World3");
} while (true);
```

---

### 五、随机数 Random 类

Random 是 Java 中用于生成**伪随机数**的工具类（位于 `java.util` 包下），相比 `Math.random()` 更灵活，支持生成多种类型的随机数（整数、小数、布尔值等）。

#### 5.1 基本用法

导入类：

```java
import java.util.Random;
```

创建对象：

```java
Random random = new Random();
```

#### 5.2 生成 0~n 的随机整数

方法 `nextInt(n)`：生成 **[0, n)** 范围内的随机整数（含 0，不含 n）。

```java
Random rand = new Random();
int x = rand.nextInt(10); // 0~9 之间的整数
System.out.println(x);
```

#### 5.3 生成指定区间 [min, max] 的随机数

公式（适用于任意整数范围）：

```java
random.nextInt(max - min + 1) + min
```

案例 1：打印 5~15 之间的随机数。

```java
Random rand = new Random();
int x = rand.nextInt(15 - 5 + 1) + 5;
System.out.println(x);
```

案例 2：模拟点名系统。班级有 5 个学生，程序每执行一次随机选择一名学生回答问题。

```java
// 学员姓名信息存储
String name1 = "唐僧";
String name2 = "孙悟空";
String name3 = "猪八戒";
String name4 = "沙和尚";
String name5 = "哪吒";

Random random = new Random();
// 获取1~5之间的随机数
int num = random.nextInt(5 - 1 + 1) + 1;
System.out.println(num);
// 用随机数在switch中匹配
switch (num) {
    case 1:
        System.out.println(name1 + "：回答问题");
        break;
    case 2:
        System.out.println(name2 + "：回答问题");
        break;
    case 3:
        System.out.println(name3 + "：回答问题");
        break;
    case 4:
        System.out.println(name4 + "：回答问题");
        break;
    case 5:
        System.out.println(name5 + "：回答问题");
        break;
}
```

> 学完数组后，点名系统可以用数组大幅简化（见第六章数组案例）。

#### 5.4 随机布尔值 nextBoolean()

方法 `nextBoolean()` 随机生成 `true` 或 `false`。

案例：模拟抛硬币。

```java
Random rand = new Random();
boolean isFlag = rand.nextBoolean();
if (isFlag) {
    System.out.println("抛硬币结果：正面");
} else {
    System.out.println("抛硬币结果：反面");
}
```

#### 5.5 综合案例：猜数字小游戏

需求：程序产生一个 1~100 之间的随机数作为中奖数字，键盘录入用户猜的数字进行比对；没猜中就给出"大了/小了"的提示，直到猜对为止，程序结束。

分析：Random 生成随机数 + Scanner 键盘录入 + `while(true)` 死循环反复猜测 + 猜对时 `break` 结束。

```java
import java.util.Random;
import java.util.Scanner;

public class GuessNumber {
    public static void main(String[] args) {
        Random r = new Random();
        Scanner sc = new Scanner(System.in);

        // 1. 产生 1~100 的随机中奖数字
        int luckyNumber = r.nextInt(100) + 1;

        // 2. 反复猜测
        while (true) {
            System.out.println("请输入你猜的数字（1~100）：");
            int guess = sc.nextInt();
            if (guess > luckyNumber) {
                System.out.println("猜大了，往小了猜！");
            } else if (guess < luckyNumber) {
                System.out.println("猜小了，往大了猜！");
            } else {
                System.out.println("恭喜你，猜对了！中奖数字就是：" + luckyNumber);
                break; // 猜对，结束死循环
            }
        }
    }
}
```

---

### 本章小结

- 程序三大流程：顺序、分支（if / switch）、循环（for / while / do-while）。
- Debug 断点调试是排查问题的核心工具：加断点 → Debug 运行 → F8 步过/F7 步入/F9 恢复，观察变量变化和方法调用链。
- if 适合范围判断，switch 适合多值匹配；switch 不要漏写 break，但可主动利用穿透性合并相同分支。
- for 适合已知次数，while 适合次数不确定，do-while 保证循环体至少执行一次。
- 嵌套循环的核心：外循环控制行数，内循环控制列数；外循环走一次，内循环跑一圈；break/continue 默认只作用内层，可用标号控制外层。
- break 结束整个循环/switch，continue 跳过本次循环，return 结束整个方法。
- Random 的 `nextInt(n)` 生成 [0,n) 的整数；指定区间公式 `nextInt(max-min+1)+min`。

---

<div style="page-break-after: always;"></div>

## 第六章 数组

### 一、认识数组

#### 1.1 什么是数组

在 Java 中，**数组（Array）** 是一种用于存储**相同类型数据**的容器，它是一种**引用类型**，长度固定（一旦创建，长度不可改变）。

数组可以存储基本类型（如 `int`、`char`）或引用类型（如 `String`、对象）的数据。

核心理解：**数组就是一个容器，用来存一批同种类型的数据。**

```java
// 20, 10, 80, 60, 90
int[] arr = {20, 10, 80, 60, 90};
// 牛二, 西门, 全蛋
String[] names = {"牛二", "西门", "全蛋"};
```

#### 1.2 为什么使用数组

如果用普通变量存储 5 个学生姓名，需要定义 5 个变量；新增学生还要再定义变量，导致**代码冗余、难以维护**。数组可将这些数据集中管理，大幅简化代码，让程序逻辑更清晰。

问题案例（变量 + switch 点名）：

```java
// 学员姓名信息存储
String name1 = "唐僧";
String name2 = "孙悟空";
String name3 = "猪八戒";
String name4 = "沙和尚";
String name5 = "哪吒";
// 实现点名
Random random = new Random();
int num = random.nextInt(5 - 1 + 1) + 1;
System.out.println(num);
switch (num) {
    case 1:
        System.out.println(name1 + "：回答问题");
        break;
    case 2:
        System.out.println(name2 + "：回答问题");
        break;
    case 3:
        System.out.println(name3 + "：回答问题");
        break;
    case 4:
        System.out.println(name4 + "：回答问题");
        break;
    case 5:
        System.out.println(name5 + "：回答问题");
        break;
}
```

数组优化案例：

```java
String[] studentNames = {"唐僧", "孙悟空", "猪八戒", "沙和尚", "哪吒", "白素贞"};
Random random = new Random();
int index = random.nextInt(studentNames.length);
System.out.println(studentNames[index] + "：出来回答问题");
```

---

### 二、数组的定义

数组的定义分为**静态初始化**和**动态初始化**两种。

#### 2.1 静态初始化数组

直接指定数组中的所有元素，由系统自动计算长度，也就是：**定义数组的时候直接给数组赋值**。

```java
// 完整格式：数据类型[] 数组名 = new 数据类型[]{元素1, 元素2, ...};
int[] ages = new int[]{12, 24, 36};
String[] fruits = new String[]{"苹果", "香蕉", "橙子"};

// 简化写法：数据类型[] 数组名 = {元素1, 元素2, ...};
int[] ages2 = {12, 24, 36};
String[] fruits2 = {"苹果", "香蕉", "橙子"};
```

注意：

- "数据类型[] 数组名"也可写成"数据类型 数组名[]"（如 `int ages[]`），但推荐前者。
- **什么类型的数组只能存放什么类型的数据**。

#### 2.2 数组在计算机中的基本原理

执行 `int[] ages = {12, 24, 36};` 时：

1. 先在内存中新建一个 ages 变量空间，一开始是空的；
2. 随后在内存中新建一块**连续的空间区域**，称为数组对象，它有一个访问地址，里面存储数组值；每个值都有一个对应的编号（称为**索引**，从 0 开始）；
3. 数组对象把自己的地址交给变量空间 ages，ages 就指向该地址，通过地址访问数组数据。

注意：因为数组变量名中存储的是数组在内存中的**地址**，所以数组是一种**引用数据类型**。

---

### 三、访问数组

#### 3.1 通过索引访问

数组元素通过**索引（index）** 访问，索引从 `0` 开始。

```java
数组名[索引值]
```

```java
int[] ages = {12, 24, 36};
System.out.println(ages[0]); // 12
System.out.println(ages[1]); // 24
System.out.println(ages[2]); // 36

String[] names = {"小张", "小明", "小花"};
System.out.println(names[0]); // 小张
System.out.println(names[1]); // 小明
System.out.println(names[2]); // 小花
```

#### 3.2 获取数组长度

数组有一个内置的 `length` 属性，用于获取数组长度（元素个数）：

```java
数组名.length
```

```java
int[] nums = {1, 2, 3};
System.out.println(nums.length); // 输出：3
```

#### 3.3 数组的最大索引

数组的最大索引为 `数组名.length - 1`（前提：数组元素个数大于 0）。

如果访问时使用的索引超过最大索引，会出现**索引越界异常**（`ArrayIndexOutOfBoundsException`）：

```java
String[] names = {"小张", "小明", "小花"};
System.out.println(names[0]);
System.out.println(names[1]);
System.out.println(names[2]);
System.out.println(names[3]); // Index 3 out of bounds for length 3
```

---

### 四、数组遍历

#### 4.1 概述

- 需要将数组的值一个一个访问使用时就要遍历；
- 遍历数组即逐个访问所有元素，通过 **for 循环 + 索引**挨个访问；
- 遍历可以用来求和、元素搜索、找最大值、最小值等。

```java
int[] scores = {85, 92, 78};
// 遍历并打印所有元素，i 从 0 到 length-1
for (int i = 0; i < scores.length; i++) {
    System.out.println(scores[i]);
}
```

#### 4.2 案例 1：遍历求和

需求：5 名员工的销售额分别是 16、26、36、6、100，计算部门总销售额。

```java
public static void main(String[] args) {
    int[] money = {16, 26, 36, 6, 100};
    int totalMoney = 0;
    for (int i = 0; i < money.length; i++) {
        totalMoney += money[i];
    }
    System.out.println("总销售额为：" + totalMoney + "万");
}
```

#### 4.3 案例 2：求最大值和最小值

需求：用数组存储游戏人物的战力值，求出最大战力和最小战力。

实现步骤：

1. 用数组 power 存战力值；
2. 定义变量 max、min 记录结果，**建议初始化为数组第一个元素** `arr[0]` 作为参照；
3. 从第二个位置开始遍历，当前数据大于 max 就替换 max，小于 min 就替换 min；
4. 循环结束后输出。

```java
public class Test6 {
    public static void main(String[] args) {
        int[] powers = {5, 44, 33, 55, 22};
        int resMax = getMax(powers);
        System.out.println("最大战力值为：" + resMax);

        int resMin = getMin(powers);
        System.out.println("最小战力值为：" + resMin);
    }

    // 求最大值
    public static int getMax(int[] arr) {
        int max = arr[0]; // 默认第一个就是最大值
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] > max) {
                max = arr[i];
            }
        }
        return max;
    }

    // 求最小值
    public static int getMin(int[] arr) {
        int min = arr[0]; // 认为第一个值就是最小值
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] < min) {
                min = arr[i];
            }
        }
        return min;
    }
}
```

---

### 五、动态初始化数组

定义数组时先不存入具体元素值，只确定数据类型和数组长度，系统为元素分配**默认值**，后续再手动赋值。

#### 5.1 语法格式

```java
// 创建数组
数据类型[] 数组名 = new 数据类型[长度];

// 给数组赋值
数组名[索引值] = 值;
```

```java
// 动态定义数组
int[] ages = new int[3];
// 赋值
ages[0] = 20;
ages[1] = 18;
ages[2] = 22;
```

练习：动态创建一个长度为 6 的明星姓名数组 names，分别赋值为黄晓明、胡歌、吴京、张译、彭于晏、杨洋，最后遍历打印。

#### 5.2 动态初始化元素的默认值规则

| 数据类型 | 具体类型 | 默认值 |
| --- | --- | --- |
| 基本类型 | byte、short、int、long | `0` |
| 基本类型 | float、double | `0.0` |
| 基本类型 | char | `' '`（空字符，不是空格） |
| 基本类型 | boolean | `false` |
| 引用类型 | 类、数组、接口、String | `null` |

---

### 六、综合案例（一）

#### 6.1 评委打分案例

需求：编程竞赛中 6 个评委为选手打分，分数为 0-100 的整数；选手最后得分为**去掉一个最高分和一个最低分后剩余 4 个分数的平均值**。

分析：

- 分数是后期录入的，一开始不知道具体值，因此用**动态初始化**数组存分数；
- 遍历数组每个位置提示录入分数，需校验成绩在 0~100 之间（输入非法时 `i--` 退回重新输入）；
- 再遍历求最低分、最高分、总分，最后算平均分。

```java
import java.util.Scanner;

public class Test3 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int[] scores = new int[6];
        // 遍历录入每一个评委的分数
        for (int i = 0; i < scores.length; i++) {
            System.out.println("请输入第" + (i + 1) + "个评委的分数");
            int score = sc.nextInt();
            if (score >= 0 && score <= 100) {
                scores[i] = score; // 满足要求存入当前索引位置
            } else {
                System.out.println("输入有误，请输入0~100之间的分数~~~");
                i--; // 索引退回，重新输入该位置
            }
        }
        // 最小值
        int min = scores[0];
        for (int i = 1; i < scores.length; i++) {
            if (scores[i] < min) {
                min = scores[i];
            }
        }
        System.out.println("最低分是：" + min);
        // 最大值
        int max = scores[0];
        for (int i = 1; i < scores.length; i++) {
            if (scores[i] > max) {
                max = scores[i];
            }
        }
        System.out.println("最高分是：" + max);
        // 求和
        int sum = 0;
        for (int i = 0; i < scores.length; i++) {
            sum += scores[i];
        }
        // 求平均值：(总分 - 最高 - 最低) / (长度 - 2)
        double avg = (sum - min - max) * 1.0 / (scores.length - 2);
        System.out.println("总成绩是：" + sum);
        System.out.println("平均成绩是" + avg);
    }
}
```

优化为方法版本（职责拆分）：

```java
import java.util.Scanner;

public class Test2 {
    public static void main(String[] args) {
        int[] scores = initData();        // 成绩录入
        int min = getMin(scores);         // 最小值
        System.out.println("最低分是：" + min);
        int max = getMax(scores);         // 最大值
        System.out.println("最高分是：" + max);
        int sum = getSum(scores);         // 求和
        System.out.println("总成绩是：" + sum);
        // 计算平均值
        double avg = ((sum - max - min) * 1.0) / (scores.length - 2);
        System.out.println("平均分是：" + avg);
    }

    // 成绩录入方法，返回装好分数的数组
    public static int[] initData() {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入6个评委的分数：");
        int[] arr = new int[6];
        for (int i = 0; i < arr.length; i++) {
            System.out.println("第" + (i + 1) + "个评委评分：");
            int score = sc.nextInt();
            if (score >= 0 && score <= 100) {
                arr[i] = score;
            } else {
                System.out.println("输入有误，请输入0~100之间的分数~~~");
                i--;
            }
        }
        return arr;
    }

    public static int getMin(int[] arr) {
        int min = arr[0];
        for (int i = 1; i < arr.length; i++) {
            if (arr[i] < min) {
                min = arr[i];
            }
        }
        return min;
    }

    public static int getMax(int[] arr) {
        int max = arr[0];
        for (int i = 1; i < arr.length; i++) {
            if (arr[i] > max) {
                max = arr[i];
            }
        }
        return max;
    }

    public static int getSum(int[] arr) {
        int sum = 0;
        for (int i = 0; i < arr.length; i++) {
            sum += arr[i];
        }
        return sum;
    }
}
```

#### 6.2 统计及格人数

需求：成绩为 99, 100, 62, 15, 48, 65, 98, 99, 5, 59.5, 75，统计及格（>=60）学生总人数。

分析：用静态初始化数组存成绩；for 循环遍历，循环外定义计数器 count；每个成绩 >=60 就让 count 加 1。

```java
public static void main(String[] args) {
    double[] scores = {99, 100, 62, 15, 48, 65, 98, 99, 5, 59.5, 75};
    int count = 0; // 及格人数计数器
    for (int i = 0; i < scores.length; i++) {
        if (scores[i] >= 60) {
            count++;
        }
    }
    System.out.println("及格总人数有：" + count + "人");
}
```

---

### 七、数组在计算机中的执行原理

#### 7.1 Java 程序的内存划分

`ArrayDemo.java` 通过 javac 编译生成 `ArrayDemo.class` 文件，class 文件在 JVM 虚拟机中运行。JVM 将内存划分为 5 个功能区：**方法区、栈、堆**、本地方法栈、寄存器，目前只需了解前三个：

- **方法区**：字节码文件（.class）先加载到方法区；
- **栈**：方法运行时进入的内存，变量存在方法中，所以变量也存在栈里；
- **堆**：`new` 出来的东西会在这块内存中开辟空间并产生地址。

```java
public class ArrayDemo {
    public static void main(String[] args) {
        int a = 10;
        System.out.println(a);

        int[] arr = {11, 22, 33};
        System.out.println(arr);
        System.out.println(arr[1]);

        arr[0] = 44;
        arr[1] = 55;
        arr[2] = 66;

        System.out.println(arr[0]);
        System.out.println(arr[1]);
        System.out.println(arr[2]);
    }
}
```

执行过程：

1. 编译好的 `ArrayDemo.class` 先加载进方法区；
2. main 方法进入栈内存执行；
3. `int a = 10;` 在栈内存开辟空间命名为 a，存入 10，所以打印 10；
4. `int[] arr = {11, 22, 33};`：`int[] arr` 先在栈中创建空变量占位；`{11,22,33}` 在**堆内存**中创建连续空间存储数据，并产生访问地址（如 `[I@b4c966a`）；把地址赋值给 arr，arr 根据地址去堆中找数据；
   - `System.out.println(arr)` 打印的是地址 `[I@b4c966a`；
   - `arr[1]` 通过地址找到堆中对应位置的值，打印 22；
5. `arr[0] = 44;` 等三行：通过地址去堆内存中找到对应位置修改值，最后打印 44、55、66。

#### 7.2 多个变量指向同一个数组对象

```java
public class ArrayDemo2 {
    public static void main(String[] args) {
        int[] arr1 = {11, 22, 33};
        int[] arr2 = arr1; // arr2 拿到的是 arr1 存储的地址

        System.out.println(arr1);
        System.out.println(arr2);

        arr2[1] = 99;
        System.out.println(arr1[1]); // 99
    }
}
```

执行过程：

1. class 文件加载进方法区，main 方法进栈；
2. `int[] arr1 = {11,22,33};`：arr1 在栈中占位，堆中创建数组对象（地址如 `[I@b4c966a`），地址赋给 arr1；
3. `int[] arr2 = arr1;`：arr2 在栈中占位，arr1 把地址 `[I@b4c966a` 赋给 arr2，**两个变量指向同一个数组对象**；
4. 打印 arr1、arr2，两个地址相同；
5. `arr2[1] = 99;`：arr2 通过地址修改堆中的值；因为 arr1 和 arr2 指向同一地址，所以 `arr1[1]` 也是 99。

#### 7.3 数组变量为 null 的问题

如果数组变量存储的地址是 `null`，表示该变量不再指向任何数组对象。此时再访问元素或 length，会报**空指针异常**（`NullPointerException`）。

```java
public class ArrayDemo3 {
    public static void main(String[] args) {
        int[] arr1 = {11, 22, 33};
        int[] arr2 = arr1;

        arr2[1] = 99;
        System.out.println(arr1[1]); // 99

        arr2 = null; // 把 null 赋值给 arr2
        System.out.println(arr2);   // 可以正常打印，结果是 null
        // 以下两行均报错：空指针异常 NullPointerException
        // System.out.println(arr2[0]);
        // System.out.println(arr2.length);
    }
}
```

#### 7.4 思考题

**问题 1：运行一个 Java 程序，主要涉及 JVM 中的哪几部分内存区域？**

方法区、栈内存、堆内存（本地方法栈与寄存器现阶段了解即可）。

**问题 2：说说 `int a = 20;` 和 `int[] arr = new int[3];` 这两行代码的执行原理。**

- `int a = 20;`：a 是基本类型变量，直接放在栈中，a 变量中存储的数据就是 20 这个值；
- `int[] arr = new int[3];`：`new int[3]` 创建一个数组对象，会在**堆内存**中开辟区域存储 3 个整数（默认值均为 0）；arr 是变量，在**栈**中，arr 中存储的是数组对象在堆内存中的**地址值**。

---

### 八、综合案例（二）

#### 8.1 临时变量 temp 交换值原理

临时变量 `temp` 的作用就像"腾地方"：想把两个杯子里的水互换，总得先找个空杯子临时装一下其中一杯，不然直接倒会把原来的水弄丢。

```java
// 交换 a 和 b 的值：a=10, b=20 → a=20, b=10
int a = 10;
int b = 20;

int temp;   // 准备一个空"杯子"
temp = a;   // 先把 a 的值（10）倒进 temp，temp=10
a = b;      // 再把 b 的值（20）倒进 a，a=20
b = temp;   // 最后把 temp 里的值（原来的 10）倒进 b，b=10

System.out.println(a); // 20
System.out.println(b); // 10
```

temp 的核心作用是**暂时保存其中一个值**，防止交换过程中原值被覆盖丢失。

#### 8.2 翻转数组

需求：把数组 `{11, 22, 33, 44, 55, 66}` 反转为 `{66, 55, 44, 33, 22, 11}`，并在控制台输出交换后的数组元素。

##### 方法 1：双指针（start / end）两两交换

用两个变量模拟两个指针，分别指向首尾位置，交换指针指向的元素后 start 后移、end 前移；**交换条件是 `start < end`**（两指针相遇时中间元素无需再换），条件不成立时停止。

以 `{11, 22, 33, 44, 55, 66}` 为例，初始 `start = 0`，`end = arr.length - 1 = 5`，交换过程：

| 轮次 | 交换位置 | 交换后数组 |
| --- | --- | --- |
| 第 1 次 | arr[0] 和 arr[5] | {66, 22, 33, 44, 55, 11} |
| start++，end-- | | start=1，end=4 |
| 第 2 次 | arr[1] 和 arr[4] | {66, 55, 33, 44, 22, 11} |
| start++，end-- | | start=2，end=3 |
| 第 3 次 | arr[2] 和 arr[3] | {66, 55, 44, 33, 22, 11} |
| start++，end-- | | start=3，end=2，start > end，循环结束 |

while 循环实现：

```java
public static void main(String[] args) {
    int[] arr = {11, 22, 33, 44, 55, 66};
    int start = 0, end = arr.length - 1;
    // start < end 时持续交换，两指针相遇即停止
    while (start < end) {
        int temp = arr[start];
        arr[start] = arr[end];
        arr[end] = temp;
        start++;
        end--;
    }
    // 打印数组
    System.out.print("[");
    for (int i = 0; i < arr.length; i++) {
        if (i == arr.length - 1) {
            System.out.print(arr[i]);
        } else {
            System.out.print(arr[i] + ", ");
        }
    }
    System.out.println("]");
}
```

for 循环简化版（推荐）：把 start、end 直接定义在 for 循环中。

```java
public class Test1 {
    public static void main(String[] args) {
        int[] arr = {16, 26, 36, 6, 100};
        reverseArray(arr);
    }

    public static void reverseArray(int[] arr) {
        for (int start = 0, end = arr.length - 1; start < end; start++, end--) {
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;
        }
        // Arrays.toString：JDK 提供的数组快速打印工具
        // 直接把数组内容以 [元素1, 元素2, ...] 的格式打印，不用手写 for 循环
        System.out.println(Arrays.toString(arr));
    }
}
```

> 提示：使用 `Arrays.toString(arr)` 需要 `import java.util.Arrays;`。

##### 方法 2：只遍历前半部分，交换对称位置

```java
int[] arr = {10, 20, 30, 40, 50};
for (int i = 0; i < arr.length / 2; i++) {
    int temp = arr[i];
    // arr.length - 1 - i 是与索引 i 对称的"尾部索引"
    // i=0 交换 arr[0] 和 arr[4]；i=1 交换 arr[1] 和 arr[3]；中间元素不动
    arr[i] = arr[arr.length - 1 - i];
    arr[arr.length - 1 - i] = temp;
}
for (int i = 0; i < arr.length; i++) {
    System.out.print(arr[i] + " "); // 50 40 30 20 10
}
```

##### 方法 3：借助新数组

新建一个等长的新数组，把原数组**尾部对称位置**的元素依次取出来放进新数组：新数组的第 i 个位置，放原数组第 `arr.length - 1 - i` 个位置的元素。

```java
int[] arr = {10, 20, 30, 40, 50, 60};
int[] newArr = new int[arr.length];
for (int i = 0; i < arr.length; i++) {
    // i=0 取 arr[5] 放到 newArr[0]；i=1 取 arr[4] 放到 newArr[1]……
    newArr[i] = arr[arr.length - 1 - i];
}
// newArr = {60, 50, 40, 30, 20, 10}
```

三种方式对比：方法 1、2 都是在原数组上直接交换（省内存），方法 3 思路最直观但会多占一块数组空间。

---

### 九、printf 格式化打印

`printf` 按照指定格式输出数据，其中 `%` 作为占位符实现"拼接"效果。

常见占位符：

| 占位符 | 含义 |
| --- | --- |
| `%s` | 字符串占位符 |
| `%d` | 整数占位符 |
| `%f` | 浮点数占位符 |
| `%c` | 字符占位符 |

注意：

- `%s` 可以兼容所有类型的占位符；
- 浮点数默认精度较长，需要保留两位小数时写 `%.2f`。

```java
String name = "小明";
int age = 18;
double score = 95.5;
System.out.printf("姓名：%s，年龄：%d，成绩：%.2f%n", name, age, score);
// 输出：姓名：小明，年龄：18，成绩：95.50
```

---

### 本章小结

- 数组是存储**同种类型**多个数据的容器，属于**引用类型**，长度固定；变量中存的是堆内存中的地址。
- 两种初始化：静态初始化（直接给元素，适合数据已知）、动态初始化（只给长度，元素取默认值，适合数据后期录入）。
- 元素通过索引访问，索引从 0 开始，最大索引是 `length - 1`；越界访问报 `ArrayIndexOutOfBoundsException`。
- 动态初始化默认值：整数 `0`、小数 `0.0`、char `' '`、boolean `false`、引用类型 `null`。
- 内存模型：class 进方法区，方法运行进栈，`new` 出来的数组在堆中；多个变量可指向同一数组（一改全改）；引用为 null 时访问元素报 `NullPointerException`。
- 经典操作：遍历求和、求最值（参照值取 `arr[0]`）、双指针反转数组、temp 三行交换两个变量。

---

<div style="page-break-after: always;"></div>

## 第七章：面向对象基础

### 一、面向对象编程概述

Java 面向对象（Object-Oriented Programming，简称 OOP）是 Java 编程语言的核心思想之一。它**通过"对象"来组织代码，使程序更模块化、可重用、易维护**。

核心思想：**把现实世界中的事物，都抽象成「类」（模板）和「对象」（利用模板创建的实体）**，以「事物」为核心，关注**事物有什么特征、能做什么行为**，而不是关注步骤。

与之相对的是面向过程编程：只关注「步骤」——做一件事需要第一步做什么、第二步做什么、第三步做什么，是「执行者」思维。

| 对比项 | 面向过程 | 面向对象 |
| --- | --- | --- |
| 关注点 | 怎么做（步骤） | 谁来做（对象） |
| 代码组织 | 变量 + 方法，流水账 | 属性和行为封装在类中 |
| 思维方式 | 执行者 | 指挥者 |

#### 1.1 入门案例：明星演出

需求：有 2 位明星——周杰伦（45 岁、中国、代表作《七里香》）、刘德华（62 岁、中国、代表作《冰雨》）；每位明星都能执行 3 个行为：**自我介绍、唱歌、商业演出**。

**面向过程实现**：按步骤写代码，变量与方法分离，所有功能揉在一起。

```java
public class Star_mxgc {
    public static void main(String[] args) {
        System.out.println("============ 周杰伦 ============");
        //定义周杰伦的属性
        String name1 = "周杰伦";
        int age1 = 45;
        String country1 = "中国";
        String works1 = "七里香";
        //调用方法
        introduce(name1, age1, country1, works1);
        sing(name1, works1);
        show(name1, age1, country1);

        System.out.println("------------------------");
        System.out.println("============ 刘德华 ============");
        String name2 = "刘德华";
        int age2 = 62;
        String country2 = "中国";
        String works2 = "冰雨";
        introduce(name2, age2, country2, works2);
        sing(name2, works2);
        show(name2, age2, country2);
    }
    //自我介绍方法
    public static void introduce(String name,int age,String country,String works) {
        System.out.println("大家好，我是" + country + "歌手" + name + "，今年" + age + "岁，代表作《" + works + "》");
    }
    //商业演出方法
    public static void show(String name, int age, String country) {
        System.out.println(name + "(" + age + "岁，" + country + ")正在参加商业演出，人气爆棚！");
    }
    //唱歌方法
    public static void sing(String name, String works) {
        System.out.println(name + "正在演唱《" + works + "》，掌声响起！");
    }
}
```

面向过程写法的问题：新增一个明星就要重新定义一堆变量，调用方法时还要把所有变量一个个传参，参数多了容易写错、漏写。

#### 1.2 类与对象

面向对象编程：**需要先设计对象类，然后再使用对象类创建实例对象**。

之前用的 Scanner、Random 都是 Java 已经写好的对象，直接拿来用即可；当要解决的问题 Java 没有提供现成对象时，就需要自己设计。所以本章有两个学习目标：**学习自己如何设计对象，掌握已有对象如何使用**。

- **class 类（对象类）**：对一类具有相同属性和行为的事物的抽象描述，可以理解为"模板"或"蓝图"。
- **object 对象（实例对象）**：类的具体实例，通过 `new` 关键字创建。

所有明星共有的特征：姓名（name）、年龄（age）、国籍（country）、代表作（works）；共有的动作：唱歌（sing）、演出（show）、自我介绍（introduce）。把这些特征和动作封装到一个明星类 Star 里，相当于设计一张明星信息表格，每个明星按模板填写数据即可生成一个实例。

**定义对象类**：

```java
//明星对象类
public class Star {
    //成员属性（变量）
    String name;
    int age;
    String country;
    String works;

    //成员方法（对象行为方法）
    //自我介绍
    public void introduce() {
        System.out.println("大家好，我是" + country + "歌手" + name + "，今年" + age + "岁，代表作《" + works + "》");
    }
    //唱歌
    public void sing() {
        System.out.println(name + "正在演唱《" + works + "》，掌声响起！");
    }
    //商业演出
    public void show() {
        System.out.println(name + "(" + age + "岁，" + country + ")正在参加商业演出，人气爆棚！");
    }
}
```

**测试类（创建并使用对象）**：

```java
public class Test {
    public static void main(String[] args) {
        System.out.println("========== 创建实例对象周杰伦 ==========");
        Star star1 = new Star();
        //设置实例对象的相关属性值
        star1.name = "周杰伦";
        star1.age = 45;
        star1.works = "七里香";
        //实例对象执行相应方法
        star1.introduce();
        star1.show();
        star1.sing();

        System.out.println("========== 创建实例对象刘德华 ==========");
        Star star2 = new Star();
        star2.name = "刘德华";
        star2.age = 62;
        star2.works = "冰雨";
        star2.introduce();
        star2.show();
        star2.sing();
    }
}
```

**类的组成规则（与之前学的变量、方法写法对比记忆）**：

- **成员变量**：格式和之前定义变量完全一样，区别只是**位置必须放在类中、方法的外面**；
- **成员方法**：格式和之前定义方法完全一样，区别只是**必须去掉 `static` 关键字**（static 是后面才学的内容，成员方法属于对象，不加 static）。
- 属性（成员变量）描述事物的**名词**特征（姓名、年龄、价格），行为（成员方法）描述事物的**动词**动作（学习、吃饭、打电话）。

**创建对象、使用对象的固定格式**：

```java
// 1. 创建对象：类名 对象名 = new 类名();
Student stu = new Student();

// 2. 使用成员变量：对象名.变量名
System.out.println(stu.name);   // 取值
stu.name = "李四";               // 赋值

// 3. 使用成员方法：对象名.方法名(实际参数);
stu.study();
```

一个类可以创建出多个对象，每个对象各自拥有一份成员变量，互不影响。

### 二、面向对象编程的好处

**好处 1：代码更简洁，调用更简单（最直观）**

- 面向过程：新增一个明星，要重新定义一堆变量，调用方法时把所有变量一个个传参。
- 面向对象：新增一个明星只需 `new Star()` 创建对象，用 `对象名.属性 = "属性值"` 设置属性，调用方法直接 `对象名.方法名()`，不用传任何参数，因为对象自己带着所有属性。

```java
Star star3 = new Star();
star3.name = "林俊杰";
star3.age = 44;
star3.works = "一千年以后";
```

**好处 2：属性和行为绑定在一起，符合现实逻辑**

面向过程中属性是零散的变量、方法是独立的函数，代码里看不出「周杰伦唱歌」的关联性；面向对象中明星的属性和行为封装在一个 Star 类里，`star1.sing()` 就是「周杰伦唱歌」，`star2.show()` 就是「刘德华演出」，和现实世界逻辑完全一致。

**好处 3：代码复用性极高，扩展超级方便（最核心的好处）**

- 新增属性（如身高）：面向过程要在所有相关方法的参数里都加；面向对象只需在类里加一行 `double height;`，所有对象自动拥有该属性。
- 新增行为（如跳舞）：面向对象只需在类里新增一个 `dance()` 方法，所有对象都可直接 `对象名.dance()` 调用，一次编写，所有对象复用。
- 新增 100 个明星：面向过程要写 100 组变量 + 100 次方法调用；面向对象只需写 100 行 `new Star(...)`。

**好处 4：易维护、易修改，出错好排查**

每个类都是独立模块，各司其职。唱歌逻辑要改，只需改 Star 类里的 `sing()` 方法，所有明星的唱歌行为同步更新——一处修改，处处生效。

#### 2.1 练习案例：手机类

- 定义手机类 Phone：属性（品牌 brand、颜色 color、价格 price）；行为：打电话 call（输出给 xxx 打电话）、发短信 sendMessage（输出群发短信）。
- 编写测试类 PhoneTest，创建两个手机对象并赋值：小米/白色/4999、华为/黑色/6999；打印属性校验赋值成功，调用各自的成员方法。

```java
public class Phone {
    //成员属性（变量）
    String brand;
    String color;
    double price;

    //成员方法
    public void call(String name){
        System.out.println("用"+brand+"手机给"+name+"打电话~~");
    }
    public void sendMessage(){
        System.out.println(brand+"手机发了一条群发信息~~~");
    }
}
```

```java
public class PhoneTest {
    public static void main(String[] args) {
        Phone phone1 = new Phone();
        //给phone1实例对象属性赋值
        phone1.brand ="小米";
        phone1.color ="白色";
        phone1.price=4999.9;
        //打印属性校验
        System.out.println(phone1.brand);
        System.out.println(phone1.color);
        System.out.println(phone1.price);
        //调用成员方法
        phone1.call("小哈叔");
        phone1.sendMessage();

        //华为手机，黑色，6999.9
        //......
    }
}
```

### 三、对象在内存中的存储原理

了解对象在内存中的操作流程，有利于理解复杂案例。以 Student 类为例：

```java
public class Student {
    String name;
    int age;

    public void study() {
        System.out.println("学习Java");
    }

    public void eat() {
        System.out.println("吃饭");
    }
}
```

#### 3.1 单个对象内存图

```java
public class TestStudent {
    public static void main(String[] args) {
        Student stu = new Student();
        System.out.println(stu);          // Student@2f4d3709（对象地址）

        System.out.println(stu.name);     // null（未赋值的默认值）
        System.out.println(stu.age);      // 0
        stu.name = "张三";
        stu.age = 23;
        System.out.println(stu.name);     // 张三
        System.out.println(stu.age);      // 23

        stu.study();                      // 学习Java
        stu.eat();                        // 吃饭
    }
}
```

执行顺序与原理：

1. 先加载 TestStudent 测试类，将 TestStudent.class 字节码文件放入方法区；
2. main 方法进栈执行：在栈内存新建 `Student stu` 变量，在堆内存中 new 出对象（产生地址如 0x2f4d3709），把地址赋值给 stu；
3. 直接打印 stu 得到地址值 `类名@十六进制地址`；未赋值的成员变量为默认值（引用类型 null、int 为 0）；
4. `stu.name = "张三"` 通过地址找到堆中的对象，修改其属性；
5. 调用 `stu.study()`：study 方法进栈执行，打印后弹栈清除；再调用 eat 方法同理；
6. main 方法执行完毕弹栈，程序结束。

#### 3.2 两个对象内存图

```java
public class Test {
    public static void main(String[] args) {
        Student stu1 = new Student();
        stu1.name = "张三";
        stu1.age = 23;

        Student stu2 = new Student();
        stu2.name = "李四";
        stu2.age = 24;

        System.out.println(stu1.name);   // 张三
        System.out.println(stu1.age);    // 23

        stu1.study();                    // 学习Java
        stu2.study();                    // 学习Java
    }
}
```

两个引用变量 stu1、stu2 在栈中各自保存一个地址，分别指向堆中两个独立的对象，互不影响。

#### 3.3 两个引用指向同一个对象

```java
public class Test {
    public static void main(String[] args) {
        Student stu1 = new Student();
        stu1.name = "张三";
        stu1.age = 23;

        Student stu2 = stu1;       // 把stu1保存的地址赋值给stu2
        stu2.name = "小哈叔";      // 通过stu2修改的是堆中同一个对象

        System.out.println(stu1.name);   // 小哈叔
        System.out.println(stu2.name);   // 小哈叔
    }
}
```

`Student stu2 = stu1;` 是把 stu1 中保存的对象地址赋值给 stu2，两个变量指向堆中**同一个对象**。通过 stu2 修改属性，stu1 读取时也是修改后的值。

### 四、成员变量与局部变量

```java
public class Student {
    //成员变量
    String name;
    int age;

    //成员方法 —— 小括号中的 name 是局部变量
    public void chat(String name) {
        final double pi = 3.14159265358979;   // 方法内定义的也是局部变量
        System.out.println("在给" + name + "打电话聊天！");
    }
}
```

| 对比项 | 成员变量（全局变量） | 局部变量 |
| --- | --- | --- |
| 定义位置 | 类中、方法体之外 | 方法体内部、方法形参列表、代码块（for/if/while）内部 |
| 初始化值 | 有默认初始化值（int=0、引用类型=null 等） | 没有默认值，使用之前必须完成赋值 |
| 内存位置 | 堆内存（对象中） | 栈内存（方法栈帧中） |
| 生命周期 | 随着对象的创建而存在，随着对象的消失而消失 | 随着方法的调用而存在，随着方法运行结束而消失 |
| 作用域 | 整个类中有效，所有方法都能访问 | 仅限自己所归属的大括号 {} 内，出范围即失效 |

### 五、this 关键字

#### 5.1 就近原则与 this 的作用

```java
public class Student {
    String name;
    int age;

    //形参 name 与成员变量 name 重名
    public void chat(String name) {
        System.out.println(name + "在给" + name + "打电话聊天！");
    }
}
```

```java
public class test{
     public static void main(String[] args) {
         Student s1 = new Student();
         s1.name ="小哈";
         s1.age = 18;
         s1.chat("小米");
     }
 }
```

当局部变量和成员变量重名时，Java 遵循**就近原则**——方法里直接用的是局部变量。要访问成员变量，需要用 **this 关键字区分**：

```java
public class Student {
    String name;
    int age;

    public void chat(String name) {
        // this.name 是成员变量，name 是局部变量（形参）
        System.out.println(this.name + "在给" + name + "打电话聊天！");
    }
}
```

#### 5.2 this 的本质

- **this 代表当前类对象的引用（地址）**：哪个对象调用了当前方法，this 就指向哪个对象本身。

```java
public class Student {
    String name;
    int age;

    public void print(){
        System.out.println(this);   // 打印的就是调用对象的地址
    }
}
```

```java
public class Test{
    public static void main(String[] args) {
        Student s1 = new Student();
        System.out.println(s1);     // s1 的地址
        s1.print();                 // this 的地址，与上面完全相同
    }
}
```

**this 的用法**：调用本类的成员。

- `this.本类成员变量;` —— 区分重名的成员变量与局部变量；
- `this.本类成员方法();` —— 调用本类成员方法。

```java
public class Student {
    String name;
    int age;

    public void sayHello(String name) {
        System.out.println("Hello " + this.name);
    }

    //调用本类里面的成员方法
    public void print(){
        this.sayHello(name);
    }
}
```

使用规则：

- this 只能在**成员方法、构造方法、代码块**中使用，**绝对不能在 static 静态方法中使用**；
- 省略规则：不涉及重名问题时 `this.成员变量` 可以省略；`this.成员方法()` 可以直接省略。

**内存原理**：this 是一个引用变量，存储在栈内存中，指向堆内存中当前调用方法的对象的地址。

### 六、构造器（构造方法）

#### 6.1 作用与语法

构造器是 Java 中专门用来**创建实例对象**的特殊方法，分为**无参构造器**和**有参构造器**两种。

- **本质作用**：创建对象；
- **结合执行时机的作用**：给对象中的属性（成员变量）进行初始化。

**执行时机**：创建对象（new）的时候自动调用，**每创建一次对象就执行一次构造方法**；构造方法**不能手动调用**。

语法要求：

- 方法名与类名完全相同（大小写也要一致）；
- 没有返回值类型，连 `void` 都不写；
- 没有具体的返回值（不能由 return 带回结果数据）。

**无参构造器**：创建对象时成员变量先赋默认值（int=0、String=null、double=0.0、boolean=false），创建后再设置想要的值。

```java
修饰符 类名(){

}
```

**有参构造器**：创建对象的同时直接给成员变量赋值，完成对象初始化。

```java
修饰符 类名(参数1, 参数2, ...){
    // 用 this 区分成员变量和参数
    this.成员变量名 = 参数名;
}
```

IDEA 快捷生成：**Alt + Insert** → 选择 **Constructor** → 选择有参/无参构造器。

```java
public class Student {
    //成员属性（变量）
    String name;
    int age;

    //无参构造器
    public Student() {
    }

    //有参构造器
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

#### 6.2 使用注意事项

- 类中**默认自带无参构造器**：当一个类没有手动定义任何构造器时，编译器会自动生成一个默认无参构造器；
- 一旦**手动定义了有参构造器**，编译器就**不再自动生成**默认无参构造器，此时 `new 类名()` 会编译报错；
- 如需继续使用无参构造器，必须**手动补充定义**一个无参构造器（开发中建议无参、带参构造器全部手动给出）。

#### 6.3 构造器的执行流程（内存）

以 `Student stu = new Student("钢门吹雪", 23);` 为例：

1. 类加载时 Student.class 字节码进入方法区；
2. main 方法进栈，执行 new：在**堆内存**中开辟对象空间，成员变量先赋默认值（name=null、age=0），产生对象地址（如 0x0011）；
3. 构造方法 `Student(String name, int age)` 进栈执行，方法内的 **this 存放新对象的地址 0x0011**（构造器的调用者就是这个新对象）；
4. 形参 name、age 接收实参 "钢门吹雪"、23（存在栈中构造方法的栈帧里）；
5. 执行 `this.name = name; this.age = age;`：通过 this 的地址找到堆中的对象，把属性改为 "钢门吹雪"、23；
6. 构造方法执行完毕弹栈，new 把对象地址 0x0011 赋值给栈中的 stu 变量。

这也解释了为什么构造器里能用 this——**对象在构造器执行前就已经在堆中创建好了，构造器只负责初始化**。

### 七、封装

#### 7.1 封装思想

面向对象的三大特征：**封装、继承、多态**。

封装就是把某一事物的相关数据（属性）以及操作数据的方法，用类设计到一个对象中去——**类本身就是一种封装**。核心原则是"**合理隐藏，合理暴露**"：好比汽车不需要把内部零件都暴露出来，只需暴露驾驶员要操作的部件（方向盘、油门、刹车）。

**不封装的问题**：属性可以被外部随意赋值，非法数据（年龄 -18、成绩 9000）不会报错，造成数据不合理。

```java
public class Test {
    public static void main(String[] args) {
        Student s1 = new Student();
        s1.id = -1;
        s1.age = -18;
        s1.mathScore = 9000;
        s1.chineseScore = -80;   // 全部不报错，但数据完全非法
    }
}
```

封装的第一层含义是**把数据（属性）和操作数据的方法捆绑在一起组成一个整体（类）**。以学生成绩表为例，不封装时，每个学生的数据都是一堆零散变量，算总分、展示信息也要靠外部函数一个个传参：

```java
// 不封装：数据零散，处理数据的方法和数据没有任何归属关系
int id1 = 1;
String name1 = "张三";
int age1 = 23;
double chineseScore1 = 87;
double mathScore1 = 90;
// 再来一个学生就要再定义 5 个变量……
```

封装后，数据和处理数据的方法都属于学生对象自己：

```java
public class Student {
    int id;
    String name;
    int age;
    double mathScore;
    double chineseScore;

    public Student(int id, String name, int age, double mathScore, double chineseScore) {
        this.id = id;
        this.name = name;
        this.age = age;
        this.mathScore = mathScore;
        this.chineseScore = chineseScore;
    }

    // 计算总成绩：数据和方法捆绑在类中
    public double getTotalScore() {
        return mathScore + chineseScore;
    }

    // 展示学生所有信息
    public void showStudentInfos() {
        System.out.println("学号: " + id);
        System.out.println("姓名: " + name);
        System.out.println("年龄: " + age);
        System.out.println("数学成绩: " + mathScore);
        System.out.println("语文成绩: " + chineseScore);
    }
}
```

```java
Student stu1 = new Student(1, "张三", 23, 90, 87);
stu1.showStudentInfos();
System.out.println("总成绩：" + stu1.getTotalScore());
```

这样做的好处：**更好地维护数据；使用者无需关心内部实现，只要知道如何调用即可**（Scanner、Random 也是这样设计的）。

封装的第二层含义是通过访问修饰符控制访问权限，实现"**合理隐藏，合理暴露**"。典型例子：手机打电话时内部要保存通话记录，但保存记录是手机自己的事，不该让外部直接调用：

```java
public class Phone {
    public void call(String name) {
        System.out.println("给" + name + "打电话");
        saveLog();   // 内部方法自己调用
    }

    // 私有方法：只在类内部使用，对外隐藏实现细节
    private void saveLog() {
        System.out.println("将联系人-时间-通话时长保存到本地");
    }
}
```

外部只能调用 `call()`，直接调用 `p.saveLog()` 会编译报错——这就是合理暴露 call、合理隐藏 saveLog。

#### 7.2 封装的步骤（必须记住）

**步骤 1：给成员变量添加 `private` 私有修饰符**

被 private 修饰的成员变量只能在当前类内部访问/赋值，外部类无法直接访问、直接修改，从根源上杜绝外部随意操作数据。

```java
private 数据类型 变量名;   // 例：private String name;
```

**步骤 2：在类内部提供 public 修饰的、成对的 getXxx() / setXxx() 方法**

这是给外部类提供的唯一合法访问入口：

- `getXxx()`：获取值，有返回值，无参数；
- `setXxx()`：设置值，void 无返回值，有参数；可以在方法内加入数据校验逻辑。

```java
public class Student {
    //合理隐藏
    private int id;
    private String name;
    private int age;
    private double mathScore;
    private double chineseScore;

    //合理暴露
    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    //在 set 方法中进行非法值过滤
    public void setAge(int age) {
        if (age >= 0 && age <= 130) {
            this.age = age;
        } else {
            System.out.println("您的年龄不合法，请输入0~130之间的数值");
        }
    }

    public double getMathScore() {
        return mathScore;
    }

    public void setMathScore(double mathScore) {
        this.mathScore = mathScore;
    }

    public double getChineseScore() {
        return chineseScore;
    }

    public void setChineseScore(double chineseScore) {
        this.chineseScore = chineseScore;
    }
}
```

测试：

```java
public class Test {
    public static void main(String[] args) {
        Student s1 = new Student();
        //设置数据
        s1.setId(1);
        s1.setName("小哈");
        s1.setAge(18);
        s1.setMathScore(88.9);
        s1.setChineseScore(100);
        //获取数据
        System.out.println(s1.getId());
        System.out.println(s1.getName());
        System.out.println(s1.getAge());
        System.out.println(s1.getMathScore());
        System.out.println(s1.getChineseScore());
    }
}
```

#### 7.3 封装的好处

1. **保证数据的安全性和正确性**（核心价值）：所有赋值都经过 setXxx()，可在方法中校验，过滤非法值（年龄负数、分数超 100）。
2. **隐藏内部实现细节**：遵循"对内开放，对外隐藏"，外部只需要知道调用哪个方法，不关心内部实现，降低耦合度。如同用手机打电话只需拨号，不用关心芯片和信号如何工作（Random、Scanner 也是如此）。
3. **提升可维护性和可扩展性**：修改内部逻辑（如年龄合法范围）只改类内部方法，外部调用代码一行不改；新增属性只需加私有变量 + get/set 方法。

例如对数学成绩加合法性校验，外部调用无需任何改动：

```java
public void setMathScore(double mathScore) {
    if (mathScore >= 0 && mathScore <= 100) {
        this.mathScore = mathScore;
    } else {
        System.out.println("您输入的数学成绩不合理，请输入0~100的数");
    }
}
```

#### 7.4 权限修饰符

权限修饰符用来控制**类、成员变量、成员方法、构造方法**的可访问范围，是封装特性的核心实现手段。Java 中常用 4 个，权限从大到小：

| 修饰符 | 本类 | 同包 | 不同包子类 | 任意位置 |
| --- | --- | --- | --- | --- |
| **public**（公共权限） | 可以 | 可以 | 可以 | 可以 |
| **protected**（受保护权限） | 可以 | 可以 | 可以 | 不可以 |
| **default**（默认权限，不写修饰符） | 可以 | 可以 | 不可以 | 不可以 |
| **private**（私有权限） | 可以 | 不可以 | 不可以 | 不可以 |

### 八、标准 JavaBean（实体类）

#### 8.1 概述

JavaBean 实体类是 Java 开发中"标准化的数据容器"，通过严格规范实现数据的安全封装，提升代码通用性和可维护性。实体类只负责数据存取，数据的处理交给其他类完成，实现**数据与业务处理相分离**。

也就是说，一个标准的面向对象程序通常分两类角色：

- **实体类（JavaBean）**：只装数据（私有属性 + get/set + 构造器），如 Student、Movie；
- **操作类（Operator/Service）**：接收实体对象，负责对数据进行处理（计算、展示、查询）。

```java
// 操作类：专门处理学生数据，实体类 Student 作为参数传入
public class StudentOperator {
    private Student s;

    // 通过构造器接收要操作的学生对象
    public StudentOperator(Student s) {
        this.s = s;
    }

    // 操作类中定义处理数据的业务方法（展示、统计、筛选等）
    public void showStudent() {
        System.out.println(s.getName() + "，" + s.getAge() + "岁");
    }
}
```

**编写条件**：

1. 类必须是公共的（public）；
2. 成员变量全部私有（private），并提供 public 修饰的 getXxx/setXxx 方法；
3. 提供一个无参构造器，有参构造器可选。

```java
package pojo;

public class Student {
    //成员变量（属性）
    private int id;
    private String name;
    private int age;
    private double mathScore;
    private double chineseScore;

    //无参构造器
    public Student() {
    }

    //有参构造器
    public Student(int id, String name, int age, double mathScore, double chineseScore) {
        this.id = id;
        this.name = name;
        this.age = age;
        this.mathScore = mathScore;
        this.chineseScore = chineseScore;
    }

    //set和get方法
    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public double getMathScore() {
        return mathScore;
    }

    public void setMathScore(double mathScore) {
        this.mathScore = mathScore;
    }

    public double getChineseScore() {
        return chineseScore;
    }

    public void setChineseScore(double chineseScore) {
        this.chineseScore = chineseScore;
    }
}
```

#### 8.2 JavaBean 与 POJO

JavaBean 实体类通常保存在 `pojo` 包中。POJO = Plain Ordinary Java Object，即"简单普通的 Java 对象"。

- 日常开发中 **JavaBean ≈ POJO**，二者指同一个东西，可以划等号；
- 严格区别（了解即可）：JavaBean 是 Sun 公司定义的标准规范，要求更严格；POJO 是程序员约定的开发规范，更简洁。企业开发中写的 Student、User、Order 这类类，既叫 JavaBean 也叫 POJO。

### 九、static 关键字

#### 9.1 概述

static 是静态的意思，可以修饰成员变量和成员方法。

**特点**：

- 被 static 修饰的成员，被该类的**所有对象共享**；
- 多了一种调用方式：可以直接通过**类名调用**（推荐）；
- **随着类的加载而加载，优先于对象存在**。

**内存原理**：static 成员变量在类加载时就存入方法区的**静态成员区**（不属于任何一个对象，而是属于类），全类只有一份。每个对象在堆中各自存储自己的成员变量，但访问 static 变量时都指向方法区中同一份数据——这就是"共享"的底层含义。

典型应用：统计在线人数。所有用户对象共享一个计数器：

```java
class User {
    String name;
    int age;
    static int onLineNumber;   // 静态变量：所有用户共享的在线人数
}

public class StaticTest {
    public static void main(String[] args) {
        User.onLineNumber++;            // 第 1 个用户上线，推荐用类名操作
        User u1 = new User();
        u1.name = "张三";
        u1.age = 23;
        System.out.println(u1.name + "---" + u1.age + "---" + u1.onLineNumber);  // 张三---23---1

        User.onLineNumber++;            // 第 2 个用户上线
        User u2 = new User();
        u2.name = "李四";
        u2.age = 24;
        System.out.println(u2.name + "---" + u2.age + "---" + u2.onLineNumber);  // 李四---24---2
    }
}
```

**使用场景**：static 成员变量用于**需要被所有对象共享的数据**（学校名、在线人数、序列号）；static 成员方法常用于**工具类**。

```java
public class Student {
    private static String school;   // 共享数据，所有学生同一个学校
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public static String getSchool() {
        return school;
    }

    public static void setSchool(String school) {
        Student.school = school;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Student.setSchool("黑马程序员");   // 类名直接调用，推荐
        //创建学生1
        Student student1 = new Student();
        student1.setName("小哈");
        student1.setAge(18);
        //创建学生2
        Student student2 = new Student("小米",16);

        //使用实例对象访问 static 共享数据（不推荐）
        System.out.println(student1.getName() + "，今年" + student1.getAge()+"岁，就读于"+student1.getSchool());
        System.out.println(student2.getName() + "，今年" + student2.getAge()+"岁，就读于"+student2.getSchool());
        System.out.println("--------------------------------------");
        //使用类名访问 static 共享数据（推荐使用）
        System.out.println(student1.getName() + "，今年" + student1.getAge()+"岁，就读于"+Student.getSchool());
        System.out.println(student2.getName() + "，今年" + student2.getAge()+"岁，就读于"+Student.getSchool());
    }
}
```

#### 9.2 static 注意事项

- **static 中不允许使用 this 关键字**：this 代表对象地址，地址是创建对象之后才有的东西，而静态成员优先于对象存在。
- **static 方法中只能直接访问静态成员**：静态成员随类加载而加载，非静态成员需要创建对象后才能使用；静态成员存在时非静态成员可能还不存在。

```java
public class Test1 {
    int num = 10;
    public static void main(String[] args) {
        //编译报错：static 静态方法中不能直接访问非静态成员
        System.out.println(num);
    }
}
```

解决方案：

```java
// 方案1：创建对象访问（不推荐）
public class Test1 {
    int num = 10;
    public static void main(String[] args) {
        Test1 t = new Test1();
        System.out.println(t.num);
    }
}

// 方案2：把成员变量改为 static 修饰
public class Test1 {
    static int num = 10;
    public static void main(String[] args) {
        System.out.println(num);
    }
}
```

### 十、工具类

#### 10.1 概述

Java 工具类是封装了**通用、高频复用逻辑**的类，核心特点是**全静态方法**，无需创建对象，直接通过 `类名.方法名` 调用，能大幅简化开发、避免重复造轮子。

- JDK 原生工具类（无依赖直接使用）：字符串 String、数字 Integer/Long、数学 Math、集合 Collections、数组 Arrays、判空 Objects、日期 java.time 包等；
- 第三方工具包（需引入依赖）：如 Apache Commons；
- 开发中也经常需要**自定义工具类**，这是开发标配习惯。

**什么时候必须写自定义工具类**：

- 同一段业务逻辑在多处重复书写（校验手机号、格式化金额）；
- JDK 原生和第三方工具类解决不了的业务需求；
- 一段代码逻辑需要统一维护、统一修改（规则变了只需改 1 处）。

**自定义工具类的固定编写规范（3 条）**：

1. 所有业务方法全部加 `public static`，直接 `类名.方法名()` 调用；
2. 写**私有化无参构造器** `private 类名(){}`，防止别人创建对象（工具类创建对象毫无意义）；
3. 类名命名为 **XXXUtil / XXXUtils**（如 DateUtil、CommonUtil）。

#### 10.2 案例：验证码工具类

需求：创建 ValidateCodeUtil，提供 `generateNumberCode`（生成指定长度纯数字验证码）和 `generateMixCode`（生成数字+大小写字母混合验证码）两个功能。

```java
package com.itheima.utils;

import java.util.Random;

/**
 * 这是一个验证码生成工具类，内部提供了生成指定位数的验证码
 * 纯数字验证码、大小写字母数字混合的验证码
 * @version 1.0
 * @author 小哈
 */
public class ValidateCodeUtil {
    static Random r = new Random();

    //私有化构造器，禁止实例化，工具类的固定规范
    private ValidateCodeUtil() {
    }

    /**
     * 生成指定长度的【纯数字验证码】【开发最常用】
     * 适用：短信验证码、登录验证码、注册验证码 （推荐4/6位）
     * @param length 验证码长度
     * @return codeStr  纯数字验证码字符串
     */
    public static String generateNumberCode(int length) {
        //非法参数兜底：长度不在 1~8 范围内，直接用4位兜底
        if (length <= 0 || length > 8) {
            length = 4;
        }
        String codeStr = "";
        for (int i = 0; i < length; i++) {
            int num = r.nextInt(10);   //生成0~9的随机数
            codeStr += num;
        }
        return codeStr;
    }

    /**
     * 生成指定长度的【数字+大小写字母 混合验证码】
     * 适用：图形验证码、注册页面验证码、支付验证 （推荐4位）
     * @param length 验证码长度
     * @return codeStr 混合验证码字符串
     */
    public static String generateMixCode(int length){
        if (length <= 0 || length > 8) {
            length = 4;
        }
        // 验证码字符库：数字 + 大小写字母
        String codeData = "0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
        String codeStr = "";
        for (int i = 0; i < length; i++) {
            int index = r.nextInt(codeData.length());   //随机下标
            codeStr += codeData.charAt(index);          //取下标处的单个字符
        }
        return codeStr;
    }
}
```

使用：

```java
import com.itheima.utils.ValidateCodeUtil;

public class Test {
    public static void main(String[] args) {
        // 1. 生成6位纯数字验证码（登录/短信常用）
        String numberCode = ValidateCodeUtil.generateNumberCode(6);
        System.out.println("生成的6位数字验证码是："+numberCode);

        //2. 生成6位混合验证码
        String mixCode = ValidateCodeUtil.generateMixCode(6);
        System.out.println("生成的6位混合验证码是："+mixCode);
    }
}
```

**IDEA 中跨模块引用工具类（基础班方式，无需 Maven）**：

1. `File` → `Project Structure`（快捷键 Ctrl+Alt+Shift+S）；
2. 左侧选 `Modules` → 选中要调用工具类的业务模块（如 user 模块）；
3. 右侧选 `Dependencies` → 点 **+** → `Module Dependency` → 选中 common 模块 → OK。

**生成帮助文档（JavaDoc）**：写好工具类后建议配帮助文档（降低使用门槛、明确使用边界、减少沟通成本、方便维护迭代、符合企业规范）。步骤：打开工具类 → 菜单栏 `Tools` → `Generate JavaDoc`（多个工具类时选择对应 Module）。

### 十一、重新认识 main 方法

```java
package utils;

public class Test1 {
    public static void main(String[] args) {
        for (int i = 0; i < args.length; i++) {
            System.out.println(args[i]);
        }
    }
}
```

`public static void main(String[] args)` 中：

- `public`：被 JVM 调用，权限要足够大；
- `static`：JVM 调用时不创建对象，直接用类名调用；**正因为 main 是静态方法，测试类中被 main 直接调用的其他方法也必须加 static**（静态只能直接访问静态）；
- `void`：没有返回值返回给 JVM；
- `main`：一个通用的名称，**虽然不是关键字，但是被 JVM 识别**为程序入口；
- `String[] args`：字符串数组，早期用于接收命令行传入的参数（键盘录入数据），现在基本不用。

注意：用命令行 javac 编译、java 运行时，如果类写了 package 包名，需要先 `cd..` 回到 src 目录，再用 `java 包名.类名` 的格式运行，否则会报找不到类的错误。

### 十二、综合案例：电影信息系统

需求：展示系统中的全部电影（每部展示名称、价格等）；允许用户根据电影编号（id）查询某部电影的详细信息。

电影数据：

```
1,"水门桥",38.9,9.8,"徐克","吴京","12万人想看"
2,"出拳吧",39,7.8,"唐晓白","田雨","3.5万人想看"
3,"月球陨落",42,7.9,"罗兰","贝瑞","17.9万人想看"
4,"一点到家",35,8.7,"徐宏宇","刘昊然","10.8万人想看"
```

**第一步：创建实体 JavaBean——电影类 Movie**

```java
public class Movie {
    private int id;            //编号
    private String name;       //名字
    private double price;      //价格
    private double scroe;      //评分
    private String director;   //导演
    private String actor;      //主演
    private String info;       //描述

    public Movie() {
    }

    public Movie(int id, String name, double price, double scroe, String director, String actor, String info) {
        this.id = id;
        this.name = name;
        this.price = price;
        this.scroe = scroe;
        this.director = director;
        this.actor = actor;
        this.info = info;
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        this.price = price;
    }

    public double getScroe() {
        return scroe;
    }

    public void setScroe(double scroe) {
        this.scroe = scroe;
    }

    public String getDirector() {
        return director;
    }

    public void setDirector(String director) {
        this.director = director;
    }

    public String getActor() {
        return actor;
    }

    public void setActor(String actor) {
        this.actor = actor;
    }

    public String getInfo() {
        return info;
    }

    public void setInfo(String info) {
        this.info = info;
    }
}
```

**第二步：创建操作类 MovieOperator，专门实现对象操作**

```java
public class MovieOperator {
    //展示所有电影信息，需要传一个电影数据数组
    public static void show(Movie[] movies) {
        System.out.println("======所有电影信息如下======");
        for (int i = 0; i < movies.length; i++) {
            Movie movie = movies[i];//遍历到的当前电影数据
            //使用实体类Movie提供的get方法获取数据
            System.out.println("电影编号：" + movie.getId());
            System.out.println("电影名称：" + movie.getName());
            System.out.println("电影价格：" + movie.getPrice());
            System.out.println("电影评分：" + movie.getScroe());
            System.out.println("导演：" + movie.getDirector());
            System.out.println("主演：" + movie.getActor());
            System.out.println("电影简介：" + movie.getInfo());
            System.out.println("----------------------------");
        }
    }

    //根据id查询某一部电影详情
    public static void searchMovieId(int id, Movie[] movies) {
        System.out.println("======您所查询的电影详情如下======");
        for (int i = 0; i < movies.length; i++) {
            Movie movie = movies[i];
            if (movie.getId() == id) {
                System.out.println("电影编号：" + movie.getId());
                System.out.println("电影名称：" + movie.getName());
                System.out.println("电影价格：" + movie.getPrice());
                System.out.println("电影评分：" + movie.getScroe());
                System.out.println("导演：" + movie.getDirector());
                System.out.println("主演：" + movie.getActor());
                System.out.println("电影简介：" + movie.getInfo());
                return;   //查到后直接结束方法
            }
        }
        System.out.println("没有查到相关信息！！！");
    }
}
```

**第三步：测试类组装系统**

```java
public class Test {
    public static void main(String[] args) {
        //使用Movie实体类创建一个数组对象，用来存放电影数据
        Movie[] movies = new Movie[4];
        //使用有参构造器给数组传值
        movies[0] = new Movie(1,"水门桥",38.9,9.8,"徐克","吴京","12万人想看");
        movies[1] = new Movie(2,"出拳吧",39,7.8,"唐晓白","田雨","3.5万人想看");
        movies[2] = new Movie(3,"月球陨落",42,7.9,"罗兰","贝瑞","17.9万人想看");
        movies[3] = new Movie(4,"一点到家",35,8.7,"徐宏宇","刘昊然","10.8万人想看");

        //创建电影操作对象
        MovieOperator operator = new MovieOperator();

        //系统界面
        Scanner sc = new Scanner(System.in);
        System.out.println("======欢迎进入电影信息管理系统======");
        while (true) {
            System.out.println("1.查看所有电影信息");
            System.out.println("2.根据id查找某一电影信息");
            System.out.println("3.退出");
            System.out.println("======请选择您的命令======");
            int command = sc.nextInt();
            switch (command) {
                case 1:
                    operator.show(movies);
                    break;
                case 2:
                    System.out.println("请输入您要查询的电影ID");
                    int id = sc.nextInt();
                    operator.searchMovieId(id,movies);
                    break;
                case 3:
                    System.out.println("成功退出系统");
                    return;//退出当前方法运行
                default:
                    System.out.println("您输入的命令不正确！请重新输入!!!");
            }
        }
    }
}
```

这个案例体现了标准的面向对象分层思想：**实体类（Movie）只封装数据，操作类（MovieOperator）负责业务逻辑，测试类负责组装与交互**。

---

### 本章小结

1. 面向对象的核心是**先设计类、再用类 new 出对象**，把属性和行为封装在一起，关注"谁来做"。
2. 对象在**堆内存**中存储，栈中的引用变量保存对象地址；多个引用可以指向同一个对象。
3. 成员变量在类中方法外、存堆内存、有默认值；局部变量在方法/代码块中、存栈内存、必须先赋值。
4. **this** 代表当前对象的引用，用于区分重名的成员变量与局部变量，不能在 static 方法中使用。
5. **构造器**与类同名、无返回值类型，用于创建对象；写了有参构造器后默认无参构造器消失，需手动补写。
6. **封装**两步走：成员变量 private 私有化 + 提供 public 的 get/set 方法，并在 set 中做数据校验。
7. 权限修饰符权限从大到小：public > protected > default > private。
8. **标准 JavaBean**：public 类、私有属性、get/set、无参构造器，通常放在 pojo 包中。
9. **static** 修饰的成员被所有对象共享、可用类名调用、随类加载；静态方法中只能直接访问静态成员、不能用 this。
10. **工具类**三规范：方法全 static、构造器 private 私有化、类名 XXXUtil/XXXUtils。

---

<div style="page-break-after: always;"></div>

## 第八章 面向对象高级（上）：继承、Object、final、抽象类与模板模式

本章进入面向对象的核心高级特性。首先学习**继承**——让子类复用父类代码、建立类之间的层次关系；然后认识所有类的祖宗类 `Object`；接着掌握 `final` 关键字与**抽象类**；最后了解基于抽象类的**模板方法设计模式**。

---

### 一、继承

#### 1.1 继承概述

- Java 中的**继承（Inheritance）** 是面向对象三大特性（封装、继承、多态）之一，核心思想是 **"复用已有类的代码，实现类之间的层次关系"**。
- 多个子类如果有**相同的属性和方法**，不需要在每个子类中重复编写，只需要把这些共性内容抽取到**父类**中，所有子类通过继承直接"拿来即用"，极大减少冗余代码。

例如公司的员工有程序员 Programmer 和经理 Manager，都有各自的姓名 name、工号 id、薪资 salary。如果每个类都单独设置，代码会冗余繁琐，此时就可以使用继承来简化代码。

#### 1.2 继承的语法

**Java 中提供了关键字 `extends`，用这个关键字可以让一个类和另一个类建立起父子关系。**

```java
// 父类（基类/超类）：被继承的类
class 父类名 {
    
}

// 子类（派生类）：继承父类的类
class 子类名 extends 父类名 {
    
}
```

#### 1.3 引导案例：员工体系

**第一步：将共性的属性提取出来，设置给一个父类 Employee 员工类。**

注意：我们可以将属性私有化合理隐藏，然后使用 get 和 set 方法合理暴露（此处暂不操作）。

```java
public class Employee {
    //共有属性
    String name;    // 姓名（共性）
    String id;      // 工号（共性）
    double salary;  // 薪资（共性）
    //共有方法
    public void goWork() {
        System.out.println(name +"每天需要上班打卡！");
    }
}
```

**第二步：让子类——程序员类 Programmer 和经理类 Manager 继承父类，同时定义自己独立的方法。**

```java
public class Programmer extends Employee{
    //成员独有方法
    public void workTask(){
        System.out.println(name + "每天的任务就是和客户沟通！");
    }
}
```

```java
public class Manager extends Employee{
    //成员独有方法
    public void workTask(){
        System.out.println(name + "每天的任务就是在公司写代码，调试bug");
    }
}
```

**第三步测试：**

```java
public class Test {
    public static void main(String[] args) {
        //创建程序员实例
        Programmer p = new Programmer();
        p.name = "小哈";
        p.id = "KF001";
        p.salary = 18000.0;
        System.out.println(p.name + "，是公司的一名程序员,每月薪资是：" + p.salary);
        p.goWork();
        p.workTask();

        System.out.println("---------------------------------");

        //创建经理实例
        Manager m = new Manager();
        m.name = "小米";
        m.id = "JL001";
        m.salary = 28000.0;
        System.out.println(m.name + "，是公司的一名销售经理,每月薪资是：" + m.salary);
        m.goWork();
        m.workTask();
    }
}
```

测试结果：

```
小哈，是公司的一名程序员,每月薪资是：18000.0
小哈每天需要上班打卡！
小哈每天的任务就是在公司写代码，调试bug
---------------------------------
小米，是公司的一名销售经理,每月薪资是：28000.0
小米每天需要上班打卡！
小米每天的任务就是和客户沟通！
```

#### 1.4 什么时候使用继承

**当类与类之间存在相同（共性）的内容，并且产生了 is-a 的关系，就可以考虑使用继承来优化代码。**

例如：程序员 is a 员工、经理 is a 员工、猫 is a 动物。不要为了省几行代码而滥用继承，必须符合"is-a"的语义。

**反例（不能滥用继承）：** 程序员有 id、姓名、年龄；商品有 id、品牌、价格。两者虽然都有 id，但不存在 is-a 关系（程序员不是商品），如果硬抽出一个父类存放"id、姓名、年龄、品牌、价格"，父类就会变得不伦不类。继承的前提是**共性内容 + is-a 关系**同时成立。

#### 1.5 继承中成员变量的访问特点

继承中访问成员变量，**遵循"就近原则"：谁离我近，我就用谁的**。

JVM 会按"从小范围到大范围"的顺序查找，找到即停止，找不到才继续找：

> 查找优先级：子类局部变量 → 子类的成员变量 → 父类的成员变量 → 报错

如果局部变量、子类成员变量、父类成员变量同名，可以使用 `this` 和 `super` 关键字明确指定：

- `this`：调用本类成员
- `super`：调用父类成员

```java
public class Fu {
    //父类成员变量
    String name = "FatherName";
}
```

```java
class Zi extends Fu {
    //子类成员变量
    String name = "SonName";

    public void show() {
        //局部变量
        String name = "LocalName";
        //直接打印 name：遵循就近原则，优先访问方法内的局部变量；
        System.out.println(name); //LocalName
        
        //this.name：this 代表当前子类对象，访问子类的成员变量；
        System.out.println(this.name);//SonName
        
        //super.name：super 代表父类对象，访问父类的成员变量
        System.out.println(super.name);//FatherName
    }
}
```

测试：

```java
public class Test {
    public static void main(String[] args) {
        Zi zi = new Zi();
        zi.show();
    }
}
```

#### 1.6 继承中成员方法的访问特点：方法重写

##### 1.6.1 什么是方法重写

思考：子类继承父类之后，如果编写的方法结构和父类相同、但方法内逻辑不相同，创建子类对象调用该方法时，执行的是父类逻辑还是子类逻辑？

答案是执行"子类的方法"——但这不是就近原则，而是**方法重写（Override）**。

- 在 Java 中，**方法重写（Override）** 是指子类重新定义父类中已有的方法，使子类对象在调用该方法时执行子类的实现而非父类的实现。这是实现**多态**的核心机制之一。
- **简单理解：** 当子类觉得父类中的某个方法不好用，或者无法满足自己的需求时，**子类可以重写一个方法名称、参数列表完全一样的方法**，去覆盖父类的这个方法。
- **格式要求：** 子类重写父类方法时，方法声明需要和父类完全一致——**方法名、参数列表、返回值类型都要保持一致**。

##### 1.6.2 引导案例

需求：

> **一、定义父类 `Employee`（员工类）**
>
> 1. 定义私有成员变量：`private String name`（员工姓名）
> 2. 为私有姓名提供对应的 `getter` 和 `setter` 方法
> 3. 定义成员方法 `work()`：输出 `姓名 + 每天早上8:00准时打卡上班！`
>
> **二、定义子类 `Developer`（开发人员类）**
>
> 1. 让该类继承父类 `Employee`
> 2. **重写**父类的 `work()` 方法（必须添加 `@Override` 注解）
> 3. 重写后的 work() 输出三行内容：
>    - 姓名 + 每天早上 10:00 准时打卡上班！
>    - 打完卡后就开始工作：写代码，调试 Bug
>    - 姓名 + 每天晚上 8:30 准时打卡下班！
> 4. 注意：子类中不能直接访问父类的私有成员变量 name，必须通过父类提供的 getName() 方法获取姓名

员工类 Employee：

```java
public class Employee {
    //成员属性
    private String name;    // 姓名

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    //工作方法
    public void work() {
        System.out.println(name +"每天早上8:00准时打卡上班！");
    }
}
```

开发人员类：

```java
public class Developer extends Employee {
    //方法重写
    @Override
    public void work() {
        //super.work();//保留父类的逻辑（根据需求删除或者保留）
        System.out.println(getName() +"每天早上10:00准时打卡上班！");
        System.out.println("打完卡后就开始工作：写代码，调试Bug~~");
        System.out.println(getName() +"每天晚上8:30准时打卡下班！");
    }
}
```

测试类：

```java
public class Test {
    public static void main(String[] args) {
        Developer d1 = new Developer();
        d1.setName("小哈叔");
        d1.work();
    }
}
```

打印结果：

```
小哈叔每天早上10:00准时打卡上班！
打完卡后就开始工作：写代码，调试Bug~~
小哈叔每天晚上8:30准时打卡下班！
```

##### 1.6.3 方法重写的注意事项

- 使用 `@Override` 注解：它可以让 Java 编译器检查方法重写的格式是否正确（比如方法名写错、形参列表不一致都会报错），代码可读性也更好。
- 子类重写父类方法时，**访问权限必须大于或者等于父类该方法的权限**（`public > protected > default > private`）。
- **私有方法、静态方法不能被重写**（父类私有方法子类压根看不到，谈不上重写；静态方法是静态绑定，子类写同名方法属于"隐藏"而非重写）。

四种权限修饰符的访问范围（重写时权限只能放大、不能缩小的依据）：

| 修饰符 | 同一个类中 | 同一个包中 | 不同包的子类 | 不同包的无关类 |
| --- | :---: | :---: | :---: | :---: |
| `private` | √ | | | |
| `default`（默认，什么都不写） | √ | √ | | |
| `protected` | √ | √ | √ | |
| `public` | √ | √ | √ | √ |

#### 1.7 继承的特点：单继承与多层继承

- **Java 只支持单继承，不支持多继承，但支持多层继承。**
  - 一个类只能有一个直接父类（不能 `class A extends B, C`）。
  - 但可以有多层：`A extends B`、`B extends C`，此时 A 间接继承了 C。
  - 一个父类可以同时拥有多个子类。

**为什么不支持多继承？** 如果一个子类同时继承两个父类，而两个父类中都有同名方法，子类调用时就会产生歧义——到底执行哪个父类的逻辑？

```java
public class 父类A {
    public void method(){ System.out.println("复习数学"); }
}
public class 父类B {
    public void method(){ System.out.println("复习语文"); }
}
// class 子类 extends 父类A, 父类B { }  // 语法不允许
// 若允许，new 子类().method() 到底复习啥？懵了！
```

**为什么多层继承可以？** 多层继承链上方法调用是确定的：`C extends B`、`B extends A`，C 调用 method() 时按就近原则先找到 B 的实现，不会产生二义性。

##### 案例：公司员工体系（多层继承）

需求：基于"公司人员体系"设计多层继承结构，最终输出：

```
小哈，性别男，23岁，所属部门 - 软件开发部，工号SF006，薪资为8000
```

顶层父类——公司人员基础信息：

```java
/**
 * 顶层父类：公司人员基础信息
 * 包含所有人员的通用属性：姓名、性别、年龄
 */
public class CompanyPerson {
    // protected修饰，子类可访问
    protected String name;
    protected String gender;
    protected int age;

    public CompanyPerson(){}
    /**
     * 构造方法：初始化基础人员信息
     */
    public CompanyPerson(String name, String gender, int age) {
        this.name = name;
        this.gender = gender;
        this.age = age;
    }
}
```

中间子类——普通员工（继承 CompanyPerson），新增部门、工号：

```java
/**
 * 中间子类：普通员工信息（继承CompanyPerson）
 * 新增员工专属属性：所属部门、工号
 */
public class RegularEmployee extends CompanyPerson {
    // 新增员工专属属性
    protected String deptName;
    protected String id;

    public RegularEmployee(){}
    /**
     * 构造方法：初始化普通员工信息
     */
    public RegularEmployee(String name, String gender, int age, String deptName, String id) {
        // 调用父类构造方法初始化基础信息
        super(name, gender, age);
        this.deptName = deptName;
        this.id = id;
    }
}
```

底层子类——开发人员（继承 RegularEmployee），新增薪资：

```java
/**
 * 底层子类：开发人员（继承RegularEmployee）
 * 新增开发人员专属属性：薪资
 */
public class Developer extends RegularEmployee {
    // 开发人员专属属性（私有，仅本类访问）
    private double salary;

    public Developer(){}
    /**
     * 构造方法：初始化开发人员信息
     */
    public Developer(String name, String gender, int age, String deptName, String id, double salary) {
        // 调用父类构造方法初始化员工信息
        super(name, gender, age, deptName, id);
        this.salary = salary;
    }

    /**
     * 输出开发人员完整信息（严格匹配指定格式）
     */
    public void showInfo() {
        System.out.println(name + "，性别" + gender + "，" + age + "岁，所属部门 - " + deptName + "，工号" + id + "，薪资为" + (int)salary);
    }
}
```

测试：

```java
/**
 * 测试类：运行并验证多层继承的输出结果
 */
public class TestDemo {
    public static void main(String[] args) {
        // 实例化开发人员对象，传入指定参数
        Developer dev = new Developer("小哈", "男", 23, "软件开发部", "SF006", 8000);
        // 调用方法输出信息
        dev.showInfo();
    }
}
```

#### 1.8 this 和 super 关键字

- `this` 代表**本类对象的引用**：指向"自己"，用来区分自己的属性/方法和外部变量（如构造方法参数）。
- `super` 代表**父类存储空间的标识**（可以理解为父类对象的引用）：用来访问父类的属性、方法、构造方法。

两者的完整用法对比：

| 关键字 | 访问成员变量 | 访问成员方法 | 访问构造方法 |
| --- | --- | --- | --- |
| `this` | `this.本类成员变量;` | `this.本类成员方法();` | `this();` / `this(参数);` 调用本类构造方法 |
| `super` | `super.父类成员变量;` | `super.父类成员方法();` | `super();` / `super(参数);` 调用父类构造方法 |

注意：

- **构造方法不能被继承**，子类需要自己手动编写构造方法。
- `this(...)` 和 `super(...)` 都要求写在构造方法的**第一行**，二者争夺同一个位置，所以**不能同时出现**。
- 子类通过 `super(...)` 调用父类构造方法，本质是为了先完成父类成员的初始化——子类初始化之前，必须先保证父类部分初始化完毕。

##### 1.8.1 super 访问成员变量和方法的细节

格式：

> `super.父类成员变量`
> `super.父类成员方法();`

- 如果调用的成员在子类中不存在，`super` 可以省略不写。
- 实际上子类继承了父类之后，子类就拥有了一份父类的成员变量，所以我们访问的本质上是 `this.成员变量` 和 `this.成员方法`。

```java
public class Demo1 {
    public static void main(String[] args) {
        Zi zi = new Zi();
        zi.method();
    }
}
class Fu {
    int num = 10;
    public void show(){
        System.out.println("Ful类的show方法~~~");
    }
}
/*
     super的调用细节：
        super.父类成员变量
        super.父类成员方法();
        如果调用的成员，在子类中不存在，super可以省略不写,
        实际上子类继承了父类，此时子类就有了一份父类的成员变量，
        所以我们访问的是this.成员变量 和 this.成员方法
 */
class Zi extends Fu{
    //子类中访问父类的成员和方法
    public void method(){
        //System.out.println(super.num);
        System.out.println(num);
        //super.show();
        show();
    }
}
```

##### 1.8.2 this 访问本类构造器

格式：

- `this()`：调用本类无参构造器
- `this(参数)`：调用本类有参构造器

**使用场景：** 项目 1.0 版本上线后需要升级 2.0 版本，新功能需要在原本构造器的基础上添加参数。如果直接修改原有构造器，1.0 项目中所有创建对象的代码都要改，非常不方便。此时可以在类中多定义一个构造器，用 `this(...)` 调用已有构造器来简化代码。

1.0 版本：记录明星的姓名、年龄、性别。

```java
/*
    项目1.0 版本 记录明星的姓名年龄性别
 */
public class Demo2 {
    public static void main(String[] args) {
        Star star = new Star("黄晓明",48,'男');
        System.out.println(star);
    }
}
class Star {
    String name;
    int age;
    char sex;

    public Star() {
    }
    public Star(String name, int age,char sex) {
        this.name = name;
        this.age = age;
        this.sex = sex;
    }
}
```

2.0 版本：新增身高和代表作。类中存在多个构造器，某些构造器的内容已经被其他构造器实现，直接使用 `this(...)` 调用即可。**注意：this 调用构造器必须放在构造方法的第一行。**

```java
/*
    项目1.0 版本 记录明星的姓名年龄性别
    项目升级2.0，记录明星的姓名、年龄、性别、身高和代表作
 */
public class Demo2 {
    public static void main(String[] args) {
        Star star1 = new Star("黄晓明",48,'男');
        //项目2.0的功能不影响1.0部分使用
        Star star2 = new Star("刘德华",64,'男',174,"《忘情水》");
    }
}
class Star {
    String name;
    int age;
    char sex;
    double height;
    String masterpiece;

    public Star() {
    }
    public Star(String name, int age,char sex) {
        this.name = name;
        this.age = age;
        this.sex = sex;
    }
    //新功能构造器
    public Star(String name, int age, char sex, double height, String masterpiece) {
        //name、age、sex前面的构造器定义过了
        //使用this调用本类构造器简化代码
        this(name,age,sex);   //必须在第一行
        this.height = height;
        this.masterpiece = masterpiece;
    }
}
```

##### 1.8.3 子类构造器的特点

**子类的全部构造器，都会先调用父类的构造器，再执行自己。**

实现机制：

- 默认情况下，子类全部构造器的第一行代码都是 `super()`（写不写都有），它会调用父类的无参数构造器。
- 如果父类没有无参数构造器，则必须在子类构造器的第一行手写 `super(...)`，指定调用父类的有参数构造器。

父类有无参构造器时：

```java
public class Fu {
    public Fu() {
        System.out.println("~~~父类的无参构造器被执行啦~~~");
    }
}
```

```java
class Zi extends Fu {
    public Zi() {
        //super(); //默认存在
        System.out.println("~~~子类的无参构造器执行啦~~~");
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Zi zi1 = new Zi();
        Zi zi2 = new Zi();
    }
}
```

父类只有有参构造器时，子类必须在第一行手写 `super(...)`：

```java
public class Fu {
    public Fu(String name,int age) {
        System.out.println("~~~父类的有参构造器被执行啦~~~");
    }
}
```

```java
class Zi extends Fu {
    public Zi(int a) {
        super(name,age); //直接调用父类的有参构造器，必须在第一行
        System.out.println("~~~子类的有参构造器执行啦111~~~");
    }
}
```

**子类构造器的执行流程（内存角度）：** 以 `new Student("钢门吹雪", 23, 100)`（Student 继承 Person）为例：

1. new Student 对象时，子类构造器入栈，`this` 指向堆中的子类对象（对象中包含父类成员区域 super 和子类成员区域）；
2. 子类构造器第一行的 `super(name, age)` 先进入父类构造器，为**父类成员**（name、age）赋初始值；
3. 父类构造器执行完毕回到子类构造器，再为**子类特有成员**（如 score）赋值；
4. 整个对象初始化完成。这就是"先有父、后有子"——父类数据没初始化完，子类构造器中使用继承来的成员就会出错。

#### 1.9 综合案例：程序员与经理（继承必须掌握）

在控制台打印以下结果：

```
姓名为小哈，年龄23，工资为15000.0的程序员
正在编写代码~~~
姓名为苗苗，年龄25，工资为18000.0项目经理,奖金为5000.0
正在分配任务~~~
```

员工父类：

```java
public class Employee {
    private String name;
    private int age;
    private double salary;
    //无参构造器
    public Employee() {
    }
    //有参构造器
    public Employee(String name, int age, double salary) {
        this.name = name;
        this.age = age;
        this.salary = salary;
    }
    //set/get方法
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public int getAge() { return age; }
    public void setAge(int age) { this.age = age; }
    public double getSalary() { return salary; }
    public void setSalary(double salary) { this.salary = salary; }

    //成员方法
    public void work(){
        System.out.println("正在工作");
    }
    public void showInfo(){
        System.out.println("姓名为"+name+"，年龄"+age+"，工资为"+salary+"的员工");
    }
}
```

程序员类：

```java
public class Coder extends Employee{
    public Coder() {
    }

    public Coder(String name, int age, double salary) {
        super(name, age, salary);
    }

    @Override
    public void work() {
        System.out.println("正在编写代码~~~");
    }

    @Override
    public void showInfo(){
        System.out.println("姓名为"+getName()+"，年龄"+getAge()+"，工资为"+getSalary()+"的程序员");
    }
}
```

项目经理类（自己独有的奖金属性）：

```java
public class Manager extends Employee {
    private double bonus;

    public double getBonus() {
        return bonus;
    }

    public void setBonus(double bonus) {
        this.bonus = bonus;
    }

    public Manager() {
    }

    public Manager(double bonus) {
        this.bonus = bonus;
    }

    public Manager(String name, int age, double salary, double bonus) {
        super(name, age, salary);
        this.bonus = bonus;
    }
    @Override
    public void work() {
        System.out.println("正在分配任务~~~");
    }

    @Override
    public void showInfo(){
        System.out.println("姓名为"+getName()+"，年龄"+getAge()+"，工资为"+getSalary()+"项目经理,奖金为"+getBonus());
    }
}
```

测试类：

```java
public class Test {
    public static void main(String[] args) {
        Coder c1 = new Coder("小哈",23,15000);
        c1.showInfo();
        c1.work();

        Manager m1 = new Manager("苗苗",25,18000,5000);
        m1.showInfo();
        m1.work();
    }
}
```

#### 小结

- 继承用 `extends` 建立父子关系，把子类共性内容抽到父类，前提是存在 is-a 关系。
- 成员变量访问遵循就近原则，用 `this`/`super` 区分本类与父类成员。
- 方法重写（Override）要求方法名、参数列表与父类完全一致，建议加 `@Override`；权限不能更小；私有、静态方法不能重写。
- Java 单继承、多层继承；子类构造器第一行默认 `super()`，先父后子。

---

### 二、Object 类与 toString()

#### 2.1 Object 类概述

- 在 Java 中，`java.lang.Object` 是所有类的根类（超类），任何类都直接或间接继承自 `Object`。
- 简单理解：Object 类是 Java 所有类的祖宗类。我们写的任何一个类，其实都是 Object 的子类或子孙类。

以下代码中 Father 没有写 extends，默认继承了 Object，可以直接使用 Object 的相关方法：

```java
class Father {
    String name;
}

public class Test {
    public static void main(String[] args) {
        Father f = new Father();
        f.name = "王小哈";
        // Father 默认继承了 Object 类的相关操作
        System.out.println(f.toString());
    }
}
```

#### 2.2 toString() 方法

`toString()` 是 `Object` 类的核心方法，所有类都默认继承了它，作用是返回对象的**字符串表示形式**，方便打印、调试和理解对象的内容。

- 直接打印对象时，默认输出对象在堆内存中的地址信息，格式为 `类的全类名@十六进制哈希值`（如 `com.itheima.Father@1b6d3586`），几乎没有实际意义。
- 开发中输出对象变量，更多时候希望看到对象的内容数据而不是地址信息。
- 此时可以通过**重写 toString()** 得到想要的数据内容。

```java
public class Test {
    public static void main(String[] args) {
        Developer dev = new Developer("小哈","男",23,"软件开发部","SF006",8000);
        System.out.println(dev.toString());//com.heima.ExtendsDemo.Developer@1d81eb93
    } 
}
```

在对应类中重写 toString()，**IDEA 快捷键 Alt + Insert** 可自动生成：

```java
@Override
public String toString() {
    return "Developer{" +
            "name='" + name + '\'' +
            ", gender='" + gender + '\'' +
            ", age=" + age +
            ", deptName='" + deptName + '\'' +
            ", id='" + id + '\'' +
            ", salary=" + salary +
            '}';
}
```

#### 小结

`Object` 是所有类的根类；`toString()` 默认打印地址，重写后打印对象内容，IDEA 中 Alt + Insert 快速生成。

---

### 三、final 关键字

#### 3.1 概述

**final 关键字是"最终"的意思，可以修饰方法、类、变量。**

final 修饰的特点：

- **修饰方法：** 表明该方法是最终方法，不能被重写。
- **修饰类：** 表明该类是最终类，不能被继承。
- **修饰变量：** 表明该变量是常量，不能再次被赋值。

#### 3.2 final 修饰类

被 `final` 修饰的类**不能被继承**（即没有子类）。`String`、`System` 等核心类就是 final 类。

```java
public final class Fu {

}
//Fu类被final修饰了，最终类不能被继承
class Zi extends Fu{} //报错
```

#### 3.3 final 修饰方法

被 `final` 修饰的方法**不能被子类重写**（override），但可以被继承和调用。常用于保护核心方法逻辑不被修改。

```java
public class Parent {
    public final void eat(){};
}

class Child extends Parent {
    @Override
    public void eat() { //报错
    }
}
```

#### 3.4 final 修饰变量（常量）

被 `final` 修饰的变量一旦赋值就**不能再修改**（即成为常量）。

- 局部变量：使用前赋值即可。
- **成员变量：必须在构造方法执行结束之前完成赋值**——可以在定义时直接赋值，也可以在构造方法（或构造代码块）中赋值，否则编译报错。

注意基本类型与引用类型的区别：

- final 修饰**基本类型**的变量，变量存储的数据不能被改变。
- final 修饰**引用类型**的变量，变量存储的**地址值**不能被改变，但地址所指向对象的**内容**是可以被改变的。

```java
public class Fu2 {
    //01 - 成员变量  基本类型
    public final int number = 1;
    //02 - 引用类型（数组）
    public final int[] num = new int[2];
    //03 - 对象类型（引用数据类型）
    public final Student student = new Student();

    public static void main(String[] args) {
        Fu2 f = new Fu2();
        //01 - 不能修改final修饰的基本类型变量
        //f.number = 42; //报错
        //f.number = 68; //报错

        //02 - 引用数据类型，不能修改的是地址值，但是地址中的元素是可以修改的
        f.num[0] = 11;
        f.num[0] = 12;
       // f.num = new int[12]; //报错，不能修改final修饰的引用数据类型的地址
        
        //03 - 修改Student对象的name属性
        f.student.name =  "小哈";
        //重新赋值是可以的，因为对象是引用数据类型，不能修改的是地址值
        f.student.name =  "小米"; 
    }
}
```

#### 3.5 常量

- **定义：** 使用 `static final` 修饰的成员变量就被称为常量。
- **作用：** 通常用于记录系统的配置信息，常用来定义一些固定的值——"统一管理、安全可控、提升效率"。
- **命名规范：**
  - 如果是一个单词，所有字母大写；
  - 如果是多个单词，所有字母大写，中间用下划线 `_` 分割。

案例——学生信息管理系统常量类 SystemConstants：

```java
/**
 * 学生信息管理系统 - 通用常量类
 * 存储系统基础配置、版权信息等全局常量
 */
public class SystemConstants {

    // ======== 核心规范：私有化构造器，禁止实例化 ======================
    private SystemConstants() {}

    // ===== 1. 系统基础信息常量（分组注释，结构清晰） ======================
    /** 系统名称 */
    public static final String PROJECT_NAME = "黑马程序员-学生信息管理系统";
    /** 系统版本号 */
    public static final String PROJECT_VERSION = "1.0.0";

    // ====================== 2. 版权/作者信息常量 ======================
    /** 软件开发者 */
    public static final String AUTHOR_NAME = "小哈";
    /** 开发公司名称 */
    public static final String COMPANY_NAME = "黑马程序员";
    /** 公司备案号（公安备案） */
    public static final String RECORD_NUMBER = "苏公网安备32132202000574号";

}
```

测试类：

```java
public class TestConstants {
    public static void main(String[] args) {
        // 打印系统基础信息
        System.out.println("=== 系统信息 ===");
        System.out.println("系统名称：" + SystemConstants.PROJECT_NAME);
        System.out.println("版本号：" + SystemConstants.PROJECT_VERSION);
        System.out.println("开发者：" + SystemConstants.AUTHOR_NAME);
        System.out.println("开发公司：" + SystemConstants.COMPANY_NAME);
        System.out.println("备案号：" + SystemConstants.RECORD_NUMBER);
    }
}
```

```
=== 系统信息 ===
系统名称：黑马程序员-学生信息管理系统
版本号：1.0.0
开发者：小哈
开发公司：黑马程序员
备案号：苏公网安备32132202000574号
```

#### 小结

final 修饰类不能继承、修饰方法不能重写、修饰变量不能重新赋值；引用类型锁的是地址不是内容；`static final` 共同修饰的成员变量叫常量，命名全大写下划线分词。

---

### 四、抽象类

当多个类有**共同的属性和行为**，可以把共同属性和行为抽取出来作为父类；但**某些行为父类无法直接实现**，就将这些行为编写为抽象方法，具体功能交给子类实现。

Java 提供关键字 `abstract`（抽象的意思），可以用来修饰类、成员方法：

- abstract 修饰类，这个类就是**抽象类**；
- abstract 修饰方法，这个方法就是**抽象方法**。

#### 4.1 基本语法

```java
public abstract class 类名 {
    public abstract 返回值类型 方法名(形参列表);
}
```

```java
//被abstract修饰的类就叫做抽象类
public abstract class Fu {
    //被abstract修饰的方法就是抽象方法(不需要写方法体大括号)
    public abstract void show();
}
```

#### 4.2 引导案例：动物类

动物类 Animal 可以设置动物的名字，需要吃东西方法 eat 和叫声方法 cry，但是不能确定具体哪种动物吃什么、怎么叫，需要具体动物继承实现：

```
=== 猫的行为 ===
橘猫：喵喵喵~
橘猫：吃小鱼干

=== 狗的行为 ===
金毛：汪汪汪！
金毛：吃骨头
```

```java
public abstract class Animal {
    String name;

    //行为：抽象方法的作用，把一类的某一个功能交给子类进行实现
    public abstract void eat();
    public abstract void cry();
}
```

此时下面的代码会报错——子类继承抽象类后必须实现抽象方法：

```java
public class Cat extends Animal {
}
```

```java
public class Dog extends Animal {
}
```

#### 4.3 抽象类的注意事项

- 抽象类中**不一定**有抽象方法，但**有抽象方法的类一定是抽象类**。
- 抽象类中可以有构造器（供子类继承使用）和普通成员方法（子类继承后直接调用）。

```java
public abstract class Animal {
    String name;
    int age;

    //行为：抽象方法，把某一个功能交给子类进行实现
    public abstract void eat();
    public abstract void cry();

    //普通成员方法 喝水，动物喝水一致
    public void drink(){
        System.out.println("喝山水~~~");
    };
    //构造器，可以有但是不能创建对象，主要是用来给子类使用
    public Animal(){}

    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

- **抽象类不能创建对象（不能实例化）**。原因：抽象类中可能包含没有方法体的抽象方法，假如允许创建对象，调用抽象方法时将无代码可执行。Java 直接从语法上禁止实例化，它作为一种特殊的父类，让子类继承并实现。

```java
public static void main(String[] args) {
    Animal animal = new Animal(); //报错
}
```

- **一个类继承抽象类，必须重写完抽象类的全部抽象方法**，否则这个类也必须定义成抽象类。

```java
public class Cat extends Animal {
    @Override
    public void eat() {
        System.out.println("猫吃鱼儿~~");
    }
    @Override
    public void cry() {
        System.out.println("喵喵喵~~~");
    }
}
```

#### 4.4 综合案例：抽象员工类

之前写过 `Employee` 父类和 `Coder` 子类，父类的 `work()` 和 `showInfo()` 方法返回的是"员工工作""员工信息"这种无意义的默认值（硬写的）。不同员工（程序员、经理、测试）的工作内容完全不同，此时可以将 `Employee` 改成抽象类，把 work、showInfo 抽象成抽象方法：

```java
public abstract class Employee {
    private String name;
    private int age;
    private double salary;
    //无参构造器
    public Employee() {
    }
    //有参构造器
    public Employee(String name, int age, double salary) {
        this.name = name;
        this.age = age;
        this.salary = salary;
    }
    //set/get方法---自己写

    //成员方法：抽象方法，强制子类实现
    public abstract void work();
    public abstract void showInfo();
}
```

#### 4.5 abstract 关键字的冲突问题

abstract 不能与以下关键字共同修饰方法：

- **final：** abstract 强制子类重写，final 禁止子类重写，互相矛盾。
- **private：** abstract 强制子类重写，private 方法子类无法访问重写，互相矛盾。
- **static：** static 修饰的方法可以用类名调用，而类名直接调用抽象方法没有意义。

#### 小结

抽象类用 `abstract class` 定义，抽象方法只有声明没有方法体；抽象类不能 new 对象，但可以有构造器和普通方法；子类要么重写全部抽象方法，要么自己也声明为抽象类。

---

### 五、模板方法设计模式（了解）

设计模式是架构师的必备知识，常用于开发框架。了解模板方法模式，对后期面试笔试、阅读框架源码都有帮助。

#### 5.1 设计模式概述

Java 中的设计模式是一套经过总结的、解决特定问题的代码设计经验，目的是让代码更易维护、可扩展、复用性更高。

- 一个问题通常有 n 种解法，其中最优的解法被人总结出来，就称之为设计模式。
- 设计模式有 20 多种，对应 20 多种软件开发中会遇到的问题。
- 学习时重点关注两个问题：设计模式能解决什么问题？怎么写？

#### 5.2 模板方法模式简介

把抽象类整体看成一个**模板**，模板中不能决定的东西定义成抽象方法，让使用模板的类（继承抽象类的类）去重写抽象方法实现需求。

模板方法设计模式的写法：

1. **定义抽象类**：作为流程模板的载体，封装通用逻辑与规范。
2. 在抽象类中定义两类核心方法：
   - **模板方法：** 聚合所有**固定的通用流程**代码（如业务主流程），是对外提供的核心入口；
   - **抽象方法：** 仅声明方法规范，无具体实现，将个性化逻辑交由子类完成（强制子类重写）。
3. **模板方法建议用 final 修饰**（参考 Java 核心类如 DateFormat）：
   - 模板方法是流程的"骨架"，直接给子类对象使用，**禁止子类重写**；
   - 若子类重写模板方法，会破坏统一的流程规范，导致模板方法失去"流程统一"的核心价值。

好比小时候写作文：作文标题和结尾是固定的通用流程（写在模板方法中），作文具体内容需要不同人来写（抽象方法交给子类实现）。

抽象模板：

```java
public abstract class TextTemplate {
    //模板方法：固定流程
    public void write(){
        System.out.println("《我的爸爸》");
        body();  //个性化内容
        System.out.println("啊~~~这就是我的爸爸！");
    }
    //具体功能交给子类实现
    public abstract void body();
}
```

子类继承实现：

```java
public class XiaoHa extends TextTemplate{
    @Override
    public void body() {
        System.out.println("那是一个秋天，风儿缠绵，记忆中爸爸骑着自行车接我放学回家，"+
                "我的脚卡在了车链子李，爸爸蹬不动，就站起来蹬...");
    }
}
```

测试类：

```java
public class Test {
    public static void main(String[] args) {
        XiaoHa xiaoHa = new XiaoHa();
        xiaoHa.write();
    }
}
```

#### 5.3 模板方法模式的作用

- 解决方法中存在重复代码的问题。
- 模板已经定义了通用结构（骨架），使用者只需要关心自己需要实现的功能即可。

#### 5.4 案例：员工日常工作流程模板

需求：公司需统一所有岗位员工的日常工作核心流程，同时保留不同岗位的工作内容差异化。

1. 所有岗位员工遵循**统一的日常工作流程**：打卡上班 → 开展核心工作 → 输出工作成果 → 整理工作 → 打卡下班，不允许篡改流程顺序；
2. 不同岗位（程序员、经理、测试工程师等）的**核心工作内容、工作产出**可个性化定义；
3. 后续新增岗位（产品经理、设计师）时可快速扩展，无需修改原有流程逻辑。

预期效果：

```
=== 程序员的一天 ===
✅ 打卡上班，到工位就位
张三：编写Java代码、修复Bug、联调接口
张三：产出可运行的代码、修复Bug清单
✅ 整理桌面，总结当日工作
✅ 打卡下班，离开公司

=== 经理的一天 ===
✅ 打卡上班，到工位就位
李四：开项目会议、制定计划、协调资源
李四：产出项目计划文档、会议纪要
✅ 整理桌面，总结当日工作
✅ 打卡下班，离开公司
```

抽象类模板（模板方法用 final 锁死流程）：

```java
// 抽象类：所有员工的工作模板（模板设计模式核心）
public abstract class EmployeeWorkTemplate {
    // 核心：模板方法（用final锁死流程，子类不能改）
    public final void doDailyWork() {
        // 步骤1：通用流程——上班（固定逻辑）
        goToWork();
        // 步骤2：个性化流程——核心工作（留空白，子类实现）
        coreWork();
        // 步骤3：个性化流程——工作产出（留空白，子类实现）
        workOutput();
        // 步骤4：通用流程——结束工作（固定逻辑）
        finishWork();
        // 步骤5：通用流程——下班（固定逻辑）
        getOffWork();
    }

    // 通用方法1：上班（所有员工都一样，写死）
    private void goToWork() {
        System.out.println("✅ 打卡上班，到工位就位");
    }

    // 通用方法2：结束工作（所有员工都一样，写死）
    private void finishWork() {
        System.out.println("✅ 整理桌面，总结当日工作");
    }

    // 通用方法3：下班（所有员工都一样，写死）
    private void getOffWork() {
        System.out.println("✅ 打卡下班，离开公司\n");
    }

    // 抽象方法1：核心工作（个性化，子类必须实现）
    public abstract void coreWork();

    // 抽象方法2：工作产出（个性化，子类必须实现）
    public abstract void workOutput();
}
```

程序员子类：

```java
// 程序员子类：只填“核心工作+工作产出”的空白，不用碰通用流程
public class Programmer extends EmployeeWorkTemplate {
    private String name; // 程序员姓名

    public Programmer(String name) {
        this.name = name;
    }

    // 实现抽象方法：程序员的核心工作
    @Override
    public void coreWork() {
        System.out.println(name + "：编写Java代码、修复Bug、联调接口");
    }

    // 实现抽象方法：程序员的工作产出
    @Override
    public void workOutput() {
        System.out.println(name + "：产出可运行的代码、修复Bug清单");
    }
}
```

经理子类：

```java
// 经理子类：只填自己的个性化细节
public class Manager extends EmployeeWorkTemplate {
    private String name; // 经理姓名

    public Manager(String name) {
        this.name = name;
    }

    @Override
    public void coreWork() {
        System.out.println(name + "：开项目会议、制定计划、协调资源");
    }

    @Override
    public void workOutput() {
        System.out.println(name + "：产出项目计划文档、会议纪要");
    }
}
```

测试：

```java
public class EmployeeTemplateDemo {
    public static void main(String[] args) {
        // 程序员的一天：调用模板方法，自动走完整流程
        Programmer programmer = new Programmer("张三");
        System.out.println("=== 程序员的一天 ===");
        programmer.doDailyWork();

        // 经理的一天：流程不变，只改细节
        Manager manager = new Manager("李四");
        System.out.println("=== 经理的一天 ===");
        manager.doDailyWork();
    }
}
```

---

### 本章小结

| 知识点 | 核心结论 |
| --- | --- |
| 继承 | `class 子类 extends 父类`，前提是 is-a 关系；Java 单继承、支持多层继承 |
| 成员访问 | 变量就近原则；`this` 访问本类、`super` 访问父类 |
| 方法重写 | 方法名和参数列表与父类完全一致，加 `@Override`；权限不可更小；私有/静态不能重写 |
| 构造器 | 子类构造器先执行 `super(...)` 调用父类构造器，再执行自己；`this(...)` 调用本类构造器须在第一行 |
| Object | 所有类的根类；重写 `toString()` 让对象打印出内容 |
| final | 修饰类不能继承、修饰方法不能重写、修饰变量不能改值；`static final` 为常量 |
| 抽象类 | `abstract class`，抽象方法无方法体；不能 new；子类必须重写全部抽象方法（或自己也抽象） |
| 模板方法模式 | 抽象类定义 final 模板方法固定流程骨架，抽象方法交给子类填充个性化步骤 |

---

<div style="page-break-after: always;"></div>

## 第九章 面向对象高级（下）：接口、多态、代码块、内部类与 Lambda

本章继续学习面向对象高级特性：**接口**（制定规范、弥补单继承不足）、**多态**（提升程序扩展性）、Object 的 `equals` 方法与 `Objects` 工具类、**代码块**、**package 包**、**内部类**，最后学习 JDK 8 的 **Lambda 表达式**。

---

### 一、接口

#### 1.1 接口的定义

**Java 接口是"规范/契约"，核心作用是定义标准、解耦和实现多态，弥补了类单继承的不足。**

接口体现的思想是**对规则的声明**，Java 中的接口更多体现的是**对行为的抽象**。

Java 提供关键字 `interface`，用它可以定义出一个特殊的结构——接口：

```java
public interface 接口名{
    //成员变量（常量）
    //成员方法（抽象方法）
}
```

接口的成员特点（JDK 7 及之前）：

- 接口中的成员变量都是**常量**，默认加了 `public static final`。
- 接口中的成员方法都是**抽象方法**，默认加了 `public abstract`。
- 接口中**不允许定义构造方法**。

```java
//JDK 1.7 的接口实现
public interface A {
    //成员变量：必须是公共静态常量（需要赋值）
    public static final String NAME = "hello";
    // public static final 可以省略不写
    int AGE = 18;

    //成员方法：都是公共的抽象方法（不能有方法体）
    //public abstract可以省略不写
    public abstract void show();
}
```

```java
public class Test {
    public static void main(String[] args) {
        //因为是静态常量，可以直接用接口名访问
        //接口名.属性名
        System.out.println(A.NAME);
        System.out.println(A.AGE);
    }
}
```

#### 1.2 接口的使用（implements）

接口用抽象方法制定好规则后，需要让其他类按照规则实现相关功能。

- 接口**不能创建对象**，接口是用来被类**实现（implements）**的，实现接口的类称为**实现类**。
- 一个类可以**实现多个接口**（接口可以理解成"干爹"），实现类必须重写完接口的全部抽象方法，否则实现类需要定义成抽象类。

```java
修饰符 class 实现类 implements 接口1,接口2,接口3,...{
    
}
```

**接口的好处：弥补了单继承的不足，一个类可以实现多个接口。**

```java
//实现类
public class A implements B,C {
}
//接口
public interface B {
}
//接口
public interface C {
}
```

案例：People 人类中抽取人相关的属性和方法，LaoWang 类单继承 People 类，同时实现 Driver（司机）、Singer（歌手）接口扩展功能。

```java
public class People {
    private String name;
    private int age;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
public interface Driver {
    //抽象方法：开车功能
    public abstract void driver();
}
```

```java
public interface Singer {
    //抽象方法：唱歌功能
    public abstract void singer();
}
```

```java
public class LaoWang extends People implements Driver,Singer {
    private String skill;

    public String getSkill() {
        return skill;
    }

    public void setSkill(String skill) {
        this.skill = skill;
    }

    //接口中的抽象方法必须要重写
    @Override
    public void driver() {
        System.out.println("下班后还要去开滴滴~~~");
    }

    @Override
    public void singer() {
        System.out.println("休息的时候在酒吧唱歌挣钱~~~");
    }
}
```

#### 1.3 接口的优势和作用

1. 解决类单继承的问题：通过接口，可以让一个类有一个"亲爹"的同时，还可以找多个"干爹"去扩展自己的功能。
2. 一个类可以实现多个接口，同时一个接口也可以被多个类实现。这样程序就可以**面向接口编程**，程序员可以很方便地灵活切换各种业务实现。

```java
public class Test1 {
    public static void main(String[] args) {
        //Runnable runnable = new Cat();
        Runnable runnable = new Duck();  //切换实现类即可切换业务
        runnable.run();
    }
}
```

#### 1.4 类和接口的各种关系

**类与类的关系：** 继承关系。只能**单继承**（一个类只能有一个直接父类），但可以**多层继承**（A 继承 B，B 继承 C，形成继承链，C 的成员一路传承给 A）。

**类与接口的关系：** 实现关系。可以单实现，也可以多实现，甚至可以在继承一个类的同时实现多个接口：

```java
public class LaoWang extends People implements Driver,Singer{}
```

**接口与接口的关系：多继承关系。** 一个接口可以继承多个接口，用类实现时需要重写所有接口（含父接口）的方法：

```java
interface A {
    void a();
}
interface B {
    void b();
}
//接口和接口之间是多继承关系
interface C extends A, B {
    void c();
}
//使用 Student 类实现接口 C，需要重写 A、B、C 三个接口的方法
class Student implements C {
    @Override
    public void c() {
    }

    @Override
    public void a() {
    }

    @Override
    public void b() {
    }
}
```

#### 小结

接口用 `interface` 定义，成员变量默认 `public static final`、方法默认 `public abstract`、没有构造器；类用 `implements` 实现接口且可多实现；接口之间可以多继承；类与类之间只能单继承、但可以多层继承。

---

### 二、抽象类和接口的对比

#### 2.1 语法对比

| 对比项 | 抽象类 | 接口 |
| --- | --- | --- |
| 成员变量 | 可以定义变量，也可以定义常量 | 只能定义常量 |
| 成员方法 | 可以定义具体方法，也可以定义抽象方法 | JDK8 前只能定义抽象方法 |
| 构造方法 | 有（给子类使用） | 没有 |
| 关系 | 类与类之间单继承 | 类可多实现，接口可多继承 |

#### 2.2 使用场景

- **抽象类是对事物进行抽象（描述事物是什么）。**
  比如公司里的员工：项目经理、程序员、人事都有姓名、年龄、工资这些共性属性，但"工作"内容各不相同。就可以把共性抽取到抽象员工类中，把 `work()` 定义为抽象方法强制子类各自实现：

  | 角色 | 成员变量 | 工作内容 |
  | --- | --- | --- |
  | 员工（抽象类） | 姓名、年龄、工资 | `work()` 定义为抽象方法 |
  | 项目经理 | 额外有奖金 | 项目管理、人员管理 |
  | 程序员 | 姓名、年龄、工资 | 写代码、改 Bug |
  | 人事 | 姓名、年龄、工资 | 人才招聘 |

  ```java
  public abstract class Employee {
      private String name;
      private int age;
      private double salary;

      // 工作内容因人而异，定义为抽象方法，强制子类重写
      public abstract void work();

      // getter / setter ...
  }

  public class Manager extends Employee {
      private double bonus;   // 项目经理特有：奖金
      @Override
      public void work() {
          System.out.println("项目经理：项目管理、人员管理");
      }
  }

  public class Programmer extends Employee {
      @Override
      public void work() {
          System.out.println("程序员：写代码、改Bug");
      }
  }

  public class Hr extends Employee {
      @Override
      public void work() {
          System.out.println("人事：人才招聘");
      }
  }
  ```

- **接口是对行为进行抽象（制定规则/规范）。**
  接口可以为程序制定规则，让代码更加规范。比如实际开发中写订单业务，包含创建订单、查询订单、查询订单列表、取消订单、完结订单、支付订单等功能：
  - 如果直接在订单类里书写、不设计接口，代码可读性差，而且有可能漏写某些功能；
  - 如果提前写好接口、在里面定义好相关抽象方法，实现类实现接口时必须全部重写，就不会出现漏写的问题。

**经验法则：** 描述"事物是什么"用抽象类（is-a 的共性抽取）；描述"能做什么/规范"用接口（like-a 的能力扩展）。

---

### 三、接口的新特性（JDK 8 / JDK 9）

从 JDK 8 开始，接口中的方法允许带有方法体，可以编写逻辑了。这么设计是为了解决**接口升级**的问题：

假如项目 1.0 版本的接口中有 2 个抽象方法并成功上线；2.0 版本需要加入 10 个新方法，如果这 10 个方法都是抽象方法，所有实现类都要跟着改动，牵一发动全身，维护成本太高。如果接口中的方法能带有方法体、实现类可以直接拿去用，就能在加入新功能的同时不改造已有实现类。

- **JDK 8 新特性：** 接口中可以定义有方法体的方法（默认方法、静态方法）。
- **JDK 9 新特性：** 接口中可以定义私有方法。

#### 3.1 默认方法

允许在接口中定义非抽象方法，但需要使用关键字 `default` 修饰，这些方法就是默认方法。

**作用：解决接口升级的问题，不需要改之前的代码，就可以使用 default 修饰的新方法。**

```java
//接口中默认方法的定义格式：public可以省略，但是default不能省略
格式：public default 返回值类型 方法名(参数列表) {}
范例：public default void show() {}
```

注意事项：

- 默认方法不是抽象方法，所以**不强制被重写**（但可以被重写，重写时去掉 `default` 关键字）。
- `public` 可以省略，`default` 不能省略。
- 如果实现了多个接口，多个接口中存在相同的方法声明，子类就必须对该方法进行重写（逻辑冲突）。

项目 1.0 版本：

```java
public class TestInterface1 {
    public static void main(String[] args) {
        OrderServiceImplA a = new OrderServiceImplA();
        a.create();
        a.cancel();
    }
}
interface OrderService {
    void create();//创建订单
    void cancel();//取消订单
}
class OrderServiceImplA implements OrderService {
    @Override
    public void create() {
        System.out.println("创建A订单~~~");
    }

    @Override
    public void cancel() {
        System.out.println("取消A订单~~~");
    }
}

class OrderServiceImplB implements OrderService {
    @Override
    public void create() {
        System.out.println("创建B订单~~~");
    }

    @Override
    public void cancel() {
        System.out.println("取消B订单~~~");
    }
}
```

项目升级，新增支付功能，使用 `default` 避免改动所有实现类：

```java
public class TestInterface1 {
    public static void main(String[] args) {
        OrderServiceImplA a = new OrderServiceImplA();
        a.create();
        a.cancel();
        //default修饰的方法实现类对象可以直接调用
        a.paid();
    }
}

interface OrderService {
    void create();//创建订单
    void cancel();//取消订单

    //新建一个支付功能（默认方法，实现类不强制重写）
    public default void paid(){
        System.out.println("支付功能~~~");
    };
}

class OrderServiceImplA implements OrderService {
    @Override
    public void create() {
        System.out.println("创建A订单~~~");
    }

    @Override
    public void cancel() {
        System.out.println("取消A订单~~~");
    }
    //默认方法可以被重写，重写时去掉default关键字
    @Override
    public void paid(){
        System.out.println("订单A支付功能被新增了~~~~~");
    }
}

class OrderServiceImplB implements OrderService {
    @Override
    public void create() {
        System.out.println("创建B订单~~~");
    }

    @Override
    public void cancel() {
        System.out.println("取消B订单~~~");
    }
}
```

**逻辑冲突问题：** 如果一个类实现了两个接口，两个接口中的默认方法同名但逻辑不同，会编译报错，必须在实现类中重写，并用 `接口名.super.方法名()` 指定调用哪个接口的逻辑：

```java
interface A {
    default void method() {
        System.out.println("A的逻辑~~~");
    }
}
interface B {
    default void method() {
        System.out.println("B的逻辑~~~");
    }
}
class C implements A,B{
    @Override
    public void method() {
        A.super.method();
        B.super.method();
    }
}
```

#### 3.2 静态方法

接口中允许定义 `static` 静态方法：

```java
//接口中静态方法的定义格式：
格式：public static 返回值类型 方法名(参数列表) {}
范例：public static void show() {}
```

注意事项：

- 静态方法**只能通过接口名调用**，不能通过实现类名或者对象名调用。
- `public` 可以省略，`static` 不能省略。

```java
public class TestInterface1 {
    public static void main(String[] args) {
        OrderServiceImplA a = new OrderServiceImplA();
        a.create();
        a.cancel();
        //静态方法只能使用 接口名调用
        OrderService.show();
       // a.show(); 报错
    }
}

interface OrderService {
    void create();//创建订单
    void cancel();//取消订单
    //静态方法只能使用 接口名调用
    public static void show(){
        System.out.println("静态方法~~~");
    };
}

class OrderServiceImplA implements OrderService {
    @Override
    public void create() {
    }
    @Override
    public void cancel() {
    }
}
```

#### 3.3 私有方法（JDK 9）

接口中允许定义 `private` 私有方法，用于在接口内部抽取默认方法/静态方法之间的公共逻辑，不对外暴露：

```java
//接口中私有方法的定义格式：
格式1：private 返回值类型 方法名(参数列表) {}
范例1：private void show() {}

格式2：private static 返回值类型 方法名(参数列表) {}
范例2：private static void method() {}
```

**为什么需要私有方法？** 当多个默认方法之间存在重复逻辑时，若抽成 `public default` 方法会连带暴露给实现类；JDK 9 允许用 `private` 方法把公共逻辑只留在接口内部复用：

```java
interface Inter {
    public default void start() {
        System.out.println("start方法执行...");
        log();
    }
    public default void end() {
        System.out.println("end方法执行...");
        log();
    }
    // 私有方法：只在本接口内部供默认方法调用，实现类看不到、也不能调用
    private void log() {
        System.out.println("日志记录");
    }
}
```

普通私有方法给默认方法复用；静态私有方法（`private static`）给接口中的静态方法复用。

#### 小结

默认方法（default）解决接口升级、实现类可不重写；静态方法只能接口名调用；私有方法（JDK9）用于接口内部代码复用；多接口默认方法冲突时必须重写并用 `接口名.super.方法()` 指定。

---

### 四、多态（Polymorphism）

**多态：同一个行为具有多个不同表现形式或形态的能力。**

#### 4.1 多态的前提条件

实现多态必须满足以下三个条件：

1. 有**继承/实现**关系；
2. 有**方法重写**；
3. 有**父类引用指向子类对象**。

```java
public class PolymorphismDemo1 {
    public static void main(String[] args) {
        //直接创建子类对象 -- 子类引用，指向子类对象
        Zi z = new Zi();

        //父类引用，指向子类对象（以多态的形式创建了对象）
        Fu f = new Zi();
    }
}
class Fu{
    int num = 10;
    public void show(){
        System.out.println("Fu ~~~show~~~");
    }
}
class Zi extends Fu{
    int num = 20;
    @Override
    public void show(){
        System.out.println("Zi ~~~show~~~");
    }
}
```

#### 4.2 多态的成员访问特点

```java
public static void main(String[] args) {
    //子类引用指向子类对象
    Zi z = new Zi();
    System.out.println(z.num);//20
    z.show();//Zi ~~~show~~~

    //父类引用指向子类对象（多态）
    Fu f = new Zi();
    System.out.println(f.num);//10
    f.show();//Zi ~~~show~~~
}
```

输出：

```
20
Zi ~~~show~~~
10
Zi ~~~show~~~
```

记忆口诀——**"编译看左边，运行看哪边"分情况：**

- **成员变量：编译看左边（父类），运行也看左边（父类）。**
  - 编译时检查调用的变量在父类中是否存在，不存在直接编译报错；
  - 因为是父类引用，访问存在局限性，只能访问父类空间的数据，所以运行时取的也是父类的值。

- **成员方法：编译看左边（父类），运行看右边（子类）。**
  - 编译时检查方法在父类中是否存在，不存在报错；
  - **运行时一定执行子类重写后的方法逻辑**（这正是多态的体现；如果调用的是父类抽象方法，执行子类实现才有意义）。

```java
public class PolymorphismDemo2 {
    public static void main(String[] args) {
        //接口类型变量 指向实现类对象（多态创建）
        Inter i = new InterImpl();
        i.show();
    }
}
interface Inter{
    void show();
}
class InterImpl implements Inter{
    @Override
    public void show() {
        System.out.println("实现类重写后的show方法~~~");
    }
}
```

- **静态成员：编译看左边（父类），运行也看左边（父类）。**
  - static 修饰的成员推荐使用类名调用；`f.show()` 在字节码中会解析为 `Fu.show()`，与对象无关。

```java
public class PolymorphismDemo2 {
    public static void main(String[] args) {
        Fu1 f = new Son();
        //字节码文件中都是Fu1.show();
        f.show();
        Fu1.show();
    }
}

class Fu1 {
    public static void show() {
        System.out.println("Fu...show....");
    }
}

class Son extends Fu1 {
    //@Override 静态方法不能重写
    public static void show() {
        System.out.println("实现类重写后的show方法~~~");
    }
}
```

#### 4.3 多态的好处：提高程序扩展性

- **对象多态：** 将方法的形参定义为父类类型，这个方法就可以接收该父类的任意子类对象。
- **行为多态：** 同一个行为，具有多个不同表现形式或形态的能力。

```java
public abstract class Animal {
    public abstract void eat();
}
```

```java
public class Dog extends Animal{
    @Override
    public void eat() {
        System.out.println("狗吃骨头~~~");
    }
    public void lookDoor(){
        System.out.println("狗看门~~~");
    }
}
```

```java
public class Cat extends Animal{
    @Override
    public void eat() {
        System.out.println("猫吃鱼~~~");
    }
    public void catchMouse() {
        System.out.println("猫抓老鼠~~~");
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        //如果没有多态，每加一种动物就要写一个useXxx方法，代码冗余
        //useDog(new Dog());
        //useCat(new Cat());

        //形参为父类类型，可以接收所有子类对象
        useAnimal(new Dog());
        useAnimal(new Cat());
    }

    //将方法的参数设置为父类类型，该方法就可以接收该父类的所有子类对象
    //以后新增动物子类，这个方法一行都不用改——扩展性
    public static void useAnimal(Animal animal) {
        animal.eat();
    }
}
```

#### 4.4 多态的弊端与类型转型

**弊端：不能直接调用子类特有的属性和行为。**

因为实例的表现形态是父类（如 `Animal animal = new Dog()`），父类引用不单指某一个子类，所以编译时无法调用子类特有方法，需要进行**类型转换**。

**向上转型：** 从子到父（父类引用指向子类对象），是多态的默认写法：

```java
Fu f = new Zi();   // 向上转型
```

**向下转型（强制类型转换）：** 从父到子（将父类引用所指向的对象转交给子类类型），目的是调用子类特有方法：

```java
Zi z = (Zi) f;    // 向下转型
```

```java
public class Test1 {
    public static void main(String[] args) {
        useAnimal(new Dog());
        useAnimal(new Cat());
    }
    public static void useAnimal(Animal animal) {
        animal.eat();
        //调用子类特有的方法，不能直接调用，需要向下转型
        //animal.lookDoor();   //---> Animal animal = new Dog()
        //animal.catchMouse(); //---> Animal animal = new Cat()

        //向下转型（父转子）
        Dog dog = (Dog) animal;
        dog.lookDoor();
    }
}
```

#### 4.5 转型安全问题与 instanceof

如果被转的引用变量对应的**实际类型**和**目标类型**不是同一种类型，转换时会出现 `ClassCastException`（类型转换异常）。比如实际是 Cat 的对象强转成 Dog。

**解决方案：使用关键字 `instanceof` 先判断再强转。**

格式：

```
对象名 instanceof 类型
```

- 判断一个对象是否是一个类（或其子类）的实例；
- 通俗理解：判断关键字左边的对象是否是右边的类型，返回 boolean 结果。

```java
public class Test1 {
    public static void main(String[] args) {
        useAnimal(new Dog());
        useAnimal(new Cat());
    }
    public static void useAnimal(Animal animal) {
        animal.eat();
        //先判断类型，再向下转型，避免ClassCastException
        if (animal instanceof Dog) {
            Dog dog = (Dog) animal;
            dog.lookDoor();
        } else if (animal instanceof Cat) {
            Cat cat = (Cat) animal;
            cat.catchMouse();
        }
    }
}
```

#### 小结

多态三前提：继承/实现、方法重写、父类引用指向子类对象；成员变量和静态方法"编译运行都看左"，成员方法"编译看左、运行看右"；好处是扩展性（形参用父类），弊端是不能直接用子类特有成员，需向下转型，转型前用 `instanceof` 判断。

---

### 五、多态综合案例

#### 5.1 模拟订单业务

订单业务接口（规范）：

```java
/**
 * 订单业务接口
 */
public interface OrderService {
    /** 创建单个订单 */
    void create();
    /** 查询单个订单 */
    void findOne();
    /** 查询订单列表 */
    void findList();
    /** 取消订单 */
    void cancel();
    /** 完结订单 */
    void finish();
    /** 支付订单 */
    void paid();
}
```

国内订单实现类：

```java
public class OrderServiceImpl implements OrderService {
    @Override
    public void create() {
        System.out.println("创建订单");
    }
    @Override
    public void findOne() {
        System.out.println("查询单个订单");
    }
    @Override
    public void findList() {
        System.out.println("查询订单列表");
    }
    @Override
    public void cancel() {
        System.out.println("取消订单");
    }
    @Override
    public void finish() {
        System.out.println("完结订单");
    }
    @Override
    public void paid() {
        System.out.println("支付订单");
    }
}
```

国外订单实现类（含特有方法 check）：

```java
public class OverseasServiceImpl implements OrderService {

    public void check() {
        System.out.println("IP地址检测");
    }

    @Override
    public void create() {
        System.out.println("国外业务 --- 创建订单");
    }
    @Override
    public void findOne() {
        System.out.println("国外业务 --- 查询单个订单");
    }
    @Override
    public void findList() {
        System.out.println("国外业务 --- 查询订单列表");
    }
    @Override
    public void cancel() {
        System.out.println("国外业务 --- 取消订单");
    }
    @Override
    public void finish() {
        System.out.println("国外业务 --- 完结订单");
    }
    @Override
    public void paid() {
        System.out.println("国外业务 --- 支付订单");
    }
}
```

不使用多态时，每个分支都要重复写一遍 6 个方法调用，代码冗余。用多态优化——**父（接口）引用统一接收，方法只写一遍：**

```java
import java.util.Scanner;

public class Test {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入:  1. 国内订单   2. 国外订单");

        int choice = sc.nextInt();

        // OrderService orderService;  // 接口引用（多态）
        OrderService orderService;
        switch (choice) {
            case 1:
                // 创建国内订单的业务类
                orderService = new OrderServiceImpl();
                break;
            case 2:
                // 创建国外订单的业务类
                orderService = new OverseasServiceImpl();
                //调用国外业务独有的检测IP方法（需要用实现类类型接收）
                OverseasServiceImpl overseasService = new OverseasServiceImpl();
                overseasService.check();
                break;
            default:
                //输入不是1和2时，默认国内订单
                orderService = new OrderServiceImpl();
        }

        //统一调用，代码只写一遍
        orderService.create();
        orderService.findOne();
        orderService.findList();
        orderService.cancel();
        orderService.finish();
        orderService.paid();
    }
}
```

#### 5.2 模拟支付接口

支付接口：

```java
//支付接口
public interface Payment {
    void pay(double money);
}
```

三种支付方式实现：

```java
//平台支付
public class PlatformPaymentImpl implements Payment {
    @Override
    public void pay(double money) {
        System.out.println("通过平台成功支付" + money + "元");
    }
}
```

```java
//银行卡支付
public class BankcardPaymentImpl implements Payment {
    @Override
    public void pay(double money) {
        System.out.println("通过银行卡成功支付" + money + "元");
    }
}
```

```java
//信用卡支付
public class CreditCardPaymentImpl implements Payment {
    @Override
    public void pay(double money) {
        System.out.println("通过信用卡成功支付" + money + "元");
    }
}
```

多态简化调用（对比每个分支各 new 各调的写法）：

```java
import java.util.Scanner;

public class Test1 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请选择支付方式:  1. 支付平台支付   2. 银行卡网银支付  3. 信用卡快捷支付");
        int command = sc.nextInt();
        double money;//要支付的钱
        Payment payment = null;   //定义父类（接口）引用
        switch (command) {
            case 1:
                payment = new PlatformPaymentImpl();
                break;
            case 2:
                payment = new BankcardPaymentImpl();
                break;
            case 3:
                payment = new CreditCardPaymentImpl();
                break;
        }
        System.out.println("请输入您要支付的金额~~");
        money = sc.nextDouble();
        payment.pay(money);   //统一一行调用
    }
}
```

---

### 六、Object 类的 equals 方法

#### 6.1 概述

`equals()` 是 Java 中判断**对象内容是否相等**的核心方法。

- Object 父类中 equals 方法存在的意义就是为了被子类重写，以便子类自己定制比较规则。
- Java 自带的核心类（如 `String`、`Integer`、`Date`）都重写了 `equals()`，用于判断内容相等。

**`==` 和 `equals()` 的区别：**

|  | 含义 | 适用场景 |
| --- | --- | --- |
| `==` | 判断**引用地址**是否相同（是否指向同一个对象）；基本类型比较值 | 基本数据类型（int/long 等）、判断对象是否是同一个实例 |
| `equals()` | Object 默认实现和 `==` 一样（判断地址），但可重写为判断**对象内容**是否相同 | 引用数据类型（String、自定义类、对象）判断内容相等 |

#### 6.2 字符串对比与字符串常量池

```java
public static void main(String[] args) {
    String name1 = "123456";
    String name2 = "123456";
    System.out.println(name1 == name2);       //true
    System.out.println(name1.equals(name2));  //true
}
```

字符串常量池：JVM 为了节省内存，会把所有字符串字面量（比如 `"123456"`）缓存到一块特殊的内存区域（常量池），相同内容的字面量只会创建一个对象，所以 `name1 == name2` 为 true。

#### 6.3 对象对比与重写 equals

```java
public class Student {
    String name;
    int age;
    public Student(){}
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

```java
public class Test2 {
    public static void main(String[] args) {
        Student s1=new Student("小哈",23);
        Student s2=new Student("小哈",23);
        System.out.println(s1.equals(s2));//false
    }
}
```

- Object 自带的 equals 底层是 `==`，两个对象都是 new 出来的，在堆内存中各有各的地址，所以结果是 false。
- 如果想判断两个"外观一样"的对象内容相等，必须**重写 equals 方法**。IDEA 快捷键 **Alt + Insert** 自动生成：

```java
class Student {
    String name;
    int age;
    public Student(){}
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Student student = (Student) o;
        return age == student.age && Objects.equals(name, student.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(name, age);
    }
}
```

#### 6.4 解读生成的 equals 源码

```java
public class Student {
    private String name;
    private int age;

    @Override
    public boolean equals(Object o) {
        // this: stu1（调用者）  o: stu2（被比较者）
        if (this == o) {
            // 如果两个对象的地址相同, 代表是同一块内存空间, 内容肯定相同
            return true;
        }

        // 能执行到这里说明 stu1 不是 null
        // stu2 为 null，直接返回 false
        // 比较两个对象的字节码（Class对象），字节码不同代表类型不一致，返回 false
        if (o == null || this.getClass() != o.getClass()) {
            return false;
        }

        // 向下转型，才能调用子类特有的属性
        Student student = (Student) o;

        // 比较两个对象的属性值（String 等引用类型用 Objects.equals 比较，避免空指针）
        return this.age == student.age && Objects.equals(this.name, student.name);
    }
}
```

---

### 七、Objects 工具类

#### 7.1 Objects 简介

`Objects` 是 JDK 7 新增的工具类（`java.util.Objects`），专门用来处理 Object 相关的通用操作，核心价值是**简化空指针判断、统一对象操作逻辑、避免手写重复的空安全代码**。

问题场景：如果对象为 null，调用 equals 会出现空指针异常，需要手动判空，代码冗余且容易出错：

```java
public class Test2 {
    public static void main(String[] args) {
        Student s1=null;
        Student s2=new Student("小哈",23);
        System.out.println(s1.equals(s2));//空指针异常 NullPointerException
    }
}
```

`Objects` 把这些通用逻辑封装成静态方法，一行代码搞定，既简洁又安全：

```java
public class Test2 {
    public static void main(String[] args) {
        Student s1 = null;
        Student s2 = new Student("小哈", 23);
        /* 手动判空，冗余：
        if (s1 == null || s2 == null) {
            System.out.println("对象不能为空~~");
            return;
        } else {
            System.out.println(s1.equals(s2));
        }
        */
        System.out.println(Objects.equals(s1, s2));  //false，不报错
    }
}
```

注意：`Objects.equals` 仅仅是工具类中的方法，**底层仍依赖我们自己编写的 equals 方法**——如果不重写，还是按 `==` 比较地址；它的优势是加入了健壮性（空安全）判断。

源码如下（Objects 与其他类一样直接/间接继承自 Object，本身从 JDK 1.7 开始提供）：

```java
// Objects.equals 源码（JDK 自带）
public static boolean equals(Object a, Object b) {
    return (a == b) || (a != null && a.equals(b));
}
```

解读：先比较地址——两个引用都为 `null`、或指向同一个对象时直接返回 true；否则只有 `a` 不为 null 才调用 `a.equals(b)`，从而避免空指针异常。

#### 7.2 Objects 常用方法

- `Objects.equals(a, b)`：空安全地比较两个对象内容是否相等。
- `Objects.isNull(obj)`：判断对象是否为 null（等价于 `obj == null`）。
- `Objects.nonNull(obj)`：判断对象不为 null。

```java
public static void main(String[] args) {
    Student s1 = new Student("小哈", 23);
    Student s2 = new Student("小哈", 23);
    Student s3 = null;
    Student s4 = s1;

    System.out.println(Objects.equals(s1, s2));  //true（重写equals后比内容）
    System.out.println(Objects.isNull(s3));      //true
    System.out.println(Objects.isNull(s4));      //false
    System.out.println(Objects.equals(s1, s4));  //true（同一个对象）
}
```

---

### 八、代码块

**在 Java 类中，使用 `{ }` 括起来的代码被称为代码块。** 分类：

- 局部代码块
- 构造代码块
- 静态代码块
- 同步代码块（多线程阶段学习）

#### 8.1 局部代码块（了解）

- **位置：** 方法中的一对 `{}`。
- **作用：** 限定变量的生命周期，提早释放内存。

```java
public class CodeBlock {

    public static void main(String[] args) {
        {
            int num = 10;
            System.out.println(num);
        }
        
        System.out.println(num);    // 这里会报错, num 变量已经被释放了
    }
}
```

#### 8.2 构造代码块

- **位置：** 类中方法外的一对 `{}`。
- **特点：** 创建对象时被调用执行，**无论使用哪一个构造方法创建对象，都要执行构造代码块**，且**优先于构造方法执行**。
- **作用：** 如果发现所有构造方法中存在相同的代码，就可以将这段相同代码抽取到构造代码块中。

```java
public class Test3 {
    public static void main(String[] args) {
        Student1 s1 = new Student1();
        Student1 s2 = new Student1(10);
    }
}
class Student1 {
    {
        System.out.println("~~~~~~Student1类的构造代码块执行了~~~~~~");
    }

    public Student1() {
        System.out.println("Student1类的空参数构造方法...");
    }

    public Student1(int num) {
        System.out.println("Student1类的带参数构造方法...");
    }
}
```

输出：

```
~~~~~~Student1类的构造代码块执行了~~~~~~
Student1类的空参数构造方法...
~~~~~~Student1类的构造代码块执行了~~~~~~
Student1类的带参数构造方法...
```

#### 8.3 静态代码块（掌握）

- **位置：** 类中方法外的一对 `{}`，需要加 `static` 关键字。
- **特点：** 随着**类的加载**而执行。字节码加载时静态代码块就会执行；因为字节码文件只加载一次，**静态代码块也只执行一次**。
- **作用：** 用于执行一些初始化操作——哪些代码只需要执行一次，就放在静态代码块中。

```java
public class Test3 {
    public static void main(String[] args) {
        Student1 s1 = new Student1();
        Student1 s2 = new Student1(10);
    }
}
class Student1 {
    static {
        System.out.println("===========Student类的静态代码块=============");
    }
    {
        System.out.println("Student1类的构造代码块执行了~~~~");
    }

    public Student1() {
        System.out.println("Student1类的空参数构造方法...");
    }

    public Student1(int num) {
        System.out.println("Student1类的带参数构造方法...");
    }
}
```

执行顺序总结：**静态代码块（类加载时，仅一次）→ 构造代码块（每次 new 对象）→ 构造方法（每次 new 对象）**。

案例——用静态代码块初始化薪资规则（只加载一次，后续计算直接复用）：

```java
/**
 * 体现静态代码块初始化固定规则的作用
 */
public class Employee {
    // 静态变量：存储薪资等级的固定阈值（全局共用）
    public static double MANAGER_BASE_SALARY; // 经理底薪
    public static double STAFF_BASE_SALARY;   // 普通员工底薪
    public static double BONUS_RATIO;         // 绩效奖金比例

    // 静态代码块：类加载时初始化薪资规则（仅执行一次）
    static {
        System.out.println("=== 静态代码块执行：初始化薪资规则 ===");
        MANAGER_BASE_SALARY = 8000;  // 经理底薪8000
        STAFF_BASE_SALARY = 4000;    // 普通员工底薪4000
        BONUS_RATIO = 0.2;           // 绩效奖金为底薪的20%
    }

    // 员工实例变量
    private String name;    // 姓名
    private String position; // 职位（经理/普通员工）
    private double performance; // 绩效分（1.0为满分）

    // 构造器：初始化员工信息
    public Employee(String name, String position, double performance) {
        this.name = name;
        this.position = position;
        this.performance = performance;
    }

    // 计算员工总薪资（复用静态代码块初始化的规则）
    public double calculateSalary() {
        double baseSalary;
        // 根据职位获取底薪（用静态变量，不用写死数值）
        if ("经理".equals(position)) {
            baseSalary = MANAGER_BASE_SALARY;
        } else {
            baseSalary = STAFF_BASE_SALARY;
        }
        // 总薪资 = 底薪 + 底薪*奖金比例*绩效分
        return baseSalary + baseSalary * BONUS_RATIO * performance;
    }

    // 打印员工薪资信息
    public void printSalary() {
        System.out.println(name + "（" + position + "）的薪资：" + calculateSalary() + "元");
    }

    public static void main(String[] args) {
        // 创建员工对象（触发类加载，静态代码块先执行）
        Employee emp1 = new Employee("张三", "经理", 0.9);
        Employee emp2 = new Employee("李四", "普通员工", 1.0);
        emp1.printSalary();
        emp2.printSalary();

        // 再次创建员工，静态代码块不会重复执行
        Employee emp3 = new Employee("王五", "普通员工", 0.8);
        emp3.printSalary();
    }
}
```

```
=== 静态代码块执行：初始化薪资规则 ===
张三（经理）的薪资：9440.0元
李四（普通员工）的薪资：4800.0元
王五（普通员工）的薪资：4640.0元
```

---

### 九、package 包

#### 9.1 包的概述

- 包本质来说就是**文件夹**，用来管理类文件。
- 建包语法格式：`package 公司域名倒写.技术名称;`，包名建议全部英文小写且具备意义。

```java
package com.itheima.pojo;
public class Student {}
```

- 建包语句必须在源代码第一行，一般 IDEA 工具会帮助创建。

#### 9.2 导包

- 相同包下的类可以直接访问；**不同包下的类必须导包才可以使用**。导包格式：`import 包名.类名;`
- 如果要使用的类在 `java.lang` 包（核心包）下，不需要编写 import 导包代码（比如 String、System）。
- 假如一个类中需要用到两个同名类，默认只能导入一个，另一个要带**全类名**访问。

```java
package com.itheima.packagedemo;

// 自己新建的 Scanner 类
public class Scanner {
}
```

```java
package com.itheima.packagedemo;

public class TestPackage {
    public static void main(String[] args) {
        //scanner 使用的是我们自己新建的 Scanner 类
        //自己新建的 Scanner 和 java.util 中的命名冲突
        //实际开发中类的命名不能和 Java 自带类重复
        Scanner scanner = new Scanner();
        //想使用 java.util 中的 Scanner，需要全类名访问
        java.util.Scanner sc = new java.util.Scanner(System.in);
        int command = sc.nextInt();
    }
}
```

---

### 十、内部类

**内部类就是定义在一个类里面的类。**

#### 10.1 成员内部类（了解）

语法格式：

```java
class Outer {
    // 内部类
    class Inner {
    }
}
```

创建对象的格式：

```java
格式：外部类名.内部类名 对象名 = new 外部类对象().new 内部类对象();
范例：Outer.Inner in = new Outer().new Inner();
```

```java
public class InnerDemo {
    public static void main(String[] args) {
        Outer.Inner inner = new Outer().new Inner();
        System.out.println(inner.a);
        inner.show();
    }
}
class Outer {
    class Inner {
        int a = 10;
        public void show(){
            System.out.println("Inner~~~show~~~");
        }
    }
}
```

**内部类成员访问特点：**

- 内部类访问外部类成员，**直接访问即可，包括私有成员**，因为内部类本身就是外部类的一部分；
- 外部类访问内部类成员，需要**先创建内部类对象**再访问。

```java
public class InnerDemo {
    public static void main(String[] args) {
        Outer.Inner inner = new Outer().new Inner();
        System.out.println(inner.a);
        inner.show();
        System.out.println("------ 内部类访问外部类 ------");
        inner.innerPrint();
        System.out.println("------ 外部类访问内部类 ------");
        Outer outer = new Outer();
        outer.outerPrint();
    }
}
class Outer {
    int num = 100;
    public void method() {
        System.out.println("外部类的方法~~~");
    }
    //外部类访问内部类不能直接访问，需要创建对象
    public void outerPrint(){
        //System.out.println(a); 报错
        //show();
        Inner inner = new Inner();
        System.out.println(inner.a);
        inner.show();
    }
    class Inner {
        int a = 10;
        public void show(){
            System.out.println("Inner~~~show~~~");
        }
        //内部类访问外部类成员直接访问（包括私有）
        public void innerPrint(){
            System.out.println(num);
            method();
        }
    }
}
```

同名变量练习（局部、内部类成员、外部类成员三层同名）：

```java
class Outer{
    int num = 150;
    class Inner{
        int num = 110;
        public void print(){
            int num = 78;
            System.out.println(num);           // 78  局部变量（就近）
            System.out.println(this.num);      // 110 内部类成员
            System.out.println(Outer.this.num);// 150 外部类成员
        }
    }
}
```

**为什么学习内部类：封装性更好。** 比如描述汽车，发动机是汽车的一部分，可以把发动机类定义在汽车类内部：

```java
class Car {
    String carName;
    int carAge;
    int carColor;
    //发动机
    class Engine {
        String engineName;
        int engineAge;
    }
}
```

注意：不推荐主动定义内部类（调用麻烦），了解这种写法、以后能看懂别人的代码即可。

#### 10.2 静态内部类（了解）

有 `static` 修饰的成员内部类：

```java
class Outer {
    static class Inner {
    }
}
```

创建对象的格式：

```java
格式：外部类名.内部类名 对象名 = new 外部类名.内部类对象();
范例：Outer.Inner in = new Outer.Inner();
```

```java
public class Test {
    public static void main(String[] args) {
        Outer.Inner inner = new Outer.Inner();
        inner.show();
        //静态方法访问
        Outer.Inner.method();
    }
}
class Outer{
   static class Inner{
       public void show(){
           System.out.println("Inner show");
       }
       public static void method(){
           System.out.println("Inner method");
       }
   }
}
```

#### 10.3 局部内部类（了解）

局部内部类放在方法、代码块、构造器等执行体中：

```java
public class Test {
    public static void main(String[] args) {
        A obj = new A();
        obj.f();
    }
}
class A {
    public void f() {
        class B{
            public void print() {
                System.out.println("局部内部类是鸡肋语法~~");
            }
        }
        //局部内部类只能在方法内创建对象使用
        B b = new B();
        b.print();
    }
}
```

#### 10.4 匿名内部类（重点）

**思考：** 调用方法时，方法的形参是接口，我们应该传入什么？——传入该接口的实现类对象（多态）。

```java
public class Test {
    public static void main(String[] args) {
        useInter(new Cat());
        useInter(new Dog());
    }
    //形参是接口，传入接口的实现类对象
    //Runnable r = new Cat();
    public static void useInter(Runnable r) {
        r.run();
    }
}
interface Runnable {
    void run();
}
class Cat implements Runnable {
    @Override
    public void run() {
        System.out.println("猫仔奔跑~~~");
    }
}
class Dog implements Runnable {
    @Override
    public void run() {
        System.out.println("狗仔奔跑~~~");
    }
}
```

但为了传一次参数就单独写一个实现类文件太麻烦，于是有了**匿名内部类**。

- 概述：匿名内部类本质上是一个特殊的局部内部类（定义在方法内部）。
- 前提：需要存在一个接口或类（抽象类/普通类）。

```java
new 类或接口(){
    //类体(一般是方法重写)
}
```

- `new 类` —— 继承这个类，创建一个子类对象，然后重写方法；
- `new 接口` —— 实现这个接口，创建一个实现类对象，然后重写方法。

```java
public class Test1 {
    public static void main(String[] args) {
        //1.实现了接口 2.重写了方法 3.创建了实现类对象
        new Runnable() {
            @Override
            public void run() {
                System.out.println("小猫在奔跑~~~");
            }
        }.run();
        //1.继承了抽象类 2.重写了方法 3.创建了子类对象
        new Animal() {
            @Override
            public void eat() {
                System.out.println("小猫在吃鱼~~~");
            }
        }.eat();
    }
}
abstract class Animal {
    public abstract void eat();
}

interface Runnable {
    void run();
}
```

用匿名内部类优化思考案例：

```java
public class Test1 {
    public static void main(String[] args) {
        //用匿名内部类对象接收变量，可重复使用
        Runnable r1 = new Runnable() {
            @Override
            public void run() {
                System.out.println("小狗在奔跑~~~");
            }
        };
        useInter(r1);
        //----------------------------------------------
        //直接作为方法实参传入
        useInter(new Runnable() {
            @Override
            public void run() {
                System.out.println("小猫在奔跑~~~");
            }
        });
    }
    //使用接口的方法
    public static void useInter(Runnable r) {
        r.run();
    }
}
interface Runnable {
    void run();
}
```

**总结：**

- **作用：** 更方便地创建一个子类对象，不需要去包里手动创建多余的类文件。
- **好处：** 测试时代码简化，不用创建多余类文件。
- **使用场景：** 如果调用方法时形参是接口或者抽象类，就可以使用匿名内部类快速构建这个参数对象。
- **注意：** 如果接口/父类中的抽象方法只有一两个，建议使用匿名内部类；如果抽象方法很多，不建议使用，建议用正常的实现类完成。

```java
//接口中抽象方法太多，建议使用普通实现类完成
public class Test {
    public static void main(String[] args) {
        useFu(new Son());
    }

    public static void useFu(Fu f) {
        f.show();
        f.eat();
        f.sleep();
        f.play();
        f.run();
    }
}
interface Fu {
    void show();
    void eat();
    void sleep();
    void play();
    void run();
}
//普通实现类
class Son implements Fu {
    @Override
    public void show() { System.out.println("show~~~"); }
    @Override
    public void eat() { System.out.println("eat~~~"); }
    @Override
    public void sleep() { System.out.println("sleep~~~"); }
    @Override
    public void play() { System.out.println("play~~~"); }
    @Override
    public void run() { System.out.println("run~~~"); }
}
```

#### 10.5 匿名内部类案例：通用数学运算

设计一个算术运算接口 `maths`，抽象方法 `getMaths` 能计算任意两个数的各种算术结果，表达式拼接格式统一为 `操作数1 运算符 操作数2 = 结果`：

```java
public class Test1 {
    public static void main(String[] args) {
        //两个数相加
        String resSum = mathsMethod(2, 3, new maths() {
            @Override
            public String getMaths(int a, int b) {
                return a + " + " + b + " = " + (a + b);
            }
        });
        System.out.println(resSum);
        //两个数相除
        String resDiv = mathsMethod(5, 2, new maths() {
            @Override
            public String getMaths(int a, int b) {
                return a + " ÷ " + b + " = " + (1.0 * a / b);
            }
        });
        System.out.println(resDiv);
    }

    //通用数学运算方法：运算规则由传入的匿名内部类决定
    public static String mathsMethod(int a, int b, maths m) {
        return m.getMaths(a, b);
    }
}

interface maths {
    //任意两个数做各种数学运算
    String getMaths(int a, int b);
}
```

输出：

```
2 + 3 = 5
5 ÷ 2 = 2.5
```

---

### 十一、Lambda 表达式

#### 11.1 概述和作用

- Lambda 表达式是 **JDK 8** 开始新增的一种语法形式。
- **作用：简化匿名内部类的代码写法。**
- **注意：Lambda 表达式只能简化函数式接口的匿名内部类！**
  - **函数式接口：** 首先必须是接口，其次接口中有且仅有一个抽象方法。
  - 通常会在接口上加 `@FunctionalInterface` 注解，标记并校验该接口必须满足函数式接口。

#### 11.2 语法格式

```java
(被重写方法的形参列表) -> {
    被重写方法的方法体代码。
}
```

- `()` 对应接口中唯一抽象方法的形参列表；
- `->` 是箭头运算符（固定语法）；
- `{}` 表示方法体。

#### 11.3 使用条件

- 只能是一个接口；
- 接口中只有一个抽象方法（函数式接口）。

基本语法演示：

```java
public interface Swimming {
    void swim();
}
```

```java
public class Test {
    public static void main(String[] args) {
       //匿名内部类写法：
       //Swimming swimming = new Swimming() {
       //    @Override
       //    public void swim() {
       //        System.out.println("正在游泳~~~");
       //    }
       //};
       //swimming.swim();

        //Lambda 表达式改写：
        Swimming swimming = () -> {
            System.out.println("正在游泳~~~");
        };
        swimming.swim();
    }
}
```

有参数、有返回值演示：

```java
public interface Swimming {
    //设置参数，返回值为String
    String swim(String name);
}
```

```java
public class Test {
    public static void main(String[] args) {
        Swimming swimming = (String name) -> {
            return name + "，在游泳~~~";
        };
        System.out.println(swimming.swim("小猫"));
    }
}
```

#### 11.4 Lambda 的省略写法

进一步简化规则：

1. 参数类型可以省略不写；
2. 如果只有一个参数，参数类型可以省略，同时 `()` 也可以省略；
3. 如果方法体只有一行代码，可以省略大括号 `{}` 和分号；此时如果这行代码是 return 语句，`return` 也必须去掉。

```java
public class Test {
    public static void main(String[] args) {
        //完整写法：
        //Swimming swimming = (String name) -> {
        //    return name + "，在游泳~~~";
        //};
        //省略写法：
        Swimming swimming = name -> name + "，在游泳~~~";
        System.out.println(swimming.swim("小猫"));
    }
}
```

#### 小结

Lambda 是 JDK 8 简化函数式接口匿名内部类的语法：`(参数) -> {方法体}`；前提是接口只有一个抽象方法；参数类型可省略、单参数可省括号、单行方法体可省大括号和 return。

---

### 本章小结

| 知识点 | 核心结论 |
| --- | --- |
| 接口 | `interface` 定义、`implements` 实现；常量 + 抽象方法；可多实现、接口间多继承 |
| 抽象类 vs 接口 | 抽象类描述"事物是什么"，接口制定"行为规范" |
| 接口新特性 | JDK8 默认方法（default，解决升级）、静态方法（接口名调用）；JDK9 私有方法 |
| 多态 | 三前提：继承/实现、重写、父引用指子对象；方法"编译看左运行看右" |
| 转型 | 向上转型自动完成；向下转型需强转，先用 `instanceof` 判断防 ClassCastException |
| equals | `==` 比地址/基本值，equals 重写后比内容；IDEA Alt+Insert 生成 |
| Objects | 空安全工具类，`Objects.equals`、`isNull`、`nonNull` |
| 代码块 | 静态代码块（类加载一次）→ 构造代码块（每次建对象）→ 构造方法 |
| 包 | `package` 声明、`import` 导包；`java.lang` 免导包；同名类用全类名 |
| 内部类 | 成员/静态/局部内部类了解即可；匿名内部类重点：快速创建接口/抽象类的子类对象 |
| Lambda | JDK8 简化函数式接口匿名内部类：`(参数) -> {方法体}`，仅适用于单抽象方法接口 |

---

<div style="page-break-after: always;"></div>

## 第10章 常用 API（String、StringBuilder、ArrayList）与综合案例

本章分为上下两篇：

- **上篇**学习 JDK 中最常用的几个 API：`String`、`StringBuilder`、`StringBuffer` 和 `ArrayList`，掌握它们的创建方式、常用方法与底层特点；
- **下篇**通过一个完整的「商品管理系统」综合案例，把 `ArrayList` 存储 JavaBean 对象、增删改查、信号位思想、静态代码块等知识点串起来，形成完整的项目开发思路。

---

## 上篇：常用 API

### 一、API 简介

- **API**（全称 Application Programming Interface：应用程序编程接口），就是别人写好的一些程序（类和方法），程序员直接拿去调用即可解决问题。

**为什么要学习别人写好的程序？**

- **不要重复造轮子**：实际开发中很多功能都可以重复使用，或者在行业内应用广泛，这些功能前辈可能都已经写好了，我们只需要使用即可，可以**提高开发效率**。
- 比如之前使用的 `Scanner`、`Random` 都是 JDK 提前写好的，直接使用即可。

**怎么学习 API？**

- 通过 API 文档学习。我们现在使用的是 JDK 的 API 文档，后期还会接触到其他 API（阿里的 API、微信的 API、字节的 API），甚至我们自己也要编写 API 文档供别人使用。
- JDK 的 API 文档提供了 Java 开发所需要的所有类，类里面有一堆方法，这些方法就称之为 API。

本章重点学习两个常用类：`String` 和 `ArrayList`，以及用于高效拼接字符串的 `StringBuilder`。

---

### 二、String 字符串

在 Java 中，`String` 是用于表示字符串（字符序列）的类，属于 `java.lang` 包（**无需显式导入**），是开发中最常用的数据类型之一。

#### 2.1 概述

- `String` 代表字符串对象，可以用来封装字符串数据，并提供了很多操作字符串的方法。

#### 2.2 创建 String 字符串对象的方法

##### 方法 1：直接用双引号封装字符串对象

```java
String 字符串名 = "字符串值";
```

```java
String name = "小哈";
String schoolName = "黑马程序员";
```

##### 方法 2：通过 String 类的构造器初始化字符串对象

```java
// 使用 String 的无参构造器，创建一个空字符串对象（长度为 0，内容为空）
String str1 = new String();
System.out.println(str1);

// 使用字符串参数构造器，直接根据传入的字符串字面量创建对象
String str2 = new String("黑马程序员");
System.out.println(str2);

// 使用字符数组参数构造器，将字符数组的内容按顺序拼接成字符串
char[] chars = {'我', '爱', '黑', '马'};
String str3 = new String(chars);
System.out.println(str3);

// 使用字节数组参数构造器，将字节按默认编码解码为字符
// 基于 ASCII 编码：97 对应 'a'，98 对应 'b'，99 对应 'c'
byte[] bytes = {97, 98, 99};
String str4 = new String(bytes);
System.out.println(str4); // abc
```

#### 2.3 字符串的常用方法

| 方法 | 说明 |
| --- | --- |
| `int length()` | 获取字符串的长度（字符个数） |
| `char charAt(int index)` | 获取某个索引位置的字符 |
| `char[] toCharArray()` | 将字符串转换成字符数组返回 |
| `boolean equals(Object obj)` | 判断两个字符串内容是否一致（区分大小写） |
| `boolean equalsIgnoreCase(String s)` | 判断内容是否一致，**忽略大小写** |
| `String substring(int begin, int end)` | 截取字符串，**包前不包后** |
| `String substring(int begin)` | 从指定索引截取到字符串末尾 |
| `String replace(CharSequence old, CharSequence new)` | 用新值替换字符串中的旧值 |
| `boolean contains(CharSequence s)` | 判断字符串中是否包含某段内容 |
| `boolean startsWith(String s)` | 判断字符串是否以某段内容开头 |
| `String[] split(String regex)` | 按指定分隔符把字符串拆分成字符串数组 |

示例代码：

```java
// 01 length()：获取字符串长度
String str1 = "黑马程序员";
System.out.println(str1.length()); // 5

// 02 charAt(索引)：获取某个索引位置的字符
String str2 = "黑马程序员";
System.out.println(str2.charAt(3)); // 序

// 03 toCharArray()：转换成字符数组
String str3 = "黑马程序员";
char[] charArray = str3.toCharArray();
System.out.println(charArray);

// 04 equals()：比较内容是否一致
String str4 = "黑马程序员";
String str5 = "黑马程序员呀";
boolean result = str4.equals(str5);
System.out.println(result); // false

// 05 equalsIgnoreCase()：忽略大小写比较
String str6 = "abcD";
String str7 = "ABcD";
boolean result1 = str6.equalsIgnoreCase(str7);
System.out.println(result1); // true

// 06 substring(开始索引, 结束索引)：包前不包后
String str8 = "我们都是好孩子";
String result2 = str8.substring(0, 6);
System.out.println(result2); // 我们都是好孩子

// 07 substring(开始索引)：截取到末尾
String str9 = "我们都是好孩子";
String result3 = str9.substring(3);
System.out.println(result3); // 好孩子

// 08 replace(旧值, 新值)：替换
String str10 = "我们都是好孩子";
String result4 = str10.replace("都是", "***");
System.out.println(result4); // 我们***好孩子

// 09 contains()：是否包含
String str11 = "我们都是在黑马学习java的学生，我们爱java";
System.out.println(str11.contains("java")); // true
System.out.println(str11.contains("Java")); // false（区分大小写）

// 10 startsWith()：是否以某内容开头
String str12 = "王大锤";
System.out.println(str12.startsWith("王")); // true
System.out.println(str12.startsWith("李")); // false

// 11 split(分隔符)：拆分成字符串数组
String str13 = "唐僧,猴子,猪猪,沙沙";
String[] result14 = str13.split(",");
for (int i = 0; i < result14.length; i++) {
    System.out.println(result14[i]);
}
```

> 小结：比较字符串内容必须用 `equals`，不能用 `==`（`==` 比较的是地址）；`substring` 截取区间是「包前不包后」。

#### 2.4 案例

##### 案例 1：用户登录

**需求**：正确的登录名和密码是 `itheima/123456`，在控制台开发登录界面，接收用户输入的登录名和密码，登录成功后展示「欢迎进入系统!」并停止程序；最多给用户三次登录机会。

```java
public class Test2 {
    public static void main(String[] args) {
        login();
    }

    public static void login() {
        Scanner sc = new Scanner(System.in);
        int i = 0;
        int count = 3;
        do {
            // 准备正确的用户名和密码
            String okUserName = "小哈";
            String okUserPassword = "123456";
            // 用户输入
            System.out.println("请输入您的用户名");
            String userName = sc.nextLine();
            System.out.println("请输入您的密码");
            String password = sc.nextLine();
            // 判断用户输入的和原来是否一致
            if (okUserName.equals(userName) && okUserPassword.equals(password)) {
                System.out.println("登录成功！");
                return; // 成功后结束当前方法
            } else {
                if (count != 0) {
                    System.out.println("您的密码错误，请重新输入！");
                    System.out.println("您还剩余" + count + "次登录机会");
                    count--;
                } else {
                    System.out.println("您3次机会已经用完，请60分钟后重试！！！");
                }
            }
            i++;
        } while (i <= 3);
        sc.close(); // 关闭 Scanner，释放关联资源
    }
}
```

##### 案例 2：统计字符次数

**需求**：键盘录入一个字符串，统计其中大写字母、小写字母、数字字符出现的次数（不考虑其他字符）。

例如 `aAb3&c2B*4CD1` 的结果：小写字母 3 个、大写字母 4 个、数字 4 个。

```java
public class StringTest2 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入: ");
        String content = sc.next();

        // 1. 定义三个计数器变量
        int smallCount = 0;
        int bigCount = 0;
        int numCount = 0;
        // 2. 将字符串转换为字符数组
        char[] arr = content.toCharArray();
        // 3. 遍历字符数组，获取每一个字符
        for (int i = 0; i < arr.length; i++) {
            // 4. 判断当前字符属于哪一种（字符可以直接比较大小）
            if (arr[i] >= 'a' && arr[i] <= 'z') {
                smallCount++;
            } else if (arr[i] >= 'A' && arr[i] <= 'Z') {
                bigCount++;
            } else if (arr[i] >= '0' && arr[i] <= '9') {
                numCount++;
            }
        }
        // 5. 打印结果
        System.out.println("小写字母: " + smallCount);
        System.out.println("大写字母: " + bigCount);
        System.out.println("数字字符: " + numCount);
    }
}
```

##### 案例 3：手机号屏蔽

**需求**：以字符串形式从键盘接收一个手机号，将中间四位屏蔽，效果为 `156****1234`。

思路：截取前三位 + 拼接 `****` + 截取后四位。

```java
public class StringTest3 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入手机号: ");
        String tel = sc.next();

        // 1. 截取前三位
        String start = tel.substring(0, 3);
        // 2. 截取后四位（从索引 7 截到末尾）
        String end = tel.substring(7);
        // 3. 拼接
        System.out.println(start + "****" + end);
    }
}
```

##### 案例 4：敏感词替换

**需求**：键盘录入一个字符串，如果其中包含 `TMD`，则使用 `***` 替换。

```java
public class StringMethodDemo4 {
    public static void main(String[] args) {
        method();
    }

    private static void method() {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入: ");
        String msg = sc.next();
        msg = msg.replace("TMD", "***");
        System.out.println(msg);
    }
}
```

#### 2.5 String 使用时的注意事项

##### 注意 1：String 对象的内容不可改变（不可变字符串）

`System.identityHashCode(Object)`：获取对象的「身份哈希码」（可看作逻辑地址，JVM 基于对象地址生成），可用来观察变量到底指向哪个对象。

```java
public static void main(String[] args) {
    String name = "黑马";
    name += "程序员";
    name += "播妞";
    System.out.println(name); // 黑马程序员播妞
}
```

变量 `name` 指向的对象看起来「变了」，为什么还说 String 不可变？

- 只要是以 `"..."` 方式写出的字符串对象，会在**堆内存的字符串常量池（StringTable）**中存储。
- **每次试图改变字符串内容，实际上都是新产生了一个字符串对象**，变量每次都指向了新对象，而之前字符串对象的内容从未改变——所以说 String 对象是不可变的。

执行流程：

1. `String name = "黑马";`：在栈内存新建 `name` 变量，把 `"黑马"` 存入字符串常量池，把地址交给 `name`；
2. `name += "程序员";`：把 `"程序员"` 存入常量池，拼接出的 `"黑马程序员"` 是放在堆中的新对象，生成新地址赋值给 `name`；
3. `name += "播妞";`：同理，拼出新对象 `"黑马程序员播妞"` 放在堆中；
4. 最终输出 `黑马程序员播妞`。

##### 注意 2：双引号写出的字符串进常量池，相同内容只存一份

```java
public class Test {
    public static void main(String[] args) {
        String s1 = "abc";
        String s2 = "abc";
        System.out.println(s1 == s2); // true
    }
}
```

执行流程：

1. `String s1 = "abc";`：`s1` 进栈，`"abc"` 存入常量池，地址交给 `s1`；
2. `String s2 = "abc";`：`s2` 进栈，常量池中已有 `"abc"`，直接把**同一个地址**交给 `s2`；
3. `s1 == s2` 比较地址，结果为 `true`。

##### 注意 3：通过 new 创建字符串，每 new 一次都产生新对象

```java
public class Test2 {
    public static void main(String[] args) {
        char[] chs = {'a', 'b', 'c'};
        String s1 = new String(chs);
        String s2 = new String(chs);
        System.out.println(s1 == s2); // false
    }
}
```

执行流程：`chs` 在堆中创建数组；两次 `new String(chs)` 分别在堆中 new 出两个不同的字符串对象，地址不同，所以 `==` 结果为 `false`。

##### 问答：下面代码分别创建了几个对象？

```java
public class Test2 {
    public static void main(String[] args) {
        String s2 = new String("abc"); // 创建了几个对象？
        String s1 = "abc";             // 创建了几个对象？
        System.out.println(s1 == s2);  // false
    }
}
```

- `new String("abc")`：`"abc"` 在常量池中创建 1 个对象，`new` 在堆中再创建 1 个对象，共 **2 个**；
- `String s1 = "abc"`：常量池中已有 `"abc"`，**不再创建新对象**，直接复用。

```java
public class Test2 {
    public static void main(String[] args) {
        String s1 = "abc";
        String s2 = "ab";
        String s3 = s2 + "c";   // 变量参与拼接，运行时在堆中产生新对象
        System.out.println(s1 == s3); // false
    }
}
```

```java
public class Test2 {
    public static void main(String[] args) {
        String s1 = "abc";
        String s2 = "a" + "b" + "c"; // 编译期优化
        System.out.println(s1 == s2); // true
    }
}
```

- **Java 存在编译优化机制**：程序在编译时，`"a" + "b" + "c"` 这种纯字面量拼接会直接转成 `"abc"`，以提高执行性能，所以 `s1 == s2` 为 `true`；
- 而 `s2 + "c"` 中有变量参与拼接，编译期无法确定结果，运行时会在堆中产生新对象，所以地址不同。

> 小结：字符串比较内容一律用 `equals`；`==` 只在「双引号字面量」场景下碰巧为 true，不能作为判断内容相等的依据。

---

### 三、StringBuilder

#### 3.1 作用

**StringBuilder 可以显著提高字符串的操作效率。** 下面的代码对比了拼接 10 万次字符串的耗时：

```
String 字符串拼接需要：2946 毫秒
StringBuilder 字符串拼接需要：4 毫秒
```

```java
public class Test {
    public static void main(String[] args) {
        stringMethod();
        sbMethod();
    }

    public static void stringMethod() {
        // System.currentTimeMillis()：1970年1月1日 0时0分0秒到现在的毫秒数
        long startTime = System.currentTimeMillis();
        String str = "";
        for (int i = 0; i < 100000; i++) {
            str += i; // 每次拼接都产生新对象，效率极低
        }
        long endtTime = System.currentTimeMillis();
        System.out.println("String字符串拼接需要：" + (endtTime - startTime) + "毫秒");
    }

    public static void sbMethod() {
        long startTime = System.currentTimeMillis();
        StringBuilder sb = new StringBuilder("");
        for (int i = 0; i < 100000; i++) {
            sb.append(i); // 始终在同一个容器中追加
        }
        long endtTime = System.currentTimeMillis();
        System.out.println("StringBuilder字符串拼接需要：" + (endtTime - startTime) + "毫秒");
    }
}
```

原因：String 每次 `+=` 都会产生新的字符串对象（不可变），而 StringBuilder 始终在同一个缓冲区上操作。

**底层原理（为什么 `+` 拼接慢）：**

```java
String s1 = "a";
String s2 = s1 + "b";   // 有变量参与拼接
String s3 = s2 + "c";
System.out.println(s3); // abc
```

- 变量之间用 `+` 拼接时，底层每出现一个加号都会：先 `new StringBuilder()` 把内容 append 进去，再调用 `toString()` 生成一个新的 String 对象——**一个加号就在堆内存中产生两个对象**（StringBuilder 对象 + toString 出的 String 对象）；
- 上例拼接两次，堆中先后产生 4 个临时对象，用完即弃，浪费内存、效率低；
- 而直接使用 StringBuilder 时全程只有 **1 个 StringBuilder 对象**，`"a"、"b"、"c"` 在字符串常量池中，拼接结果始终在同一个缓冲区内修改，这就是 StringBuilder 高效的根本原因。

> 补充：JDK 8 之后编译器对简单的 `+` 拼接做了优化，但在循环内反复拼接字符串时，仍应手动使用 StringBuilder。

#### 3.2 特点

- **StringBuilder 是字符串的缓冲区，可以理解为一种容器**：容器可以添加任意数据类型，但只要进入这个容器，全部变为字符串。

```java
public class StringBuilderDemo2 {
    public static void main(String[] args) {
        StringBuilder sb = new StringBuilder();

        sb.append(10);
        sb.append('a');
        sb.append(12.3);
        sb.append(false);
        sb.append("你好");

        System.out.println(sb); // 10a12.3false你好
    }
}
```

- **StringBuilder 是一种可变的字符序列**：多次 `append` 操作的始终是同一个对象（用 `System.identityHashCode(sb)` 观察可发现地址不变）。

```java
public class StringBuilderDemo3 {
    public static void main(String[] args) {
        StringBuilder sb = new StringBuilder();
        sb.append("Hello World");
        sb.append(" World");
        System.out.println(sb); // Hello World World
    }
}
```

#### 3.3 构造方法和常用方法

**构造方法：**

| 构造方法 | 说明 |
| --- | --- |
| `public StringBuilder()` | 创建一个空的字符串缓冲区（容器） |
| `public StringBuilder(String str)` | 创建一个字符串缓冲区，并初始化好指定内容 |

```java
// 创建一个空白的字符串缓冲区
StringBuilder sb1 = new StringBuilder();
System.out.println(sb1); // （空）

// 创建一个字符串缓冲区，并指定初始值
StringBuilder sb2 = new StringBuilder("abc");
System.out.println(sb2); // abc
```

**常用方法：**

| 方法 | 说明 |
| --- | --- |
| `public StringBuilder append(任意类型)` | 添加数据到缓冲区尾部，**返回对象本身**（支持链式编程） |
| `public StringBuilder reverse()` | 反转容器中的内容 |
| `public int length()` | 返回长度（字符个数） |
| `public String toString()` | 把 StringBuilder 转换为 String |

```java
public class Test1 {
    public static void main(String[] args) {
        StringBuilder sb = new StringBuilder();

        // append 添加数据（返回对象本身，可以链式编程）
        sb.append("红色");
        sb.append("蓝色");
        sb.append("绿色");
        // 链式编程：如果方法的返回值是对象，就可以继续向下调用方法
        // sb.append("红色").append("蓝色").append("绿色");
        System.out.println(sb); // 红色蓝色绿色

        // 反转缓冲区的内容
        sb.reverse();
        System.out.println(sb); // 色绿色蓝色红

        // 获取长度
        System.out.println(sb.length());

        // 转换为 String 类型：想用 String 有而 StringBuilder 没有的方法时，先转成 String
        String[] arr = sb.toString().split("色");
        for (int i = 0; i < arr.length; i++) {
            System.out.println(arr[i]);
        }
    }
}
```

> String 与 StringBuilder 的互转：`new StringBuilder(str)` 把 String 变成 StringBuilder；`sb.toString()` 把 StringBuilder 变回 String。

#### 3.4 案例

##### 案例 1：判断回文字符串

**需求**：键盘接收一个字符串，判断它是否是对称（回文）字符串，在控制台打印「是」或「不是」。

经典回文：「上海自来水来自海上」「蜜蜂采蜂蜜」「奶牛产牛奶」。

思路：把字符串反转，若反转后与原串相同即为回文。

```java
public class StringBuilderTest1 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入: ");
        String content = sc.next();

        // 将 String 转成 StringBuilder，调用反转方法
        StringBuilder sb = new StringBuilder(content);
        sb.reverse();

        // 比较内容：content 是 String，sb 是 StringBuilder，需要统一类型
        if (content.equals(sb.toString())) {
            System.out.println("是回文字符串");
        } else {
            System.out.println("不是回文字符串");
        }
    }
}
```

##### 案例 2：按指定格式拼接数组

**需求**：定义一个方法，把 `int` 数组中的数据按指定格式拼接成字符串返回。例如数组 `int[] arr = {1,2,3};`，输出 `[1, 2, 3]`。

```java
public class StringBuilderTest2 {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3};
        System.out.println(arrayToString(arr));
    }

    public static String arrayToString(int[] arr) {
        // 代码健壮性判断：数组为 null 或长度为 0 时直接返回
        if (arr == null || arr.length == 0) {
            return "[]";
        }

        // 创建 StringBuilder 对象用于拼接（拼接频繁时优先使用）
        StringBuilder sb = new StringBuilder("[");

        // 遍历数组，取出每个元素（最后一个单独处理，避免多出逗号）
        for (int i = 0; i < arr.length - 1; i++) {
            sb.append(arr[i]).append(", ");
        }

        // 单独拼接最后一个元素和右括号
        sb.append(arr[arr.length - 1]).append("]");

        // 方法返回值是 String，需要转换
        return sb.toString();
    }
}
```

#### 3.5 StringBuilder 原理（扩容机制）

核心逻辑：

1. **初始「空位」**：创建 `StringBuilder` 时，底层默认给一个能装 **16 个字符**的字符数组（汉字、字母、数字都占一个位置），这 16 个位置就是初始空位；
2. **逐位填充**：调用 `append` 时，把字符挨个填到空位上，填一个少一个空位。比如 `append("上海")` 填掉 2 个空位，剩 14 个；
3. **触发扩容**：当要添加的字符数 > 剩余空位时触发扩容——
   - 默认把数组扩大到 **「旧容量 × 2 + 2」**（例如 16 → 34，34 → 70）；
   - 把原来的字符全部「搬」到新数组里，旧数组丢弃；
4. **继续填充**：扩容后有了新空位，继续填入剩余字符。全程只操作这一个容器，不反复新建字符串对象，这就是它高效的原因。

> 小结：String 适合表示固定不变的字符串；凡是需要频繁拼接、反转的场景，都应使用 StringBuilder。

---

### 四、StringBuffer

- `StringBuffer` 和 `StringBuilder` 的构造器、操作方法**完全一致**；
- 区别在于：`StringBuffer` 的方法加了同步锁，**多线程访问时更安全，但效率更低**；`StringBuilder` 线程不安全但效率高。
- 实际开发中单线程场景（绝大多数业务代码）优先使用 `StringBuilder`。

| 类 | 可变性 | 线程安全 | 效率 |
| --- | --- | --- | --- |
| String | 不可变 | 安全 | 拼接效率最低 |
| StringBuilder | 可变 | 不安全 | 高 |
| StringBuffer | 可变 | 安全（synchronized） | 较低 |

---

### 五、ArrayList 集合

#### 5.1 概述

之前存储一组数据用的是数组，但数组定义完成后**长度就固定了**，后期想增删元素很麻烦。集合的大小可变，开发中使用更多。

- `ArrayList` 是 Java 集合框架中最常用的类之一，本质是**动态数组**（长度可以自动调整），相比普通数组更灵活，适合存储数量不确定的元素；
- 支持创建、添加、获取、修改、删除、遍历等操作。

#### 5.2 创建 ArrayList

```java
ArrayList<数据类型> 集合名 = new ArrayList<>();
```

```java
ArrayList<String> list = new ArrayList<>();
```

创建约束数据类型的集合时要注意：

- 集合里存放的数据必须是**同一种引用数据类型**，否则报错；
- **没有固定长度**：是动态数组，随元素增长自动扩容；
- 泛型中需要指定存储的数据类型；
- **不支持基本数据类型**，必须是引用数据类型或自定义类型（JavaBean 实体类型）。基本类型要使用对应的包装类：`int → Integer`、`char → Character`、`double → Double`、`boolean → Boolean` 等。

#### 5.3 操作 ArrayList 的常用方法

| 方法 | 说明 |
| --- | --- |
| `boolean add(E e)` | 将元素添加到集合**末尾** |
| `void add(int index, E e)` | 在指定索引位置**插入**元素 |
| `E get(int index)` | 根据索引获取该位置的元素 |
| `int size()` | 获取集合中元素的个数（长度） |
| `E remove(int index)` | 根据索引删除元素，**返回被删除的元素** |
| `boolean remove(Object o)` | 根据元素值删除，返回是否删除成功；数据重复时**默认删除第一个** |
| `E set(int index, E e)` | 修改指定索引位置的元素，**返回被修改前的元素** |

```java
ArrayList<String> list = new ArrayList<>();

// add(数据)：添加到末尾
list.add("小哈");
list.add("小明");
list.add("小花");
System.out.println(list); // [小哈, 小明, 小花]

// add(索引, 数据)：在指定位置插入
list.add(1, "小乖");
System.out.println(list); // [小哈, 小乖, 小明, 小花]

// get(索引)：获取元素
String res = list.get(1);
System.out.println(res); // 小乖

// size()：获取集合长度
int size = list.size();
System.out.println(size); // 4

// remove(索引)：按索引删除，返回被删除的元素
String removed = list.remove(1);
System.out.println("被删除的元素是：" + removed); // 小乖
System.out.println(list); // [小哈, 小明, 小花]

// remove(元素值)：按内容删除，返回布尔值；重复内容只删第一个
boolean flag = list.remove("小明");
System.out.println(flag); // true
System.out.println(list); // [小哈, 小花]

// set(索引, 新数据)：修改元素，返回修改前的旧值
String old = list.set(1, "小米");
System.out.println("被修改的元素值之前是：" + old); // 小花
System.out.println(list); // [小哈, 小米]
```

**遍历集合**（用 `size()` 控制循环次数，`get(i)` 取元素）：

```java
for (int i = 0; i < list.size(); i++) {
    System.out.println(list.get(i));
}
```

> 注意：数组用 `length` 属性获取长度，集合用 `size()` 方法获取元素个数。

#### 5.4 案例

##### 案例 1：删除集合中包含指定内容的元素

集合内容：`Java入门, 宁夏枸杞, 黑枸杞, 人字拖, 特级枸杞, 枸杞子`，要求删除所有包含「枸杞」的元素。

删除时的陷阱：直接正序遍历并删除，删除后元素左移，会跳过相邻元素。两种解决方法：

**方法 1：正序遍历，删除后索引回退**

```java
import java.util.ArrayList;

public class Test2 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Java入门");
        list.add("宁夏枸杞");
        list.add("黑枸杞");
        list.add("人字拖");
        list.add("特级枸杞");
        list.add("枸杞子");

        for (int i = 0; i < list.size(); i++) {
            String str = list.get(i);
            if (str.contains("枸杞")) {
                list.remove(i);
                i--; // 删除后元素左移，索引回退一位，避免跳过元素
            }
        }
        System.out.println(list); // [Java入门, 人字拖]
    }
}
```

**方法 2：倒序遍历**（删除元素不影响前面元素的索引）

```java
for (int i = list.size() - 1; i >= 0; i--) {
    String str = list.get(i);
    if (str.contains("枸杞")) {
        list.remove(i);
    }
}
```

##### 案例 2：集合存储字符串并遍历

**需求**：创建一个存储字符串的集合，存储若干姓名，遍历并打印长度为 4 的字符串。

```java
public class ArrayListTest1 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();

        list.add("张三");
        list.add("上官玉米");
        list.add("李四");
        list.add("诸葛钢铁");
        list.add("王五");

        // 需要操作集合中的每一个元素时，就遍历集合
        for (int i = 0; i < list.size(); i++) {
            String name = list.get(i);
            if (name.length() == 4) {
                System.out.println(name);
            }
        }
    }
}
```

##### 案例 3：集合存储学生对象并遍历

**需求**：创建存储学生对象的集合，存储 3 个学生对象，遍历集合并打印年龄小于 18 的学生。

建议在模块下专门建立 `pojo`（或 `entity`）包，专门存放 JavaBean 对象。

```java
import com.itheima.pojo.Student;
import java.util.ArrayList;

public class ArrayListTest2 {
    public static void main(String[] args) {
        Student stu1 = new Student("张三", 23);
        Student stu2 = new Student("李四", 14);
        Student stu3 = new Student("王五", 15);

        // 集合的泛型指定为自定义的 JavaBean 类型
        ArrayList<Student> list = new ArrayList<>();
        list.add(stu1);
        list.add(stu2);
        list.add(stu3);

        for (int i = 0; i < list.size(); i++) {
            // 从集合中取出每一个学生对象
            Student stu = list.get(i);
            // 获取年龄进行判断
            if (stu.getAge() < 18) {
                System.out.println(stu);
            }
        }
    }
}
```

##### 综合案例：外卖商家菜品管理系统

功能：菜品的添加（add）、浏览（get）、下架（remove）、修改（set）。

**第一步：新建 Dish 实体类，封装菜品数据**

```java
public class Dish {
    // 私有成员变量
    private int id;         // 编号
    private String name;    // 菜名
    private double oldPrice;// 原价
    private double vipPrice;// 现价
    private String info;    // 描述

    // 构造器
    public Dish() {
    }

    public Dish(int id, String name, double oldPrice, double vipPrice, String info) {
        this.id = id;
        this.name = name;
        this.oldPrice = oldPrice;
        this.vipPrice = vipPrice;
        this.info = info;
    }

    // set/get 方法
    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getOldPrice() {
        return oldPrice;
    }

    public void setOldPrice(double oldPrice) {
        this.oldPrice = oldPrice;
    }

    public double getVipPrice() {
        return vipPrice;
    }

    public void setVipPrice(double vipPrice) {
        this.vipPrice = vipPrice;
    }

    public String getInfo() {
        return info;
    }

    public void setInfo(String info) {
        this.info = info;
    }
}
```

**第二步：编写操作类（菜单 + 增删改查）**

```java
public class DishCms {
    // 成员属性：Scanner 和集合在整个类中公用
    Scanner sc = new Scanner(System.in);
    // 1.创建一个集合用来存放数据
    ArrayList<Dish> itemList = new ArrayList<>();

    public void start() {
        // 2.模拟初始菜品：程序加载时就有数据
        itemList.add(new Dish(1, "宫保鸡丁", 19.1, 9.9, "单点不送"));
        itemList.add(new Dish(2, "鱼香肉丝", 18.8, 6.9, "鲜香麻辣"));
        itemList.add(new Dish(3, "麻辣小龙虾", 188.8, 36.9, "够辣够爽"));

        // 3.菜单控制页面
        while (true) {
            System.out.println("======欢迎来到商家菜品管理系统======");
            System.out.println("1.添加菜品（add）");
            System.out.println("2.浏览菜品（get）");
            System.out.println("3.下架菜品（remove）");
            System.out.println("4.修改菜品（set）");
            System.out.println("5.退出");
            System.out.println("=====请选择您的命令======");
            int command = sc.nextInt();
            switch (command) {
                case 1:
                    addDish();
                    break;
                case 2:
                    showDish();
                    break;
                case 3:
                    removeDish();
                    break;
                case 4:
                    modifyDish();
                    break;
                case 5:
                    System.exit(0); // 退出 JVM
                    break;
                default:
                    break;
            }
        }
    }

    // 添加菜品
    public void addDish() {
        Dish dish = new Dish();
        System.out.println("请输入菜品名称");
        dish.setName(sc.next());
        System.out.println("请输入菜品原价");
        dish.setOldPrice(sc.nextDouble());
        System.out.println("请输入菜品现价");
        dish.setVipPrice(sc.nextDouble());
        System.out.println("请输入菜品信息");
        dish.setInfo(sc.next());
        itemList.add(dish);
    }

    // 浏览菜单
    public void showDish() {
        for (int i = 0; i < itemList.size(); i++) {
            Dish dish = itemList.get(i);
            System.out.println("编号：" + dish.getId());
            System.out.println("菜名：" + dish.getName());
            System.out.println("原价：" + dish.getOldPrice());
            System.out.println("现价：" + dish.getVipPrice());
            System.out.println("描述：" + dish.getInfo());
            System.out.println("----------------------------");
        }
    }

    // 菜品下架
    private void removeDish() {
        System.out.println("请输入您要下架的菜品名称");
        String dishName = sc.next();
        boolean flag = false; // 信号位：默认没有这个菜品
        for (int i = 0; i < itemList.size(); i++) {
            Dish dish = itemList.get(i);
            if (dishName.equals(dish.getName())) {
                itemList.remove(i);
                System.out.println("删除" + dishName + "成功！");
                flag = true;  // 找到后更改信号位
                break;        // 停止查找
            }
        }
        if (!flag) {
            System.out.println("没找到您的菜品，请检查后重新输入...");
        }
    }

    // 修改菜品价格
    private void modifyDish() {
        System.out.println("请输入您要修改的菜品名字");
        String dishName = sc.next();
        boolean flag = false;
        for (int i = 0; i < itemList.size(); i++) {
            Dish dish = itemList.get(i);
            if (dishName.equals(dish.getName())) {
                System.out.println("请输入修改的原价价格");
                dish.setOldPrice(sc.nextDouble());
                System.out.println("请输入修改的现价价格");
                dish.setVipPrice(sc.nextDouble());
                System.out.println("菜品修改成功！");
                flag = true;
                break;
            }
        }
        if (!flag) {
            System.out.println("没找到您的菜品，请检查后重新输入...");
        }
    }
}
```

**第三步：测试使用**

```java
public class Test {
    public static void main(String[] args) {
        DishCms dishCms = new DishCms();
        dishCms.start();
    }
}
```

#### 5.5 ArrayList 的底层原理（长度为什么可变）

ArrayList 底层基于数组实现，却能"长度可变"，靠的是**自动扩容**：

1. **创建集合**：`new ArrayList<>()` 时，JDK 8 起底层先创建一个默认长度为 **0** 的空数组（JDK 7 及以前是创建时就给出长度 10 的数组）；
2. **首次添加**：添加第一个元素时，底层才创建一个长度为 **10** 的新数组，把元素放进去；
3. **记录位置**：每添加一个元素，记录元素个数的 `size` 就往后移一位——`size` 既是已有元素个数，也是下一个元素的存放位置；
4. **存满扩容**：数组存满后再添加元素时，会扩容出一个**原容量 1.5 倍**大小的新数组（10 → 15 → 22……），把原数组数据拷贝到新数组，再把新元素放进去；
5. **批量添加的特例**：如果一次添加多个元素（如 `addAll`），1.5 倍的新数组还是放不下，则新数组长度以**实际需要**为准（例如原容量 10，一次倒入 11 个元素，新数组长度直接为 21）。

扩容四步小结：创建 1.5 倍新数组 → 原数组数据拷贝过去 → 新元素加入新数组 → 旧数组丢弃。

> 正因为扩容涉及数组拷贝，ArrayList **适合查询、不适合频繁增删**；频繁在首尾增删的场景可使用 LinkedList（详见第 16 章）。

---

## 下篇：综合案例——商品管理系统

上篇学习了 ArrayList 的基本用法，下篇用一个完整的「商品管理系统」把知识点串起来：用 JavaBean 封装商品数据，用 `ArrayList<JavaBean>` 存储数据，围绕集合完成增、删、改、查，并学习**静态代码块初始化数据**和**信号位思想**两个重要开发技巧。

### 一、准备工作

#### 1.1 编写 JavaBean 实体类

商品的基本信息包括：编号 `id`、产品名 `name`、价格 `price`、库存 `num`、产品描述 `desc`。在 `pojo` 包中编写 `PmGoods` 类：

```java
package com.itheima.pojo;

public class PmGoods {
    // 成员变量
    private String id;    // 编号
    private String name;  // 产品名
    private double price; // 价格
    private int num;      // 库存
    private String desc;  // 产品描述

    // 构造器
    public PmGoods() {
    }

    public PmGoods(String id, String name, double price, int num, String desc) {
        this.id = id;
        this.name = name;
        this.price = price;
        this.num = num;
        this.desc = desc;
    }

    // setXxx / getXxx
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

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        this.price = price;
    }

    public int getNum() {
        return num;
    }

    public void setNum(int num) {
        this.num = num;
    }

    public String getDesc() {
        return desc;
    }

    public void setDesc(String desc) {
        this.desc = desc;
    }

    // 重写 toString，方便直接打印对象
    @Override
    public String toString() {
        return "PmGoods{" +
                "id='" + id + '\'' +
                ", name='" + name + '\'' +
                ", price=" + price +
                ", num=" + num +
                ", desc='" + desc + '\'' +
                '}';
    }
}
```

#### 1.2 搭建项目欢迎界面

在 `start` 包中新建 `App` 类作为程序入口，用 `while(true) + switch` 搭建菜单框架：

```java
package com.itheima.start;

import java.util.Scanner;

public class App {
    // 静态方法中无法直接访问非静态成员，而 main 是静态的，所以 Scanner 定义为 static
    static Scanner sc = new Scanner(System.in);

    public static void main(String[] args) {
        while (true) {
            System.out.println("-------------欢迎使用商品管理系统-------------");
            System.out.println("1. 添加商品");
            System.out.println("2. 删除商品");
            System.out.println("3. 修改商品");
            System.out.println("4. 查询全部商品");
            System.out.println("5. 查询单个商品");
            System.out.println("6. 退出");
            System.out.println("--------------------------------------------");
            System.out.println("请输入您的选择: ");

            String choice = sc.next();
            switch (choice) {
                case "1":
                    System.out.println("添加商品");
                    break;
                case "2":
                    System.out.println("删除商品");
                    break;
                case "3":
                    System.out.println("修改商品");
                    break;
                case "4":
                    System.out.println("查询全部商品");
                    break;
                case "5":
                    System.out.println("查询单个商品");
                    break;
                case "6":
                    System.out.println("感谢您的使用, 再见!");
                    // System.exit(0)：退出 JVM 虚拟机，0 表示正常终止，非 0 表示异常终止
                    return; // 直接结束 main 方法也可以退出循环
                default:
                    System.out.println("您输入有误, 请检查后重新输入!");
                    break;
            }
        }
    }
}
```

### 二、数据准备

#### 2.1 创建集合

数据需要存入一个集合中统一管理，集合的泛型就是我们自己编写的 JavaBean 类型。注意集合也要定义为 `static`，才能在静态的 `main` 和各静态方法中共享：

```java
public class App {
    static Scanner sc = new Scanner(System.in);
    // 集合类型就是自定义的 JavaBean 类型
    static ArrayList<PmGoods> goodsList = new ArrayList<>();

    public static void main(String[] args) {
        // ...
    }
}
```

#### 2.2 通过静态代码块添加默认测试数据

- 静态代码块在类加载（字节码文件加载）时执行，**且只执行一次**，非常适合做初始化数据：

```java
public class App {
    static Scanner sc = new Scanner(System.in);
    static ArrayList<PmGoods> goodsList = new ArrayList<>();

    // 静态代码块：类加载时执行一次，准备初始数据
    static {
        goodsList.add(new PmGoods("001", "华为平板", 3999, 60, "平板电脑"));
        goodsList.add(new PmGoods("002", "华为手机", 6999, 200, "手机"));
        goodsList.add(new PmGoods("003", "华为电脑", 8999, 100, "电脑"));
    }

    public static void main(String[] args) {
        // ...
    }
}
```

### 三、具体功能实现

> 贯穿所有功能的两个核心技巧：
> 1. **信号位（flag）思想**：先假设「没找到」（`flag = false`），遍历集合，如果找到目标就把 `flag` 改为 `true`；遍历结束后根据 `flag` 决定提示「成功」还是「不存在」。
> 2. **按 id 查找的固定套路**：遍历集合 → `goodsList.get(i)` 取出每个对象 → 用 `equals` 比较 id。

#### 3.1 添加商品 addGoods

- 用 JavaBean 创建一个新的商品对象；
- 按提示让用户填写数据；
- **id 不能重复**：输入后先遍历集合校验，重复则重新输入，不重复才存入。

```java
private static void addGoods() {
    // 创建一个空的商品对象
    PmGoods goods = new PmGoods();

    System.out.println("请输入您的商品id");
    String id = sc.next();
    while (true) {
        // 信号位：假设 id 不存在
        boolean flag = false;
        for (int i = 0; i < goodsList.size(); i++) {
            // 遍历集合，判断每个商品的 id 是否和用户输入的一致
            if (goodsList.get(i).getId().equals(id)) {
                flag = true;
                break;
            }
        }
        if (flag) {
            System.out.println("您输入的id已存在，请重新输入~~~");
            id = sc.next(); // 只重新接收 id
        } else {
            goods.setId(id); // id 可用，赋值给商品对象
            break;
        }
    }

    System.out.println("请输入您的商品名称");
    goods.setName(sc.next());
    System.out.println("请输入您的商品价格");
    goods.setPrice(sc.nextDouble());
    System.out.println("请输入您的商品库存");
    goods.setNum(sc.nextInt());
    System.out.println("请输入您的商品描述");
    goods.setDesc(sc.next());

    // 将商品对象添加到集合
    goodsList.add(goods);
    System.out.println("商品：" + goods.getName() + " 添加完成！");
    System.out.println("当前系统共有商品： " + goodsList.size() + "个");
}
```

#### 3.2 删除商品 deleteGoodsById

- 用户输入要删除的产品编号；
- 遍历集合比较 id，找到就删除并 `return` 结束方法；没找到就提示编号不存在，可重新输入。

```java
private static void deleteGoodsById() {
    while (true) {
        System.out.println("请输入您要删除的产品id");
        String id = sc.next();
        // 信号位：假设没找到
        boolean flag = false;
        for (int i = 0; i < goodsList.size(); i++) {
            PmGoods goods = goodsList.get(i);
            if (goods.getId().equals(id)) {
                flag = true;
                goodsList.remove(i);
                System.out.println("成功删除了商品- " + goods.getName());
                System.out.println("当前系统剩余商品- " + goodsList.size() + "个");
                return; // 删除成功，结束方法
            }
        }
        if (!flag) {
            System.out.println("您输入的id不存在，请重新输入~~~~");
        }
    }
}
```

#### 3.3 修改商品 updateGoodsById

- 用户输入产品编号，遍历集合找到对应商品；
- 找到后逐项询问用户是否修改（输入 `y/n`），输入 `y` 才接收新值。

```java
private static void updateGoodsById() {
    System.out.println("请输入您要修改的产品id");
    String id = sc.next();
    // 信号位：假设没找到
    boolean flag = false;
    for (int i = 0; i < goodsList.size(); i++) {
        PmGoods goods = goodsList.get(i);
        if (goods.getId().equals(id)) {
            flag = true;
            // 逐项确认是否修改：equalsIgnoreCase 忽略大小写
            System.out.println("请确认是否要修改商品" + goods.getName() + "的名称，y/n");
            if (sc.next().equalsIgnoreCase("y")) {
                System.out.println("请输入新的商品名字");
                goods.setName(sc.next());
            }

            System.out.println("请确认是否要修改商品" + goods.getName() + "的价格，y/n");
            if (sc.next().equalsIgnoreCase("y")) {
                System.out.println("请输入新的商品价格");
                goods.setPrice(sc.nextDouble());
            }
            // 库存、描述等属性可按同样方式继续补充
        }
    }
    if (!flag) {
        System.out.println("您输入的id不存在，请重新输入~~~~");
    }
}
```

#### 3.4 查询全部商品 showAllGoods

遍历集合，打印每个商品对象的所有属性：

```java
private static void showAllGoods() {
    System.out.println("本系统所有的商品信息如下：");
    for (int i = 0; i < goodsList.size(); i++) {
        PmGoods goods = goodsList.get(i);
        // 如果 JavaBean 重写了 toString，也可以直接 System.out.println(goods);
        System.out.println("编号：" + goods.getId());
        System.out.println("商品名：" + goods.getName());
        System.out.println("商品价格：" + goods.getPrice());
        System.out.println("商品库存：" + goods.getNum());
        System.out.println("商品描述：" + goods.getDesc());
        System.out.println("-----------------------------");
    }
}
```

#### 3.5 查询单个商品 showGoodsById

- 用户输入产品编号，遍历集合比较 id；
- 找到就打印该商品信息并 `return` 结束；没找到提示不存在，可重新输入。

```java
private static void showGoodsById() {
    while (true) {
        System.out.println("请输入您要查询的产品id");
        String id = sc.next();
        // 信号位：假设没找到
        boolean flag = false;
        for (int i = 0; i < goodsList.size(); i++) {
            PmGoods goods = goodsList.get(i);
            if (goods.getId().equals(id)) {
                flag = true; // 推翻假设
                System.out.println("编号：" + goods.getId());
                System.out.println("商品名：" + goods.getName());
                System.out.println("商品价格：" + goods.getPrice());
                System.out.println("商品库存：" + goods.getNum());
                System.out.println("商品描述：" + goods.getDesc());
                System.out.println("-----------------------------");
                return; // 查询成功，结束当前方法
            }
        }
        if (!flag) {
            System.out.println("您输入的id不存在，请重新输入~~~~");
        }
    }
}
```

最后在 `main` 方法的 `switch` 各分支中调用对应方法（`case "1": addGoods();` …），系统即完成。

---

### 本章小结

1. **String**：不可变字符串，双引号字面量存字符串常量池、相同内容只存一份；`new String` 每次创建新对象；比较内容用 `equals`，纯字面量拼接有编译期优化。
2. **StringBuilder**：可变字符序列，拼接/反转效率远高于 String；核心方法 `append`（返回自身、可链式）、`reverse`、`length`、`toString`；底层数组初始容量 16，扩容规则「旧容量 × 2 + 2」。
3. **StringBuffer**：API 与 StringBuilder 相同，线程安全但效率低。
4. **ArrayList**：动态数组，泛型必须是引用类型；`add / get / remove / set / size` 完成增删改查；底层靠自动扩容实现长度可变（首次添加建长度 10 的数组，存满按 1.5 倍扩容）；遍历中删除元素要注意索引错位（`i--` 或倒序遍历）。
5. **综合开发套路**：JavaBean 封装数据 → `ArrayList<JavaBean>` 存储 → `while + switch` 搭建菜单 → 静态代码块初始化数据 → 信号位（flag）+ 遍历比较 id 实现查找类功能。

---

# 第二部分 · JavaSE 进阶

<div style="page-break-after: always;"></div>

## 第十一章 面向对象进阶（一）：static 与继承

本章学习面向对象高级部分的两块基础内容：

- **static 关键字**：修饰成员变量、成员方法、代码块，理解"类成员"与"实例成员"的区别，并掌握单例设计模式。
- **继承**：使用 `extends` 建立父子关系，掌握权限修饰符、方法重写、`super` 关键字、子类构造器的执行特点。

---

### 一、static 关键字

在 Java 中，`static` 是一个关键字，表示"静态的"，**用于修饰类的成员（变量、方法、代码块）或内部类，使其属于类本身而非类的实例**。这意味着被 `static` 修饰的成员不需要创建对象就能访问，且所有实例共享同一份资源。

#### 1. 案例引导

一个学校需要统计学生信息，建立 Student 学生类，信息包含：学校、姓名、年龄：

```java
//Student类
public class Student {
    String schoolName;
    String studentName;
    int age;
}
```

```java
public class Test1 {
    public static void main(String[] args) {
       Student s1 = new Student();
       s1.schoolName = "黑马程序员";
       s1.studentName = "小哈";
       s1.age = 22;

        Student s2 = new Student();
        s2.schoolName = "黑马程序员";
        s2.studentName = "小米";
        s2.age = 20;
    }
}
```

可以发现 `schoolName` 每个学生都一样，每个对象存一份会造成内存浪费。此时可以用 `static` 修饰 `schoolName`：

```java
public class Student {
    // 类变量（静态变量）：所有学生对象共享
    static String schoolName;
    String studentName;
    int age;
}
```

```java
public class Test1 {
    public static void main(String[] args) {

        Student.schoolName="黑马程序员";

        Student s1 = new Student();
        s1.studentName = "小哈";
        s1.age = 22;

        Student s2 = new Student();
        s2.schoolName = "传智教育";
        s2.studentName = "小米";
        s2.age = 20;

        System.out.println(s1.schoolName); //传智教育（共享同一份，被 s2 修改了）
        System.out.println(s1.studentName); //小哈
        System.out.println(s1.age); //22

        System.out.println(s2.schoolName); //传智教育
        System.out.println(s2.studentName); //小米
        System.out.println(s2.age); //20
    }
}
```

#### 2. static 修饰成员变量 —— 类变量

##### 基本定义

按照有无 `static` 修饰，成员变量分为两种：

- **类变量（静态变量）**：有 `static` 修饰，属于类，在内存中只有一份，被全部对象共享。
- **实例变量（对象变量）**：没有 `static` 修饰，属于每个对象，每个对象各存一份。

如果成员变量使用了 `static` 修饰，无论用该类创建多少个对象，都不会再为这个变量创建副本，所有对象共享这一份。

##### 类变量的访问方式

```java
public class Student {
    //类变量
    static String schoolName;
    //实例变量：必须先创建实例
    String studentName;
    int age;
}
```

- **直接访问（推荐）：类名.变量名**

```java
Student.schoolName = "黑马程序员";
```

- 也可以通过实例对象访问（不推荐，需要先创建对象）：

```java
Student s2 = new Student();
s2.schoolName = "传智教育";
```

- **注意**：实例变量必须先创建实例才能访问，不能用类名直接访问。

##### 类变量的应用场景

在开发中，如果某个数据只需要一份，且希望能够被共享（访问、修改），则该数据可以定义成类变量。

**案例：统计班级人数**

需求：定义 Student 学生类，每个学生有共同的学校、自己的姓名，同时统计"当前班级一共有多少名学生"。

- 学校名所有学生共享、人数计数器也共享，这两个设计为类变量。
- 学生姓名每个学生单独拥有，设计为实例变量。
- 在构造器中对计数器累加，每创建一个学生就 +1。

```java
public class Student {
    public static String schoolName;
    public static int count;  //统计学生人数
    private String studentName;

    // 使用构造器每创建一个学生实例，count就会+1
    public Student() {
        //Student.count++;
        //在同一个类中访问自己的类变量，可以省略类名不写
        count++;
    }

    public Student(String studentName) {
        this.studentName = studentName;
        count++;
    }
    public String getStudentName() {
        return studentName;
    }

    public void setStudentName(String studentName) {
        this.studentName = studentName;
    }
}
```

测试：

```java
public class Test {
    public static void main(String[] args) {

        Student.schoolName = "黑马程序员";

        //创建第1个学生
        Student s1 = new Student();
        s1.setStudentName("小哈");
        System.out.println(s1.getStudentName() + "加入" + Student.schoolName);
        //创建第2个学生
        Student s2 = new Student();
        s1.setStudentName("小米");
        System.out.println(s1.getStudentName() + "加入" + Student.schoolName);
        //创建第3个学生
        Student s3 = new Student();
        s1.setStudentName("黑马吴彦祖");
        System.out.println(s1.getStudentName() + "加入" + Student.schoolName);

        System.out.println("当前班级人数是：" + Student.count + "人");
    }
}
```

#### 3. static 修饰成员方法 —— 类方法

##### 基本定义

按照有无 `static` 修饰，成员方法分为两种：

- **类方法（静态方法）**：使用 `static` 修饰的成员方法，属于类。
- **实例方法**：没有 `static` 修饰的成员方法，属于每个对象。

```java
public class Student {
    //成员变量
    public static String schoolName; //类变量
    private String name;
    private double score;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getScore() {
        return score;
    }

    public void setScore(double score) {
        this.score = score;
    }

    //类方法
    public static void printWelcome() {
        System.out.println("======欢迎来到，" + schoolName + "成绩查询系统！======");
    }

    //类方法
    public static void isQualified(double score) {
        if (score > 60) {
            System.out.println("您的成绩合格！");
        } else {
            System.out.println("您的成绩不合格！");
        }
    }
}
```

##### 类方法的访问方式

- **直接访问（推荐）：类名.类方法名()**

```java
//直接使用类名访问（推荐）---> 类名.类方法名()
Student.printWelcome();
```

- 也可以通过对象访问（不推荐，需要先创建对象）：

```java
Student s1 = new Student();
//使用实例对象调用类方法（不推荐）---》 对象.类方法
s1.printWelcome();
```

##### 类方法的应用场景：工具类

类方法最常见的应用场景是做**工具类**。工具类中的方法都是类方法，每个方法完成一个功能，供开发人员共同使用。好处：提高代码复用性，调用方便，提高开发效率。

**案例：验证码生成工具类**

验证码是复用性很强的代码，可以封装到工具类中，使用时直接用工具类名调用：

```java
public class MyUtil {
    //验证码生成器
    public static String captchaGenerator(int length){
        // 验证码字符库：数字 + 大小写字母
        String chars = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz";
        Random random = new Random();
        String str = "";

        // 循环生成指定长度的随机字符
        for (int i = 0; i < length; i++) {
            // 从字符库中随机取一个字符
            int index = random.nextInt(chars.length());
            str += chars.charAt(index);
        }
        return str;
    }
}
```

测试：

```java
public class Test {
    public static void main(String[] args) {
        String str1 = MyUtil.captchaGenerator(6);
        System.out.println(str1);
    }
}
```

**多学一招：**

- 为什么工具类中的方法要用类方法而不用实例方法？
  1. 实例方法需要创建对象来调用，对象只是为了调用方法，对象占内存，浪费内存。
  2. 类方法直接用类名调用，调用方便，也能节省内存。
- 工具类没有创建对象的需求，建议将工具类的构造器**私有**（比如 Java 的 `Math` 类）。构造器私有后，其他地方就不能创建该类的实例对象；因为工具类直接使用即可，里面的方法设计为 `static` 修饰的类方法：

```java
public class MyUtil {
   //将工具类的构造器私有
    private MyUtil() {
    }

    //验证码生成器
    public static String captchaGenerator(int length){
       //此处省略很多很多代码......
    }
}
```

##### 使用类方法、实例方法的注意事项

- **类方法中可以直接访问类成员，不可以直接访问实例成员。**

```java
public class Student {
    static String  schoolName; //类变量
    double score;  //实例变量
    //类方法中可以直接访问类的成员，不可以直接访问实例成员。
    public static void printWelcome(){
        System.out.println(schoolName);
        System.out.println(score); //报错
        //类方法中可以调用类方法
        printWelcome1();
        printinfo(); //报错：类方法中不能调用实例方法，实例方法只能实例调用
    }
    public static void printWelcome1(){
        //类方法2
    }
     public void printinfo(){
        //实例方法
    }
}
```

- **实例方法中既可以直接访问类成员，也可以直接访问实例成员。**

```java
public class Student {
    static String  schoolName; //类变量
    double score;  //实例变量

    public static void printWelcome(){
        //类方法
    }

    //实例方法中既可以直接访问类成员，也可以直接访问实例成员。
    public void printinfo(){
        System.out.println(schoolName);
        System.out.println(score);
        printWelcome(); //类方法
        printinfo1(); //实例方法
    }

    public void printinfo1(){
        //实例方法2...
    }
}
```

- **实例方法中可以出现 `this` 关键字，类方法中不可以出现 `this`。**

```java
public class Student {
    static String  schoolName; //类变量
    double score;  //实例变量
    //类方法中可以直接访问类的成员，不可以直接访问实例成员。
    public static void printWelcome(){
        System.out.println(this); //报错：类方法是类直接调用，this没有对象指向
    }

    //实例方法
    public void printinfo(){
        System.out.println(this); //谁调用指向谁
    }

}
```

> 记忆要点：静态只能直接访问静态；实例全都能访问；`this` 代表当前对象，静态环境中没有对象。

#### 4. 代码块（了解）

##### 概述

代码块是类的 5 大成分之一（成员变量、构造器、方法、代码块、内部类）。在 Java 中，"代码块"是用 `{}` 包裹的一段代码，各自有不同的作用和执行时机。

代码块分为两种：

##### 静态代码块

- 格式：`static { }`
- 特点：**类加载时自动执行**，由于类只会加载一次，所以静态代码块也只会执行一次。
- 作用：通常用于初始化静态变量或执行类级别的预处理逻辑，例如对类变量初始化赋值。

```java
public class Student {
    static String schoolName;
    String name;
    //静态代码块
    static {
        schoolName = "黑马程序员";
        System.out.println("静态代码块执行了~~~");
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        System.out.println("======欢迎来到"+Student.schoolName+"======");
        System.out.println("在这你将会学会java和AI相关的知识~~~");
        System.out.println("让我们一起开心快乐的学习吧~~~");
    }
}
```

##### 实例代码块

- 格式：`{ }`
- 特点：**每次创建对象时都会执行**。
- 作用：和构造器一样，用来完成对象的初始化，例如对实例变量进行初始化赋值。

```java
public class Student {
    static String schoolName;
    String grade;
    String name;
    //静态代码块
    static {
        schoolName = "黑马程序员";
        System.out.println("静态代码块执行了~~~");
    }
    //实例代码块
    {
        System.out.println("====== 实例代码块执行了======");
        grade =  "上海黑马AI智能应用开发(Java)就业175期";
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        System.out.println("=======欢迎来到" + Student.schoolName + "========");
        System.out.println("在这你将会学会java和AI相关的知识~~~");
        System.out.println("让我们一起开心快乐的学习吧~~~");
        System.out.println("============================================");

        //创建一个Student实例对象
        Student s1 = new Student();
        s1.name = "小哈";
        System.out.println(s1.name + "同学您就读的班级是：" + s1.grade);
        System.out.println("--------------------------------");

        Student s2 = new Student();
        s2.name = "小哈";
        System.out.println(s2.name + "同学您就读的班级是：" + s2.grade);
        System.out.println("--------------------------------");

    }
}
```

##### 注意

- 代码块主要用于初始化静态变量（尤其是初始化逻辑复杂时），或执行类加载时的一次性操作（如加载配置文件、注册驱动等）。
- 开发中用得不多，一般是 JDK 源码中会使用，用来记录一个复杂的对象。比如 JDK 的 `Socket` 类对一些变量进行复杂对象的设置。

#### 5. 设计模式（了解）：单例设计模式

设计模式是一套经过总结的、解决特定问题的代码设计经验，目的是让代码更易维护、可扩展、复用性更高。简单理解：一个问题通常有 n 种解法，其中最优的解法被人总结出来，就称之为设计模式。设计模式有 20 多种，这里学习**单例设计模式**。

##### 概述

**单例设计模式：确保一个类只有一个对象。**

- **核心**：保证一个类只有一个实例，并提供全局访问点。
- **场景**：工具类（如日志工具）、配置管理器（避免重复加载配置）。例如 JDK 的 `Runtime` 类、计算机的任务管理器。

`java.lang.Runtime` 类代表当前 Java 应用程序的运行时环境，提供与底层操作系统交互的方法（执行命令、管理内存等）。每个应用程序只能有一个运行时环境，因此 `Runtime` 被设计为单例——全局只有一个实例。

单例模式要满足三个要求：

1. 定义一个类变量记住一个对象；
2. 类的构造器私有；
3. 定义一个方法返回对象。

##### 饿汉式单例

**"饿汉式"：拿对象时，对象早就创建好了。**

```java
public class A {
    //定义一个类变量记住类的对象
    private static A a = new A();

    //把类的构造器私有
    private A() {
    }

    //定义一个类方法，返回对象
    public static A getA() {
        return a;
    }
}
```

测试：

```java
public class Test {
    public static void main(String[] args) {
        //A a = new A();//报错：构造器已经私有
        A a1 = A.getA();
        A a2 = A.getA();

        System.out.println(a1);
        System.out.println(a2);
    }
}
```

##### 懒汉式单例

**"懒汉式"：拿对象时，才创建对象。** 一开始不创建对象，需要使用时才创建。

固定写法：

1. 定义一个类变量用于存储对象；
2. 把类的构造器私有；
3. 提供一个类方法，保证返回的是同一个对象。

```java
public class B {
    //定义一个类变量用于存储对象
    private static B b;

    //把类的构造器私有
    private B() {}

    //提供一个类方法，保证返回的是同一个对象
    public static B getB() {
        if (b == null) {
            b = new B();
        }
        return b;
    }
}
```

一开始类变量没有对象，第一次调用 `getB()` 时 `b` 为 `null`，于是 `new B()` 创建对象并返回；之后再调用直接返回已有的对象。

```java
public class Test1 {
    public static void main(String[] args) {
        B b1 = B.getB();//第一次拿对象
        B b2 = B.getB();
        System.out.println(b1 == b2); //true
    }
}
```

##### 案例：模拟系统的任务管理器

操作系统的任务管理器无论打开多少次，都只有一个窗口，用单例模式模拟：

```java
public class TaskManager {
    //类变量记住一个对象
    private static TaskManager instance = new TaskManager();
    //类的构造器私有
    private TaskManager() {}
    //定义一个方法返回对象
    public static TaskManager getInstance() {
        return instance;
    }

    //显示进程列表
    public void showProcesses(){
        System.out.println("进程列表：[QQ.exe,chrome.exe,doubao.exe]");
    }
}
```

```java
public class Test2 {
    public static void main(String[] args) {
        System.out.println("用户第一次点击任务管理器");
        TaskManager t1 = TaskManager.getInstance();
        t1.showProcesses();

        System.out.println("用户第二次点击任务管理器");
        TaskManager t2 = TaskManager.getInstance();
        t2.showProcesses();

        System.out.println();
        System.out.println("\n两个窗口是否是同一个：" + (t1 == t2));//true
    }
}
```

---

### 二、继承

#### 1. 快速入门

Java 中的**继承（Inheritance）**是面向对象三大特性（封装、继承、多态）之一，核心思想是**复用已有类的代码，实现类之间的层次关系**。

##### 语法

Java 提供关键字 `extends`，用它可以让一个类和另一个类建立父子关系：

```java
// 父类（基类/超类）：被继承的类
class 父类名 {

}

// 子类（派生类）：继承父类的类
class 子类名 extends 父类名 {

}
```

##### 继承特点

**子类能继承父类的所有成员（成员变量、成员方法），但不能直接访问私有的成员。**

```java
public class Father {
    //父类的属性
    String name;
    int age;
    String nationality;
    private String homestead;
    private String work;
    //父类的方法
    public void eat(){
        System.out.println(name + "正在吃饭！");
    }
    public void sleep(){
        System.out.println(name + "在睡觉！");
    }
    private void tourism(){
        System.out.println(name + "总是自己一个人去旅行！");
    }
}
```

```java
public class Son extends Father {
    //子类属性
    String schoolName;
    //子类方法
    public void study(){
        System.out.println(name + "是在"+schoolName + "学习！");
    }
}
```

```java
public class Test1 {
    public static void main(String[] args) {
        //创建一个儿子对象
        Son s1 = new Son();
        s1.name = "小哈";
        s1.age = 18;
        //s1.homestead = "四合院";//报错：子类不能访问父类的私有成员
        s1.eat(); //小哈正在吃饭！
        s1.sleep();//小哈在睡觉！
        //s1.tourism();//报错：子类不能访问父类的私有方法
    }
}
```

##### 使用继承的好处

**减少重复代码的编写，提高代码的复用性。**

例如员工管理系统中需要处理讲师、咨询师的数据：

- 讲师的数据：姓名 name、技能 skill
- 咨询师的数据：姓名 name、解答问题的人数 number

姓名是重复代码，可以提取到公共类 People 中，让子类继承：

```java
public class People {
    private String name;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

```java
public class Teacher extends People {
    private String skill; //技能

    public String getSkill() {
        return skill;
    }

    public void setSkill(String skill) {
        this.skill = skill;
    }
}
```

```java
public class Consultant extends People {
    private int number;//解答人数

    public int getNumber() {
        return number;
    }

    public void setNumber(int number) {
        this.number = number;
    }
    public void printIfo(){
        System.out.println(getName()+"一天服务学员：" + number + "个");
    }
}
```

测试：

```java
public class Test1 {
    public static void main(String[] args) {
        Teacher t = new Teacher();
        t.setName("波仔");
        t.setSkill("java、Python");
        System.out.println(t.getName());
        System.out.println(t.getSkill());

        System.out.println("==================");

        Consultant c = new Consultant();
        c.setName("小哈");
        c.setNumber(20);
        System.out.println(c.getName());
        System.out.println(c.getNumber());
        c.printIfo();
    }
}
```

#### 2. 权限修饰符

Java 中的**权限修饰符**用于控制类、属性、方法的访问范围（即"谁能访问它们"），是封装特性的重要体现。共有 4 种，从开放到严格依次为：`public`（公开）、`protected`（受保护）、`default`（默认/缺省，不写修饰符）、`private`（私有）。

```java
public class Fu {
    //私有：只能在本类中访问
    private void privateMethod(){
        System.out.println("===private===");
    }
    //缺省：本类，同一个包下的类都可以访问
    void method(){
        System.out.println("===method===");
    }
    //protected：本类，同一个包下的类，任意包下的子类
    protected void protectedMethod(){
        System.out.println("===protectedMethod===");
    }
    //public：本类，同一个包下的类，任意包下的子类，任意包下的任意类
    public void publicMethod(){
        System.out.println("===publicMethod===");
    }
}
```

四种修饰符的可见范围：

| 修饰符 | 本类 | 同包类 | 不同包的子类 | 不同包的任意类 |
|---|---|---|---|---|
| `private` | 可以 | 不可以 | 不可以 | 不可以 |
| 缺省（default） | 可以 | 可以 | 不可以 | 不可以 |
| `protected` | 可以 | 可以 | 可以 | 不可以 |
| `public` | 可以 | 可以 | 可以 | 可以 |

- **`private`（私有）：仅自己可见**。只有当前类内部可以访问，其他任何类（包括子类）都不能直接访问。用于保护类的核心数据，只能通过类内部方法操作（封装的核心）。
- **缺省（默认）：同包可见**。同一包中的类可以访问，不同包的类（包括子类）不能访问。用于包内共享的工具类或辅助方法。
- **`protected`（受保护）：子类可见 + 同包可见**。同一包中的类可访问，不同包的子类也可访问，但不同包的非子类不可访问。用于父类中需要被子类继承和修改的方法/属性。
- **`public`（公开）：全局可见**。任何地方都可以访问。用于对外提供的接口、工具方法或公共类（如 `java.lang.String`）。

本类中四种都能访问：

```java
package xiushifu;

public class Fu {

    //private只能在本类中使用
    public void Test(){
        privateMethod();
        method();
        protectedMethod();
        publicMethod();
    }
}
```

同一个包中的类：private 不可见，其余可见：

```java
package xiushifu;

public class Test1 {
    public static void main(String[] args) {
        Fu f = new Fu();
       // f.privateMethod();//报错
        f.protectedMethod();
        f.method();
        f.protectedMethod();
        f.publicMethod();
    }
}
```

不同包的子孙类：只有 protected 和 public 可见：

```java
package util;

import xiushifu.Fu;

public class Zi extends Fu {
    public void Test() {
        // privateMethod(); //报错
        // method();  //报错
        protectedMethod();
        publicMethod();
    }
}
```

不同包的任意类：只有 public 可见：

```java
package util;

import xiushifu.Fu;

public class Test2 {
    public static void main(String[] args) {
        Fu f = new Fu();
        //f.privateMethod(); //报错
        //f.method(); //报错
        //f.protectedMethod(); //报错
        f.publicMethod();
    }
}
```

#### 3. 单继承与 Object 类

##### 单继承

- **Java 是单继承的：Java 中的类不支持多继承（一个类只能有一个亲爹），但是支持多层继承（继承链）。**

```java
class A {}
class B extends A {}   // B 继承 A
class C extends B {}   // C 继承 B，间接继承 A —— 多层继承
// class D extends A, B {} // 报错：不能多继承
```

##### Object 类

- `java.lang.Object` 是所有类的根类（超类），任何类都直接或间接继承自 `Object`。
- 简单理解：Object 类是 Java 所有类的祖宗类。我们写的任何一个类，其实都是 Object 的子类或子孙类。

以下代码中 Father 默认继承了 Object，可以使用 Object 的相关方法：

```java
public class Test {
    public static void main(String[] args) {
        Father f = new Father();
        f.name = "王小哈";
        //Father 默认继承了Object类的相关操作
        System.out.println(f.toString());
    }
}
```

#### 4. 方法重写（Override）

##### 概述

**方法重写（Override）**是指子类重新定义父类中已有的方法，使子类对象调用该方法时执行子类的实现而非父类的实现。这是实现**多态**的核心机制之一。

简单理解：当子类觉得父类中的某个方法不好用，或者无法满足自己的需求时，**子类可以重写一个方法名称、参数列表完全一样的方法**，去覆盖父类的这个方法。

```java
public class Singer {
    public void singSong(){
        System.out.println("千年等一回！");
    }
    public void hobby(int month){
        System.out.println("喜欢"+month + "月份去，爬山");
    }
}
```

进行方法重写：

```java
public class Star extends Singer {
    @Override
    public void singSong(){
        System.out.println("成都");
    }
    @Override
    public void hobby(int month){
        System.out.println("喜欢"+month + "月份去，旅行");
    }
}
```

测试：

```java
public class Test {
    public static void main(String[] args) {
        Star zhaoLei = new Star();
        zhaoLei.singSong();
        zhaoLei.hobby(5);
    }
}
```

##### 方法重写的注意事项

- 使用 `@Override` 注解：它可以让 Java 编译器检查方法重写的格式是否正确（比如方法名或形参列表写错就会报错），代码可读性也更好。
- 子类重写父类方法时，**访问权限必须大于或等于父类该方法的权限**（`public` > `protected` > 缺省）。
- 重写的方法**返回值类型**必须与被重写方法的返回值类型一样，或者范围更小（子类类型）。
- **私有方法、静态方法不能被重写**，如果"重写"会报错。

**方法重写的八字方针：声明不变，重新实现。**

##### 方法重写的应用场景

父类的默认方法实现不符合子类需求时，通过重写"替换"父类逻辑。典型例子是 `Object` 类的 `toString()` 方法：

- 父类 Object 的 `toString()` 默认返回 `类名@哈希码`（如 `Star1@1b6d3586`），几乎没有实际意义；
- 重写后可以得到想要的数据内容：

```java
public class Star1 {
    String name;
    int age;
    String job;

    @Override
    public String toString() {
        return "Star1{" +
                "name='" + name + '\'' +
                ", age=" + age +
                ", hobby='" + job + '\'' +
                '}';
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Star1 star1 = new Star1();
        star1.name = "赵雷";
        star1.age = 40;
        star1.job ="民谣歌手";

        //重写前：Star1@2f4d3709；重写后：Star1{name='赵雷', age=40, hobby='民谣歌手'}
        System.out.println(star1.toString());
    }
}
```

#### 5. 子类访问成员的特点：就近原则与 super

```java
public class Fu {
    String name = "父类名字";
    public void print1(){
        System.out.println("=== 父类的print方法执行===");
    }
}
```

```java
public class Zi extends Fu {
    String name = "子类名称";

    public void showName() {
        String name = "局部名称";
        System.out.println(name);        //局部名称
        System.out.println(this.name);  //子类名称
        //可以通过super关键字，指定访问父类的成员：super.父类成员变量/父类成员方法
        System.out.println(super.name); //父类名字
    }
    @Override
    public void print1(){
        System.out.println("===子类重写的方法打印啦~~===");
    }

    public void showMethod(){
        print1();        //===子类重写的方法打印啦~~===
        //可以通过super关键字，指定访问父类的成员
        super.print1();  //=== 父类的print方法执行===
    }
}
```

**在子类方法中访问其他成员（成员变量、成员方法），依照就近原则：**

1. 先在子类局部范围找；
2. 然后在子类成员范围找；
3. 然后在父类成员范围找，如果父类范围还没有找到则报错。

如果子父类中出现重名成员，会优先使用子类的；如果一定要在子类中使用父类的，可以通过 `super` 关键字指定访问父类成员：`super.父类成员变量` / `super.父类成员方法()`。

```java
public class Test {
    public static void main(String[] args) {
        Zi zi = new Zi();
        zi.showName();
        zi.showMethod();
    }
}
```

#### 6. 子类构造器的特点

**子类的全部构造器，都会先调用父类的构造器，再执行自己。**

实现方式：

- 默认情况下，子类全部构造器的第一行代码都是 `super()`（写不写都有），它会调用父类的无参构造器。
- 如果父类没有无参构造器，则必须在子类构造器的第一行手写 `super(...)`，指定调用父类的有参构造器。

父类有无参构造器时：

```java
public class Fu {
    public Fu() {
        System.out.println("~~~父类的无参构造器被执行啦~~~");
    }
}
```

```java
class Zi extends Fu {
    public Zi() {
        //super(); //默认存在
        System.out.println("~~~子类的无参构造器执行啦~~~");
    }
     public Zi(int a) {
         //super(); //默认存在
        System.out.println("~~~子类的有参构造器执行啦111~~~");
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Zi zi1 = new Zi();
        Zi zi2 = new Zi();
    }
}
```

父类没有无参构造器时，必须手写 `super(...)`：

```java
public class Fu {
    public Fu(String name,int age) {
        System.out.println("~~~父类的有参构造器被执行啦~~~");
    }
}
```

```java
class Zi extends Fu {
    public Zi() {
       super("小哈",18); //必须手写，调用父类有参构造器
        System.out.println("~~~子类的无参构造器执行啦~~~");
    }
    public Zi(int a) {
        super("小哈",18);
        System.out.println("~~~子类的有参构造器执行啦111~~~");
    }
}
```

#### 7. 子类构造器的常见应用

子类构造器可以通过调用父类构造器，把对象中包含父类这部分的数据先初始化赋值，再回来初始化子类这部分的数据：

```java
public class People {
    private String name;
    private int age;
    //父类的无参构造器
    public People() {
    }
    //父类的有参构造器
    public People(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
public class Teacher extends People {
    private String skill;
    //子类无参构造器
    public Teacher() {
    }
    //子类有参构造器
    public Teacher(String name, int age, String skill) {
        super(name, age);//调用父类的构造器，将公共部分初始化
        this.skill = skill;
    }

    public String getSkill() {
        return skill;
    }

    public void setSkill(String skill) {
        this.skill = skill;
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Teacher t = new Teacher("小哈",36,"java");
        System.out.println(t.getName());
        System.out.println(t.getAge());
        System.out.println(t.getSkill());
    }
}
```

#### 8. this(...) 调用兄弟构造器

任意类的构造器中，都可以通过 `this(...)` 去调用该类的其他构造器（兄弟构造器）。

例如 Student 类有三个属性：name、age、schoolName。如果创建学生对象时只传姓名和年龄，学校默认是"黑马程序员"，可以再写一个两参构造器：

```java
class Student{
    private String name;
    private int age;
    private String schoolName;

    public Student() {
    }
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
        this.schoolName = "黑马程序员";
    }
    public Student(String name, int age, String schoolName) {
        this.name = name;
        this.age = age;
        this.schoolName = schoolName;
    }
    // ...getter/setter 省略
}
```

但两个有参构造器出现了大量重复代码。优化方式：在两参构造器中用 `this(...)` 调用三参构造器：

```java
public Student(String name, int age) {
    this(name, age, "黑马程序员");
}
public Student(String name, int age, String schoolName) {
    this.name = name;
    this.age = age;
    this.schoolName = schoolName;
}
```

测试：

```java
public class Test1 {
    public static void main(String[] args) {
        //传三个参数
        Student s1 = new Student("张三",28,"北京大学");
        //只传姓名和年龄，学校默认"黑马程序员"
        Student s2 = new Student("小哈",23);
        System.out.println(s2.getSchoolName()); //黑马程序员
    }
}
```

**注意：`this(...)` 和 `super(...)` 都只能放在构造器的第一行，因此有了 `this(...)` 就不能写 `super(...)`，反之亦然。**

---

### 本章小结

- `static` 修饰的成员属于类：类变量全类只有一份、被所有对象共享；类方法推荐用"类名.方法名"调用，典型用途是工具类（构造器私有）。
- 静态成员只能直接访问静态成员；实例成员静态、实例都能访问；`this` 只能出现在实例方法中。
- 静态代码块在类加载时执行一次；实例代码块每次创建对象时执行。
- 单例模式保证一个类只有一个实例：饿汉式提前创建对象，懒汉式第一次使用时才创建。
- 继承用 `extends` 建立父子关系，提高代码复用性；Java 单继承、多层继承，Object 是所有类的根类。
- 四种权限修饰符范围：`private` < 缺省 < `protected` < `public`。
- 方法重写要求"声明不变，重新实现"，建议加 `@Override`；私有方法、静态方法不能重写。
- 子类访问成员遵循就近原则，`super` 访问父类成员；子类构造器第一行默认 `super()` 先调用父类构造器；`this(...)` 调用本类兄弟构造器，与 `super(...)` 互斥。

---

<div style="page-break-after: always;"></div>

## 第十二章 面向对象进阶（二）：多态、final、抽象类与接口

本章在继承的基础上学习面向对象的另外几块核心内容：

- **多态**：同一行为在不同对象上有不同表现，掌握向上转型、向下转型与 `instanceof`。
- **final**：修饰类、方法、变量，理解"不可改变"的含义与常量的定义。
- **抽象类**：用 `abstract` 定义抽象父类与抽象方法。
- **接口**：用 `interface` 定义行为规范，理解实现、多实现、接口多继承以及 JDK8 新特性。

---

### 一、多态

在 Java 中，**多态（Polymorphism）**是面向对象三大特性之一，指**同一行为（方法）在不同对象上有不同的表现形式**。简单来说：**父类引用指向子类对象，调用方法时执行子类的实现**。

多态是在继承/实现情况下的一种现象，表现为：**对象多态、行为多态**（一个对象存在多种表现形态）。

#### 1. 对象多态

**一个对象存在多个表现形态。** 例如猫是一只猫，也可以说猫是一只动物：

```java
public class Animal {
}
```

```java
public class Cat extends Animal {
}
```

```java
public class Test {
    public static void main(String[] args) {
        //一个对象存在多种形态  动物1是只猫 / 动物2是条狗 / 动物3是只鸟
        Animal animal = new Cat();   //猫
        Animal anima2 = new Dog();   //狗
        Animal anima3 = new Bird();  //鸟
    }
}
```

#### 2. 行为多态（方法多态）

**同一行为（方法）在不同对象上有不同的表现形式。**

```java
public class Animal {
    public void eat(){
        //不知道动物们都吃啥
        System.out.println("动物进食");
    }
}
```

在 Cat 和 Dog 中重写方法，实现不同动物的不同表现：

```java
public class Cat extends Animal {
    @Override
    public void eat() {
        System.out.println("小猫吃鱼~~");
    }
}
```

```java
public class Dog extends Animal {
    @Override
    public void eat() {
        System.out.println("小狗吃骨头~~");
    }
}
```

测试：

```java
public class Test {
    public static void main(String[] args) {
        //行为（方法）多态：同一个方法调用出不同的行为表现
        Animal animal1 = new Cat(); //对象多态
        animal1.eat(); //小猫吃鱼~~（行为多态）

        Animal animal2 = new Dog(); //对象多态
        animal2.eat(); //小狗吃骨头~~（行为多态）
    }
}
```

#### 3. 多态的实现条件

要实现多态，必须满足三个条件：

1. **继承关系**：子类必须继承父类（或实现接口）。
2. **方法重写**：子类必须重写父类的方法。
3. **父类引用指向子类对象**：通过父类类型的变量引用子类实例，格式为 **父类类型 变量名 = new 子类类型();**

```java
Animal animal = new Cat();
```

**注意**：多态是对象、行为的多态，Java 中的属性（成员变量）没有多态。

#### 4. 使用多态的好处

- **代码复用性高**：父类定义通用逻辑，子类按需重写，无需重复编写。
- **右边对象解耦合，更便于扩展和维护**：右边的对象可以随时更换。

```java
//所谓解耦合就是右边的对象可以随时更改
Animal animal = new Cat();
animal = new Dog();
animal = new Pig();
```

- **多态实现通用方法**：定义方法时使用**父类类型的形参**，可以接收一切子类对象，扩展性更强。

如果给每种动物都单独写一个喂食方法，代码量大且不利于维护：

```java
public class AnimalOpera {
    //给狗喂食
    public void eatDog(Dog dog){
        System.out.println("开始喂食。。。");
        dog.eat();
        System.out.println("喂食结束。。。");
    }
    //给猫喂食
    public void eatCat(Cat cat){
        System.out.println("开始喂食。。。");
        cat.eat();
        System.out.println("喂食结束。。。");
    }
    //给猪喂食
    public void eatPig(Pig pig){
        System.out.println("开始喂食。。。");
        pig.eat();
        System.out.println("喂食结束。。。");
    }
}
```

利用多态，把方法形参设为父类类型，只写一个方法即可：

```java
public class AnimalOpera {
    //利用多态的原理编写一个给动物喂食的方法
    public void eatAnimal(Animal animal){
        System.out.println("开始喂食。。。");
        animal.eat();
        System.out.println("喂食结束。。。");
    }
}
```

```java
public class Test1 {
    public static void main(String[] args) {
        AnimalOpera animalOpera = new AnimalOpera();
        Animal animal1 = new Cat(); //对象多态
        animalOpera.eatAnimal(animal1);

        Animal animal2 = new Dog();//对象多态
        animalOpera.eatAnimal(animal2);

        Animal animal3 = new Pig();//对象多态
        animalOpera.eatAnimal(animal3);
    }
}
```

#### 5. 多态下的问题与类型转换

##### 问题：多态下不能使用子类的独有功能

多态对象的引用类型是父类，父类代表一大类，不能直接调用某个子类特有的方法：

```java
public class Cat extends Animal {
    @Override
    public void eat() {
        System.out.println("小猫吃鱼~~");
    }
    //子类特有的
    public void playMouse(){
        System.out.println("大脸猫抓老鼠~~");
    }
}

public class Dog extends Animal {
    @Override
    public void eat() {
        System.out.println("小狗吃骨头~~");
    }
    //子类特有的方法
    public void lookDoor(){
        System.out.println("狗看门~~");
    }
}

public class Pig extends Animal{
    @Override
    public void eat() {
        System.out.println("猪吃菜~~~");
    }
    //子类特有的方法
    public void sleep(){
        System.out.println("猪睡觉~~");
    }
}
```

```java
public class Test2 {
    public static void main(String[] args) {
        Animal animal1 = new Cat();
        //animal1.playMouse(); //多态下不能使用子类的独有功能
        //强制转换后可以使用子类的独有功能
        Cat cat = (Cat)animal1;
        cat.playMouse();

        Animal animal2 = new Dog();
        //强制转换
        Dog dog = (Dog)animal2;
        dog.lookDoor();

        Animal animal3 = new Pig();
        //强制转换（也可以转完直接调用）
        ((Pig)animal3).sleep();
    }
}
```

##### 类型转换原理

- **自动类型转换（向上转型）**：`父类 变量名 = new 子类();` —— 子类指向父类。

```java
Animal animal2 = new Dog();
```

- **强制类型转换（向下转型）**：`子类 变量名 = (子类) 父类变量名`。

```java
Dog dog = (Dog)animal2;
```

##### 强制转换的注意事项

- 存在继承/实现关系就可以在编译阶段进行强制类型转换，编译阶段不会报错。
- 运行时，如果发现对象的**真实类型**与强转后的类型不同，就会报类型转换异常（`ClassCastException`）。

```java
public class Test3 {
    public static void main(String[] args) {
        Animal animal = new Dog();
        palyMethod(animal);
    }
    //编写一个方法实现所有动物的特有方法调用
    public static void palyMethod(Animal animal) {
        //直接强转不可以，需要知道animal的真实类型才能强转
        ((Cat)animal).playMouse();
        ((Dog)animal).lookDoor();
        ((Pig)animal).sleep();
        //直接运行会报 ClassCastException 类型转换异常
        //因为不确定到底是什么类型
    }
}
```

**解决方案**：强转前，使用 `instanceof` 关键字判断当前对象的真实类型，再进行强转：

```java
public class Test3 {
    public static void main(String[] args) {
        Animal animal = new Dog();
        palyMethod(animal);

        Animal animal2 = new Cat();
        palyMethod(animal2);

        Animal animal3 = new Pig();
        palyMethod(animal3);
    }
    //编写一个方法实现所有动物的特有方法调用
    public static void palyMethod(Animal animal) {
        //强转前，使用instanceof判断当前对象的真实类型，再进行强转
        if (animal instanceof Cat) {
            ((Cat)animal).playMouse();
        }
        if(animal instanceof Dog){
            ((Dog)animal).lookDoor();
        }
        if(animal instanceof Pig){
            ((Pig)animal).sleep();
        }
    }
}
```

---

### 二、final

#### 1. 概述

`final` 是关键字，含义是"不可改变的、最终的"，用于修饰类、方法和变量。合理使用 `final` 可以提高代码的安全性和可读性：

- 修饰**类**：该类称为最终类，不能被其他类继承。
- 修饰**方法**：该方法称为最终方法，不能被重写。
- 修饰**变量**：该变量只能被赋值一次。

#### 2. 修饰类

被 `final` 修饰的类**不能被继承**（没有子类）：

```java
public final class Fu {

}
//Fu类被final修饰了，最终类不能被继承
class Zi extends Fu{} //报错
```

#### 3. 修饰方法

被 `final` 修饰的方法**不能被子类重写**（override），但可以被继承和调用。常用于保护核心方法逻辑不被修改：

```java
public class Parent {
    public final void eat(){};
}

class Child extends Parent {
    @Override
    public void eat() { //报错
    }
}
```

#### 4. 修饰变量（常量）

被 `final` 修饰的变量一旦赋值就**不能再修改**。必须在声明时或构造方法中初始化，否则报错：

```java
public class Fu2 {
    //01 - 成员变量  基本类型
    public final int number = 1;
    //02 - 数组（引用类型）
    public final int[] num = new int[2];
    //03 - 对象类型（引用数据类型）
    public final Student student = new Student();

    public static void main(String[] args) {
        Fu2 f = new Fu2();
        //01 - 不能修改final修饰的基本类型变量
        //f.number = 42; //报错

        //02 - 引用数据类型，不能修改的是地址值，但地址中的元素可以修改
        f.num[0] = 11;
        f.num[0] = 12;
       // f.num = new int[12]; //报错，不能修改final修饰的引用的地址

        //03 - 修改Student对象的name属性
        f.student.name =  "小哈";
        //可以修改属性内容，因为不能修改的只是地址值
        f.student.name =  "小米";
    }
}
```

**注意：**

- `final` 修饰**基本类型**变量：变量存储的数据不能被改变。
- `final` 修饰**引用类型**变量：变量存储的地址值不能被改变，但地址所指向对象的内容是可以被改变的。

#### 5. 常量

使用 **`static final`** 共同修饰的成员变量称为**常量**。作用：通常用于记录系统的配置信息，定义一些固定不变的值。

例如学生管理系统有多个功能模块都要显示系统名字，如果每个功能都写死一个值，后期修改很麻烦。可以定义一个常量类把常用常量集中存放：

```java
public class Constants {
    //构造器私有，让常量类只能使用，不能创建
    private Constants() {
    }
    //系统名称
    public static final String PROJECT_NAME = "黑马程序员-学生信息管理系统";
    //系统版本号
    public static final String PROJECT_VERSION = "1.0.0";
    //软件作者
    public static final String SOFT_NAME = "小哈";
    //公司名称
    public static final String JOB_NAME  = "黑马程序员";
    //公司备案号
    public static final String RECORD_NUMBER = "苏公网安备32132202000574号";
}
```

```java
public class Test {
    public static void main(String[] args) {

    }
    //多个功能模块都使用常量
    public void test01(){
        System.out.println(Constants.PROJECT_NAME);
    }
    public void test02(){
        System.out.println(Constants.PROJECT_NAME);
    }
}
```

- **常量命名规范：单词全部大写，多个单词用下划线分隔连接**。
- 使用常量记录系统配置信息的优势：**代码可读性更好，可维护性也更好**。

---

### 三、抽象类

Java 中有一个关键字 `abstract`（抽象的），可以用来修饰类和成员方法：

- `abstract` 修饰类，这个类就是**抽象类**；
- `abstract` 修饰方法，这个方法就是**抽象方法**。

#### 1. 基本语法

```java
public abstract class 类名 {
    public abstract 返回值类型 方法名(形参列表);
}
```

```java
//被abstract修饰的类就叫做抽象类
public abstract class Fu {
    //被abstract修饰的方法就是抽象方法(没有方法体，不需要写大括号)
    public abstract void show();
}
```

#### 2. 理解抽象类

抽象类表示一个**广泛的概念（泛指一类事物）**。

比如 `Animal` 是一个抽象类，它表示动物，但不知道具体是什么动物，可以是猫、狗、猪等等。它作为父类抽取子类共有的属性和方法让子类继承，比如动物的名字和吃东西。再比如 `People` 表示人，但不知道具体是老师、学生、班主任还是保洁阿姨，不过不管什么人都有姓名、年龄等共同属性和走路、睡觉等共同方法。

```java
public abstract class Animal {
    String name;

    //抽象方法的作用：把一类事物的某一个功能交给子类去实现
    public abstract void eat();
}
```

此时子类如果不实现抽象方法会报错：

```java
public class Cat extends Animal {
} //报错：必须重写 eat()，或者把 Cat 也定义为抽象类
```

#### 3. 抽象类的注意事项

- **抽象类中不一定有抽象方法，但有抽象方法的类一定是抽象类。**
- 类该有的成员（成员变量、方法、构造器）抽象类都可以有：

```java
public abstract class Animal {
    String name;
    int age;

    //抽象方法
    public abstract void eat();

    //普通成员方法
    public void show(){};
    //构造器：可以有，但是不能用来创建对象
    public Animal(){
        System.out.println("Animal构造器");
    }
}
```

- **抽象类不能创建对象（不能实例化）**，它作为一种特殊的父类，让子类继承并实现：

```java
public static void main(String[] args) {
    Animal animal = new Animal(); //报错
}
```

- **一个类继承抽象类，必须重写完抽象类的全部抽象方法**，否则这个类也必须定义成抽象类：

```java
public class Cat extends Animal {
    @Override
    public void eat() {
        System.out.println("猫吃鱼儿~~");
    }
}
```

#### 4. 案例：宠物游戏

需求：某宠物游戏需要管理猫、狗的数据。猫有名字，行为是喵喵喵地叫；狗有名字，行为是汪汪汪地叫。用面向对象编程设计。

第一步：用抽象类把猫狗共有的属性（名字）和行为（叫）提取为父类：

```java
public abstract class Animal {
    private String name;
    //共有行为方法（抽象方法）
    //类中存在抽象方法，这个类必须是抽象类
    public abstract void cry();

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

第二步：Cat 和 Dog 继承抽象类，重写全部抽象方法：

```java
public class Cat extends Animal {

    @Override
    public void cry() {
        System.out.println("小猫喵喵喵的叫~~~");
    }
}
```

```java
public class Dog extends Animal {

    @Override
    public void cry() {
        System.out.println("小狗汪汪汪的叫~~~");
    }
}
```

#### 5. 抽象类的应用场景和好处

- **场景 1**：用抽象类可以把子类中相同的代码（包括方法）抽上来，更好地支持多态，提高代码灵活性。
- **场景 2**：不知道系统未来具体的业务实现时，可以先定义抽象类，将来让子类去继承实现，便于系统扩展。

---

### 四、接口

#### 1. 定义

Java 提供关键字 **`interface`**，用它可以定义出一个特殊的结构——**接口**：

```java
public interface 接口名{
    //成员变量（常量）
    //成员方法（抽象方法）
}
```

- 接口中的成员变量都是**常量**；
- 接口中的成员方法都是**抽象方法**（JDK8 之前）。

```java
//JDK 1.7 的接口
public interface A {
    //成员变量：必须是公共静态常量（需要赋值）
    public static final String name = "hello";
    // public static final 可以省略不写
    int age = 18;

    //成员方法：都是公共的抽象方法（不能有方法体）
    //public abstract可以省略不写
    public abstract void show();
}
```

```java
public class Test {
    public static void main(String[] args) {
        //因为是静态常量，可以直接用 接口名.属性名 访问
        System.out.println(A.name);
        System.out.println(A.age);
    }
}
```

#### 2. 接口的使用：implements 实现

接口不能创建对象，接口是用来被类**实现（implements）**的，实现接口的类称为**实现类**：

```java
修饰符 class 实现类 implements 接口1, 接口2, 接口3, ... {

}
```

一个类可以实现**多个接口**（接口可以理解成"干爹"）。实现类实现多个接口，必须重写完全部接口的全部抽象方法，否则实现类需要定义成抽象类。

**接口的好处：弥补了类单继承的不足，一个类可以实现多个接口。**

```java
//接口
public interface B {
}
```

```java
//接口
public interface C {
}
```

```java
//实现类：可以同时实现多个接口
public class A implements B,C {
}
```

**案例：老师既是人，又是司机和歌手**

People 类抽取人相关的属性和方法；Teacher 单继承 People，同时实现 Driver、Singer 两个接口的功能：

```java
public class People {
    private String name;
    private int age;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
public interface Driver {
    //抽象方法：开车功能
    public abstract void driver();
}
```

```java
public interface Singer {
    //抽象方法：唱歌功能
    public abstract void singer();
}
```

```java
public class Teacher extends People implements Driver,Singer {
    private String skill;

    public String getSkill() {
        return skill;
    }

    public void setSkill(String skill) {
        this.skill = skill;
    }
    //接口中的抽象方法必须重写
    @Override
    public void driver() {
        System.out.println("下班后还要去开滴滴~~~");
    }

    @Override
    public void singer() {
        System.out.println("休息的时候在酒吧唱歌挣钱~~~");
    }
}
```

#### 3. 综合案例：动物园管理系统

动物园有猫 Cat、鸭子 Duck、老鹰 Eagle、狗 Dog、鱼 Fish，它们都有名字 name 属性和吃 eat() 功能，可以提取到 Animal 类。由于类是单继承的，跑、飞、游泳等能力无法都通过继承获得，可以采用接口单独抽出 `Runnable`、`Flyable`、`Swimmable` 三个接口，让需要的类各自 `implements`。

第一步：实现 Animal 类：

```java
public class Animal {
    //属性
    String name;
    //行为
    public void eat(){
        System.out.println("正在吃食物~~~");
    }
}
```

第二步：实现三个接口：

```java
//具有跑功能的动物
public interface Runnable {
    public abstract void run();
}
```

```java
//具有飞能力的动物
public interface Flyable {
    public abstract void fly();
}
```

```java
//有游泳能力的动物
public interface Swimmable {
    public abstract void swim();
}
```

第三步：创建各种动物类，先继承 Animal，再实现对应接口（重写接口中的全部抽象方法）：

```java
public class Cat extends Animal implements Runnable  {
    @Override
    public void run() {
        System.out.println("猫在跑~~~");
    }
}
```

```java
public class Duck extends Animal implements Runnable,Swimmable {

    @Override
    public void run() {
        System.out.println("鸭子在跑~~~");
    }

    @Override
    public void swim() {
        System.out.println("鸭子在游泳~~~");
    }
}
```

第四步：测试。注意：**父类类型不能访问子类特有的行为；接口类型也只能访问该接口中定义的行为**：

```java
public class Test {
    public static void main(String[] args) {
        //创建一只猫
        Cat cat = new Cat();
        cat.eat();
        cat.run();
        // 父类类型不能访问子类特有的行为和属性
        Animal animal = new Cat();
        animal.eat();
        //接口类型只能访问接口中定义的方法
        Runnable runnable = new Cat();
        runnable.run();

        System.out.println("------------------------");
        //创建一只鸭子
        Duck duck = new Duck();
        duck.eat();
        duck.run();
        duck.swim();

        Animal animal2 = new Duck();
        animal2.eat();

        Swimmable swimmable = new Duck();
        swimmable.swim();
    }
}
```

#### 4. 接口的优势和作用

1. 解决类单继承的问题：通过接口，一个类可以有一个亲爹（继承）的同时，还可以找多个干爹（实现接口）来扩展功能。
2. 一个类可以实现多个接口，一个接口也可以被多个类实现。这样程序就可以**面向接口编程**，方便灵活切换各种业务实现：

```java
public class Test1 {
    public static void main(String[] args) {
        //Runnable runnable = new Cat();
        Runnable runnable = new Duck(); //右边实现类可以灵活切换
        runnable.run();
    }
}
```

#### 5. JDK8 接口的新特性

JDK8 开始，接口新增了默认方法、私有方法（JDK9）、静态方法三种形式，增强了接口能力，更便于项目扩展和维护：

```java
public interface A {
    //JDK1.7（包含）的内容
    //属性 ---》 常量
    public static final String name = "小哈";
    //行为 ---》 抽象方法（没有方法体）
    public abstract void method();

    //==========================新增的方法=======================================
    //默认方法（实例方法）：使用default修饰，默认会被加上public修饰
    //注意：只能使用接口实现类的对象调用
    default void test1() {
        System.out.println("我是默认方法~~");
        //调用私有方法
        test2();
    }

    //私有方法：必须用private修饰（JDK9 开始才支持）
    private void test2() {
        System.out.println("我是私有方法~~");
    }

    //类方法（静态方法）：使用static修饰，默认会被加上public修饰
    //注意：只能用接口名来调用
    static void test3() {
        System.out.println("我是静态方法~~");
    }
}
```

```java
public class B implements A{
    @Override
    public void method() {
        //重写抽象方法
    }
}
```

测试：

```java
public class Test {
    public static void main(String[] args) {
        //调用静态方法：只能用接口名调用
        A.test3();
        //私有方法不能在类外调用，只能在接口内部调用
        //接口不能创建对象
        // A a = new A(); //报错
        A a = new B(); //用实现类对象调用默认方法
        a.test1();
    }
}
```

#### 6. 接口的多继承

**接口与接口之间是多继承关系**：一个接口可以继承多个接口，用类实现时需要重写所有接口（包括父接口）的方法：

```java
interface A {
    void a();
}
interface B {
    void b();
}
//接口和接口之间是多继承关系
interface C extends A, B {
    void c();
}
//使用 Student 类实现接口C，需要重写 A、B、C 三个接口的全部方法
class Student implements C {
    @Override
    public void c() {

    }

    @Override
    public void a() {

    }

    @Override
    public void b() {

    }
}
```

#### 7. 接口的其他注意事项（了解）

1. 一个接口继承多个接口时，如果多个接口中存在**方法签名冲突**（同名方法返回值类型不同等），则不支持多继承。
2. 一个类实现多个接口时，如果多个接口中存在方法签名冲突，则不支持多实现。
3. 一个类继承了父类、又同时实现了接口，父类中和接口中有同名的**默认方法**，实现类会优先使用父类的。
4. 一个类实现了多个接口，多个接口中存在同名的默认方法，不冲突，这个类重写该方法即可。

---

### 本章小结

- 多态的前提：继承/实现 + 方法重写 + 父类引用指向子类对象；成员变量没有多态。
- 多态的好处：提高复用性、右边对象解耦便于扩展；用父类类型作形参可以接收一切子类对象。
- 向上转型自动完成；向下转型需要强转，真实类型不匹配会抛 `ClassCastException`，强转前用 `instanceof` 判断。
- `final` 修饰类不能继承、修饰方法不能重写、修饰变量只能赋值一次；引用类型被 final 锁定的是地址值，对象内容仍可修改。
- `static final` 修饰的成员变量是常量，命名全大写下划线分隔，常集中放在构造器私有的常量类中。
- 抽象类用 `abstract` 修饰，不能实例化；抽象方法没有方法体；子类继承抽象类必须重写全部抽象方法，否则自己也得是抽象类。
- 接口用 `interface` 定义，成员是常量和公共抽象方法；类用 `implements` 实现接口且可多实现；接口之间可以多继承；JDK8 起接口支持 default 默认方法、static 静态方法（JDK9 起支持 private 私有方法）。

---

<div style="page-break-after: always;"></div>

## 第十三章 面向对象进阶（三）

本章学习四个进阶主题：模板方法设计模式、内部类、枚举、泛型。其中**匿名内部类**和**泛型**是重点，在集合和 API 学习中会反复使用。

---

### 一、模板方法设计模式（了解）

#### 1.1 概述

**模板方法设计模式解决了什么问题？**

- 解决方法中存在重复代码的问题：把多个子类中相同的代码抽取到父类的一个方法中，不同的部分定义为抽象方法交给子类实现。

#### 1.2 写法

1. 定义一个抽象类。
2. 在里面定义两类方法：
   - **模板方法**：把相同代码放里面。
   - **抽象方法**：具体实现交给子类完成。
3. 建议使用 `final` 关键字修饰模板方法（JDK 中的 `DateFormat` 就是这样做的）：
   - 模板方法是给对象直接使用的，不能被子类重写；
   - 一旦子类重写了模板方法，模板方法就失效了。

```java
public abstract class Fu {
    // 模版方法：用 final 修饰，子类不能重写
    public final void sing(){
        System.out.println("唱一首你喜欢的歌~~~");
        doSing();
        System.out.println("---唱完了---");
    }
    // 抽象方法：具体唱什么交给子类
    public abstract void doSing();
}
```

```java
public class A extends Fu  {
    @Override
    public void doSing() {
        System.out.println("我爱你亲爱的中国~~~");
    }
}
```

```java
public class B extends Fu {
    @Override
    public void doSing() {
        System.out.println("不管你怎么洗呀~~");
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        A a = new A();
        a.sing();

        B b = new B();
        b.sing();
    }
}
```

#### 1.3 小结

- 模板方法 = 父类中固定的流程骨架（final 修饰）+ 抽象方法（子类填空）。
- 优点：相同代码只写一份，子类只关心自己的差异部分。

---

### 二、内部类

#### 2.1 概念

**内部类**是类中的五大成分之一（成员变量、方法、构造器、内部类、代码块）。如果**一个类定义在另一个类的内部，这个类就是内部类**。

```java
public class Person {
    // 内部类，也是 Person 类的成员之一
    public class Student{

    }
}
```

#### 2.2 使用场景

当一个类的内部包含了一个完整的事物，且这个事物没有必要单独设计时，就可以把这个事物设计成内部类。

```java
public class Car{
    // 发动机是汽车的一部分，没必要单独对外暴露，可以设计成内部类
    public class Engine{
    }
}
```

#### 2.3 内部类的分类

- 成员内部类（了解）
- 静态内部类（了解）
- 局部内部类（了解）
- 匿名内部类（重点）

#### 2.4 成员内部类（了解）

成员内部类就是类中的一个普通成员，类似普通的成员变量、成员方法。

##### 语法

```java
public class 外部类名 {
    // 类的5大组成：成员变量（属性）、方法、构造器、内部类、代码块
    public class 内部类名 {

    }
}
```

##### 创建对象的格式

```java
// 外部类名.内部类名 对象名 = new 外部类().new 内部类();
Outer.Inner inner = new Outer().new Inner();
```

##### 访问特点案例

```java
public class Outer {
    // 成员属性
    private int age = 17;
    // 成员方法
    public void showOuter(){
        System.out.println("outer的show方法~~~");
    }

    // 成员内部类
    public class Inner {
        // 成员属性
        private String name;
        private int age = 18;
        // 成员方法
        public void showInner(){
            System.out.println("Inner的show方法~~~");
        }
        public void test(){
            int age = 19; // 局部变量
            // 访问局部变量 age（就近原则）
            System.out.println(age);            // 19
            // 访问内部类的成员属性 name
            System.out.println(name);
            // 访问内部类的 age = 18
            System.out.println(this.age);
            // 访问外部类的 age = 17：外部类名.this.属性
            System.out.println(Outer.this.age);
        }
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        // 创建内部类对象
        Outer.Inner inner = new Outer().new Inner();
        inner.test();
    }
}
```

要点：当局部变量、内部类成员、外部类成员重名时，分别用 `age`、`this.age`、`Outer.this.age` 区分。

#### 2.5 静态内部类（了解）

有 `static` 修饰的内部类。

- 可以访问外部类的**静态**属性和方法；
- **不能**访问外部类的**实例**属性和方法。

```java
public class Outer {
    // 外部静态属性
    private static String name = "小哈";
    // 外部实例属性
    private int age;
    // 外部静态方法
    public static void print() {
        System.out.println("外部的静态方法执行了~~~");
    }
    // 外部实例方法
    public void print1() {
        System.out.println("外部的实例方法执行了~~~");
    }

    public static class Inner {
        public void test() {
            System.out.println(name);   // 可以访问静态属性
            // System.out.println(age); // 报错：不能访问实例属性
            print();                    // 可以调用静态方法
            // print1();                // 报错：不能调用实例方法
        }
    }
}
```

#### 2.6 局部内部类（了解）

局部内部类定义在方法中、代码块中、构造器等执行体中，只能在定义它的局部范围内使用。

```java
public class Outer {
    public void test(){
        // 局部内部类：在方法中定义一个类
        class Inner {
            public void show(){
                System.out.println("局部内部类中的show方法~~~");
            }
        }
        // 只能在方法内部创建对象
        Inner inner = new Inner();
        inner.show();
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Outer outer = new Outer();
        outer.test();
    }
}
```

#### 2.7 匿名内部类（重点）

匿名内部类是一种特殊的局部内部类；所谓匿名，指程序员不需要为这个类声明名字。

##### 语法格式

```java
new 类或接口(参数值...){
    // 类体（一般是方法重写）
}
```

##### 特点与作用

- **特点**：匿名内部类本质就是一个子类，会立即创建出一个子类对象。
- **作用**：更方便地创建一个子类对象，不需要去包里手动创建多余的类文件。
- **好处**：测试时代码更简洁，不需要为只用一次的实现类单独建文件。
- **使用场景**：如果调用方法时，**形参是接口或者抽象类**，就可以用匿名内部类快速构建这个对象。

##### 入门案例

先定义抽象类和接口：

```java
// 抽象类：定义动物"叫"的行为模板
public abstract class Animal {
    public abstract void cry();
}
```

```java
// 接口：定义动物"移动"的行为标准
public interface Runnable {
    public abstract void run();
}
```

不用匿名内部类时，测试小猫必须先新建一个 `Cat` 类去继承/实现、重写方法，再创建对象：

```java
public class Test {
    public static void main(String[] args) {
        Animal animal = new Cat();
        animal.cry();
        Runnable r = new Cat();
        r.run();
    }
}
```

如果要测试 10 个小动物，就要新建 10 个类，非常繁琐。使用匿名内部类：

```java
public class Test {
    public static void main(String[] args) {
        // 匿名内部类继承 Animal 抽象类
        Animal cat = new Animal() {
            @Override
            public void cry() {
                System.out.println("小猫在喵喵的叫~~");
            }
        };
        cat.cry();

        // 匿名内部类实现 Runnable 接口
        Runnable catRunnable = new Runnable() {
            @Override
            public void run() {
                System.out.println("小猫在奔跑~~~");
            }
        };
        catRunnable.run();
    }
}
```

匿名内部类编译后会生成对应的 class 文件（如 `Test$1.class`），不需要我们自己命名。

##### 综合案例：游泳比赛

小猫和小狗进行游泳比赛，设计游泳接口 `Swimming` 和比赛入口 `go()` 方法：

```java
public interface Swimming {
    // 接口里的抽象方法可以省略 public abstract
    void swim();
}
```

```java
public class Test {
    public static void main(String[] args) {
        Swimming swimmAnimal1 = new Swimming() {
            @Override
            public void swim() {
                System.out.println("小猫在游泳~~~");
            }
        };
        go(swimmAnimal1);

        Swimming swimmAnimal2 = new Swimming() {
            @Override
            public void swim() {
                System.out.println("小狗在游泳~~~");
            }
        };
        go(swimmAnimal2);
    }

    // 比赛入口：接收实现了 Swimming 接口的对象
    public static void go(Swimming swimming){
        System.out.println("开始游泳。。。");
        swimming.swim();
        System.out.println("-----------------------");
    }
}
```

##### 匿名内部类的简写

开发中匿名内部类一般直接作为参数传给方法，不需要先拿变量接收：

```java
public class Test {
    public static void main(String[] args) {
        go(new Swimming() {
            @Override
            public void swim() {
                System.out.println("小猫在游泳~~~");
            }
        });
        go(new Swimming() {
            @Override
            public void swim() {
                System.out.println("小狗在游泳~~~");
            }
        });
    }

    public static void go(Swimming swimming){
        System.out.println("开始游泳。。。");
        swimming.swim();
        System.out.println("-----------------------");
    }
}
```

#### 2.8 内部类小结

| 分类 | 定义位置 | 重点程度 |
| --- | --- | --- |
| 成员内部类 | 类中成员位置 | 了解 |
| 静态内部类 | 类中成员位置，static 修饰 | 了解 |
| 局部内部类 | 方法/代码块/构造器中 | 了解 |
| 匿名内部类 | 方法中，`new 接口/抽象类(){...}` | **重点** |

---

### 三、枚举

#### 3.1 概念

在 Java 中，**枚举（Enum）** 是 Java 5 引入的一种特殊数据类型，用于定义**固定数量的常量集合**（如星期、季节、性别、状态等）。它把一组相关常量组织在一个枚举类中，使代码更具可读性、安全性和可维护性。

**简单理解：枚举是一种特殊类，是存放一组常量的集合。**

#### 3.2 语法

```java
修饰符 enum 枚举类名{
    名称1, 名称2, ... ;
    // 其他成员…
}
```

注意：

- 枚举类第一行只能写合法的标识符（名称），多个名称用逗号隔开；
- 这些名称本质是常量，每个常量都记住枚举类的一个对象。

```java
public enum Sex {
    男, 女
}
```

```java
public class Test {
    public static void main(String[] args) {
        // 枚举类自带 values() 方法，获取所有常量
        Sex[] sexs = Sex.values();
        for (int i = 0; i < sexs.length; i++) {
            System.out.println(sexs[i]);
        }
    }
}
```

#### 3.3 入门案例

```java
public enum WeekDay{
    星期一, 星期二, 星期三, 星期四, 星期五, 星期六, 星期天
}
```

学生类使用枚举约束性别和星期的取值：

```java
public class Student {
    private String name;
    // 不要用 String：String 可以放任何字符串，数据不安全
    // 使用枚举确保类型安全，避免出现无效值
    private Sex sex;
    private WeekDay weekDay;

    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public Sex getSex() {
        return sex;
    }
    public void setSex(Sex sex) {
        this.sex = sex;
    }
    public WeekDay getWeekDay() {
        return weekDay;
    }
    public void setWeekDay(WeekDay weekDay) {
        this.weekDay = weekDay;
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Student s1 = new Student();
        s1.setName("小哈");
        s1.setSex(Sex.男);              // 只能传枚举中定义的常量
        s1.setWeekDay(WeekDay.星期一);
        System.out.println(s1.getSex());
        System.out.println(s1.getWeekDay());
    }
}
```

#### 3.4 枚举的特点

- 第一行只能罗列名称，这些名称都是常量，每个常量记住的都是枚举类的一个对象。
- 枚举类的构造器都是**私有**的（写不写 `private` 都只能是私有的），因此枚举类对外不能创建对象。
- 枚举都是**最终类**，不可以被继承。
- 从第二行开始，可以定义类的其他各种成员（成员变量、方法、代码块等）。
- 编译器为枚举类新增了几个方法，枚举类都继承自 `java.lang.Enum`。

```java
public enum Sex {
    // 第一行：常量，每个常量记住枚举类的一个对象
    BOY, GIRL;

    // 第二行开始：可以定义其他成员
    private String name;

    // 构造器默认私有，private 可以省略
    private Sex() {
    }

    // 代码块
    {
        // 代码块内容
    }
}
```

#### 3.5 枚举的应用场景：常量类 vs 枚举

**常量类**方式：用一个个常量表示一组信息，作为参数传输时**参数值不受约束**：

```java
public class Constant {
    private Constant(){}
    // static final 修饰的成员变量称为常量，常用来定义固定值
    public static final String BOY = "男";
    public static final String GIRL = "女";
}
```

**枚举**方式：用枚举表示一组信息并作为参数传输，代码可读性好，**参数值得到约束**，对使用者更友好，建议使用：

```java
public enum Sex {
    BOY, GIRL
}
```

```java
public class Test {
    public static void main(String[] args) {
        // 传入的参数只能是枚举中定义的常量
        provideInfo(Sex.BOY);
        provideInfo(Sex.GIRL);
    }

    // 形参是枚举类型，传值受到约束
    public static void provideInfo(Sex sex) {
        switch (sex) {
            case BOY:
                System.out.println("进入男生信息展示区域~~~");
                break;
            case GIRL:
                System.out.println("进入女生信息展示区域~~");
                break;
        }
    }
}
```

#### 3.6 小结

- 枚举 = 一组常量的集合，本质是一个继承 `java.lang.Enum` 的最终类。
- 优点：类型安全、取值受约束、可读性好，可直接用于 `switch`。

---

### 四、泛型（了解）

#### 4.1 概念

**泛型（Generics）** 是 Java 5 引入的核心特性，用于在编译时**约束数据类型**，避免类型转换错误，同时实现代码的复用性和安全性。

定义类、接口、方法时，同时声明一个或多个类型变量（如 `<E>`），就称为**泛型类、泛型接口、泛型方法**，它们统称为泛型。

**作用**：在编译阶段约束所能操作的数据类型并自动检查，**避免强制类型转换及其可能出现的异常**（限定了数据存储的类型）。

不用泛型的问题：

```java
public class Test1 {
    public static void main(String[] args) {
        ArrayList list = new ArrayList();
        list.add("java1");
        list.add("java2");
        list.add(12);            // 什么类型都能存
        list.add(new Cat());

        // 取出来都是 Object，使用时需要强转
        for (int i = 0; i < list.size(); i++) {
            String s = (String) list.get(i);  // 运行时 ClassCastException
            System.out.println(s);
        }

        // 使用泛型后：限定存储类型
        ArrayList<String> list1 = new ArrayList<>();
        list1.add("java1");
        list1.add("java2");
        // list1.add(22);            // 编译报错
        // list1.add(new Cat());     // 编译报错
        String s = list1.get(0);     // 取出直接是 String，无需强转
    }
}
class Cat{}
```

#### 4.2 泛型类

**语法**：

```java
修饰符 class 类名<类型变量, 类型变量, …> {

}
// 类型变量建议用大写字母，常用：E、T、K、V 等
public class ArrayList<E>{
    // ...
}
```

基础案例：一个"通用容器" Box：

```java
// E 是泛型参数（占位符），表示 Box 可以存储的对象类型
// 避免为每种类型单独定义 StringBox、IntegerBox，实现代码复用
public class Box<E> {
    public E item;
}
```

```java
public class Test {
    public static void main(String[] args) {
        Box<String> box1 = new Box<>();
        box1.item = "玩具";

        Box<Student> box2 = new Box<>();
        box2.item = new Student();
    }
}
class Student{}
```

案例升级（私有属性 + getter/setter）：

```java
public class Box<E> {
    private E item;

    public E getItem() {
        return item;
    }
    public void setItem(E item) {
        this.item = item;
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Box<String> box1 = new Box<>();
        box1.setItem("玩具");
        System.out.println(box1.getItem());

        Box<Student> box2 = new Box<>();
        box2.setItem(new Student());
        System.out.println(box2.getItem());

        Box<Integer> box3 = new Box<>();
        box3.setItem(2);
        System.out.println(box3.getItem());
    }
}
class Student{}
```

泛型类可以声明多个类型变量（实际开发中几乎不自己写泛型类，但要会用）：

```java
public class Box<E, F> {
    private E item;
    private F item1;
}
```

#### 4.3 泛型接口

**语法**：

```java
修饰符 interface 接口名<类型变量, 类型变量, …> {

}

public interface A<E>{
    // ...
}
```

案例：定义泛型接口，分别由学生操作类和老师操作类实现：

```java
public interface A<T> {
    // 添加元素
    public void add(T t);
}
```

```java
public class Student {
    String name;
}
```

```java
public class Teacher {
    String name;
}
```

```java
import java.util.Scanner;

public class TeacherOper implements A<Teacher> {
    Scanner sc = new Scanner(System.in);
    @Override
    public void add(Teacher teacher) {
        System.out.println("请输入老师姓名~~");
        String name = sc.nextLine();
        teacher.name = name;
        System.out.println(teacher.name + "老师添加成功了！");
    }
}
```

```java
import java.util.Scanner;

public class StudentOper implements A<Student> {
    Scanner sc = new Scanner(System.in);
    @Override
    public void add(Student student) {
        System.out.println("请输入学生姓名~~");
        String name = sc.nextLine();
        student.name = name;
        System.out.println(student.name + "学生添加成功了！");
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        TeacherOper t = new TeacherOper();
        t.add(new Teacher());
        t.add(new Teacher());

        StudentOper s = new StudentOper();
        s.add(new Student());
        s.add(new Student());
    }
}
```

#### 4.4 泛型方法

**语法**：

```java
修饰符 <类型变量, 类型变量, …> 返回值类型 方法名(形参列表) {

}

public static <T> T test(T t){
    return t;
}
```

案例：传入什么类型，返回什么类型：

```java
public class Test {
    public static void main(String[] args) {
        // 传 String，T 就是 String，返回值也是 String
        String string = get("你好");
        // 传 Integer，T 就是 Integer
        Integer i = get(1);
        // 传 Cat，T 就是 Cat
        Cat cat = get(new Cat());
    }

    // <T> 声明这是一个泛型方法，T 只是占位符
    public static <T> T get(T data) {
        return data;
    }
}
class Cat{}
```

设计原则：

- **代码在设计层面越通用越好**：所以会大量使用泛型类、泛型方法、泛型接口；
- **代码在使用层面越精确越好**：使用时一定要明确具体类型。

#### 4.5 泛型限定

- **通配符 `?`**：在"使用泛型"的时候代表一切类型；而 `E、T、K、V` 是在"定义泛型"的时候使用。
- **泛型上限**：`? extends Car` —— `?` 能接收的必须是 `Car` 或其子类。
- **泛型下限**：`? super Car` —— `?` 能接收的必须是 `Car` 或其父类。

```java
public class Test {
    public static void main(String[] args) {
        ArrayList<Car> carsList = new ArrayList<>();
        ArrayList<BENZ> benzsList = new ArrayList<>();
        ArrayList<BMW> bmwsList = new ArrayList<>();
        ArrayList<Fu> fuList = new ArrayList<>();

        // 通配符 ?：可以接收任何类型
        test(carsList);
        test(benzsList);
        test(bmwsList);
        test(fuList);

        // ? extends Car：Car 本身或 Car 的子类
        test1(carsList);
        test1(benzsList);
        test1(bmwsList);
        // test1(fuList); // 报错：Fu 是 Car 的父类

        // ? super Car：Car 本身或 Car 的父类
        test2(carsList);
        // test2(benzsList); // 报错
        // test2(bmwsList);  // 报错
        test2(fuList);
    }

    public static void test(ArrayList<?> list) {}              // 通配符
    public static void test1(ArrayList<? extends Car> list) {} // 上限
    public static void test2(ArrayList<? super Car> list) {}   // 下限
}

class Fu {}
class Car extends Fu {}
class BENZ extends Car {}
class BMW extends Car {}
```

#### 4.6 泛型的擦除与注意事项

- 泛型工作在**编译阶段**：程序编译成 class 文件后，class 文件中就不存在泛型了，这就是**泛型擦除**。
- 理解为：泛型在编译期（写代码时）有效，运行期无效——**面试点**。
- 面试题：构建一个 `ArrayList<String>` 集合，想存入非 String 类型可不可以？（学完反射后可以做到）
- **泛型不支持基本数据类型，只能支持引用数据类型（对象类型）**，所以集合中存整数要用 `ArrayList<Integer>`。

#### 4.7 本章小结

- 模板方法：`final` 模板方法固定流程 + 抽象方法交给子类。
- 内部类重点是**匿名内部类**：`new 接口/抽象类(){ 重写方法 }`，常用于方法形参为接口/抽象类的场景。
- 枚举是常量的集合，构造器私有、不可继承，参数取值受约束。
- 泛型在编译期约束类型，避免强转异常；记住泛型类/接口/方法的声明格式、通配符 `?` 与上下限 `extends`/`super`、泛型擦除。

---

<div style="page-break-after: always;"></div>

## 第十四章 常用 API

### 一、什么是 API

- API（Application Programming Interface）：应用程序编程接口。
- **就是 Java 已经帮我们写好的一些程序（类、方法等），直接拿过来用就可以解决问题。**
- 学习 API 的重点：记住类的作用、构造器和常用方法，查 API 帮助文档掌握用法。

---

### 二、Object 类

#### 2.1 Object 类的作用

Object 是 Java 中所有类的**祖宗类**，Java 中所有类的对象都可以直接使用 Object 提供的方法。

#### 2.2 toString()

- 返回对象的字符串表现形式。
- **toString 存在的意义**：就是为了被子类重写，以便返回对象具体的内容（默认返回 `类名@哈希值`，没有实际意义）。

```java
public class Test {
    public static void main(String[] args) {
        Student student = new Student("小哈", 16);
        String str = student.toString();
        System.out.println(str);
    }
}

class Student {
    private String name;
    private int age;

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // 重写父类的 toString()，返回对象内容
    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```

#### 2.3 equals()

- 默认比较两个对象的**地址**是否相同。
- equals 存在的意义：比较地址完全可以用 `==` 替代，equals 的意义就是被子类重写，由子类定制比较规则（比如比较对象内容）。
- **面试题：`==` 和 `equals` 的区别？** 默认情况下没区别——祖宗类 Object 中 equals 的本质就是 `==`；区别在于 equals 可以被子类重写（如 String 重写后比较内容）。

```java
public class EqualsDemo {
    public static void main(String[] args) {
        Student1 s1 = new Student1("小哈", 18);
        Student1 s2 = new Student1("小哈", 18);
        System.out.println(s1);
        System.out.println(s2);
        System.out.println(s1.equals(s2)); // 重写前 false（地址不同），重写后 true（内容相同）
        System.out.println(s1 == s2);      // 永远 false：new 了两个对象，地址不同
    }
}

class Student1 {
    private String name;
    private int age;

    public Student1(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // 重写 equals：比较两个对象的内容是否一致
    @Override
    public boolean equals(Object o) {
        // 两个对象地址一样，直接返回 true
        if (this == o) return true;
        // 被比较者为 null，或类型不一致，返回 false
        if (o == null || getClass() != o.getClass()) return false;
        // 类型一致，开始比较内容
        Student1 student1 = (Student1) o;
        return age == student1.age && name.equals(student1.name);
    }

    // 重写 hashCode：用对象内容计算哈希值
    @Override
    public int hashCode() {
        int result = Objects.hashCode(name);
        result = 31 * result + age;
        return result;
    }
}
```

**为什么要重写 hashCode？**

- 重写 equals 只是让两个对象在**逻辑层面**一致；
- 重写 hashCode 让两个对象在**物理层面**（哈希值）也一致（HashMap、HashSet 等哈希容器依赖它）。

注意：即使重写了 equals 和 hashCode，`s1 == s2` 仍然是 false——`==` 比较的是堆内存地址，new 出来的两个对象地址不同，重写方法不会改变堆中的地址。

#### 2.4 clone() 对象克隆

对象调用该方法时，会复制一个一模一样的新对象返回。

```java
protected Object clone()
```

使用步骤：类实现 `Cloneable` 标记接口（接口是空的），重写 clone 方法，调用时处理 `CloneNotSupportedException` 异常并强转：

```java
// Cloneable 是空接口，属于标记接口
public class Student implements Cloneable {
    private String name;
    private int age;
    private double[] scores;

    public Student() {
    }

    public Student(String name, int age, double[] scores) {
        this.name = name;
        this.age = age;
        this.scores = scores;
    }

    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    public double[] getScores() {
        return scores;
    }
    public void setScores(double[] scores) {
        this.scores = scores;
    }

    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                ", scores=" + Arrays.toString(scores) +
                '}';
    }

    // 重写克隆方法
    @Override
    protected Object clone() throws CloneNotSupportedException {
        return super.clone();
    }
}
```

```java
public class Test {
    public static void main(String[] args) throws CloneNotSupportedException {
        Student s1 = new Student("小哈", 18, new double[]{118.5, 56});
        System.out.println(s1.getScores());
        // 得到的是 Object 类型，需要强转
        Student cloneStudent = (Student) s1.clone();
        System.out.println(cloneStudent.getName());
        System.out.println(cloneStudent.getAge());
        System.out.println(cloneStudent.getScores());
    }
}
```

**浅克隆与深克隆**：

- **浅克隆**：拷贝出来的对象，其引用类型属性的地址值和源对象一样（**地址一样，名字不一样**）。修改克隆对象的数组内容，源对象会跟着变。
- **深克隆**：拷贝出来的对象，引用类型属性的地址值和源对象不一样（**地址不一样，名字也不一样**）。

浅克隆的问题演示：

```java
public class Test {
    public static void main(String[] args) throws CloneNotSupportedException {
        Student s1 = new Student("小哈", 18, new double[]{118.5, 56});
        Student cloneStudent = (Student) s1.clone();

        // 修改克隆对象的成绩
        double[] scores = cloneStudent.getScores();
        scores[0] = 80;
        cloneStudent.setScores(scores);

        // 浅克隆下：源同学的成绩也变成了 80.0！
        System.out.println("源同学" + s1.getScores()[0]);
        System.out.println("克隆同学" + cloneStudent.getScores()[0]);
    }
}
```

深克隆的实现：在重写的 clone 方法中，对引用类型字段再克隆一次：

```java
@Override
protected Object clone() throws CloneNotSupportedException {
    // 第1步：调用 Object 的 clone() 完成浅克隆（基本类型属性已复制）
    Student student = (Student) super.clone();
    // 第2步：对引用类型字段（scores 数组）单独深克隆
    student.scores = student.scores.clone();
    // 第3步：返回深克隆对象
    return student;
}
```

---

### 三、Objects 工具类

`java.util.Objects` 是**工具类**（Java 7 引入），专门简化对象操作（空判断、相等比较、哈希计算等），核心作用是减少重复代码并**避免空指针异常**。所有方法都是静态方法，无法实例化。

重写 equals 时 IDE 自动生成的代码用的就是 `Objects.equals()`：

```java
@Override
public boolean equals(Object o) {
    if (this == o) return true;
    if (o == null || getClass() != o.getClass()) return false;
    Student1 student1 = (Student1) o;
    return age == student1.age && Objects.equals(name, student1.name);
}
```

`Objects.equals()` 源码：

```java
public static boolean equals(Object a, Object b) {
    return (a == b) || (a != null && a.equals(b));
}
```

#### 3.1 equals(Object a, Object b)

先做非空判断再比较，更安全：

```java
public class Test {
    public static void main(String[] args) {
        String s1 = null;
        String s2 = "itheima";

        // System.out.println(s1.equals(s2)); // 空指针异常 NullPointerException
        System.out.println(Objects.equals(s1, s2)); // false，有 null 也安全
    }
}
```

#### 3.2 isNull(Object obj)

判断对象是否为 null，为 null 返回 true：

```java
String s1 = null;
String s2 = "itheima";
System.out.println(Objects.isNull(s1)); // true
System.out.println(Objects.isNull(s2)); // false
```

#### 3.3 nonNull(Object obj)

判断对象是否不为 null，不为 null 返回 true：

```java
System.out.println(Objects.nonNull(s1)); // false
System.out.println(Objects.nonNull(s2)); // true
```

---

### 四、包装类

#### 4.1 概述

**包装类（Wrapper Class）** 是为 8 种基本数据类型提供的**对象形式封装类**。作用是把基本类型"包装"成对象，以便在需要对象的场景（集合、泛型、反射等）中使用。

```java
// 编译报错：泛型只能用引用类型，不能用基本类型
// ArrayList<int> list = new ArrayList<>();
ArrayList<Integer> list = new ArrayList<>();
```

**8 种基本类型与包装类的对应关系**：

| 基本类型 | 包装类 |
| --- | --- |
| byte | Byte |
| short | Short |
| int | **Integer** |
| long | Long |
| float | Float |
| double | Double |
| char | **Character** |
| boolean | Boolean |

#### 4.2 装箱与拆箱（重点）

Java 5 引入了**自动装箱**和**自动拆箱**：

- **自动装箱**：基本类型自动转为包装类对象（如 `int` → `Integer`）；
- **自动拆箱**：包装类对象自动转为基本类型（如 `Integer` → `int`）。

```java
public class Test {
    public static void main(String[] args) {
        // Integer a1 = new Integer(12); // 已过时，报错
        Integer a2 = Integer.valueOf(12); // 官方推荐
        System.out.println(a2);

        Integer a3 = 18;  // 自动装箱
        int a4 = a3;      // 自动拆箱

        ArrayList<Double> list = new ArrayList<>();
        list.add(1.0);              // 自动装箱
        double rel1 = list.get(0);  // 自动拆箱
    }
}
```

#### 4.3 包装类的常见操作

##### （1）基本类型转字符串

```java
public static String toString(double d)
public String toString()
```

```java
public class Test2 {
    public static void main(String[] args) {
        int a1 = 12;
        Integer a2 = a1;                 // 自动装箱
        String a3 = a2.toString();       // 包装类对象转字符串
        // String a4 = a1.toString();    // 报错：基本类型没有方法
        String a4 = Integer.toString(a1); // 静态方法，基本类型直接转
        System.out.println(a3);
        System.out.println(a4);
    }
}
```

##### （2）字符串类型的数值转成对应数值类型

```java
public static int parseInt(String s)
public static Integer valueOf(String s)
```

```java
public class Test2 {
    public static void main(String[] args) {
        String str = "129";
        int age1 = Integer.parseInt(str);
        System.out.println(age1 + 1);     // 130

        int age2 = Integer.valueOf(str);  // 自动拆箱
        System.out.println(age2 + 1);     // 130

        String str2 = "12.8";
        double age3 = Double.parseDouble(str2);
        System.out.println(age3 + 0.5);   // 13.3

        double age4 = Double.valueOf(str2);
        System.out.println(age4 + 0.5);   // 13.3
    }
}
```

---

### 五、StringBuilder

#### 5.1 概述

- StringBuilder 代表**可变字符串对象**，相当于一个容器，里面装的字符串可以改变，专门用来操作字符串。
- **好处**：比 String 更适合做字符串修改操作，**效率更高、代码更简洁**。

#### 5.2 构造器和常用方法

```java
public class Test {
    public static void main(String[] args) {
        // 构造器
        StringBuilder s1 = new StringBuilder();          // 空白可变字符串
        StringBuilder s2 = new StringBuilder("小哈呀！"); // 指定内容

        // append：拼接内容，返回对象本身，可以添加任何数据
        s2.append(12);
        s2.append("黑马");
        s2.append(true);
        // 支持链式编程
        s2.append(666).append("传智教育").append("双击");
        System.out.println(s2);

        // reverse：翻转
        s2.reverse();
        System.out.println(s2);

        // length：长度
        System.out.println(s2.length());

        // toString：转成 String
        String res = s2.reverse().toString();
        System.out.println(res);
    }
}
```

#### 5.3 StringBuilder 和 String 的区别

- 频繁拼接、修改字符串时用 StringBuilder，效率更高；
- 操作少、不需要修改、只是定义字符串变量时，还是用 String。

效率对比（String 拼接百万次明显卡顿，StringBuilder 很快）：

```java
public class Test1 {
    public static void main(String[] args) {
        String res = "";
        for (int i = 0; i < 1000000; i++) {
            res = res + "ABC";   // 每次都产生新字符串对象
        }
        System.out.println(res);

        StringBuilder sb = new StringBuilder();
        for (int i = 1; i < 1000000; i++) {
            sb.append("ABC");    // 直接在容器中追加
        }
        System.out.println(sb);
    }
}
```

#### 5.4 StringBuffer 与 StringBuilder

- StringBuffer 用法与 StringBuilder 一模一样；
- **StringBuilder 线程不安全，StringBuffer 线程安全**（方法加了 synchronized）；
- 不考虑多线程同时操作数据时用 StringBuilder（更快），考虑线程安全时用 StringBuffer。

#### 5.5 案例：数组转字符串

需求：返回任意整型数组的内容，格式如 `[11,22,33]`。

```java
public class Test3 {
    public static void main(String[] args) {
        System.out.println(getArrayData(new int[]{11, 22, 33, 44, 55, 66}));
    }

    public static String getArrayData(int[] arr) {
        if (arr == null || arr.length == 0) {
            return null;
        }
        StringBuilder sb = new StringBuilder();
        sb.append("[");
        for (int i = 0; i < arr.length; i++) {
            if (i == arr.length - 1) {
                sb.append(arr[i]);
            } else {
                sb.append(arr[i]).append(",");
            }
        }
        sb.append("]");
        return sb.toString();
    }
}
```

---

### 六、StringJoiner

JDK 8 开始提供，和 StringBuilder 一样是可变字符串容器；**好处是代码更简洁**，拼接时自动处理分隔符和前后缀。

构造器：`new StringJoiner(分隔符, 前缀, 后缀)`

```java
import java.util.StringJoiner;

public class Test {
    public static void main(String[] args) {
        StringJoiner sj = new StringJoiner(",", "[", "]");
        sj.add("java");
        sj.add("AI");
        sj.add("鸿蒙");
        System.out.println(sj); // [java,AI,鸿蒙]
    }
}
```

数组转字符串案例（对比 StringBuilder 更简洁）：

```java
public class Test2 {
    public static void main(String[] args) {
        System.out.println(getArrayData(new int[]{11, 22, 33, 44, 55, 66}));
    }

    public static String getArrayData(int[] arr) {
        if (arr == null || arr.length == 0) {
            return null;
        }
        StringJoiner sj = new StringJoiner(",", "[", "]");
        for (int i = 0; i < arr.length; i++) {
            sj.add(arr[i] + ""); // add 接收字符串，需要转换
        }
        return sj.toString();
    }
}
```

---

### 七、Math、System、Runtime

#### 7.1 Math

数学工具类，方法都是静态方法：

```java
public class Test {
    public static void main(String[] args) {
        System.out.println(Math.abs(-18));     // 绝对值：18
        System.out.println(Math.abs(-3.14));   // 3.14

        System.out.println(Math.ceil(5.0000001)); // 向上取整：6.0
        System.out.println(Math.ceil(5.0));       // 5.0

        System.out.println(Math.floor(4.99999)); // 向下取整：4.0
        System.out.println(Math.floor(4.0));     // 4.0

        System.out.println(Math.round(4.345)); // 四舍五入：4
        System.out.println(Math.round(3.514)); // 4

        System.out.println(Math.max(10, 20)); // 较大值：20
        System.out.println(Math.min(10, 20)); // 较小值：10

        System.out.println(Math.pow(2, 3)); // 2的3次方：8.0

        System.out.println(Math.random()); // [0.0, 1.0) 随机数，包前不包后
    }
}
```

#### 7.2 System

代表程序所在系统的工具类：

```java
public class Test1 {
    public static void main(String[] args) {
        // System.exit(0); // 终止 JVM，非 0 状态码表示异常终止（不建议使用）

        // 当前时间毫秒值：从 1970-01-01 00:00:00 到此刻的总毫秒数，1s = 1000ms
        long time = System.currentTimeMillis();
        System.out.println(time);

        for (int i = 0; i < 1000000; i++) {
            System.out.print("输出了" + i + "次：");
        }

        // 统计程序执行耗时（性能分析）
        long time2 = System.currentTimeMillis();
        System.out.println((time2 - time) / 1000 + "s");
    }
}
```

**时间毫秒值为什么从 1970 年 1 月 1 日开始？** 1969 年贝尔实验室的肯·汤普逊在开发 UNIX 时以 1970-01-01 作为时间起点，这一天也被算作 C 语言的生日，之后成为行业惯例。

#### 7.3 Runtime

代表程序所在的运行环境，是一个**单例类**：

```java
public class Test2 {
    public static void main(String[] args) throws IOException {
        // 获取与当前 Java 应用关联的运行时对象
        Runtime r = Runtime.getRuntime();

        // JVM 可用处理器数
        System.out.println(r.availableProcessors());

        // JVM 最大内存总量
        System.out.println(r.maxMemory() / 1024.0 / 1024.0 + "MB");

        // JVM 空闲内存
        System.out.println(r.freeMemory() / 1024.0 / 1024.0 + "MB");

        // 启动某个程序，返回代表该程序的 Process 对象（需处理异常）
        Process process = r.exec("D:\\soft\\Doubao\\Doubao.exe");
    }
}
```

---

### 八、BigDecimal

用于解决浮点型运算结果失真的问题：

```java
System.out.println(0.1 + 0.2);      // 0.30000000000000004
System.out.println(1.0 - 0.32);     // 0.6799999999999999
System.out.println(1.015 * 100);    // 101.49999999999999
System.out.println(1.301 / 100);    // 0.013009999999999999
```

正确用法：

```java
import java.math.BigDecimal;
import java.math.RoundingMode;

public class Test {
    public static void main(String[] args) {
        double a = 0.1;
        double b = 0.2;

        // 注意：new BigDecimal(double) 无法精确计算，不推荐
        // new BigDecimal(Double.toString(a)) 可以，但下面的方式最好
        BigDecimal a1 = BigDecimal.valueOf(a);
        BigDecimal b1 = BigDecimal.valueOf(b);

        BigDecimal c1 = a1.add(b1);           // 加
        System.out.println(c1);               // 0.3

        BigDecimal c2 = a1.subtract(b1);      // 减
        BigDecimal c3 = a1.multiply(b1);      // 乘
        BigDecimal c4 = a1.divide(b1);        // 除（能除尽时）

        // 除不尽时必须指定精度和舍入模式，否则抛 ArithmeticException
        BigDecimal d1 = BigDecimal.valueOf(0.1);
        BigDecimal d2 = BigDecimal.valueOf(0.3);
        BigDecimal d3 = d1.divide(d2, 2, RoundingMode.HALF_UP); // 保留2位，四舍五入
        System.out.println(d3); // 0.33

        // 转回 double
        double db1 = d3.doubleValue();
        System.out.println(db1);
    }
}
```

要点：

- 创建对象用 `BigDecimal.valueOf(double)`，不要用 `new BigDecimal(double)`；
- 除法除不尽时用 `divide(对象, 保留位数, 舍入模式)`，`RoundingMode.HALF_UP` 表示四舍五入；
- 运算完可用 `doubleValue()` 转回基本类型。

---

### 九、JDK8 之前传统的日期、时间

#### 9.1 Date

代表日期和时间：

```java
import java.util.Date;

public class Test {
    public static void main(String[] args) {
        Date d = new Date();      // 无参构造：系统当前时间
        System.out.println(d);

        long time = d.getTime();  // 拿到时间毫秒值
        System.out.println(time);

        // 有参构造：时间毫秒值转日期对象（如 2 秒后的时间）
        time += 2 * 1000;
        Date d2 = new Date(time);
        System.out.println(d2);

        // setTime：修改日期对象的时间
        Date d3 = new Date();
        d3.setTime(time);
        System.out.println(d3);
    }
}
```

#### 9.2 SimpleDateFormat 简单日期格式化

用来把日期对象、时间毫秒值格式化成想要的字符串形式，也能把字符串时间解析回日期对象。

常用模式字母：`yyyy` 年、`MM` 月、`dd` 日、`HH` 时（24小时制）、`mm` 分、`ss` 秒、`a` 上午/下午。

```java
import java.text.SimpleDateFormat;
import java.util.Date;

public class Test {
    public static void main(String[] args) {
        Date d = new Date();
        long time = d.getTime();

        // 创建格式化对象并指定格式
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss a");

        // format：格式化日期对象 / 时间毫秒值
        String res = sdf.format(d);
        System.out.println(res);
        String res1 = sdf.format(time);
        System.out.println(res1);
    }
}
```

解析字符串时间为日期对象（`parse` 方法，模式必须与字符串完全一致）：

```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class Test1 {
    public static void main(String[] args) throws ParseException {
        String dateStr = "2025-12-12 12:12:12";
        // 格式必须与被解析的时间一模一样，否则出 bug
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
        Date d2 = sdf.parse(dateStr); // 注意导包和异常处理
        System.out.println(d2);
    }
}
```

**秒杀案例**：判断下单时间是否在秒杀时间段内：

```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class Test2 {
    public static void main(String[] args) throws ParseException {
        String start = "2025年11月26日 0:0:0";
        String end = "2025年11月26日 0:10:0";
        String xj = "2025年11月26日 0:01:09";
        String xp = "2025年11月26日 0:10:01";

        SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 HH:mm:ss");
        Date startDt = sdf.parse(start);
        Date endDt = sdf.parse(end);
        Date xjDt = sdf.parse(xj);
        Date xpDt = sdf.parse(xp);

        // 统一转毫秒值比较大小
        long starTime = startDt.getTime();
        long endTime = endDt.getTime();
        long xjTime = xjDt.getTime();
        long xpTime = xpDt.getTime();

        if (xjTime >= starTime && xjTime <= endTime) {
            System.out.println("小贾秒杀成功了！！！");
        } else {
            System.out.println("小贾秒杀失败！！！");
        }

        if (xpTime >= starTime && xpTime <= endTime) {
            System.out.println("小皮秒杀成功了！！！");
        } else {
            System.out.println("小皮秒杀失败！！！");
        }
    }
}
```

#### 9.3 Calendar 日历类

Calendar 表示日历，提供了直接对年、月、日、时、分、秒进行运算的方法，比 Date 方便。**注意：Calendar 是可变对象，修改后对象本身表示的时间会变化。**

```java
import java.util.Calendar;
import java.util.Date;

public class Test3 {
    public static void main(String[] args) {
        // 1、得到系统此刻时间对应的日历对象
        Calendar now = Calendar.getInstance();
        System.out.println(now);

        // 2、获取日历中的某个信息
        int year = now.get(Calendar.YEAR);
        System.out.println("年份：" + year);
        int days = now.get(Calendar.DAY_OF_YEAR);
        System.out.println("一年中的第：" + days);

        // 3、拿到日历中记录的日期对象
        Date d = now.getTime();
        System.out.println("日期:" + d);

        // 4、拿到时间毫秒值
        long time = now.getTimeInMillis();
        System.out.println("时间毫秒值:" + time);

        // 5、修改日历中的某个信息
        now.set(Calendar.MONTH, 9);        // 修改月份为 10 月
        now.set(Calendar.DAY_OF_YEAR, 125); // 修改为一年中的第 125 天

        // 6、为某个信息增加或减少多少
        now.add(Calendar.DAY_OF_YEAR, 100);
        now.add(Calendar.DAY_OF_YEAR, -10);
        now.add(Calendar.DAY_OF_MONTH, 6);
        now.add(Calendar.HOUR, 12);
        System.out.println(now);
    }
}
```

---

### 十、JDK8 新增的日期、时间类

#### 10.1 为什么要新增

传统时间类（Date、SimpleDateFormat、Calendar）的问题：

- 设计不合理，使用不方便，很多方法已被淘汰；
- 都是**可变对象**，修改后会丢失最开始的时间信息；
- **线程不安全**；
- 只能精确到毫秒，不能精确到纳秒。

JDK8 新增的日期类划分更细致：`LocalDate`（年月日）、`LocalTime`（时分秒）、`LocalDateTime`（年月日时分秒），还有时区、时间间隔等类，几乎所有操作都有 API 方法，且都是**不可变对象、线程安全、可精确到纳秒**。

时间单位换算：1 秒 = 1000 毫秒；1 毫秒 = 1000 微秒；1 微秒 = 1000 纳秒；即 1 秒 = 1,000,000,000 纳秒。

#### 10.2 LocalDate（本地日期：年、月、日、星期）

```java
import java.time.LocalDate;

public class Test_LocalDate {
    public static void main(String[] args) {
        // 0、获取本地日期对象（不可变）
        LocalDate ld = LocalDate.now();
        System.out.println(ld);

        // 1、获取日期信息
        int year = ld.getYear();                  // 年
        int month = ld.getMonthValue();           // 月
        int day = ld.getDayOfMonth();             // 日
        int dayOfYear = ld.getDayOfYear();        // 一年中第几天
        int dayOfWeek = ld.getDayOfWeek().getValue(); // 星期几

        // 2、修改某个信息：withXxx 返回新对象，原对象不变
        LocalDate ld2 = ld.withYear(2099);
        LocalDate ld3 = ld.withMonth(3);
        LocalDate ld4 = ld.withDayOfMonth(12);
        LocalDate ld5 = ld.withDayOfYear(100);

        // 3、加多少：plusXxx
        LocalDate ld6 = ld.plusYears(2);
        LocalDate ld7 = ld.plusMonths(2);
        LocalDate ld8 = ld.plusDays(2);
        LocalDate ld9 = ld.plusWeeks(2);

        // 4、减多少：minusXxx
        LocalDate ld10 = ld.minusYears(2);
        LocalDate ld11 = ld.minusMonths(2);

        // 5、获取指定日期对象
        LocalDate ld12 = LocalDate.of(2099, 12, 12);

        // 6、比较：equals / isBefore / isAfter
        System.out.println(ld12.equals(ld11));
        System.out.println(ld12.isBefore(ld9));
        System.out.println(ld12.isAfter(ld9));
    }
}
```

#### 10.3 LocalTime（本地时间：时、分、秒、纳秒）

方法体系与 LocalDate 一致：

```java
import java.time.LocalTime;

public class Test2_LocalTime {
    public static void main(String[] args) {
        LocalTime lt = LocalTime.now(); // 不可变

        // 1、获取信息
        int hour = lt.getHour();
        int minute = lt.getMinute();
        int second = lt.getSecond();
        int nano = lt.getNano();

        // 2、修改：withHour / withMinute / withSecond / withNano
        LocalTime lt3 = lt.withHour(10);
        LocalTime lt4 = lt.withMinute(10);
        LocalTime lt5 = lt.withSecond(10);
        LocalTime lt6 = lt.withNano(10);

        // 3、加：plusHours / plusMinutes / plusSeconds / plusNanos
        LocalTime lt7 = lt.plusHours(10);

        // 4、减：minusHours / minusMinutes / minusSeconds / minusNanos
        LocalTime lt11 = lt.minusHours(10);

        // 5、指定时间
        LocalTime lt15 = LocalTime.of(12, 12, 12);
        LocalTime lt16 = LocalTime.of(12, 12, 12);

        // 6、比较
        System.out.println(lt15.equals(lt16)); // true
        System.out.println(lt15.isAfter(lt));  // false
        System.out.println(lt15.isBefore(lt)); // true
    }
}
```

#### 10.4 LocalDateTime（本地日期 + 时间）

```java
import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.LocalTime;

public class Test3_LocalDateTime {
    public static void main(String[] args) {
        // 0、获取本地日期时间对象
        LocalDateTime ldt = LocalDateTime.now();

        // 1、获取全部信息
        int year = ldt.getYear();
        int month = ldt.getMonthValue();
        int day = ldt.getDayOfMonth();
        int dayOfYear = ldt.getDayOfYear();
        int dayOfWeek = ldt.getDayOfWeek().getValue();
        int hour = ldt.getHour();
        int minute = ldt.getMinute();
        int second = ldt.getSecond();
        int nano = ldt.getNano();

        // 2、修改：withYear / withMonth / withDayOfMonth / withHour / withMinute ...
        LocalDateTime ldt2 = ldt.withYear(2029);
        LocalDateTime ldt3 = ldt.withMinute(59);

        // 3、加：plusYears / plusMonths / plusDays / plusHours / plusMinutes ...
        LocalDateTime ldt4 = ldt.plusYears(2);
        LocalDateTime ldt5 = ldt.plusMinutes(3);

        // 4、减：minusYears / minusMonths / minusDays / minusMinutes ...
        LocalDateTime ldt6 = ldt.minusYears(2);
        LocalDateTime ldt7 = ldt.minusMinutes(3);

        // 5、指定日期时间
        LocalDateTime ldt8 = LocalDateTime.of(2029, 12, 12, 12, 12, 12, 1222);

        // 6、比较：equals / isBefore / isAfter
        System.out.println(ldt8.isAfter(ldt));

        // 7、与 LocalDate / LocalTime 互转
        LocalDate ld = ldt.toLocalDate();
        LocalTime lt = ldt.toLocalTime();
        LocalDateTime ldt10 = LocalDateTime.of(ld, lt);
    }
}
```

#### 10.5 ZoneId、ZonedDateTime（时区）

```java
import java.time.Clock;
import java.time.ZoneId;
import java.time.ZonedDateTime;
import java.util.Set;

public class Test4_ZoneId_ZonedDateTime {
    public static void main(String[] args) {
        // 系统默认时区
        ZoneId zoneId = ZoneId.systemDefault();
        System.out.println(zoneId.getId());

        // Java 支持的全部时区 Id
        Set<String> zoneIds = ZoneId.getAvailableZoneIds();
        System.out.println(zoneIds);

        // 把时区 id 封装成 ZoneId 对象
        ZoneId zoneId1 = ZoneId.of("America/New_York");

        // 获取某个时区的带时区时间对象
        ZonedDateTime now = ZonedDateTime.now(zoneId1);
        System.out.println(now);

        // 世界标准时间 UTC
        ZonedDateTime now1 = ZonedDateTime.now(Clock.systemUTC());
        System.out.println(now1);

        // 系统默认时区的带时区时间
        ZonedDateTime now2 = ZonedDateTime.now();
        System.out.println(now2);
    }
}
```

ZonedDateTime 的常用方法与 LocalDateTime 差不多。

#### 10.6 Instant（时间戳，推荐代替 Date）

- 时间由两部分组成：从 1970-01-01 00:00:00 开始的**总秒数** + 不够 1 秒的**纳秒数**。
- 作用：记录代码执行时间、记录用户操作的时间点。
- 对比 Date：Date 只能精确到毫秒且可变；Instant 可精确到纳秒且不可变，**推荐用 Instant 代替 Date**。

```java
import java.time.Instant;

public class Test5_Instant {
    public static void main(String[] args) {
        // 1、获取此刻时间（不可变对象）
        Instant now = Instant.now();

        // 2、总秒数
        long second = now.getEpochSecond();
        System.out.println(second);

        // 3、不够 1 秒的纳秒数
        int nano = now.getNano();
        System.out.println(nano);

        System.out.println(now);

        Instant instant = now.plusNanos(111);

        // 典型用途：性能分析
        Instant now1 = Instant.now();
        // 代码执行...
        Instant now2 = Instant.now();
    }
}
```

#### 10.7 DateTimeFormatter（日期格式化器，代替 SimpleDateFormat）

```java
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

public class Test6_DateTimeFormatter {
    public static void main(String[] args) {
        // 1、创建格式化器
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy年MM月dd日 HH:mm:ss");

        // 2、正向格式化：formatter.format(时间对象)
        LocalDateTime now = LocalDateTime.now();
        String rs = formatter.format(now);
        System.out.println(rs);

        // 3、反向格式化：时间对象.format(formatter)
        String rs2 = now.format(formatter);
        System.out.println(rs2);

        // 4、解析：格式必须与字符串一致
        String dateStr = "2029年12月12日 12:12:11";
        LocalDateTime ldt = LocalDateTime.parse(dateStr, formatter);
        System.out.println(ldt);
    }
}
```

#### 10.8 Period、Duration（时间间隔）

**Period**：计算两个 `LocalDate` 相差的年数、月数、天数：

```java
import java.time.LocalDate;
import java.time.Period;

public class Test7_Period {
    public static void main(String[] args) {
        LocalDate start = LocalDate.of(2029, 8, 10);
        LocalDate end = LocalDate.of(2029, 12, 15);

        Period period = Period.between(start, end);
        System.out.println(period.getYears());   // 相差年
        System.out.println(period.getMonths());  // 相差月
        System.out.println(period.getDays());    // 相差天
    }
}
```

**Duration**：计算两个时间对象相差的天、时、分、秒、纳秒，支持 LocalTime、LocalDateTime、Instant：

```java
import java.time.Duration;
import java.time.LocalDateTime;

public class Test8_Duration {
    public static void main(String[] args) {
        LocalDateTime start = LocalDateTime.of(2025, 11, 11, 11, 10, 10);
        LocalDateTime end = LocalDateTime.of(2025, 11, 11, 11, 11, 11);

        Duration duration = Duration.between(start, end);
        System.out.println(duration.toDays());    // 间隔天
        System.out.println(duration.toHours());   // 间隔小时
        System.out.println(duration.toMinutes()); // 间隔分
        System.out.println(duration.toSeconds()); // 间隔秒
        System.out.println(duration.toMillis());  // 间隔毫秒
        System.out.println(duration.toNanos());   // 间隔纳秒
    }
}
```

---

### 本章小结

- **Object**：所有类的父类；重点掌握 `toString()`（重写返回内容）、`equals()`（重写比较内容，配合 `hashCode()`）、`clone()`（浅克隆与深克隆的区别）。
- **Objects**：静态工具类，`equals` 防空指针、`isNull`/`nonNull` 判空。
- **包装类**：8 种基本类型的对象形式；自动装箱/拆箱；`parseXxx` 字符串转数值、`toString` 数值转字符串。
- **字符串操作**：频繁修改用 StringBuilder（线程不安全、快），线程安全用 StringBuffer；JDK8 拼接分隔内容用 StringJoiner 更简洁。
- **工具类**：Math（数学运算）、System（`currentTimeMillis` 计时）、Runtime（单例，运行环境信息）。
- **BigDecimal**：解决浮点失真；用 `valueOf` 创建，除法除不尽要指定精度和舍入模式。
- **传统日期**：Date + SimpleDateFormat（格式化/解析）+ Calendar（日历运算），可变、线程不安全。
- **JDK8 新日期**：LocalDate/LocalTime/LocalDateTime（不可变）、Instant（纳秒时间戳）、DateTimeFormatter（线程安全格式化）、Period/Duration（日期间隔/时间间隔），开发中优先使用新 API。

---

<div style="page-break-after: always;"></div>

## 第十五章 常见API、Lambda表达式、常见算法与正则表达式

本章包含四部分内容：

1. **Arrays 工具类**：数组操作与对象排序（Comparable 与 Comparator 两种方案）；
2. **Lambda 表达式与方法引用**：JDK 8 新增的语法简化手段；
3. **常见算法**：冒泡排序、选择排序、二分查找；
4. **正则表达式**：校验、提取、替换、分割文本。

---

### 一、Arrays 类

`Arrays` 是用来操作数组的工具类，位于 `java.util` 包下。

#### 1.1 常用基本方法

| 方法 | 作用 |
| --- | --- |
| `public static String toString(类型[] arr)` | 返回数组的内容字符串 |
| `public static 类型[] copyOfRange(类型[] arr, int from, int to)` | 拷贝数组（指定范围，**包前不包后**） |
| `public static 类型[] copyOf(类型[] arr, int newLength)` | 拷贝数组，可指定新数组长度 |
| `public static void setAll(类型[] array, XxxFunction generator)` | 把数组中的原数据改为新数据再存进去 |
| `public static void sort(类型[] arr)` | 对数组排序（默认升序） |

基本使用示例：

```java
public class ArraysDemo {
    public static void main(String[] args) {
        int[] arr = {22, 56, 89, 45, 35, 98, 65, 38};

        // 1、toString：返回数组内容
        System.out.println(Arrays.toString(arr));

        // 2、copyOfRange：拷贝指定范围（包前不包后，即索引 2、3、4）
        int[] arr2 = Arrays.copyOfRange(arr, 2, 5);
        System.out.println(Arrays.toString(arr2));

        // 3、copyOf：拷贝并指定新数组长度（多出的位置填默认值）
        int[] arr3 = Arrays.copyOf(arr, 10);
        System.out.println(Arrays.toString(arr3));

        // 4、setAll：按规则修改数组元素（示例：全部打 8 折，保留 2 位小数）
        double[] prices = {99.5, 80, 128};
        Arrays.setAll(prices, new IntToDoubleFunction() {
            @Override
            public double applyAsDouble(int value) {
                // value 是数组的索引：0、1、2
                BigDecimal price = BigDecimal.valueOf(prices[value]);
                BigDecimal discount = BigDecimal.valueOf(0.8);
                BigDecimal res = price.multiply(discount).setScale(2, BigDecimal.ROUND_HALF_UP);
                return res.doubleValue();
            }
        });
        System.out.println(Arrays.toString(prices));

        // 5、sort：排序（默认升序）
        Arrays.sort(arr);
        System.out.println(Arrays.toString(arr));
    }
}
```

> 注意：金额等小数运算不要直接用 `double` 乘除，应使用 `BigDecimal` 保证精度。

#### 1.2 对象排序：Comparable 接口

直接使用 `Arrays.sort()` 给对象数组排序会报 **类型转换异常**：`Student cannot be cast to Comparable`。

原因：`sort` 方法不知道对象之间"谁大谁小"，要求元素必须实现 `Comparable` 接口，自己定义比较规则。

```java
public class Student {
    private String name;
    private int age;
    private double height;

    public Student() {
    }

    public Student(String name, int age, double height) {
        this.name = name;
        this.age = age;
        this.height = height;
    }

    // getter / setter 省略

    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                ", height=" + height +
                '}';
    }
}
```

让类实现 `Comparable<T>` 接口（泛型接口，需指定泛型类型），重写 `compareTo` 方法：

```java
public class Student implements Comparable<Student> {
    private String name;
    private int age;
    private double height;

    /* 构造器、getter/setter、toString 省略 */

    @Override
    public int compareTo(Student o) {
        // 比较的两个对象：this（对比者） 和 o（被对比者）
        // 约定1：左边大于右边 返回正数
        // 约定2：左边小于右边 返回负数
        // 约定3：左边等于右边 返回 0（保持初始顺序）
        // return this.age - o.age;   // 升序
        return o.age - this.age;     // 降序
    }
}
```

返回值约定（以 `Integer.compare(o1, o2)` 为例）：

| 返回值 | 含义 | 排序结果 | 举例（o1=18, o2=20） |
| --- | --- | --- | --- |
| 负数 | o1 < o2 | o1 排在 o2 前面 | `Integer.compare(18, 20)` → -2（升序） |
| 0 | o1 == o2 | 两者位置不变 | `Integer.compare(20, 20)` → 0 |
| 正数 | o1 > o2 | o1 排在 o2 后面 | `Integer.compare(22, 20)` → 2（降序） |

#### 1.3 对象排序：Comparator 排序器（推荐）

`Comparable` 方案的缺点：排序规则写死在类里面，升序降序只能二选一，不同使用方无法各用各的规则。

更灵活的方案：使用 `Arrays.sort(arr, Comparator)` 两参数方法，传入一个 `Comparator` 排序器对象。**此时实体类不需要实现任何接口。**

```java
public class ArraysDemo2 {
    public static void main(String[] args) {
        Student s1 = new Student("小哈", 36, 1.70);
        Student s2 = new Student("小米", 18, 1.85);
        Student s3 = new Student("小蒙", 28, 1.75);
        Student s4 = new Student("小刘", 18, 1.65);
        Student[] students = {s1, s2, s3, s4};

        // 写法1：匿名内部类直接作为参数
        Arrays.sort(students, new Comparator<Student>() {
            @Override
            public int compare(Student o1, Student o2) {
                // return o1.getAge() - o2.getAge();                 // 升序
                // return Integer.compare(o1.getAge(), o2.getAge()); // 升序（推荐写法）
                // return o2.getAge() - o1.getAge();                 // 降序
                return Integer.compare(o2.getAge(), o1.getAge());    // 降序（推荐写法）
            }
        });
        System.out.println(Arrays.toString(students));

        // 写法2：用变量把排序器存起来再传入
        Comparator<Student> comparator = new Comparator<Student>() {
            @Override
            public int compare(Student o1, Student o2) {
                return o1.getAge() - o2.getAge();   // 升序
            }
        };
        Arrays.sort(students, comparator);
        System.out.println(Arrays.toString(students));
    }
}
```

#### 1.4 包装类的 compare 静态方法

比较 `double` 等小数时不能直接相减转 int（会丢精度），Java 为所有基本类型包装类提供了静态 `compare()` 方法：

- `Integer.compare(int a, int b)`：比较两个 int；
- `Double.compare(double a, double b)`：比较两个 double；
- `Long.compare(long a, long b)`：比较两个 long；
- `Float.compare(float a, float b)`：比较两个 float。

返回值规则同样是：负数表示 a < b，0 表示相等，正数表示 a > b。

```java
public class CompareData {
    // 年龄升序
    public static int compareByAsc(Student o1, Student o2) {
        return Integer.compare(o1.getAge(), o2.getAge());
    }

    // 年龄降序
    public static int compareByDesc(Student o1, Student o2) {
        return Integer.compare(o2.getAge(), o1.getAge());
    }

    // 身高升序（double 必须用 Double.compare）
    public static int compareByHeightAsc(Student o1, Student o2) {
        return Double.compare(o1.getHeight(), o2.getHeight());
    }

    // 身高降序
    public static int compareByHeightDesc(Student o1, Student o2) {
        return Double.compare(o2.getHeight(), o1.getHeight());
    }
}
```

不使用 `compare` 时，需要手动判断并返回值：

```java
public class CompareByHeight {
    // 身高升序
    public static int compareByAsc(Student o1, Student o2) {
        if (o1.getHeight() > o2.getHeight()) {
            return 1;
        } else if (o1.getHeight() == o2.getHeight()) {
            return 0;
        } else {
            return -1;
        }
    }

    // 身高降序
    public static int compareByDesc(Student o1, Student o2) {
        if (o1.getHeight() < o2.getHeight()) {
            return 1;
        } else if (o1.getHeight() == o2.getHeight()) {
            return 0;
        } else {
            return -1;
        }
    }
}
```

#### 1.5 小结

- 基本类型数组排序直接用 `Arrays.sort(arr)`；
- 对象排序两种方式：类实现 `Comparable` 接口（规则固定在类上），或调用时传入 `Comparator` 排序器（规则灵活，推荐）；
- 小数比较用包装类的 `compare` 方法，不要直接相减。

---

### 二、Lambda 表达式

#### 2.1 概述与作用

- Lambda 表达式是 **JDK 8** 开始新增的语法形式；
- **作用：简化匿名内部类的代码写法**；
- 注意：Lambda **只能简化函数式接口的匿名内部类**。

#### 2.2 使用条件

- 必须是一个 **接口**；
- 接口中 **只有一个抽象方法**（函数式接口）。

#### 2.3 格式

```java
(被重写方法的形参列表) -> {
    被重写方法的方法体代码;
}
```

- `()` 对应接口中唯一抽象方法的形参列表；
- `->` 是箭头运算符；
- `{}` 是方法体。

无参无返回值示例：

```java
public interface Swimming {
    void swim();
}
```

```java
public class Test {
    public static void main(String[] args) {
        // 匿名内部类写法
        // Swimming swimming = new Swimming() {
        //     @Override
        //     public void swim() {
        //         System.out.println("正在游泳~~~");
        //     }
        // };

        // Lambda 写法
        Swimming swimming = () -> {
            System.out.println("正在游泳~~~");
        };
        swimming.swim();
    }
}
```

有参有返回值示例：

```java
public interface Swimming {
    String swim(String name);
}
```

```java
public class Test {
    public static void main(String[] args) {
        Swimming swimming = (String name) -> {
            return name + "，在游泳~~~";
        };
        System.out.println(swimming.swim("小猫"));
    }
}
```

#### 2.4 省略写法（进一步简化）

1. **参数类型可以省略**；
2. 如果只有一个参数，参数类型省略后 `()` 也可以省略；
3. 如果方法体只有一行代码，可以省略 `{}` 和分号；若这行是 `return` 语句，`return` 也必须去掉。

```java
public class Test {
    public static void main(String[] args) {
        Swimming swimming = name -> name + "，在游泳~~~";
        System.out.println(swimming.swim("小猫"));
    }
}
```

#### 2.5 案例：setAll 打 8 折

```java
public class Test1 {
    public static void main(String[] args) {
        double[] prices = {99.5, 80, 128};

        // 匿名内部类写法
        Arrays.setAll(prices, new IntToDoubleFunction() {
            @Override
            public double applyAsDouble(int value) {
                return prices[value] * 0.8;
            }
        });

        // Lambda 简写
        Arrays.setAll(prices, value -> prices[value] * 0.8);

        System.out.println(Arrays.toString(prices));
    }
}
```

---

### 三、方法引用

方法引用是 **进一步简化 Lambda 表达式** 的语法，标志性符号是 **`::`**。

> 所有简化语法都有前提条件，遇到符合条件的场景再用；不用也完全可以，效果与普通写法一致，不需要刻意使用。

#### 3.1 静态方法引用

**语法：**

```java
类名::静态方法
```

`::` 左侧是静态方法所在的类名，右侧是静态方法名（不需要括号和参数）。

**使用场景：** Lambda 表达式里只是调用一个静态方法，并且前后参数的形式一致。

```java
public class CompareByData {
    // 升序静态方法
    public static int compareByAsc(Student o1, Student o2) {
        return o1.getAge() - o2.getAge();
    }

    // 降序静态方法
    public static int compareByDesc(Student o1, Student o2) {
        return o2.getAge() - o1.getAge();
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Student s1 = new Student("小哈", 18, 1.70);
        Student s3 = new Student("李伟", 28, 1.76);
        Student s2 = new Student("小米", 18, 1.85);
        Student s4 = new Student("张三", 38, 1.70);
        Student[] students = new Student[]{s1, s3, s2, s4};

        // 演进过程：
        // 1) 匿名内部类
        Arrays.sort(students, new Comparator<Student>() {
            @Override
            public int compare(Student o1, Student o2) {
                return o1.getAge() - o2.getAge();
            }
        });
        // 2) Lambda 完整版
        Arrays.sort(students, (o1, o2) -> { return o1.getAge() - o2.getAge(); });
        // 3) Lambda 省略版
        Arrays.sort(students, (o1, o2) -> o1.getAge() - o2.getAge());
        // 4) 静态方法引用
        Arrays.sort(students, CompareByData::compareByAsc);   // 升序
        System.out.println(Arrays.toString(students));

        Arrays.sort(students, CompareByData::compareByDesc);  // 降序
        System.out.println(Arrays.toString(students));
    }
}
```

#### 3.2 实例方法引用

**语法：**

```java
对象名::实例方法
```

**使用场景：** Lambda 表达式里只是调用一个实例方法，并且前后参数形式一致。使用前要先创建对象。

```java
public class CompareByData {
    // 升序实例方法
    public int compareByAsc(Student o1, Student o2) {
        return Integer.compare(o1.getAge(), o2.getAge());
    }

    // 降序实例方法
    public int compareByDesc(Student o1, Student o2) {
        return Integer.compare(o2.getAge(), o1.getAge());
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Student s1 = new Student("小哈", 18, 1.70);
        Student s3 = new Student("李伟", 28, 1.76);
        Student s2 = new Student("小米", 18, 1.85);
        Student s4 = new Student("张三", 38, 1.70);
        Student[] students = new Student[]{s1, s3, s2, s4};

        CompareByData compare = new CompareByData();   // 先创建对象

        // Arrays.sort(students, (o1, o2) -> compare.compareByAsc(o1, o2));
        System.out.println("---------- 实例升序 ----------");
        Arrays.sort(students, compare::compareByAsc);
        System.out.println(Arrays.toString(students));

        System.out.println("---------- 实例降序 ----------");
        Arrays.sort(students, compare::compareByDesc);
        System.out.println(Arrays.toString(students));
    }
}
```

#### 3.3 特定类型的方法引用

**语法：**

```java
类型::方法
```

**使用场景：** Lambda 表达式里调用一个实例方法，并且 **参数列表中的第一个参数是方法的主调（调用者），后面的所有参数都是该方法的入参**。

```java
public class Test1 {
    public static void main(String[] args) {
        String[] names = {"body", "Andy", "Babo", "angela", "James", "Liam", "taylor", "Casey"};

        // 默认排序：按字符串首字母的字符编号升序（大写排在小写前面）
        Arrays.sort(names);
        System.out.println("------ 默认排序 ------");
        System.out.println(Arrays.toString(names));

        // 需求：忽略大小写排序
        // 匿名内部类：
        // Arrays.sort(names, new Comparator<String>() {
        //     @Override
        //     public int compare(String o1, String o2) {
        //         return o1.compareToIgnoreCase(o2);
        //     }
        // });
        // Lambda：
        // Arrays.sort(names, (o1, o2) -> o1.compareToIgnoreCase(o2));
        // 特定类型方法引用：o1 是主调，o2 是入参
        Arrays.sort(names, String::compareToIgnoreCase);
        System.out.println("------ 忽略大小写排序 ------");
        System.out.println(Arrays.toString(names));
    }
}
```

#### 3.4 构造器引用（了解）

**语法：**

```java
类名::new
```

**使用场景：** Lambda 表达式里只是在创建对象，并且前后参数情况一致。

```java
public class Car {
    private String name;
    private String color;

    public Car() {
    }

    public Car(String name, String color) {
        this.name = name;
        this.color = color;
    }

    // getter / setter / toString 省略
}
```

```java
public interface CreateCar {
    Car createCar(String name, String color);
}
```

```java
public class Test {
    public static void main(String[] args) {
        // 匿名内部类
        CreateCar cc = new CreateCar() {
            @Override
            public Car createCar(String name, String color) {
                return new Car(name, color);
            }
        };
        // Lambda 完整版
        CreateCar cc1 = (String name, String color) -> {
            return new Car(name, color);
        };
        // Lambda 省略版
        CreateCar cc2 = (name, color) -> new Car(name, color);
        // 构造器引用
        CreateCar cc3 = Car::new;

        Car car = cc3.createCar("xiaomi Su7", "五彩斑斓的黑");
        System.out.println(car);
    }
}
```

---

### 四、常见算法

算法就是解决某个实际问题的过程和方法。学习算法是为了锻炼编程思维，面试也常考。

**学习技巧：先搞清楚算法流程，再推敲如何写代码。** 练习网站：https://leetcode.cn/

#### 4.1 冒泡排序

**思路：** 每一轮从头到尾相邻两个元素比较，大的往后换，每轮结束把当前最大值"冒泡"到数组后面。

以数组 `[5, 2, 3, 1]` 升序为例：

```text
第1轮（比较3次）：
  5和2比，5放后面 -> [2,5,3,1]
  5和3比，5放后面 -> [2,3,5,1]
  5和1比，5放后面 -> [2,3,1,5]
第2轮（比较2次）：
  2和3比，位置不变 -> [2,3,1,5]
  3和1比，3放后面 -> [2,1,3,5]
第3轮（比较1次）：
  2和1比，2放后面 -> [1,2,3,5]
```

```java
public class Test {
    public static void main(String[] args) {
        int[] arr = {5, 2, 3, 1};
        // 外层循环控制轮数：n 个元素比较 n-1 轮
        for (int i = 0; i < arr.length - 1; i++) {
            System.out.println("------ 第" + (i + 1) + "轮对比 ------");
            // 内层循环：每轮比较次数递减（后面已排好的不用再比）
            for (int j = 0; j < arr.length - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j + 1];
                    arr[j + 1] = arr[j];
                    arr[j] = temp;
                }
            }
        }
        System.out.println("========= 最终结果 =========");
        System.out.println(Arrays.toString(arr));
    }
}
```

#### 4.2 选择排序

**思路：** 外层循环每执行一次，就拿当前索引位置的值与后面所有值挨个比较，更小的就交换，每轮确定一个最小值。

以数组 `[5, 1, 3, 2]` 升序为例：

```text
第1轮（i=0，与索引 1、2、3 比较）：
  5和1比，交换 -> [1,5,3,2]；之后 1 最小，不再交换
第2轮（i=1，与索引 2、3 比较）：
  5和3比，交换 -> [1,3,5,2]
  3和2比，交换 -> [1,2,5,3]
第3轮（i=2，与索引 3 比较）：
  5和3比，交换 -> [1,2,3,5]
```

基础写法（每比较一次就可能交换一次）：

```java
public class Test1 {
    public static void main(String[] args) {
        int[] arr = {5, 1, 3, 2};

        for (int i = 0; i < arr.length - 1; i++) {
            // j 从 i+1 开始，拿 i 位置的值与后面挨个比较
            for (int j = i + 1; j < arr.length; j++) {
                if (arr[i] > arr[j]) {
                    int temp = arr[i];
                    arr[i] = arr[j];
                    arr[j] = temp;
                }
            }
        }
        System.out.println("最终结果：" + Arrays.toString(arr));
    }
}
```

优化写法：**先记录最小值索引，一轮比较完只交换一次**，减少交换次数：

```java
public class Test2 {
    public static void main(String[] args) {
        int[] arr = {5, 1, 3, 2};

        for (int i = 0; i < arr.length - 1; i++) {
            int minIndex = i;   // 假设当前 i 位置就是最小值
            for (int j = i + 1; j < arr.length; j++) {
                if (arr[minIndex] > arr[j]) {
                    minIndex = j;   // 记录更小值的索引
                }
            }
            // i 不是最小值时才交换
            if (i != minIndex) {
                int temp = arr[i];
                arr[i] = arr[minIndex];
                arr[minIndex] = temp;
            }
        }
        System.out.println(Arrays.toString(arr));
    }
}
```

#### 4.3 二分查找（折半查找）

基本查找从 0 索引开始一个个找，数据量大、目标靠后时效率很低。

二分查找每次排除一半元素，效率明显提高。**前提条件：数组元素必须有序。**

核心思路：

```text
第1步：定义两个变量记录开始索引 left 和结束索引 right
第2步：计算中间索引 mid = (left + right) / 2
第3步：用 mid 位置的元素与目标元素比较：
       mid 元素 < 目标：说明 mid 前面都比目标小 -> left = mid + 1
       mid 元素 > 目标：说明 mid 后面都比目标大 -> right = mid - 1
       mid 元素 == 目标：mid 就是要找的位置，返回 mid
重复以上步骤，直到 left > right 结束；还没找到就返回 -1。
```

```java
public class Test3 {
    public static void main(String[] args) {
        int[] arr = {7, 23, 81, 103, 127, 132, 148};
        int res = binarySearch(arr, 81);
        System.out.println(res);
    }

    // 二分查找方法
    public static int binarySearch(int[] arr, int target) {
        int left = 0;
        int right = arr.length - 1;

        // 折半条件：开始位置 <= 结束位置（两位置重合后再比较一次）
        while (left <= right) {
            // 这样写可避免 (left + right) 整数溢出
            int mid = left + (right - left) / 2;
            if (target < arr[mid]) {
                right = mid - 1;      // 往左找
            } else if (target > arr[mid]) {
                left = mid + 1;       // 往右找
            } else {
                return mid;           // 找到
            }
        }
        return -1;                    // 没找到
    }
}
```

---

### 五、正则表达式（regex）

#### 5.1 概述

正则表达式由一些特定字符组成，代表一个**规则**。

作用：

1. 校验数据格式是否合法；
2. 在一段文本中查找满足要求的内容。

#### 5.2 初体验：校验 QQ 号

需求：QQ 号不能为 null，不能以 0 开头，长度 6~20 位，全部是数字。

不使用正则：

```java
public static boolean checkQQ(String qq) {
    // 1、判断 null、长度、是否以 0 开头
    if (qq == null || qq.length() < 6 || qq.startsWith("0") || qq.length() > 20) {
        return false;
    }
    // 2、判断每个字符是否都是数字
    for (int i = 0; i < qq.length(); i++) {
        char ch = qq.charAt(i);
        if (ch < '0' || ch > '9') {
            return false;
        }
    }
    return true;
}
```

使用正则只需一行：

```java
public static boolean checkQQ1(String qq) {
    // [1-9] 第一位必须是1-9；\\d{5,19} 剩下 5~19 位全是数字
    return qq != null && qq.matches("[1-9]\\d{5,19}");
}
```

#### 5.3 正则的书写规则

String 提供的匹配方法：

```java
public boolean matches(String regex)
// 判断字符串是否匹配正则表达式，匹配返回 true，否则返回 false
```

##### （1）字符类（只能匹配单个字符）

| 规则 | 含义 |
| --- | --- |
| `[abc]` | 只能是 a、b、c 中的一个 |
| `[^abc]` | 不能是 a、b、c |
| `[a-zA-Z]` | 只能是 a-z 或 A-Z 的字符 |
| `[a-z&&[^bc]]` | a 到 z，但除了 b 和 c |
| `[a-zA-Z0-9]` | 字母或数字 |

```java
System.out.println("a".matches("[abc]"));      // true
System.out.println("e".matches("[abcd]"));     // false
System.out.println("d".matches("[^abc]"));     // true
System.out.println("b".matches("[a-zA-Z]"));   // true
System.out.println("k".matches("[a-z&&[^bc]]")); // true
System.out.println("ab".matches("[a-zA-Z0-9]")); // false（[]只能匹配单个字符）
```

##### （2）预定义字符（只能匹配单个字符）

| 规则 | 含义 |
| --- | --- |
| `.` | 任意一个字符 |
| `\d` | 数字，等价于 `[0-9]`（Java 字符串中写 `\\d`） |
| `\D` | 非数字 |
| `\s` | 一个空白字符 |
| `\S` | 一个非空白字符 |
| `\w` | 单词字符，等价于 `[a-zA-Z_0-9]` |
| `\W` | 非单词字符，等价于 `[^\w]` |

> Java 字符串中 `\` 是转义字符，所以正则里的 `\d` 要写成 `"\\d"`。

```java
System.out.println("徐".matches("."));       // true
System.out.println("徐徐".matches("."));     // false（只匹配单个字符）

System.out.println("3".matches("\\d"));      // true
System.out.println("a".matches("\\d"));      // false

System.out.println(" ".matches("\\s"));      // true
System.out.println("a".matches("\\S"));      // true

System.out.println("a".matches("\\w"));      // true
System.out.println("_".matches("\\w"));      // true
System.out.println("徐".matches("\\w"));      // false

System.out.println("徐".matches("\\W"));      // true
System.out.println("23232".matches("\\d"));  // false（多个字符不能用单字符规则）
```

##### （3）数量词

| 规则 | 含义 |
| --- | --- |
| `?` |0 次或 1 次 |
| `*` | 0 次或多次 |
| `+` | 1 次或多次 |
| `{n}` | 正好 n 次 |
| `{n,}` | 至少 n 次 |
| `{n,m}` | 至少 n 次，最多 m 次 |

```java
System.out.println("a".matches("\\w?"));     // true（?：0次或1次）
System.out.println("".matches("\\w?"));      // true
System.out.println("abc".matches("\\w?"));   // false

System.out.println("abc12".matches("\\w*")); // true（*：0次或多次）
System.out.println("".matches("\\w*"));      // true

System.out.println("abc12".matches("\\w+")); // true（+：1次或多次）
System.out.println("".matches("\\w+"));      // false

System.out.println("a3c".matches("\\w{3}"));    // true（正好3次）
System.out.println("abcd".matches("\\w{3}"));   // false
System.out.println("abcd".matches("\\w{3,}"));  // true（至少3次）
System.out.println("ab".matches("\\w{3,}"));    // false
System.out.println("abc232d".matches("\\w{3,9}")); // true（3~9次）
```

##### （4）其他常用符号

| 规则 | 含义 |
| --- | --- |
| `(?i)` | 忽略大小写（放在开头对整体生效，也可包住部分内容） |
| `\|` | 或 |
| `()` | 分组 |

```java
System.out.println("abc".matches("(?i)abc"));  // true
System.out.println("ABC".matches("(?i)abc"));  // true
System.out.println("aBc".matches("a((?i)b)c")); // true（只忽略 b 的大小写）

// 需求1：要么是3个小写字母，要么是3个数字
System.out.println("abc".matches("[a-z]{3}|\\d{3}")); // true
System.out.println("123".matches("[a-z]{3}|\\d{3}")); // true
System.out.println("A12".matches("[a-z]{3}|\\d{3}")); // false

// 需求2："我爱"开头，中间至少一个"编程"，最后至少一组"666"
System.out.println("我爱编程编程666666".matches("我爱(编程)+(666)+")); // true
```

#### 5.4 正则校验案例

校验手机号、座机号、邮箱、时间：

```java
public class Anli1 {
    public static void main(String[] args) {
        System.out.println(checkPhone("0931-4889211"));   // true
        System.out.println(checkPhone("09314889211"));    // false（座机缺横杠）
        System.out.println(checkPhone("18500367896"));    // true
        System.out.println(checkPhone("1850036789634"));  // false

        System.out.println(checkEmail("1280286758@qq.com"));        // true
        System.out.println(checkEmail("1280286758@qq.com.cn"));     // true
        System.out.println(checkEmail("xiaoha@163.cn"));            // true
        System.out.println(checkEmail("i@itcast.com"));             // false（@前不足2位）
    }

    // 校验电话（手机 | 座机）
    public static boolean checkPhone(String phone) {
        // 手机：1开头，第二位3-9，共11位
        // 座机：区号3-4位以0开头 + 横杠 + 本地号码7-8位
        String pattern = "(1[3-9]\\d{9})|(0[0-9]{2,3}-\\d{7,8})";
        return phone != null && phone.matches(pattern);
    }

    // 校验邮箱
    public static boolean checkEmail(String email) {
        // @前：单词字符 2~64 位
        // @后：单词字符 2~20 位
        // 域名：. 加单词字符 2~10 位，可出现 1~2 次（如 .com.cn）
        String pattern = "\\w{2,64}@\\w{2,20}(\\.\\w{2,10}){1,2}";
        return email != null && email.matches(pattern);
    }

    // 校验时间 yyyy-MM-dd HH:mm:ss（日期部分）
    public static boolean checkDate(String date) {
        // 年：4位数字；月：01~12；日：01~31
        String nyr = "\\d{4}-(0[1-9]|1[0-2])-(0[1-9]|[12][0-9]|3[0-1])";
        return date != null && date.matches(nyr);
    }
}
```

#### 5.5 正则提取数据（爬取）

需要用到 `java.util.regex` 包下的两个类：

- `Pattern`：把正则封装成规则对象；
- `Matcher`：匹配器对象，通过 `find()` 查找、`group()` 取内容。

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class Test4 {
    public static void main(String[] args) {
        method();
    }

    public static void method() {
        String data = " 来黑马程序员学习Java，\n" +
                "        电话：18666688888，18699997777\n" +
                "        或者联系邮箱：boniu@itcast.cn，\n" +
                "        座机电话：01036517895，010-98951256\n" +
                "        邮箱：bozai@itcast.cn，\n" +
                "        邮箱：dlei0009@163.com，\n" +
                "        热线电话：400-618-9090 ，400-618-4000，4006184000，4006189090";

        // 1、定义爬取规则（手机号 或 邮箱）
        String regex = "(1[3-9]\\d{9})|(\\w{2,64}@\\w{2,20}(\\.\\w{2,10}){1,2})";
        // 2、把正则封装成 Pattern 对象
        Pattern pattern = Pattern.compile(regex);
        // 3、获取匹配器对象
        Matcher matcher = pattern.matcher(data);
        // 4、循环爬取：find() 找到返回 true，group() 返回找到的内容
        while (matcher.find()) {
            String res = matcher.group();
            System.out.println("提取的信息是：" + res);
        }
    }
}
```

#### 5.6 正则用于替换、分割

结合 String 的方法使用：

- `replaceAll(String regex, String replacement)`：按正则替换；
- `split(String regex)`：按正则切割。

```java
public static void main(String[] args) {
    String s1 = "古力娜扎ai8888迪丽热巴999aa5566马尔扎哈fbbfsfs42425卡尔扎巴";

    // 需求1：把非汉字部分替换为 "-"（\\w+ 表示一段连续的数字/字母/下划线）
    String str = s1.replaceAll("\\w+", "-");
    System.out.println(str);
    // 输出：古力娜扎-迪丽热巴-马尔扎哈-卡尔扎巴

    // 需求2：把人名取出来（用非汉字部分切割）
    String[] strs = s1.split("\\w+");
    System.out.println(Arrays.toString(strs));
    // 输出：[古力娜扎, 迪丽热巴, 马尔扎哈, 卡尔扎巴]
}
```

#### 5.7 拓展：分组与反向引用

需求：把口吃的话"我我我喜欢编编编……编程程程！"优化成"我喜欢编程！"。

```java
public class Test6 {
    public static void main(String[] args) {
        String s2 = "我我我喜欢编编编编编编编编编编编编程程程";
        System.out.println(s2.replaceAll("(.)\\1+", "$1"));
        // 输出：我喜欢编程
    }
}
```

正则 `(.)\\1+` 的含义：

- `(.)`：`()` 是分组，`.` 匹配任意单个字符，捕获为第 1 组；
- `\\1`：**反向引用**，引用第 1 组捕获的字符（即与前面相同的字符）；
- `+`：量词，前面的元素出现 1 次或多次。

整体含义：匹配"任意一个字符，后面跟着 1 个或多个相同字符"的连续重复序列。替换字符串 `$1` 表示替换为第 1 组捕获的内容（即保留一个字符）。

替换过程：

- "我我我" 匹配 `(我)\1+`，替换为 `$1` → "我"；
- "喜欢" 无连续重复，保持不变；
- "编编编…" 匹配 `(编)\1+` → "编"；
- "程程程" 匹配 `(程)\1+` → "程"。

#### 5.8 本章小结

- `Arrays`：数组工具类，对象排序用 `Comparable`（写在类上）或 `Comparator`（调用时传入，更灵活）；小数比较用包装类 `compare`；
- Lambda：JDK 8 语法，简化函数式接口（只有一个抽象方法的接口）的匿名内部类，格式 `(参数) -> {方法体}`，可按规则省略；
- 方法引用：`类名::静态方法`、`对象名::实例方法`、`类型::实例方法`、`类名::new`，是对 Lambda 的进一步简化；
- 算法：冒泡（相邻比较，大的沉后）、选择（每轮选最小放前面，可优化为每轮只交换一次）、二分查找（有序数组折半查找，找不到返回 -1）；
- 正则：字符类 `[]`、预定义字符 `\d \w \s` 等、数量词 `? * + {n,m}`、`(?i)` 忽略大小写、`|` 或、`()` 分组；`matches` 校验、`Pattern/Matcher` 提取、`replaceAll/split` 替换分割、`\\1` 与 `$1` 做分组反向引用。

---

<div style="page-break-after: always;"></div>

## 第16章 异常处理与 List 集合

本章分为两大部分：第一部分学习 Java 的异常机制，掌握程序出错时的两种处理方式（抛出与捕获）以及自定义异常；第二部分进入集合框架，学习集合的总体分类、单列集合的祖宗接口 Collection，以及 List 系列集合（ArrayList、LinkedList）的用法和底层原理。

---

### 一、异常

#### 1. 异常的概念

异常就是程序在运行过程中出现的问题。Java 是一门很"安全"的语言，它会把程序中可能出现的问题封装成异常对象，让程序员可以针对性地处理，而不是让程序直接崩溃。

```java
public class Test1 {
    public static void main(String[] args) {
        // 以下代码会有什么问题？
        int[] numbers = {1, 2};
        System.out.println(numbers[2]);      // 数组索引越界异常 ArrayIndexOutOfBoundsException

        int[] numbers1 = null;
        System.out.println(numbers1.length); // 空指针异常 NullPointerException

        System.out.println(20 / 0);          // 算术异常 ArithmeticException
    }
}
```

#### 2. 异常体系与分类

Java 的异常体系根类是 `java.lang.Throwable`，它有两个子类：

- **Error**：代表系统级别的错误（严重问题）。比如栈内存溢出、内存空间不足。这类问题是 Sun 公司给自己用的，**不能靠程序代码解决**，开发人员一般不用管。
- **Exception**：叫异常，代表程序本身可能出现的问题，程序员通常用 Exception 以及它的子类来封装程序出现的问题。

Exception 又分为两大类：

- **运行时异常**：`RuntimeException` 及其子类。编译阶段不会报错，程序运行时才出现。例如：数组索引越界异常、算术异常、空指针异常、类型转换异常等。
- **编译时异常**：编译阶段就会出现错误提醒，必须在写代码时就处理。例如：日期解析异常 `ParseException`。

```java
public class Test1 {
    public static void main(String[] args) {
        Test1 t = new Test1();
        t.exception01();
        t.exception02();
    }

    public void exception01() {
        // 运行时异常：程序在运行过程中才会出现的异常
        System.out.println(20 / 0);
    }

    public void exception02() {
        // 编译时异常：写代码的时候编译器就要求处理（下例日期解析）
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd");
        Date date = sdf.parse("2025-01-20");
    }
}
```

> 记忆要点：编译时异常是"编译器拦着你不让你过"，运行时异常是"编译器不管，跑起来才炸"。

#### 3. 异常处理方式一：throws 抛出异常

在方法上使用 `throws` 关键字，可以把方法内部出现的异常抛出去，交给调用者处理。如果一直往上抛到 main 方法还没人处理，最终由 JVM 打印异常信息并终止程序。

语法格式：

```java
方法 throws 异常1, 异常2, 异常3 ... {
    ......
}

// 推荐写法：Exception 代表可以抛出一切异常
方法 throws Exception {
    ......
}
```

示例：

```java
import java.text.SimpleDateFormat;
import java.util.Date;

public class Test2 {
    public static void main(String[] args) throws Exception {
        Test2 t = new Test2();
        t.exception02();
    }

    // throws Exception：把异常往上抛给调用者处理；一直抛到最外层则由 JVM 打印错误
    public void exception02() throws Exception {
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd");
        Date date = sdf.parse("2025年01月20日"); // 格式与模式不匹配，解析失败
    }
}
```

#### 4. 异常处理方式二：try-catch 捕获异常

直接捕获程序出现的异常，自己处理，程序可以继续往下运行。

语法格式：

```java
try {
    // 监视可能出现异常的代码
} catch (异常类型1 变量) {
    // 处理异常
} catch (异常类型2 变量) {
    // 处理异常
} ...

// 推荐写法：Exception 可以捕获一切异常
try {
    // 可能出现异常的代码
} catch (Exception e) {
    e.printStackTrace(); // 打印异常对象的信息
}
```

示例：

```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class Test3 {
    public static void main(String[] args) {
        Test3 t = new Test3();
        t.exception02();
    }

    public void exception02() {
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd");
        try {
            // 尝试执行代码块
            Date date = sdf.parse("2025年01月20日"); // 格式错误，会抛 ParseException
            // Date date = sdf.parse("2025-01-20"); // 格式正确时正常执行
            System.out.println(date);
        } catch (ParseException e) {
            // try 块中出现了异常，就执行 catch 块
            System.out.println("代码在执行时间格式转换时出现了异常~~~");
        }
    }
}
```

#### 5. throws 与 try-catch 如何选择

原则：**底层方法往上抛异常（throws），顶层方法处理异常（try-catch）**。

底层工具方法往往不知道异常发生后该怎么向用户交代，所以只管抛；最上层（如 main 方法）直接面对用户，应该捕获异常并给出友好提示，不能再抛给 JVM（否则程序崩溃并打印一堆红字）。

```java
import java.text.SimpleDateFormat;
import java.util.Date;

public class Test {
    public static void main(String[] args) {
        // 异常依次抛到 main 就不能再抛了，否则 JVM 会直接打印异常终止程序
        // 顶层使用 try...catch 处理异常
        try {
            test01();
        } catch (Exception e) {
            System.out.println("我知道异常了，联系程序员处理...请稍后重试...");
        }
    }

    public static void test01() throws Exception {
        test02();
    }

    public static void test02() throws Exception {
        test03();
    }

    public static void test03() throws Exception {
        // 底层方法：出现异常直接往上抛
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
        Date date = sdf.parse("2025-01-26"); // 解析失败抛异常
        System.out.println(date);            // 无异常才执行
    }
}
```

#### 6. 多个 catch 块的注意事项

- catch 可以写多个，分别捕获不同类型的异常。
- **多个 catch 的异常类型必须按"从小到大"的顺序书写**：先写具体的子类异常，父类异常（`RuntimeException`、`Exception`）必须写在最后，否则编译报错。
- 一次异常最终只会匹配一个 catch 块。

```java
public class Test1 {
    public static void main(String[] args) {
        try {
            division();
        } catch (NullPointerException e) {
            System.out.println("空指针异常了！！！");
        } catch (ArithmeticException e) {
            System.out.println("算术运算异常~~~");
        } catch (IndexOutOfBoundsException e) {
            System.out.println("数组越界异常~~~");
        } catch (RuntimeException e) { // 父类异常必须放最后
            System.out.println("我是运行时异常~~~");
        }
    }

    public static void division() {
        int num = 10;
        int res = num / 0;
        System.out.println(res);
    }
}
```

#### 7. 自定义异常

Java 不可能为现实世界中的所有问题都提供异常类。如果企业里的某种业务问题想用异常来表示和管理，就需要自己定义异常类。

自定义异常分两种：自定义运行时异常（继承 `RuntimeException`）和自定义编译时异常（继承 `Exception`）。

##### 7.1 自定义运行时异常

```java
/*
   运行时异常类，继承 RuntimeException
 */
// AgeException 年龄异常
public class AgeException extends RuntimeException {
    public AgeException() {
    }

    // 有参构造器：message 参数就是异常提示信息，使用时直接传参即可
    public AgeException(String message) {
        super(message);
    }
}
```

使用自定义运行时异常（用 `throw` 关键字在方法内部抛出异常对象）：

```java
public class Test1 {
    public static void main(String[] args) {
        setAge(160);
    }

    public static void setAge(int age) {
        if (age < 0 || age > 120) {
            // 出现异常，使用 throw 关键字抛出异常对象
            throw new AgeException("年龄不能超过120岁~~");
        } else {
            System.out.println("年龄修改成功！");
        }
    }
}
```

##### 7.2 自定义编译时异常

```java
/*
   编译时异常类，继承 Exception
 */
// HeightException 身高异常
public class HeightException extends Exception {
    public HeightException() {
    }

    public HeightException(String message) {
        super(message);
    }
}
```

使用自定义编译时异常（方法签名必须用 `throws` 声明）：

```java
public class Test1 {
    public static void main(String[] args) throws HeightException {
        setHeight(300); // 调用处继续把异常抛给 JVM，出问题会打印异常提示
    }

    // 编译时异常：方法上必须用 throws 声明
    public static void setHeight(int height) throws HeightException {
        if (height < 0 || height > 280) {
            throw new HeightException("身高不能超过280"); // 抛出异常
        } else {
            System.out.println("身高修改成功~~");
        }
    }
}
```

> 注意区分两个关键字：`throw` 用在方法内部，抛出一个异常对象；`throws` 用在方法签名上，声明该方法可能抛出哪些异常。

#### 异常部分小结

| 知识点 | 要点 |
| --- | --- |
| 异常分类 | Error（系统级，不管）；Exception 分运行时异常（RuntimeException 子类）和编译时异常 |
| throws | 写在方法签名上，把异常抛给调用者；底层方法常用 |
| try-catch | 捕获并处理异常，程序可继续运行；顶层方法常用 |
| 多 catch | 异常类型从小到大书写，父类异常放最后，一次只匹配一个 |
| 自定义异常 | 继承 RuntimeException = 运行时异常；继承 Exception = 编译时异常；throw 抛出对象 |

---

### 二、集合概述与 Collection 体系

#### 1. 集合是什么

集合是一种容器，用来装数据，类似于数组，但**集合的大小是可变的**，开发中非常常用。为了满足不同的业务需求，Java 提供了很多种不同的集合。

#### 2. 集合的两大分类

众多集合可以分为两大类：

- **Collection 代表单列集合**：每个元素只包含一个值。
- **Map 代表双列集合**：每个元素包含两个值（键值对 key=value）。

Collection 集合体系又分为两大系列：

- **List 系列集合**：添加的元素**有序、可重复、有索引**。
  - `ArrayList`、`LinkedList`：有序、可重复、有索引。
- **Set 系列集合**：添加的元素**无序、不重复、无索引**。
  - `HashSet`：无序、不重复、无索引；
  - `LinkedHashSet`：有序、不重复、无索引；
  - `TreeSet`：默认按大小升序排序、不重复、无索引。

List 与 Set 特点对比演示：

```java
import java.util.ArrayList;
import java.util.HashSet;

public class Test1 {
    public static void main(String[] args) {
        // List 集合：有序、可重复、有索引
        ArrayList<String> list = new ArrayList<>();
        list.add("迈动");
        list.add("康帅傅");
        list.add("奥利奥");
        list.add("奥利奥"); // 重复元素也能存
        System.out.println(list);
        System.out.println(list.get(3)); // 有索引，可以用 get 获取

        System.out.println("-----------------------");

        // Set 集合：无序、不重复、无索引
        HashSet<String> set = new HashSet<>();
        set.add("迈动");
        set.add("康帅傅");
        set.add("奥利奥");
        set.add("奥利奥"); // 重复元素存不进去
        System.out.println(set);
        // System.out.println(set.get(2)); // 编译报错：Set 没有 get 方法
    }
}
```

#### 3. Collection 的常用方法

`Collection` 是单列集合的"祖宗"接口，它规定的方法是全部单列集合（List 和 Set）都会继承的。

| 方法 | 说明 |
| --- | --- |
| `boolean add(E e)` | 添加元素 |
| `void clear()` | 清空集合 |
| `boolean remove(Object o)` | 删除指定元素 |
| `boolean contains(Object o)` | 判断是否包含某个元素 |
| `boolean isEmpty()` | 判断集合是否为空 |
| `int size()` | 获取集合中元素的个数 |
| `Object[] toArray()` | 把集合转换为数组 |

> **注意：Collection 没有 get 方法。** 因为它是所有单列集合的父接口，方法必须对 List 和 Set 通用，而 Set 集合没有索引、无法按位置获取元素，所以祖宗接口里不能定义 get。

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Collection;

public class Test2 {
    public static void main(String[] args) {
        Collection<String> list = new ArrayList<>();
        // add 添加元素
        list.add("Java");
        list.add("大数据");
        list.add("前端");
        list.add("嵌入式");
        list.add("AI机器人");
        System.out.println(list);

        // clear() 清空集合
        // list.clear();
        // System.out.println(list);

        // remove 删除元素
        list.remove("前端");
        System.out.println(list);

        // contains 判断是否包含某个元素
        System.out.println(list.contains("前端")); // false
        System.out.println(list.contains("Java")); // true

        // isEmpty 判断集合是否为空
        System.out.println(list.isEmpty());

        // size 获得元素个数
        System.out.println("集合中元素个数为：" + list.size() + "个");

        // toArray 把集合转换为数组
        Object[] array = list.toArray();
        System.out.println(Arrays.toString(array));
    }
}
```

#### 4. Collection 的三种遍历方式

Collection 提供了三种遍历方式：迭代器遍历、增强 for 遍历、Lambda 表达式遍历。

##### 4.1 迭代器遍历

迭代器是遍历集合的专用方式（数组没有迭代器），Java 中迭代器的代表是 `Iterator`。

用法三步：

1. 调用集合的 `iterator()` 方法，把集合封装成一个迭代器对象；
2. 用 `hasNext()` 判断当前位置是否有元素；
3. 用 `next()` 获取当前位置的元素，同时指针后移一位。

```java
import java.util.ArrayList;
import java.util.Collection;
import java.util.Iterator;

public class DieDaiQi {
    public static void main(String[] args) {
        Collection<String> list = new ArrayList<>();
        list.add("Java");
        list.add("大数据");
        list.add("前端");
        list.add("嵌入式");
        list.add("AI机器人");

        // 注意：Collection 没有 get 方法，不能用普通 fori 循环遍历

        // 第一步：将集合封装成迭代器对象
        Iterator<String> iterator = list.iterator();

        // 第二步：hasNext() 判断当前位置是否有元素
        while (iterator.hasNext()) {
            // 第三步：next() 获得当前元素，指针后移一位
            String next = iterator.next();
            System.out.println(next);
        }
    }
}
```

##### 4.2 增强 for 遍历（foreach）

增强 for 循环是 Java 5 引入的语法，专门用于简化数组和集合的遍历，不需要手动控制索引。

语法：

```java
for (元素类型 变量名 : 要遍历的数组或集合) {
    // 循环体：变量名就是当前元素
}
```

- 冒号后面必须是数组，或者实现了 `Iterable` 接口的集合（如 `List`、`Set`）。

```java
import java.util.ArrayList;
import java.util.Collection;

public class ForeachDemo {
    public static void main(String[] args) {
        Collection<String> list = new ArrayList<>();
        list.add("Java");
        list.add("大数据");
        list.add("前端");
        list.add("嵌入式");
        list.add("AI机器人");

        // foreach 遍历集合：ele 依次接收每一个元素
        for (String ele : list) {
            System.out.println(ele);
        }

        System.out.println("-----------------");

        // foreach 遍历数组
        String[] names = {"小哈", "小妮", "小米", "小乖"};
        for (String name : names) {
            System.out.println(name);
        }
    }
}
```

##### 4.3 Lambda 表达式遍历

本质是调用集合的 `forEach` 方法，并用 Lambda 表达式简化。

```java
import java.util.ArrayList;
import java.util.Collection;
import java.util.function.Consumer;

public class LambdaDemo {
    public static void main(String[] args) {
        Collection<String> list = new ArrayList<>();
        list.add("Java");
        list.add("大数据");
        list.add("前端");
        list.add("嵌入式");
        list.add("AI机器人");

        // forEach + 匿名内部类
        list.forEach(new Consumer<String>() {
            @Override
            public void accept(String s) {
                System.out.println(s); // s 就是每次遍历到的元素
            }
        });

        // Lambda 简化
        System.out.println("-----------lambda优化------------");
        list.forEach(s -> System.out.println(s));
        // list.forEach(System.out::println); // 方法引用进一步简化
    }
}
```

#### 5. 集合存储对象的注意事项

往集合中存储对象时，**实际存储的是对象的地址值**，而不是对象本身的一份拷贝。因此通过集合外的引用修改对象，集合里看到的内容也会变；但如果让外部引用指向一个新对象，并不会影响集合中原来存的地址。

```java
import java.util.ArrayList;
import java.util.Collection;

public class Test {
    public static void main(String[] args) {
        Collection<Movie> movies = new ArrayList<>();
        Movie m1 = new Movie("《肖申克的救赎》", 9.7, "罗宾斯");
        movies.add(m1);
        Movie m2 = new Movie("《霸王别姬》", 9.6, "张国荣、张丰毅");
        movies.add(m2);
        Movie m3 = new Movie("《阿甘正传》", 9.5, "汤姆汉克斯");
        movies.add(m3);

        // 集合中存的是地址值：通过 m1 修改对象，集合里的内容同步变化
        m1.setName("《我在人间起飞的日子》");

        // m2 指向了一个新对象，但集合里存的还是旧地址，不受影响
        m2 = new Movie("《小太阳》", 9.6, "小夏，小白");
        // movies.add(m2); // 没有重新 add，新对象不在集合中

        for (Movie movie : movies) {
            System.out.println("电影名：" + movie.getName());
            System.out.println("评分：" + movie.getScore());
            System.out.println("主演：" + movie.getActor());
            System.out.println("------------------------------");
        }
    }
}
```

#### 6. 综合案例：电影信息遍历

需求：定义一个电影类描述电影信息，把多部电影存入集合并遍历输出。

电影类：

```java
public class Movie {
    private String name;   // 电影名称
    private double score;  // 评分
    private String actor;  // 演员

    public Movie() {}

    public Movie(String name, double score, String actor) {
        this.name = name;
        this.score = score;
        this.actor = actor;
    }

    // get、set、toString 方法自己补上
}
```

测试类（分别用增强 for、迭代器、Lambda 三种方式遍历）：

```java
import java.util.ArrayList;
import java.util.Collection;
import java.util.Iterator;

public class Test {
    public static void main(String[] args) {
        Collection<Movie> movies = new ArrayList<>();
        movies.add(new Movie("《肖申克的救赎》", 9.7, "罗宾斯"));
        movies.add(new Movie("《霸王别姬》", 9.6, "张国荣、张丰毅"));
        movies.add(new Movie("《阿甘正传》", 9.5, "汤姆汉克斯"));

        // 方式一：增强 for 遍历
        for (Movie movie : movies) {
            System.out.println("电影名：" + movie.getName());
            System.out.println("评分：" + movie.getScore());
            System.out.println("主演：" + movie.getActor());
        }

        // 方式二：迭代器遍历
        Iterator<Movie> it = movies.iterator();
        while (it.hasNext()) {
            Movie movie = it.next();
            System.out.println(movie.getName() + "，" + movie.getScore() + "分，主演：" + movie.getActor());
        }

        // 方式三：Lambda 遍历
        movies.forEach(movie -> System.out.println(movie.getName() + " 主演：" + movie.getActor()));
    }
}
```

---

### 三、List 系列集合

List 系列集合的特点：**有序、可重复、有索引**。`ArrayList` 和 `LinkedList` 都具备这些特点，区别在底层实现。

#### 1. List 集合的特有方法

List 因为支持索引，比 Collection 多了很多与索引相关的方法（Collection 的功能它也全部继承）：

| 方法 | 说明 |
| --- | --- |
| `void add(int index, E e)` | 在指定索引位置插入元素 |
| `E remove(int index)` | 删除指定索引处的元素，返回被删元素 |
| `E set(int index, E e)` | 修改指定索引处的元素，返回被修改的元素 |
| `E get(int index)` | 获取指定索引处的元素 |

```java
import java.util.ArrayList;
import java.util.List;

public class ListDemo {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("Java");
        list.add("大数据");
        list.add("PHP");
        list.add("前端");
        list.add("嵌入式");
        list.add("AI机器人");
        list.add("PY");

        // 在指定索引位置添加元素
        list.add(6, "Html");
        System.out.println(list);

        // 删除指定索引处的元素
        System.out.println("被删除的元素：" + list.remove(2)); // 删除 PHP

        // 修改指定索引处的元素
        System.out.println("被修改的元素：" + list.set(0, "JavaSE"));

        // 获取指定索引处的元素
        System.out.println("索引1处的元素：" + list.get(1));

        // Lambda 遍历打印
        list.forEach(s -> System.out.println(s));
    }
}
```

List 集合因为有索引，遍历时除了迭代器、增强 for、Lambda 之外，还可以使用普通 for 循环（fori）。LinkedList 的操作方法与 ArrayList 一模一样：

```java
import java.util.LinkedList;
import java.util.List;

public class Test3 {
    public static void main(String[] args) {
        List<String> list = new LinkedList<>();
        list.add("Java");
        list.add("大数据");
        list.add("前端");
        list.add("嵌入式");
        list.add("AI机器人");

        // 迭代器遍历、增强for遍历、Lambda遍历、fori遍历 都可以
        for (int i = 0; i < list.size(); i++) {
            System.out.println(list.get(i));
        }
    }
}
```

#### 2. ArrayList 的底层原理

**ArrayList 底层基于数组实现。**

数组的特点：

- **查询速度快**（指根据索引查询快）：通过首地址 + 索引直接定位，查询任意数据耗时相同。
- **删除效率低**：删除中间元素后，后面的大量数据要向前移动。
- **添加效率低**：在中间插入元素时后面的数据要后移；数组满了还可能要扩容（数组长度不可变，只能新建更大的数组再拷贝）。

ArrayList 的扩容机制：

- 利用无参构造器创建集合时，底层先创建一个默认长度为 **0** 的数组；
- 添加第一个元素时，底层创建一个长度为 **10** 的新数组；
- 每添加一个元素，记录元素个数的 size 往后移一位——**size 既是已有元素的个数，也是下一个元素的存放位置**；
- 数组存满时，**按 1.5 倍扩容**；
- 如果一次添加多个元素，1.5 倍还放不下，则新数组长度以实际需要为准。

```java
List<String> list1 = new ArrayList<>();
list1.add("a"); // 第一次 add：创建长度为 10 的数组

// 如果 list2 里有 11 个数据，addAll 后新数组长度就是 21（10 的 1.5 倍是 15，放不下，按实际 21）
List<String> list2 = new ArrayList<>();
list2.add("a11");
// ... 共添加 11 个元素
list1.addAll(list2); // 把 list2 的数据全部倒入 list1
```

**应用场景**：ArrayList 适合根据索引查询数据（如随机取数据），或数据量不大的场景；数据量大且需要频繁增删时，不建议使用 ArrayList。

#### 3. LinkedList 的底层原理

**LinkedList 基于双链表实现。**

##### 什么是链表

链表把每个数据封装成一个节点对象 `Node`，节点中有一个属性（next）保存下一个节点对象的地址，从而把多个数据串成一条链。链表中的节点是独立的对象，在内存中**不连续**，每个节点包含数据值和下一个节点的地址。

链表的特点：

- **查询慢**：无论查哪个数据，都要从头节点开始依次往后找。
- **增删相对快**：只需修改相邻节点的指向，不需要移动大量数据。删除元素时，让被删节点的前一个节点直接指向后一个节点即可；插入元素同理。

##### 单链表与双链表

- **单链表**：节点有两个属性，一个是数据值 item，一个是 next（指向下一个节点的地址），只能从头向尾查找。
- **双链表**：节点前后有两个属性，`prev`（指向前一个节点，可从尾向头查找）和 `next`（指向后一个节点，可从头向尾查找）。LinkedList 用的就是双链表。

##### LinkedList 的特有方法

除了 List 系列共有的方法，LinkedList 额外提供了很多首尾操作的方法：

| 方法 | 说明 |
| --- | --- |
| `addFirst(E e)` | 在列表开头插入元素 |
| `addLast(E e)` | 在列表末尾添加元素 |
| `getFirst()` | 返回第一个元素 |
| `getLast()` | 返回最后一个元素 |
| `removeFirst()` | 删除并返回第一个元素 |
| `removeLast()` | 删除并返回最后一个元素 |

```java
import java.util.LinkedList;
import java.util.List;

public class Test5 {
    public static void main(String[] args) {
        List<String> list = new LinkedList<>();
        // add 是整个 List 公有的添加方法
        list.add("a");
        list.add("b");
        list.add("c");
        System.out.println(list);

        // LinkedList 特有方法
        list.addFirst("哈哈"); // 开头插入
        System.out.println(list);

        list.addLast("嘎嘎");  // 末尾添加
        System.out.println(list);

        System.out.println(list.getFirst()); // 第一个元素
        System.out.println(list.getLast());  // 最后一个元素

        System.out.println("成功删除了第一个元素：" + list.removeFirst());
        System.out.println(list);

        System.out.println("成功删除了最后一个元素：" + list.removeLast());
        System.out.println(list);
    }
}
```

#### 4. LinkedList 的应用场景：队列与栈

##### 4.1 模拟队列

队列的特点是**先进先出、后进后出**，可以用于排队购票等系统。

- 入队：`addLast` 添加到队尾；
- 出队：`removeFirst` 删除队首元素。

```java
import java.util.LinkedList;

public class QueueTest {
    public static void main(String[] args) {
        LinkedList<String> list = new LinkedList<>();
        // 入队：addLast 添加到最后面
        list.addLast("第1号");
        list.addLast("第2号");
        list.addLast("第3号");
        list.addLast("第4号");
        list.addLast("第5号");
        System.out.println("--------------排队成功-------------");
        System.out.println(list);

        // 出队：removeFirst 删除排在第一位的元素
        System.out.println(list.removeFirst() + " 完成了收票，出去了！");
        System.out.println(list.removeFirst() + " 完成了收票，出去了！");
        System.out.println(list.removeFirst() + " 完成了收票，出去了！");
        System.out.println(list.removeFirst() + " 完成了收票，出去了！");
        System.out.println(list.removeFirst() + " 完成了收票，出去了！");
        System.out.println("--------------买票成功-------------");
        System.out.println(list);
    }
}
```

##### 4.2 模拟栈

栈的特点是**先进后出**：

- 数据进入栈模型称为**压栈/进栈（push）**；
- 数据离开栈模型称为**弹栈/出栈（pop）**。

例如游戏中子弹的装填与射击：装子弹用压栈，射击用弹栈（最后装的子弹最先射出）。

- 压栈：`addFirst` 添加到头部；
- 弹栈：`removeFirst` 移除头部元素。

```java
import java.util.LinkedList;

public class StackTest {
    public static void main(String[] args) {
        LinkedList<String> stack = new LinkedList<>();
        // 进栈（压栈）：先装的子弹放在最下面
        stack.addFirst("第1颗子弹");
        stack.addFirst("第2颗子弹");
        stack.addFirst("第3颗子弹");
        stack.addFirst("第4颗子弹");
        stack.addFirst("第5颗子弹");
        System.out.println(stack);

        // 出栈（弹栈）：最上面的子弹先射击出去
        System.out.println(stack.removeFirst() + " ----被射击出去了！");
        System.out.println(stack.removeFirst() + " ----被射击出去了！");
        System.out.println(stack.removeFirst() + " ----被射击出去了！");
        System.out.println("----------射击结束，子弹还有----------");
        System.out.println(stack);
    }
}
```

#### 5. 集合边遍历边删除的坑

##### 5.1 问题描述

需求：删除 List 集合中所有的 "b" 元素。

```java
import java.util.ArrayList;

public class Test4 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("a");
        list.add("b");
        list.add("b");
        list.add("b");
        list.add("c");
        list.add("d");
        list.add("e");
        list.add("f");
        // 要求删除 list 集合中的所有 b 元素
    }
}
```

用普通 for 循环遍历删除：

```java
for (int i = 0; i < list.size(); i++) {
    String s = list.get(i);
    if (s.equals("b")) {
        list.remove(i);
    }
}
System.out.println(list);
```

**问题**：如果被删元素连续重复，会删不干净。

**原因**：删除索引 1 的 "b" 后，后面的元素整体向前移动一位，紧跟着的那个 "b" 移到了索引 1；但循环变量 i 已经自增到 2，下一次直接检查索引 2，跳过了索引 1 上这个新的 "b"。

##### 5.2 解决方案一：删除后 i-- ，或倒序遍历

```java
// 写法1：删除后 i--，让下一次循环还检查当前索引
for (int i = 0; i < list.size(); i++) {
    String s = list.get(i);
    if (s.equals("b")) {
        list.remove(i); // 删除后紧跟着的元素向前移动
        i--;
    }
}
System.out.println(list);
```

```java
// 写法2：从后往前倒序遍历（元素前移不影响尚未检查的索引）
for (int i = list.size() - 1; i >= 0; i--) {
    String s = list.get(i);
    if (s.equals("b")) {
        list.remove(i);
    }
}
System.out.println(list);
```

##### 5.3 推荐方案：迭代器自己的 remove 方法

```java
import java.util.Iterator;

// 把集合包装成迭代器
Iterator<String> iterator = list.iterator();
while (iterator.hasNext()) {
    String item = iterator.next();
    if (item.equals("b")) {
        iterator.remove(); // 用迭代器自己的 remove 删除，指针会正确回退
    }
}
System.out.println(list);
```

迭代器内部的指针在调用 `iterator.remove()` 时，不仅删除当前元素，还会正确调整指针位置，保证下一次 `next()` 能拿到正确的下一个元素，不会跳过。

##### 5.4 更简洁的方案：removeIf 批量删除

`removeIf` 是 Java 8 为 `Collection` 接口新增的默认方法，作用是**批量删除集合中所有满足条件的元素**。

核心参数是 `Predicate<? super E> filter`：`Predicate` 是函数式接口，只有一个方法 `boolean test(T t)`，负责判断；`removeIf` 遍历每个元素并调用 `test(e)`，返回 `true` 就删除。

```java
import java.util.function.Predicate;

list.removeIf(new Predicate<String>() {
    @Override
    public boolean test(String item) {
        return "b".equals(item);
    }
});
System.out.println(list);
```

Lambda 简化写法：

```java
list.removeIf(item -> "b".equals(item));
System.out.println(list);
```

##### 5.5 反面教材：增强 for 中直接删除会报并发修改异常

```java
for (String s : list) {
    if (s.equals("b")) {
        list.remove(s); // 报错：ConcurrentModificationException
    }
}
System.out.println(list);
```

增强 for 循环底层使用的是 Iterator。当在循环中调用 `list.remove(s)` 时，**绕过了迭代器直接修改集合**，迭代器下一次检查时发现集合被"非法"修改，为了保护数据一致性就抛出 `ConcurrentModificationException`（并发修改异常）。

通俗理解：`hasNext()` 判断有元素后，`next()` 取元素时元素被删，后面的元素要前移，而指针只能后移，指针新位置上没有元素，迭代器无法继续工作，只能报错。

> 结论：遍历过程中要删除元素，要么用迭代器的 `iterator.remove()`，要么用 `removeIf`，要么 fori 配合 i--/倒序；不要在增强 for 里直接调集合的 remove。

#### List 集合部分小结

| 集合 | 底层 | 特点 | 适用场景 |
| --- | --- | --- | --- |
| ArrayList | 数组 | 查询快、增删慢；默认长度 10，1.5 倍扩容 | 频繁按索引查询、数据量不大 |
| LinkedList | 双链表 | 查询慢、首尾增删快；有 addFirst/removeLast 等首尾方法 | 频繁增删首尾元素；可模拟队列、栈 |

Collection 三种遍历：迭代器 `Iterator`、增强 for、`forEach` + Lambda；List 额外支持 fori（有索引）。

---

<div style="page-break-after: always;"></div>

## 第17章 Set 与 Map 集合

本章学习 Collection 体系的另一大分支 Set 系列集合（HashSet、LinkedHashSet、TreeSet），以及双列集合 Map 系列（HashMap、LinkedHashMap、TreeMap），最后讲解集合工具类 Collections、可变参数和集合嵌套。Set 与 Map 的底层都围绕"哈希表"和"红黑树"两种数据结构展开。

---

### 一、Set 系列集合

#### 1. 认识 Set 集合的特点

Set 属于 Collection 体系下的另一个分支，**总体特点是：无序、不重复、无索引**。

- 无序：添加数据的顺序和获取数据的顺序不一致；
- 不重复：相同元素只能存一个；
- 无索引：没有 get 方法，不能按索引取元素。

三个实现类各有侧重：

- **HashSet**：无序、不重复、无索引（使用最广泛）；
- **LinkedHashSet**：有序（通过链表记录添加顺序）、不重复、无索引；
- **TreeSet**：可排序（按某种规则排列，默认升序）、不重复、无索引。

```java
import java.util.HashSet;

// HashSet（使用最广泛）：无序、不可重复、无索引
HashSet<String> set = new HashSet<>();
// 也可以写：Set<String> set = new HashSet<>(); 或 Collection<String> set = new HashSet<>();
set.add("apple");
set.add("Html");
set.add("Java");
set.add("bigdata");
set.add("javascript");
set.add("Java");       // 重复，存不进去
set.add("javascript"); // 重复，存不进去
System.out.println(set);
```

```java
import java.util.LinkedHashSet;
import java.util.Set;

// LinkedHashSet：有序（链表保证顺序）、不可重复、无索引
Set<String> set = new LinkedHashSet<>();
set.add("html");
set.add("JavaSE");
set.add("javascript");
set.add("JavaEE");
set.add("bigData");
set.add("JavaEE"); // 重复
System.out.println(set); // 输出顺序与添加顺序一致
```

```java
import java.util.Set;
import java.util.TreeSet;

// TreeSet：可排序（按规则排序，默认升序）、不可重复、无索引
Set<String> set = new TreeSet<>();
set.add("apple");
set.add("Html");
set.add("Java");
set.add("bigdata");
set.add("javascript");
set.add("Java");
set.add("javascript");
System.out.println(set); // 按字符编码排序输出
```

> Set 集合用到的常用方法基本都是 Collection 提供的（add、remove、contains、size、遍历等），自己几乎没有新增常用功能。

#### 2. 前置知识：哈希值

学习 HashSet 底层原理前，先搞懂哈希值：

- 哈希值是一个 int 类型的数值，Java 中**每个对象都有一个哈希值**，可以理解为对象的"身份证号"。
- 所有对象都可以调用 Object 类提供的 `hashCode()` 方法返回自己的哈希值：

```java
public int hashCode() // 返回对象的哈希码值
```

对象哈希值的特点：

- **同一个对象**多次调用 `hashCode()`，返回的哈希值相同；
- **不同对象**的哈希值一般不相同，但也有可能相同（称为哈希碰撞）。

```java
public static void main(String[] args) {
    Student s1 = new Student("小哈", 28);
    Student s2 = new Student("小米", 22);
    // 同一个对象多次调用，哈希值相同
    System.out.println(s1.hashCode());
    System.out.println(s1.hashCode());
    System.out.println(s1.hashCode());

    // 不同对象哈希值一般不同
    String str1 = new String("abc");
    String str2 = new String("acD");
    System.out.println(str1.hashCode());
    System.out.println(str2.hashCode());
}
```

> 补充：直接打印对象时，`toString()` 默认输出的是类名和十六进制地址值（如 `Student@1b6d3586`），这个地址值与哈希值有关联但不是同一个概念。

#### 3. HashSet 的底层原理

需要搞明白两个问题：为什么元素无序、不重复、无索引？增删改查有什么特点，适合什么场景？

##### 3.1 哈希表结构

HashSet 的底层基于**哈希表**实现，哈希表是一种增删改查性能都较好的数据结构。JDK 版本不同结构有区别：

- JDK 8 以前：哈希表 = 数组 + 链表；
- JDK 8 开始（性能提升）：哈希表 = 数组 + 链表 + 红黑树。

##### 3.2 JDK 8 以前的存储方式

先把数据封装成节点对象（Node），根据元素的哈希值与数组长度（默认 16）计算出一个下标位置，再决定如何存入：

1. 创建一个默认长度 **16** 的数组，默认加载因子 **0.75**，数组名 table；
2. 用元素的哈希值对数组长度求余，计算出应存入的位置；
3. 判断该位置是否为 null，是 null 直接存入；
4. 如果不为 null（已有元素），调用 `equals` 方法比较：相等则不存（去重），不相等则挂在该位置形成链表。

**JDK 8 之前：新元素存入数组占老元素的位置，老元素挂到下面（头插法）。**

元素按哈希值取余定位，而不是按添加顺序排座位，所以**无序**；位置由哈希值决定且 equals 判重，所以**不重复**；位置是算出来的不是连续编号，所以**无索引**。

##### 3.3 扩容机制

数组快占满时，链表可能过长导致查询性能下降，此时需要扩容：

- **扩容阈值 = 容量 × 负载因子**。默认 16 × 0.75 = 12，即存入第 13 个元素时数组扩容；
- 扩容产生一个长度约为旧数组 **2 倍**的新数组，把旧数组内容重新计算位置搬入新数组，旧数组被废弃回收。

打个比方：你有一个装 16 个球的盒子，装满后不能把盒子"拉长"成 32 格，只能找一个新的 32 格盒子，把球逐个搬到新盒子对应格子里，最后扔掉旧盒子——这就是 HashSet 扩容的本质。

##### 3.4 JDK 8 开始的存储方式与红黑树

JDK 8 以前链表过长会导致查询变慢（还可能出现环链问题）。JDK 8 开始：**当链表长度超过 8 时，链表转换为红黑树**，进一步提高操作性能。

- 红黑树通过一系列操作，按哈希值大小进行二分排序：**小的在左、大的在右、一样的不存**；
- 查找规则：**目标值小于父节点就在左侧找，大于父节点就在右侧找**（类似二分查找）。

转换条件的完整说法（面试点）：**链表长度 >= 8 且数组长度 >= 64 时才转红黑树**；若链表长度 >= 8 但数组长度 < 64，只扩容不树化；红黑树节点退化到 <= 6 时会转回链表。

面试题：为什么不一开始就用红黑树？

> 红黑树是以空间换时间的结构，节点少时维护树的成本比链表还高：
> - 链表长度不超过 8 时，链表维护成本低、实际效率更高；
> - 链表长度 >= 8 且数组长度 >= 64 时，用红黑树保证查询性能；
> - 链表长度 >= 8 但数组长度 < 64 时，只扩容，用更低成本解决问题；
> - 红黑树节点 <= 6 时转回链表，减少维护成本，避免过度优化。

##### 3.5 了解：二叉树、二叉查找树、平衡二叉树

- **二叉树**：一个父节点最多有两个分叉（左子节点、右子节点）。普通二叉树数据排列没有顺序。
- **二叉查找树（二叉排序树）**：按**左小右大**的规则排列。查找时目标值比父节点小就往左找，比父节点大就往右找，效率较高。
- 二叉查找树的问题：当数据本身已经排好序时，树会退化成一根"斜链"，查询性能和单链表一样慢。
- **平衡二叉树**：在满足左小右大规则的前提下，通过旋转让树尽可能矮小，从而保证查询性能。
- Java 使用的**红黑树**就是一种可以自平衡的二叉树，底层有自己的算法维持平衡，是增删改查性能都较好的结构。

#### 4. HashSet 的去重机制

##### 4.1 存储自定义对象的问题

Student 类（name、age、height 三个属性）：

```java
public class Student {
    private String name;
    private int age;
    private double height;

    public Student() {}

    public Student(String name, int age, double height) {
        this.name = name;
        this.age = age;
        this.height = height;
    }

    // setter、getter、toString 自己补上
}
```

测试：

```java
public static void main(String[] args) {
    HashSet<Student> set = new HashSet<>();
    Student s1 = new Student("小哈", 18, 1.88);
    Student s2 = new Student("小米", 22, 1.80);
    Student s3 = new Student("小哈", 18, 1.88); // 内容与 s1 完全相同
    Student s4 = new Student("小可", 36, 1.70);
    System.out.println(s1.equals(s3)); // false（两个不同对象，默认比地址）
    set.add(s1);
    set.add(s2);
    set.add(s3);
    set.add(s4);
    System.out.println(set); // 4 个元素都存进去了，没有去重！
}
```

**结论：HashSet 默认不能对"内容一样的两个不同对象"去重。** 因为默认的 `hashCode()` 按地址算哈希值（两个对象地址不同、哈希值不同、落点不同），默认的 `equals()` 也比地址。

##### 4.2 解决方案：重写 hashCode 和 equals

想让 HashSet 认为内容相同的两个对象是重复的，**必须重写对象的 `hashCode()` 和 `equals()` 方法**（IDEA 中 Alt + Insert 直接生成）：

```java
@Override
public boolean equals(Object o) {
    if (this == o) return true;
    if (o == null || getClass() != o.getClass()) return false;
    Student student = (Student) o;
    return age == student.age
            && Double.compare(height, student.height) == 0
            && Objects.equals(name, student.name);
}

@Override
public int hashCode() {
    return Objects.hash(name, age, height); // 用参与比较的属性算哈希值
}
```

重写后：内容相同的对象哈希值相同、equals 为 true，s3 不会再存入。

#### 5. LinkedHashSet 集合

- 特点：HashSet 的子类，**有序（添加顺序与获取顺序一致）、不重复、无索引**。
- 底层：依然基于哈希表（数组 + 链表 + 红黑树）实现，但每个元素额外多了一个**双链表**机制记录前后元素的位置，从而保证存储顺序。

节点结构示意：

```java
Node {
    Node prev;       // 前一个节点（双链表）
    Object item;     // 元素值
    Node next;       // 后一个节点（双链表）
    int hash;        // 哈希值（哈希表用）
}
```

```java
public static void main(String[] args) {
    LinkedHashSet<Student> set = new LinkedHashSet<>();
    Student s1 = new Student("小哈", 18, 1.88);
    Student s2 = new Student("小米", 22, 1.80);
    Student s3 = new Student("小哈", 18, 1.88);
    Student s4 = new Student("小可", 36, 1.70);
    System.out.println(s1.equals(s3)); // Student 重写过 equals 后为 true
    set.add(s1);
    set.add(s2);
    set.add(s3); // 内容重复，存不进去
    set.add(s4);
    System.out.println(set); // 按添加顺序输出 3 个元素
}
```

#### 6. TreeSet 集合

##### 6.1 概述

- 特点：**不重复、无索引、可排序**（默认按元素大小由小到大升序排序）；
- 底层基于**红黑树**实现（左边小、右边大）。

默认排序规则：

- 数值类型（Integer、Double）：按数值本身大小升序；
- 字符串类型：按首字符的编码升序；
- **自定义类型（如 Student）：TreeSet 默认无法直接排序**，必须指定比较规则。

```java
public static void main(String[] args) {
    TreeSet<Integer> set = new TreeSet<>();
    set.add(52);
    set.add(42);
    set.add(52);
    set.add(3);
    set.add(30);
    set.add(1);
    set.add(20);
    System.out.println(set);  // [1, 3, 20, 30, 42, 52]

    TreeSet<String> set2 = new TreeSet<>();
    set2.add("A");
    set2.add("f");
    set2.add("a");
    set2.add("c");
    set2.add("d");
    System.out.println(set2); // [A, a, c, d, f]（大写字母编码小于小写）
}
```

##### 6.2 存储自定义对象的问题

直接往 TreeSet 里存 Student 对象会报 `ClassCastException`（类型转换异常），因为 TreeSet 会尝试把元素转成 Comparable 类型来比较大小，而 Student 没有实现该接口。

##### 6.3 解决方案一：实现 Comparable 接口（不推荐）

让自定义类实现 `Comparable<T>` 接口，重写 `compareTo` 方法指定比较规则：

- 左边对象（this）大于右边对象（o）：返回正整数；
- 左边对象小于右边对象：返回负整数；
- 两边相等：返回 0（返回 0 认为元素重复，不存入）。

```java
public class Student implements Comparable<Student> {
    // ... 属性、构造器、getter/setter 省略

    @Override
    public int compareTo(Student o) {
        // this 表示比较者，o 表示被比较者
        int res = this.age - o.age;                 // 先按年龄升序
        if (res == 0) res = this.getName().compareTo(o.getName()); // 年龄相同按姓名
        if (res == 0) res = Double.compare(this.height, o.height); // 再相同按身高
        return res;
    }
}
```

> 注意：必须把所有属性都比较到（res 为 0 时继续比下一个属性），否则两个年龄相同但姓名不同的对象会被误判为重复而丢弃。

##### 6.4 解决方案二：Comparator 比较器（推荐）

调用 TreeSet 的有参构造器，传入 `Comparator` 比较器对象指定规则，类本身不用做任何修改：

```java
public TreeSet(Comparator<? super E> comparator)
```

```java
public static void main(String[] args) {
    TreeSet<Student> ts = new TreeSet<>(new Comparator<Student>() {
        @Override
        public int compare(Student o1, Student o2) {
            int res = Integer.compare(o1.getAge(), o2.getAge());       // 按年龄升序
            if (res == 0) res = o1.getName().compareTo(o2.getName());  // 年龄相同按姓名
            if (res == 0) res = Double.compare(o1.getHeight(), o2.getHeight());
            return res;
        }
    });
    Student s1 = new Student("小哈", 18, 1.75);
    Student s4 = new Student("小顾", 28, 1.68);
    Student s2 = new Student("小米", 22, 1.85);
    Student s3 = new Student("小可", 28, 1.68);
    ts.add(s1);
    ts.add(s2);
    ts.add(s3);
    ts.add(s4);
    System.out.println(ts);
}
```

两种方式对比：Comparable 是"类自己实现的默认排序规则"，Comparator 是"调用集合时临时给出的比较规则"，后者更灵活。

#### 7. Collection 体系如何选择

| 需求 | 选择 | 底层 |
| --- | --- | --- |
| 要记住添加顺序、要存重复元素、频繁按索引查询 | **ArrayList**（常用） | 数组 |
| 要记住添加顺序、增删首尾数据较多 | LinkedList | 双链表 |
| 不在意顺序、无重复元素、希望增删改查都快 | **HashSet**（常用） | 哈希表 |
| 要记住添加顺序、无重复元素、希望增删改查都快 | LinkedHashSet | 哈希表 + 双链表 |
| 要对元素排序、无重复元素、希望增删改查都快 | TreeSet | 红黑树 |

#### 8. 并发修改异常（注意事项）

使用迭代器遍历集合的同时删除集合中的数据，会出现并发修改异常 `ConcurrentModificationException`；增强 for 是迭代器的简化写法，同样会出现且无法在增强 for 内部解决。

解决方案（详见第 16 章）：

- 用迭代器遍历时，使用迭代器自己的 `iterator.remove()` 删除；
- 用普通 for 循环时，可以倒序遍历删除，或正序遍历删除后做 `i--`；
- 最简洁的方式是 `removeIf`。

```java
public static void main(String[] args) {
    ArrayList<String> list = new ArrayList<>();
    list.add("王小哈");
    list.add("小李子");
    list.add("李小可");
    list.add("柴小米");
    list.add("李玉刚");
    list.add("黄晓明");
    list.add("李春草");

    // 需求：找出集合中全部带"李"的名字并删除
    Iterator<String> iterator = list.iterator();
    while (iterator.hasNext()) {
        String name = iterator.next();
        if (name.contains("李")) {
            // list.remove(name); // 并发修改异常
            iterator.remove();  // 正确：用迭代器自己的 remove，底层相当于做了 i--
        }
    }
    System.out.println(list);
}
```

---

### 二、可变参数与 Collections 工具类

#### 1. 可变参数

##### 1.1 问题引入

定义一个求和方法，如果用方法重载应对不同参数个数，参数个数一变就要重写一个方法，代码繁琐冗余：

```java
public static void sum(int num1) { ... }
public static void sum(int num1, int num2) { ... }
public static void sum(int num1, int num2, int num3) { ... }
```

##### 1.2 基本语法

可变参数是一种特殊形参，定义在方法、构造器的形参列表里，格式为：**数据类型... 参数名称**。

```java
public static void main(String[] args) {
    test(1);
    test(1, 2);
    test(1, 2, 3, 4);
}

// 可变参数语法
public static void test(int... nums) {
}
```

##### 1.3 特点与好处

- 可以不传数据、传一个或多个数据，也可以直接传一个数组；
- 常用来灵活地接收个数不确定的数据。

##### 1.4 注意事项

- **本质是数组**：方法内部操作可变参数完全等同于操作数组：

```java
public static void test(int... nums) {
    System.out.println("长度为：" + nums.length);      // 等同数组的 length
    System.out.println(Arrays.toString(nums));        // 等同打印数组
}
```

- 传入 `null`（而非空数组）时遍历会抛 `NullPointerException`，要注意避免；
- 一个形参列表中**只能有一个可变参数，且必须放在最后**：

```java
public static void test(int num1, int... num2) { // 可变参数在最后
    int sum = 0;
    for (int i = 0; i < num2.length; i++) {
        sum += num2[i];
    }
    System.out.println(num1 + sum);
}
```

- 参数数量固定时优先用固定参数，可读性更高；仅当参数个数不确定时才用可变参数。

#### 2. Collections 工具类

`Collections` 是操作集合的工具类，提供大量静态方法。

##### 2.1 批量添加元素 addAll

```java
ArrayList<String> list = new ArrayList<>();
// Collections.addAll(集合名, "元素1", "元素2", ...)
Collections.addAll(list, "小哈", "小米", "小何", "小可");
System.out.println(list); // [小哈, 小米, 小何, 小可]
```

##### 2.2 打乱顺序 shuffle

```java
Collections.shuffle(list); // 每次运行结果都不同
System.out.println(list);  // 如 [小米, 小哈, 小可, 小何]
```

##### 2.3 升序排序 sort

```java
ArrayList<Integer> list2 = new ArrayList<>();
Collections.addAll(list2, 22, 88, 55, 6, 96);
Collections.sort(list2);
System.out.println(list2); // [6, 22, 55, 88, 96]
```

集合里存的是对象时，不能直接 sort，需要用 Comparator 比较器指定排序规则：

```java
public static void main(String[] args) {
    ArrayList<Student> students = new ArrayList<>();
    students.add(new Student("小哈", 28, 1.75));
    students.add(new Student("小红", 22, 1.70));
    students.add(new Student("小米", 18, 1.85));
    students.add(new Student("小可", 38, 1.65));
    students.add(new Student("小关", 22, 1.60));

    // Collections.sort(students); // 报错：没有指定对象排序规则
    Collections.sort(students, new Comparator<Student>() {
        @Override
        public int compare(Student o1, Student o2) {
            // return o1.getAge() - o2.getAge(); // 按年龄升序
            return Integer.compare(o1.getAge(), o2.getAge()); // 推荐写法，避免溢出
        }
    });
    System.out.println(students);
}
```

---

### 三、Map 系列集合

#### 1. Map 概述

- **Map 称为双列集合**，格式：`{key1=value1, key2=value2, ...}`，一次存一对数据作为一个元素；
- 每个元素 `key=value` 称为一个**键值对**，也叫**键值对对象**或**一个 Entry 对象**，所以 Map 也叫"键值对集合"；
- **键不允许重复，值可以重复；键和值一一对应，每个键只能找到自己对应的值**。

Map 系列集合的特点都由**键**决定，值只是附属品：

- **HashMap**（用得最多）：键无序、不重复、无索引；
- **LinkedHashMap**：键有序（按添加顺序）、不重复、无索引；
- **TreeMap**：键按大小默认升序排序、不重复、无索引。

```java
// HashMap：键无序、不重复、无索引
Map<String, Integer> map = new HashMap<>();
map.put("小米手机", 1);
map.put("华为手机", 3);
map.put("荣耀手机", 2);
map.put("红米手机", 1);
map.put("红米手机", 1); // 键重复，覆盖旧值
System.out.println(map); // {荣耀手机=2, 小米手机=1, 华为手机=3, 红米手机=1}
```

```java
// LinkedHashMap：键有序（按添加顺序）
Map<String, Integer> map = new LinkedHashMap<>();
map.put("手机", 1);
map.put("java书籍", 2);
map.put("玩具", 1);
System.out.println(map); // {手机=1, java书籍=2, 玩具=1}
```

```java
// TreeMap：键按大小升序
Map<Integer, String> map = new TreeMap<>();
map.put(1, "java");
map.put(23, "前端");
map.put(3, "AI");
System.out.println(map); // {1=java, 3=AI, 23=前端}
```

**应用场景**：需要存储一一对应的数据时（如商品名对应价格、姓名对应成绩、省份对应城市），就用 Map。

#### 2. Map 的常用方法

Map 是双列集合的祖宗接口，以下方法全部双列集合都能使用：

| 方法 | 说明 |
| --- | --- |
| `V put(K key, V value)` | 添加/修改键值对（键重复则覆盖旧值） |
| `V remove(Object key)` | 根据键删除整个键值对，返回被删的值 |
| `void clear()` | 清空集合 |
| `V get(Object key)` | 根据键获取对应的值 |
| `Set<K> keySet()` | 获取全部键的集合 |
| `Collection<V> values()` | 获取全部值的集合 |
| `boolean containsKey(Object key)` | 判断是否包含某个键 |
| `boolean containsValue(Object value)` | 判断是否包含某个值 |
| `boolean isEmpty()` | 判断集合是否为空 |
| `int size()` | 获取键值对个数 |
| `void putAll(Map m)` | 把另一个 Map 的数据全部倒入 |

```java
public static void main(String[] args) {
    Map<String, Integer> map = new HashMap<>();
    // 增
    map.put("小米手机", 1);
    map.put("华为手机", 2);
    map.put("苹果手机", 2);
    map.put("喂我手机", 3);
    map.put("红米手机", 3);
    map.put("喂我手机", 2); // 键重复，覆盖旧值
    map.put("荣耀", 2);
    map.put(null, null);   // HashMap 允许 null 键 null 值
    System.out.println(map);

    // 删：根据键删除整个元素
    map.remove("苹果手机");
    System.out.println(map);

    // 清空
    // map.clear();
    // System.out.println(map); // {}

    // 查：根据键获取值
    System.out.println(map.get("小米手机")); // 1

    // 获取全部键
    Set<String> keys = map.keySet();
    System.out.println(keys);

    // 获取全部值
    Collection<Integer> values = map.values();
    System.out.println(values);

    // 判断是否包含键 / 值
    System.out.println(map.containsKey("华为手机")); // true
    System.out.println(map.containsValue(2));       // true

    // 是否为空 / 元素个数
    System.out.println(map.isEmpty());
    System.out.println(map.size());
}
```

putAll 示例：

```java
Map<String, Integer> map = new HashMap<>();
map.put("java", 1);
map.put("AI", 2);

Map<String, Integer> map2 = new HashMap<>();
map2.put("前端", 3);
map2.put("数据分析", 2);

map.putAll(map2); // 把 map2 的数据全部倒入 map
System.out.println(map); // {java=1, AI=2, 前端=3, 数据分析=2}
```

#### 3. Map 的三种遍历方式

##### 3.1 方式一：键找值

先获取全部键，再遍历键、用 `get` 找值：

```java
public static void main(String[] args) {
    Map<String, Double> map = new HashMap<>();
    map.put("小哈", 99.5);
    map.put("小米", 100.0);
    map.put("小可", 60.0);
    map.put("小航", 88.0);

    // 第一步：获取全部键
    Set<String> keys = map.keySet();
    // 第二步：遍历键，根据键获取值
    for (String key : keys) {
        double value = map.get(key);
        System.out.println(key + ":" + value);
    }
}
```

##### 3.2 方式二：键值对 Entry

把每个"键值对"看成一个整体（Entry 对象）来遍历，更符合面向对象思想：

1. 调用 `entrySet()` 把所有 Entry 对象存入一个 Set 集合；
2. 遍历 Set，用 Entry 的 `getKey()` 和 `getValue()` 取键和值。

```java
public static void main(String[] args) {
    Map<String, Double> map = new HashMap<>();
    map.put("小哈", 99.5);
    map.put("小米", 100.0);
    map.put("小可", 60.0);
    map.put("小航", 88.0);

    // 第一步：获取全部 Entry 对象
    Set<Map.Entry<String, Double>> entrys = map.entrySet();
    // 第二步：遍历 Entry 集合，getKey 取键、getValue 取值
    for (Map.Entry<String, Double> entry : entrys) {
        String key = entry.getKey();
        Double value = entry.getValue();
        System.out.println(key + ":" + value);
    }
}
```

##### 3.3 方式三：Lambda forEach

```java
public static void main(String[] args) {
    Map<String, Double> map = new HashMap<>();
    map.put("小哈", 99.5);
    map.put("小米", 100.0);
    map.put("小可", 60.0);
    map.put("小航", 88.0);

    // 匿名内部类
    map.forEach(new BiConsumer<String, Double>() {
        @Override
        public void accept(String key, Double value) {
            System.out.println(key + ":" + value);
        }
    });

    // Lambda 简写（底层就是方式二）
    // map.forEach((key, value) -> System.out.println(key + ":" + value));
}
```

#### 4. HashMap 的底层原理

- HashMap 与 HashSet 的底层原理**一模一样**，都是基于哈希表实现。
- 实际上 **Set 系列集合的底层就是基于 Map 实现的**：Set 只取 Map 中的键，不要值。

哈希表结构：JDK 8 之前 = 数组 + 链表；JDK 8 开始 = 数组 + 链表 + 红黑树，是增删改查性能都较好的数据结构。

HashMap 的核心结论：

- 键无序、不重复、无索引（特点由键决定）；
- **键的唯一性依赖 `hashCode()` 和 `equals()` 两个方法**；
- 如果键是自定义类型的对象，重写 `hashCode()` 和 `equals()` 后，内容相同的对象就会被认为是重复的键。

往 HashMap 中存储键值对的底层步骤：

1. 第一次存储时，底层创建长度为 **16** 的数组；
2. 把键和值封装成一个 Entry 对象；
3. 根据**键**计算 hashCode 值（与值无关）；
4. 用 hashCode 值与数组长度做类似求余的运算，得到索引位置；
5. 该位置为 null：直接存入 Entry 对象；不为 null：继续第 6 步；
6. 调用 `equals` 比较两个键：
   - 返回 false：以链表形式往下挂；
   - 返回 true：认为键重复，**新的键值对覆盖旧的键值对**。

注意要点：

- 数组默认长度 16，负载因子 0.75，存入超过 12 个元素时按 **2 倍**扩容；
- 同一索引位置元素在 8 个以内（含 8）以链表存储：
  - JDK 7 链表采用**头插法**（新元素挂头部）；
  - JDK 8 链表采用**尾插法**（新元素挂尾部）；
- 同一索引位置元素超过 8 个（且数组长度 >= 64），转为红黑树存储。

**案例**：往 HashMap 中存 Student 对象作为键、工作单位作为值，要求姓名和年龄相同就认为键重复——Student 类重写 hashCode 和 equals（代码同第 4.2 节）：

```java
public static void main(String[] args) {
    Map<Student, String> map = new HashMap<>();
    map.put(new Student("小哈", 28, 1.65), "黑马");
    map.put(new Student("小哈", 28, 1.65), "百度"); // 键重复，覆盖"黑马"
    map.put(new Student("小米", 18, 1.85), "阿里");
    map.put(new Student("小徐", 38, 1.25), "京东");
    System.out.println(map); // "小哈"对应的值最终为"百度"
}
```

#### 5. LinkedHashMap 与 TreeMap

##### 5.1 LinkedHashMap

- 特点：键**有序**（按添加顺序）、不重复、无索引；
- 底层依然是哈希表，只是每个键值对额外多了一个**双链表**机制记录元素顺序（LinkedHashSet 的底层就是 LinkedHashMap）；
- 取元素时从头节点开始依次取下一个节点直到尾节点，所以有序。

```java
public static void main(String[] args) {
    Map<String, Integer> map = new LinkedHashMap<>();
    map.put("小米手机", 1);
    map.put("苹果手机", 2);
    map.put("小米手机", 3); // 键重复，值被覆盖，但位置不变
    map.put("华为手机", 1);
    map.put("红米手机", 2);
    System.out.println(map); // {小米手机=3, 苹果手机=2, 华为手机=1, 红米手机=2}
}
```

##### 5.2 TreeMap

- 特点：键不重复、无索引、**可排序**（按键的大小默认升序，只能对键排序）；
- 原理：与 TreeSet 一样基于红黑树，排序规则的指定方式也相同。

方式一：键的类实现 `Comparable` 接口，重写 `compareTo`：

```java
public class Student implements Comparable<Student> {
    // ... 属性、构造器、getter/setter 省略

    @Override
    public int compareTo(Student o) {
        return o.age - this.age; // 返回正数/负数/0；这里按年龄降序
    }
}
```

方式二：调用 TreeMap 有参构造器传入 `Comparator` 比较器（类不用改动）：

```java
public static void main(String[] args) {
    Map<Student, String> map = new TreeMap<>(new Comparator<Student>() {
        @Override
        public int compare(Student o1, Student o2) {
            return Double.compare(o1.getHeight(), o2.getHeight()); // 按身高升序
        }
    });
    // Lambda 写法：
    // Map<Student,String> map = new TreeMap<>((o1, o2) -> Double.compare(o1.getHeight(), o2.getHeight()));
    map.put(new Student("小哈", 28, 1.65), "兰州");
    map.put(new Student("小米", 18, 1.85), "兰州");
    map.put(new Student("小米", 18, 1.85), "杭州"); // 键重复，覆盖
    map.put(new Student("小花", 38, 1.55), "西安");
    map.put(new Student("小帅", 26, 1.65), "广州");
    System.out.println(map); // 按身高从低到高输出
}
```

#### 6. 集合嵌套

集合中的元素又是一个集合，就是集合嵌套。常见形式：Map 的值是一个 List。

案例：记录省份与其对应的多个城市，并能查询湖北省的城市：

```java
public static void main(String[] args) {
    // Map：键=省份名，值=该省的城市 List
    Map<String, List<String>> map = new HashMap<>();

    List<String> cities1 = new ArrayList<>();
    Collections.addAll(cities1, "南京市", "扬州市", "苏州市", "无锡市", "常州市");
    map.put("江苏省", cities1);

    List<String> cities2 = new ArrayList<>();
    Collections.addAll(cities2, "武汉市", "孝感市", "十堰市", "宜昌市", "鄂州市");
    map.put("湖北省", cities2);

    List<String> cities3 = new ArrayList<>();
    Collections.addAll(cities3, "石家庄市", "唐山市", "邢台市", "保定市", "张家口市");
    map.put("河北省", cities3);

    // Lambda 打印全部省份信息
    map.forEach((key, value) -> System.out.println(key + ":" + value));

    // 根据键查询湖北省的城市
    List<String> res = map.get("湖北省");
    for (String city : res) {
        System.out.println(city);
    }
}
```

---

### 四、综合案例

#### 1. 斗地主发牌（面向对象版，推荐）

需求：54 张牌（点数 `"3"~"2"`、四种花色、大小王），三个玩家各 17 张，3 张底牌；洗牌、发牌、捋牌（排序）、看牌；拿到红桃 3 的玩家为地主，红桃 3 在底牌中则随机选地主。

第一步：定义扑克牌类：

```java
public class PokerCard {
    private String number; // 点数
    private String color;  // 花色
    private int size;      // 牌的大小序号，用于排序

    public PokerCard(String number, String color, int size) {
        this.number = number;
        this.color = color;
        this.size = size;
    }

    public PokerCard() {}

    public String getNumber() { return number; }
    public void setNumber(String number) { this.number = number; }
    public String getColor() { return color; }
    public void setColor(String color) { this.color = color; }
    public int getSize() { return size; }
    public void setSize(int size) { this.size = size; }

    @Override
    public String toString() {
        return color + number;
    }
}
```

第二步：定义房间类，初始化时准备好 54 张牌：

```java
import java.util.*;

public class Room {
    private List<PokerCard> allCards = new ArrayList<>();

    public Room() {
        // 制作 54 张牌
        String[] numbers = {"3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K", "A", "2"};
        String[] colors = {"♣", "♦", "♠", "♥"};
        String[] wang = {"小王", "大王"};
        int size = 0;
        for (String number : numbers) {
            size++;
            for (String color : colors) {
                allCards.add(new PokerCard(number, color, size));
            }
        }
        for (String w : wang) {
            size++;
            allCards.add(new PokerCard("", w, size));
        }
        System.out.println("新牌：" + allCards);
    }

    // 第三步：启动游戏，完成洗牌、发牌、捋牌、看牌、定地主
    public void start() {
        // 洗牌
        Collections.shuffle(allCards);
        System.out.println("洗牌后：" + allCards);

        // 发牌
        List<PokerCard> user1 = new ArrayList<>();
        List<PokerCard> user2 = new ArrayList<>();
        List<PokerCard> user3 = new ArrayList<>();
        List<PokerCard> dipai = new ArrayList<>();

        for (int i = 0; i < allCards.size(); i++) {
            PokerCard p = allCards.get(i);
            if (i >= allCards.size() - 3) { // 最后 3 张是底牌
                dipai.add(p);
                continue;
            }
            if (i % 3 == 0) user1.add(p);
            else if (i % 3 == 1) user2.add(p);
            else user3.add(p);
        }

        // 捋牌（排序）
        sortPokerCard(user1);
        sortPokerCard(user2);
        sortPokerCard(user3);

        // 看牌
        System.out.println("用户1的牌：" + user1);
        System.out.println("用户2的牌：" + user2);
        System.out.println("用户3的牌：" + user3);
        System.out.println("底牌：" + dipai);

        // 定地主：谁有 ♥3 谁是地主；♥3 在底牌中则随机选
        String target = "♥3";
        if (diZhu(user1, target)) {
            System.out.println(target + " 在用户1中，用户1是地主！");
            addDipai(user1, dipai);
        } else if (diZhu(user2, target)) {
            System.out.println(target + " 在用户2中，用户2是地主！");
            addDipai(user2, dipai);
        } else if (diZhu(user3, target)) {
            System.out.println(target + " 在用户3中，用户3是地主！");
            addDipai(user3, dipai);
        } else {
            System.out.println(target + " 在底牌中，开始随机选地主");
            Random random = new Random();
            int num = random.nextInt(3) + 1; // 1~3
            switch (num) {
                case 1 -> { System.out.println("选中用户1为地主！"); addDipai(user1, dipai); }
                case 2 -> { System.out.println("选中用户2为地主！"); addDipai(user2, dipai); }
                case 3 -> { System.out.println("选中用户3为地主！"); addDipai(user3, dipai); }
            }
        }
    }

    // 底牌交给地主，并重新排序
    public static void addDipai(List<PokerCard> user, List<PokerCard> dipai) {
        user.addAll(dipai);
        sortPokerCard(user);
        System.out.println("排序后的地主牌：" + user);
    }

    // 按 size 排序
    private static void sortPokerCard(List<PokerCard> user) {
        Collections.sort(user, new Comparator<PokerCard>() {
            @Override
            public int compare(PokerCard o1, PokerCard o2) {
                return Integer.compare(o1.getSize(), o2.getSize());
            }
        });
    }

    // 判断某玩家是否持有目标牌
    public static boolean diZhu(List<PokerCard> user, String target) {
        for (PokerCard p : user) {
            if ((p.getColor() + p.getNumber()).equals(target)) {
                return true;
            }
        }
        return false;
    }
}
```

#### 2. 景点投票统计

需求：80 名学生从四个景点中选一个秋游地点，统计每个景点的投票数。

分析：用 List 收集 80 个选择，再用 `Map<景点, 票数>` 统计——遍历选择，Map 中没有该景点就存 `景点=1`，有就把值 +1。这是"单列数据分组统计"转双列集合的经典套路。

```java
public static void main(String[] args) {
    // 第一步：模拟 80 位学生的投票
    String[] selects = {"西湖", "灵隐寺", "法喜寺", "乌镇"};
    List<String> list = new ArrayList<>();
    Random r = new Random();
    for (int i = 0; i < 80; i++) {
        list.add(selects[r.nextInt(selects.length)]);
    }
    System.out.println(list);

    // 第二步：单列集合分组统计到双列集合
    Map<String, Integer> mapList = new HashMap<>();
    for (String s : list) {
        if (mapList.containsKey(s)) {
            mapList.put(s, mapList.get(s) + 1); // 已存在：票数 +1
        } else {
            mapList.put(s, 1);                  // 第一次出现：初始化为 1
        }
    }
    System.out.println(mapList); // 如 {法喜寺=21, 乌镇=17, 西湖=20, 灵隐寺=22}
}
```

#### 3. 统计文本中单词出现次数

需求：统计一段英文文本中每个单词出现的次数。思路与投票统计完全一致，区别在于先要按正则把句子切成单词。

```java
public static void main(String[] args) {
    String str = "The quick brown fox jumps over the lazy Dog. Dog! Dog! Why don you see the 3 dosgs?";
    // 按空格、句号、感叹号、问号、数字 3 切割
    String[] splitStr = str.split("[ .!?3]+");
    System.out.println(Arrays.toString(splitStr));

    Map<String, Integer> map = new HashMap<>();
    for (String s : splitStr) {
        if (map.containsKey(s)) {
            map.put(s, map.get(s) + 1);
        } else {
            map.put(s, 1);
        }
    }
    System.out.println(map); // {the=3, Dog=3, ...}
}
```

> 提示：`merge` 方法可以简化统计写法，如 `map.merge(s, 1, Integer::sum);` 一行完成"有则加 1、无则放 1"。

#### 本章小结

- Set 三兄弟：HashSet（哈希表，无序最快）、LinkedHashSet（哈希表+双链表，保序）、TreeSet（红黑树，排序）；自定义对象去重靠重写 `hashCode` + `equals`，排序靠 `Comparable` 或 `Comparator`。
- 哈希表：JDK 8 前 = 数组 + 链表；JDK 8 起 = 数组 + 链表 + 红黑树（链表 > 8 且数组 >= 64 树化）；默认容量 16、负载因子 0.75、扩容 2 倍。
- Map 三兄弟与 Set 一一对应：HashMap = HashSet 的底层，LinkedHashMap = LinkedHashSet 的底层，TreeMap = TreeSet 的底层；特点都由键决定。
- Map 遍历三方式：键找值（keySet + get）、键值对（entrySet）、Lambda（forEach）。
- Collections 工具类：`addAll`、`shuffle`、`sort`；可变参数 `类型...名` 本质是数组，只能有一个且放最后。

---

<div style="page-break-after: always;"></div>

## 第18章 JDK8 新特性：Stream 流、File 类与递归

本章包含三部分内容：JDK8 新增的 Stream 流 API（用于简洁地操作集合/数组数据）、File 类（用于操作文件和文件夹本身）、递归算法（常与 File 结合完成文件搜索等需求）。

---

### 一、Stream 流

#### 1.1 什么是 Stream

- **Stream 也叫 Stream 流**，是 JDK8 开始新增的一套 API（`java.util.stream.*`），用于操作集合或者数组中的数据。
- **优势**：Stream 流大量结合 Lambda 语法风格编程，提供了一种更强大、更简单的方式操作集合/数组数据，代码更简洁，可读性更好。

#### 1.2 引导案例

**需求**：把集合中所有以"张"开头，且是 3 个字的元素存储到一个新的集合。

```java
public static void main(String[] args) {
    List<String> names = new ArrayList<>();
    Collections.addAll(names, "张三丰", "周芷若", "张无忌", "曾阿牛", "金毛狮王", "张强");
    System.out.println(names); // [张三丰, 周芷若, 张无忌, 曾阿牛, 金毛狮王, 张强]
}
```

**方案 1：普通集合 API 实现**

```java
List<String> newList = new ArrayList<>();
// 增强for循环遍历原来的集合names
for (String name : names) {
    // 判断遍历到的值name，是否以张开头并且长度为3，满足条件就添加到新集合
    if (name.startsWith("张") && name.length() == 3) {
        newList.add(name);
    }
}
System.out.println(newList); // [张三丰, 张无忌]
```

**方案 2：Stream 流实现**

```java
List<String> newNames = names.stream().filter(str -> str.startsWith("张"))
        .filter(str -> str.length() == 3).collect(Collectors.toList());
System.out.println(newNames); // [张三丰, 张无忌]
```

对比可见，Stream 流把"遍历—判断—收集"的流程用链式调用表达，代码意图更清晰。

#### 1.3 Stream 流的使用步骤

Stream 流的使用固定分为三步：

1. **获取流**：通过集合/数组得到一条 Stream 流；
2. **中间操作**：调用一系列中间方法（filter、sorted、map 等）对数据进行加工，返回的仍是 Stream 流，可以继续链式调用；
3. **终结操作**：调用终结方法（forEach、count、collect 等）收尾，终结方法调用后流就关闭了，不能再继续使用。

#### 1.4 获取 Stream 流

##### （1）获取单列集合的流

```java
public static void main(String[] args) {
    // 单列集合：直接调用 stream() 方法
    ArrayList<String> list = new ArrayList<>();
    Stream<String> stream = list.stream();

    HashSet<String> set = new HashSet<>();
    Stream<String> stream2 = set.stream();
}
```

##### （2）获取双列集合（Map）的流

Map 不能直接获取流，需要先转成单列视图：`keySet()`（所有键）、`values()`（所有值）、`entrySet()`（所有键值对）。

```java
public class Test3 {
    public static void main(String[] args) {
        // 双列集合
        HashMap<String, Integer> map = new HashMap<>();
        map.put("小米", 1);
        map.put("红米", 2);
        map.put("华为", 2);
        map.put("荣耀", 3);

        // 集合名.keySet() --- 获取所有键的集合，再获取stream流
        Stream<String> stream1 = map.keySet().stream();
        stream1.forEach(System.out::println);

        // 集合名.values() --- 获取所有值的集合，再获取stream流
        map.values().stream().forEach(v -> System.out.println(v));

        // 键值对stream流：entrySet() 得到 Set<Map.Entry<K,V>>
        map.entrySet().stream().forEach(e -> System.out.println(e.getKey() + ":" + e.getValue()));
    }
}
```

##### （3）获取数组的流

```java
public static void main(String[] args) {
    // 数组
    String[] names = {"阿牛", "昭昭", "杀阡陌"};
    // 方式1：Arrays 类提供的方法
    Stream<String> s1 = Arrays.stream(names);
    // 方式2：Stream 类提供的方法
    Stream<String> s2 = Stream.of(names);
}
```

#### 1.5 Stream 流的常见中间方法

中间方法的特点：**返回值仍然是 Stream 流**，可以继续链式调用。常用中间方法如下：

| 方法 | 作用 |
| --- | --- |
| `filter(Predicate)` | 过滤数据，lambda 返回 true 保留、false 拦截 |
| `sorted()` / `sorted(Comparator)` | 排序；无参按自然顺序升序，带参按指定规则排序 |
| `limit(long n)` | 只保留前 n 个元素 |
| `skip(long n)` | 跳过前 n 个元素 |
| `map(Function)` | 对元素进行加工，把一个类型的流转成另一个类型的流 |
| `distinct()` | 去除流中重复的元素（依赖 hashCode 和 equals） |
| `Stream.concat(s1, s2)` | 静态方法，合并两个流为一个流 |

##### （1）filter 数据过滤

filter 的 lambda 返回 true 表示数据保留，false 表示数据拦截。

```java
public static void main(String[] args) {
    ArrayList<String> list = new ArrayList<String>();
    Collections.addAll(list, "小花", "张三丰", "张无忌", "周芷若", "曾阿牛", "张天师");

    // 匿名内部类写法（理解原理）
    /*
    list.stream().filter(new Predicate<String>() {
        @Override
        public boolean test(String s) {
            return s.startsWith("张"); // 返回true保留，false拦截
        }
    }).forEach(v -> System.out.println(v));
    */

    // Lambda 写法：找到姓张的用户并输出
    list.stream().filter(s -> s.startsWith("张")).forEach(v -> System.out.println(v));
}
```

再看一个数值集合的例子：找出成绩大于等于 60 分的数据，升序后输出。

```java
List<Double> scores = new ArrayList<>();
Collections.addAll(scores, 82.0, 62.0, 33.0, 4.0, 95.0, 56.0, 60.0);
// 需求：找出成绩大于等于60分的数据，并升序后再输出
scores.stream().filter(score -> score >= 60).sorted().forEach(score -> System.out.println(score));
```

##### （2）对象集合使用 Stream

先准备测试数据：

```java
List<Student> students = new ArrayList<>();
Student s1 = new Student("蜘蛛精", 28, 172.6);
Student s2 = new Student("蜘蛛精", 28, 172.6);
Student s3 = new Student("紫霞", 23, 167.5);
Student s4 = new Student("白晶晶", 25, 169.0);
Student s5 = new Student("牛魔王", 35, 183.3);
Student s6 = new Student("花仙子", 18, 168.0);
Student s7 = new Student("何仙姑", 18, 158.0);
Collections.addAll(students, s1, s2, s3, s4, s5, s6, s7);
```

**sorted：指定规则排序**

```java
// 需求1：找出年龄大于等于23，且年龄小于等于30岁的学生，并按照年龄降序输出
/*
students.stream().filter(student -> student.getAge() >= 23 && student.getAge() <= 30)
        .sorted(new Comparator<Student>() {
            @Override
            public int compare(Student o1, Student o2) {
                return o2.getAge() - o1.getAge();
            }
        }).forEach(student -> System.out.println(student));
*/
students.stream().filter(student -> student.getAge() >= 23 && student.getAge() <= 30)
        .sorted((o1, o2) -> o2.getAge() - o1.getAge())
        .forEach(student -> System.out.println(student));
```

**limit：获取前几个元素**

```java
// 需求2：取出身高最高的前3名学生，并输出
System.out.println("-----------身高最高的前三位-------------");
students.stream().sorted((o1, o2) -> Double.compare(o2.getHeight(), o1.getHeight()))
        .limit(3).forEach(student -> System.out.println(student));
```

**skip：跳过前几个元素**

```java
// 需求3：求出身高倒数的两名学生
System.out.println("-----------身高倒数的2名-------------");
students.stream().sorted((o1, o2) -> Double.compare(o2.getHeight(), o1.getHeight()))
        .skip(students.size() - 2).forEach(student -> System.out.println(student));
```

**map：加工元素并返回新流**。作用是可以把一个类型的流转成另一个类型的流（lambda 的返回值就是进入新流的数据）。

**distinct：去除流中重复的元素**。

```java
// 需求4：找出身高超过168的学生叫什么名字，要求去除重复的名字，再输出
System.out.println("-----------身高超过168的学员的名字-------------");
students.stream().filter(student -> student.getHeight() > 168)
        .map(student -> student.getName()).distinct().forEach(student -> System.out.println(student));

// map 的匿名内部类写法（理解原理）
/*
students.stream().filter(student -> student.getHeight() > 168)
.map(new Function<Student, Object>() {
    @Override
    public Object apply(Student student) {
        return student.getName(); // 返回值就是收集到流中的数据
    }
}).distinct().forEach(student -> System.out.println(student));
*/
```

> 注意：`distinct()` 去重对象时，依赖对象的 `hashCode()` 和 `equals()` 方法，实体类需要重写这两个方法。

##### （3）concat 合并流

`Stream.concat(流1, 流2)` 是静态方法，将两个流合并成一个流：

```java
ArrayList<String> list01 = new ArrayList<>(List.of("hello", "world"));
ArrayList<String> list02 = new ArrayList<>(List.of("hello", "Html"));
Stream.concat(list01.stream(), list02.stream()).forEach(c -> System.out.println(c));
```

#### 1.6 Stream 流的常见终结方法

**终结方法**：调用完成后不再返回 Stream，流就关闭了，后面不能再调用其他流方法。常用终结方法如下：

| 方法 | 作用 |
| --- | --- |
| `forEach(Consumer)` | 遍历流中的每个元素 |
| `count()` | 统计流中元素个数，返回 long |
| `max(Comparator)` | 获取最大值元素，返回 Optional |
| `min(Comparator)` | 获取最小值元素，返回 Optional |
| `collect(Collector)` | 把结果收集到集合中 |
| `toArray()` | 把结果收集到数组中 |

准备测试数据（同上）：

```java
List<Student> students = new ArrayList<>();
Student s1 = new Student("蜘蛛精", 28, 172.6);
Student s2 = new Student("蜘蛛精", 28, 172.6);
Student s3 = new Student("紫霞", 23, 167.5);
Student s4 = new Student("白晶晶", 25, 169.0);
Student s5 = new Student("牛魔王", 35, 183.3);
Student s6 = new Student("花仙子", 18, 168.0);
Student s7 = new Student("何仙姑", 18, 158.0);
Collections.addAll(students, s1, s2, s3, s4, s5, s6, s7);
// 需求1：计算出身高超过168的学生有几人
// 需求2：找出身高最高的学生对象，并输出
// 需求3：找出身高最矮的学生对象，并输出
// 需求4：找出身高超过170的学生对象，并放到一个新集合中去返回
```

**count：统计元素个数**

```java
// 需求1：计算出身高超过168的学生有几人
long count = students.stream().filter(s -> s.getHeight() > 168).count();
System.out.println(count);
```

**max：获取最大值元素**

```java
// 需求2：找出身高最高的学生对象，并输出
Student s = students.stream().max((o1, o2) -> Double.compare(o1.getHeight(), o2.getHeight())).get();
System.out.println(s);
```

**min：获取最小值元素**

```java
// 需求3：找出身高最矮的学生对象，并输出
Student s = students.stream().min((o1, o2) -> Double.compare(o2.getHeight(), o1.getHeight())).get();
System.out.println(s);
```

> max/min 返回的是 `Optional<T>` 对象，调用 `.get()` 取出其中的元素。

#### 1.7 收集 Stream 流（collect）

收集 Stream 流，就是把 Stream 操作后的结果转回到集合或者数组中返回。

> Stream 流是方便操作集合/数组的**手段**；集合/数组才是开发中的**目的**。

##### （1）收集到集合中

```java
// 需求：找出身高超过170的学生对象，并放到一个新集合中去返回

// 收集到 List 集合 --- collect(Collectors.toList())
List<Student> students1 = students.stream().filter(v -> v.getHeight() > 170).collect(Collectors.toList());
System.out.println(students1);

// 收集到 Set 集合 --- collect(Collectors.toSet())（自动去重）
Set<Student> students2 = students.stream().filter(v -> v.getHeight() > 170).collect(Collectors.toSet());
System.out.println(students2);

// 收集到 Map 集合 --- collect(Collectors.toMap(键的规则, 值的规则))
// 找出身高超过170的学生，把名字和身高存入Map，key=学生名，value=学生身高
/*
Map<String, Double> map = students.stream().filter(v -> v.getHeight() > 170).collect(Collectors.toMap(new Function<Student, String>() {
    @Override
    public String apply(Student student) {
        return student.getName();
    }
}, new Function<Student, Double>() {
    @Override
    public Double apply(Student student) {
        return student.getHeight();
    }
}));
*/
Map<String, Double> map = students.stream().filter(v -> v.getHeight() > 170).distinct()
        .collect(Collectors.toMap(student -> student.getName(), student -> student.getHeight()));
System.out.println(map);
```

##### （2）collect 补充：分组 groupingBy

`Collectors.groupingBy(分组规则)` 可以按指定属性对流中元素分组，还可以配合下游收集器做统计：

```java
// 分组：统计每个年龄的人是谁
// 结果形如：{18=[Student{name='花仙子', age=18, height=168.0}, Student{name='何仙姑', age=18, height=158.0}], ...}
Map<Integer, List<Student>> groupMap = students.stream().distinct().collect(Collectors.groupingBy(new Function<Student, Integer>() {
    @Override
    public Integer apply(Student student) {
        return student.getAge();
    }
}));
// Lambda 简化写法：
// Map<Integer, List<Student>> groupMap = students.stream().distinct().collect(Collectors.groupingBy(student -> student.getAge()));
System.out.println(groupMap);

// 分组计数：统计每个年龄的人有多少  结果：{18=2, 35=1, 23=1, 25=1, 28=1}
Map<Integer, Long> countMap = students.stream().distinct().collect(Collectors.groupingBy(new Function<Student, Integer>() {
    @Override
    public Integer apply(Student student) {
        return student.getAge();
    }
}, Collectors.counting()));
System.out.println(countMap);

// 分组平均值：统计每个年龄段的人平均身高  结果：{18=163.0, 35=183.3, 23=167.5, 25=169.0, 28=172.6}
/*
Map<Integer, Double> avgMap = students.stream().distinct().collect(Collectors.groupingBy(new Function<Student, Integer>() {
    @Override
    public Integer apply(Student student) {
        return student.getAge();
    }
}, Collectors.averagingDouble(new ToDoubleFunction<Student>() {
    @Override
    public double applyAsDouble(Student value) {
        return value.getHeight(); // 根据身高计算平均身高
    }
})));
*/
Map<Integer, Double> avgMap = students.stream().distinct().collect(
        Collectors.groupingBy(student -> student.getAge(),
                Collectors.averagingDouble(value -> value.getHeight())));
System.out.println(avgMap);
```

##### （3）收集到数组中

```java
// 收集为 Object 数组
Object[] arr1 = students.stream().filter(v -> v.getHeight() > 170).toArray();
System.out.println(Arrays.toString(arr1));

// 存成指定类型（Student）数组：lambda 的参数 len 是数组长度
Student[] arr2 = students.stream().filter(v -> v.getHeight() > 170).toArray(len -> new Student[len]);
System.out.println(Arrays.toString(arr2));
```

---

### 二、File 类

#### 2.1 什么是 File

目前写代码存储数据可以用变量、数组、对象、集合，但这些数据都存储在**内存**中，程序结束或断点后数据就消失了，不能永久存储。

要长久保存数据，可以将数据以**文件**的形式存在硬盘里，即使程序结束、断点，只要硬盘没坏数据就永久存在。

- **File 类表示当前系统下的文件（也可以是文件夹）**，通过 File 类提供的方法可以获取文件大小、判断文件是否存在、创建文件、创建文件夹等。
- **重要注意：File 对象只能对文件（或文件夹）本身进行操作，不能操作文件中的内容**（读写内容要用 IO 流）。

#### 2.2 File 对象的创建

常用构造器：`new File(路径字符串)`，路径可以指向文件也可以指向文件夹。

```java
// 创建一个File对象，指代某个具体文件/文件夹
File f1 = new File("D:\\code\\beike\\file\\src");
File f2 = new File("D:/code/beike/file/src");
```

路径分隔符的注意事项：

- Windows 用 `\`（在 Java 代码中需转义为 `\\`），Linux/Mac 用 `/`；
- 推荐使用 `File.separator` 实现跨平台，它会根据操作系统自动取对应分隔符：

```java
File f3 = new File("D:" + File.separator + "code" + File.separator + "beike"
        + File.separator + "file" + File.separator + "src");
```

#### 2.3 路径的分类

路径分为绝对路径和相对路径两种：

- **绝对路径：带有盘符的路径**，从盘符根目录开始定位。

```java
File f1 = new File("D:\\code\\beike\\file\\src");
```

- **相对路径：不带盘符**，默认直接到当前工程（项目）目录下寻找文件。

```java
File f1 = new File("beike\\file\\src");
```

#### 2.4 File 的判断和获取方法

```java
// 1. 创建文件对象，指代某个文件
File f1 = new File("D:\\code\\beike\\file\\src\\bxiaoha.txt");
File f2 = new File("D:\\code\\beike\\file\\src");

// 2. public boolean exists()：判断当前文件对象对应的路径是否存在，存在返回true
System.out.println(f1.exists()); // true
System.out.println(f2.exists()); // false

// 3. public boolean isFile()：判断当前文件对象指代的是否是文件，是文件返回true
System.out.println(f1.isFile());      // true
System.out.println(f2.isFile());      // false

// 4. public boolean isDirectory()：判断指代的是否是文件夹，是文件夹返回true
System.out.println(f1.isDirectory()); // false
System.out.println(f2.isDirectory()); // true

// 5. public String getName()：获取文件的名称（包含后缀名）
System.out.println(f1.getName()); // bxiaoha.txt
System.out.println(f2.getName()); // src

// 6. public long length()：获取文件的大小，返回字节个数（一个汉字大概占1~3个字节）
System.out.println(f1.length());

// 7. public long lastModified()：获取文件的最后修改时间，返回毫秒值
System.out.println(f2.lastModified());
long time = f2.lastModified();
SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
System.out.println(sdf.format(time)); // 把毫秒值格式化成日期字符串

// 8. public String getPath()：获取创建文件对象时使用的路径
System.out.println(f1.getPath()); // D:\code\beike\file\src\bxiaoha.txt
System.out.println(f2.getPath()); // D:\code\beike\file\src
File f3 = new File("beike\\file\\src");
System.out.println(f3.getPath()); // beike\file\src

// 9. public String getAbsolutePath()：获取绝对路径
System.out.println(f3.getAbsolutePath()); // D:\code\beike\beike\file\src（工程目录 + 相对路径）
```

#### 2.5 创建和删除方法

| 方法 | 说明 |
| --- | --- |
| `createNewFile()` | 创建一个新的空文件；路径不存在则抛异常，文件已存在返回 false |
| `mkdir()` | 创建单级目录（一级文件夹）；父目录不存在则失败 |
| `mkdirs()` | 创建多级目录；父目录不存在会自动创建 |
| `delete()` | 删除文件或**空**文件夹；非空文件夹删除失败 |

注意事项：

- `mkdir()` 只能创建单级文件夹；`mkdirs()` 才能创建多级文件夹；
- `delete()` 可以直接删除文件，但文件夹只能删除**空的**，文件夹有内容删除不了。

```java
public static void main(String[] args) throws IOException {
    // 1. public boolean createNewFile()：创建一个新文件（内容为空），成功返回true
    File f1 = new File("D:\\code\\beike\\file\\src\\itheima1.txt");
    // 有异常，可以try处理或者暂时抛出
    System.out.println(f1.createNewFile()); // 第一次true，第二次false（文件已存在）

    // 2. public boolean mkdir()：创建文件夹，注意只能创建一级文件夹
    File f2 = new File("D:\\code\\beike\\file\\src\\haha");
    System.out.println(f2.mkdir()); // 第一次true，第二次false

    // 3. public boolean mkdirs()：创建文件夹，注意可以创建多级文件夹
    File f3 = new File("D:\\code\\com\\heima\\me");
    System.out.println(f3.mkdirs()); // 第一次true，第二次false

    // 4. public boolean delete()：删除文件或者空文件夹，注意不能删除非空文件夹
    System.out.println(f1.delete()); // true
    File f4 = new File("D:\\code\\beike\\file\\src");
    System.out.println(f4.delete()); // false（非空文件夹）
}
```

#### 2.6 遍历文件夹的方法

File 提供了两个方法获取一个文件夹中的内容：

```java
public static void main(String[] args) {
    // File f1 = new File("D:\\code\\beike\\file"); // 绝对路径
    File f1 = new File("file"); // 相对路径

    // 1. public String[] list()：获取当前目录下所有"一级文件名称"，放到字符串数组返回
    String[] str = f1.list();
    for (String name : str) {
        System.out.println(name);
    }

    // 2. public File[] listFiles()：（重点）获取当前目录下所有"一级文件对象"，放到File数组返回
    File[] files = f1.listFiles();
    for (File file : files) {
        System.out.println(file.getAbsolutePath());
    }
}
```

**listFiles() 的返回值规则（重要）**：

- 当主调是**文件**时，或者**路径不存在**时，返回 `null`；
- 当主调是**空文件夹**时，返回一个长度为 0 的数组；
- 当主调是**有内容的文件夹**时，将里面所有一级文件和文件夹的路径放在 File 数组中返回；
- 当文件夹里有**隐藏文件**时，隐藏文件也包含在 File 数组中；
- 当主调是文件夹但**没有权限访问**时，返回 `null`。

```java
public static void main(String[] args) {
    // 1. 当主调是文件时，或者路径不存在时，返回null
    File f1 = new File("D:\\code\\beike\\file\\src\\xiaoha.txt");
    File[] files = f1.listFiles();
    System.out.println(Arrays.toString(files)); // null

    // 2. 当主调是空文件夹时，返回一个长度为0的数组
    File f2 = new File("D:\\code\\beike\\file\\src\\haha");
    File[] files2 = f2.listFiles();
    System.out.println(Arrays.toString(files2)); // []

    // 3. 当主调是有内容的文件夹时，将所有一级文件和文件夹路径放在File数组中返回
    // 4. 隐藏文件也会包含在内
    // 5. 没有权限访问时返回null
}
```

> 开发中使用 `listFiles()` 后，一定要先判断返回值是否为 `null`、数组长度是否为 0，再遍历，避免空指针异常。

---

### 三、递归 Recursion

#### 3.1 什么是递归

递归是一种算法，从形式上来说，**方法调用自己**（自己调用自己）的形式称之为递归。

递归的两种形式：

- **直接递归**：方法自己调用自己；
- **间接递归**：方法调用其他方法，其他方法又回调这个方法。

```java
// 直接递归
public static void main(String[] args) {
    test1();
}
public static void test1() {
    System.out.println("------test1执行-----");
    test1(); // 直接方法递归
}
```

```java
// 间接递归
public static void main(String[] args) {
    test1();
}
public static void test1() {
    System.out.println("------test1执行-----");
    test2();
}
private static void test2() {
    test1(); // 间接递归
}
```

如果直接执行上面的代码，会进入死循环，方法不断压栈，最终导致栈内存溢出，抛出 **`StackOverflowError`（栈溢出错误）**。

> 因此递归必须要有**出口（终结点）**，并且每次调用都要向出口靠近。

#### 3.2 递归算法的执行流程

递归的核心思想：**往下传递，往上回归**。

**案例：计算 n 的阶乘**。例如 5 的阶乘 = 1 * 2 * 3 * 4 * 5。

推导规律：

```text
5的阶乘 = 1 * 2 * 3 * 4 * 5   ----- f(5) = f(4) * 5  --- f(n) = f(n-1) * n
4的阶乘 = 1 * 2 * 3 * 4       ----- f(4) = f(3) * 4
3的阶乘 = 1 * 2 * 3           ----- f(3) = f(2) * 3
2的阶乘 = 1 * 2               ----- f(2) = f(1) * 2
1的阶乘 = 1                   ----- f(1) = 1          --- 必须存在一个终结点（出口）
```

代码实现：

```java
public static void main(String[] args) {
    System.out.println(f(5));
}

public static int f(int n) {
    // 递归必须要有出口
    if (n == 1) {
        return 1;
    } else {
        return f(n - 1) * n;
    }
}
```

执行过程：`f(5)` 调用 `f(4)`、`f(4)` 调用 `f(3)`……一路传递到 `f(1)` 命中出口返回 1，然后开始回归：`f(2)=1*2`、`f(3)=2*3`……最终 `f(5)=120`。

**递归算法三要素：**

1. **递归公式**：`f(n) = f(n-1) * n`（把大问题拆成同形式的小问题）；
2. **递归终结点（出口）**：`f(1) = 1`，到这里不再继续递归；
3. **递归方向必须走向终结点**：每次调用参数都要向出口靠近（本例 `n` 每次减 1），否则永远到不了出口，必然栈溢出。

**方法栈中的完整执行流程（以 `f(5)` 为例）：**

- 向下传递（压栈）：`main` 方法先进栈；执行到 `f(5)` 时 `f` 方法压栈，参数 `n=5`，等待 `f(4)` 的结果；接着 `f(4)` 压栈（`n=4`，等待 `f(3)`）→ `f(3)` 压栈（`n=3`，等待 `f(2)`）→ `f(2)` 压栈（`n=2`，等待 `f(1)`）→ `f(1)` 压栈，命中出口，直接返回 1；
- 向上回归（弹栈）：`f(1)` 返回 1 后弹栈 → `f(2)` 拿到结果算出 `2 * 1 = 2`，返回 2 后弹栈 → `f(3)` 算出 `3 * 2 = 6` → `f(4)` 算出 `4 * 6 = 24` → `f(5)` 算出 `5 * 24 = 120`，弹栈回到 `main`；
- 最终 `main` 中 `result = 120`，输出「5的阶乘是：120」。

可见递归的本质就是**方法不断压栈、命中出口后再依次弹栈返回**；如果没有出口，栈内存被压满就会抛出 `StackOverflowError`。

#### 3.3 递归文件搜索（经典案例）

**需求**：从 D 盘中搜索 "Weixin.exe" 这个文件，找到后直接输出其位置（还可以启动它）。

**分析**：

1. 先找出 D 盘下的所有一级文件对象；
2. 遍历全部一级文件对象，判断是否是文件；
3. 如果是文件，判断文件名是否是目标文件；
4. 如果是文件夹，需要继续进入该文件夹，重复上述过程（递归）。

```java
import java.io.File;
import java.io.IOException;

public class Test2 {
    public static void main(String[] args) throws IOException {
        File file = new File("D:\\");
        findFile(file, "Weixin.exe"); // 如果需要启动程序需要抛异常
    }

    /**
     * 递归搜索文件
     * @param file     当前搜索的目录（开始路径）
     * @param fileName 要找的目标文件名
     */
    public static void findFile(File file, String fileName) throws IOException {
        // 递归出口：file为null、路径不存在、或者它本身是一个文件，都不用再往下找
        if (file == null || !file.exists() || file.isFile()) {
            return;
        }
        // 找出当前目录的一级内容 listFiles获取目录的一级目录
        File[] files = file.listFiles();
        // 判断获取的一级目录是否为空
        if (files == null || files.length == 0) {
            return;
        }
        // 遍历一级文件，判断是否为文件
        for (File file1 : files) {
            if (file1.isFile()) {
                // 遍历到的是文件，判断文件名和目标文件名是否一致
                if (file1.getName().equals(fileName)) {
                    // 一致，打印当前文件的绝对路径
                    System.out.println(file1.getAbsolutePath());
                    // 找到了还可以启动它
                    Runtime runtime = Runtime.getRuntime();
                    runtime.exec(file1.getAbsolutePath()); // 启动程序需要抛异常
                }
            } else {
                // 是文件夹，继续重复这个过程（递归）
                findFile(file1, fileName);
            }
        }
    }
}
```

这个案例体现了递归的典型用法：对文件夹结构这种"自己包含自己"的数据，每一层的处理逻辑完全相同，用递归表达最自然。关键是写好两个出口：`listFiles()` 返回 null/空数组时停止，以及遇到文件时不再深入。

---

### 本章小结

1. **Stream 流**是操作集合/数组的利器：先获取流（`stream()`、`Arrays.stream()`、`Stream.of()`），再用中间方法（filter、sorted、limit、skip、map、distinct、concat）链式加工，最后用终结方法（forEach、count、max、min、collect、toArray）收尾。
2. Stream 流只是**手段**，最终结果要用 `collect`/`toArray` 收集回集合或数组；`groupingBy` 可以完成分组、分组计数、分组求平均值等统计需求。
3. **File 类**操作的是文件/文件夹本身：判断存在/类型、获取名称大小时间、创建删除、遍历目录；注意 `mkdirs()` 建多级目录、`delete()` 只能删空目录、`listFiles()` 可能返回 null。
4. File 对象**不能**读写文件内容，内容读写需要后续的 IO 流。
5. **递归**是方法自己调用自己，必须有出口且逐步向出口靠近，否则栈溢出 `StackOverflowError`；递归天然适合处理文件夹树、阶乘这类层级结构问题。

---

<div style="page-break-after: always;"></div>

## 第19章 字符集与字节流

### 本章导读

`File` 类只能操作文件本身（创建、删除、查询属性），无法读写文件**内容**。要读写内容，需要 IO 流；而理解 IO 流的前提是理解**字符集**——字符在计算机中到底以什么形式存储。本章先讲字符集与编码解码，再讲 IO 流的分类体系，最后重点掌握字节输入流 `FileInputStream`、字节输出流 `FileOutputStream` 的用法，以及文件复制、文件上传综合案例和 IO 资源的释放方式。

---

### 一、字符集

#### 1.1 为什么需要字符集

计算机只能处理由 0 和 1 组成的二进制数据。为了让计算机能处理文字，人们把每一个字符用一个二进制数表示，这就是**编码**。不同国家有不同的语言，如果编码方式与解析方式不匹配，就会出现**乱码**。

- **编码（Encode）**：把字符按照指定的字符集转换成字节。
- **解码（Decode）**：把字节按照指定的字符集转换成字符。

#### 1.2 常见字符集

##### （1）标准 ASCII 字符集

ASCII（American Standard Code for Information Interchange，美国信息交换标准代码），包括英文、数字、符号等。

- 标准 ASCII 使用 **1 个字节存储一个字符**，字节首位是 0，总共可表示 128 个字符。

##### （2）GBK（汉字内码扩展规范，国标）

- 汉字编码字符集，包含 2 万多个汉字等字符。
- GBK 中**一个中文字符编码成两个字节**存储。
- GBK **兼容 ASCII** 字符集（英文、数字仍占 1 个字节）。

##### （3）Unicode 字符集（统一码 / 万国码）

- 国际组织制定的、可以容纳世界上所有文字和符号的字符集。
- 如果都用 UTF-32（每个字符固定 4 个字节），会造成存储空间浪费、通信效率降低，因此 Unicode 制定了可变长的编码方案 **UTF-8**。

##### （4）UTF-8

- 是 Unicode 字符集的一种编码方案，采取**可变长编码**：1 个字节、2 个字节、3 个字节、4 个字节四个长度区。
- 英文字符、数字等只占 **1 个字节**（兼容 ASCII），**汉字字符占用 3 个字节**。

#### 1.3 必须记住的三个结论

| 字符集 | 汉字占用 | 英文/数字占用 |
| --- | --- | --- |
| ASCII | 无汉字 | 1 个字节 |
| GBK | 2 个字节 | 1 个字节 |
| UTF-8 | 3 个字节 | 1 个字节 |

**注意 1**：编码时使用的字符集和解码时使用的字符集**必须一致**，否则会出现乱码。

**注意 2**：英文、数字一般不会乱码，因为绝大多数字符集都兼容 ASCII 编码。

#### 1.4 Java 代码完成编码和解码

```java
public static void main(String[] args) throws Exception {
    System.out.println("-------------------编码---------------------");
    String data = "I爱Y";

    // 默认按照平台字符集（UTF-8）进行编码
    byte[] bytes = data.getBytes();
    System.out.println(Arrays.toString(bytes));
    // [73, -25, -120, -79, 89]  汉字 3 字节，字节首位为 1 时显示为负数

    // 按照指定字符集进行编码
    byte[] bytes1 = data.getBytes("GBK"); // 需要抛出异常
    System.out.println(Arrays.toString(bytes1));
    // [73, -80, -82, 89]  汉字 2 字节

    System.out.println("-------------------解码---------------------");
    String s1 = new String(bytes);            // 平台默认编码（UTF-8）解码
    System.out.println(s1);                   // I爱Y

    String s2 = new String(bytes, "GBK");     // 用 GBK 解码 UTF-8 的字节 → 乱码
    System.out.println(s2);                   // I鐖盰

    String s3 = new String(bytes1, "UTF-8");  // 用 UTF-8 解码 GBK 的字节 → 乱码
    System.out.println(s3);                   // I??Y
}
```

要点：

- `String.getBytes()`：按平台默认字符集编码；`String.getBytes("GBK")`：按指定字符集编码。
- `new String(byte[])`：按平台默认字符集解码；`new String(byte[], "GBK")`：按指定字符集解码。
- 编码与解码字符集不一致就会乱码。

---

### 二、IO 流概述

#### 2.1 IO 流的作用

IO 流的作用：对文件或者网络中的数据进行**读、写**操作。

- **I = Input（输入）**：把数据从磁盘、网络中**读取**到程序（内存）中来，使用**输入流**。
- **O = Output（输出）**：把程序（内存）中的数据**写出**到磁盘、网络中去，使用**输出流**。
- 简单记：**输入流读数据，输出流写数据**（方向都以内存为基准）。

#### 2.2 IO 流的应用场景

文件数据的读取、程序数据的长久存储、文件拷贝、网络通信软件等都会使用 IO 流技术。

#### 2.3 IO 流的分类

按**流的方向**和**流中数据的最小单位**两个维度分类，共四类：

- **字节输入流**：以内存为基准，把磁盘文件/网络中的数据以**字节**形式读入内存。
- **字节输出流**：以内存为基准，把内存中的数据以**字节**形式写出到磁盘文件/网络。
- **字符输入流**：以内存为基准，把数据以**字符**形式读入内存。
- **字符输出流**：以内存为基准，把内存中的数据以**字符**形式写出。

#### 2.4 IO 流的体系

IO 流分为两大派系：

- **字节流**：分为字节输入流、字节输出流，**可以操作所有类型的文件**（文本、图片、视频、压缩包等）。
- **字符流**：分为字符输入流、字符输出流，**只能操作纯文本文件**（.txt、.java 等）。

命名规律（推荐记忆）：

- 字节流的类名以 **`Stream`** 结尾，如 `FileInputStream`、`FileOutputStream`。
- 字符流的类名以 **`Reader` / `Writer`** 结尾（...er），如 `FileReader`、`FileWriter`。

每种流的顶层都是抽象类，每个抽象类都有对应的实现类。

---

### 三、字节流

#### 3.1 FileInputStream（文件字节输入流）

**作用**：以内存为基准，把磁盘文件中的数据以字节形式读入内存。

##### 3.1.1 创建流对象

```java
// 方式1：先创建 File 对象，再作为参数传入
File file = new File("IO\\src\\1.txt");
FileInputStream fis01 = new FileInputStream(file);

// 方式2：直接把文件路径字符串作为参数传入（推荐）
FileInputStream fis02 = new FileInputStream("IO\\src\\1.txt");
```

##### 3.1.2 每次读取一个字节

`read()` 方法：每次读取 1 个字节并返回；如果没有数据可读，返回 **-1**。

```java
public static void main(String[] args) throws IOException {
    FileInputStream fis = new FileInputStream("IO\\src\\1.txt");

    int read1 = fis.read();
    int read2 = fis.read();
    int read3 = fis.read();
    // read 返回的是码表值，直接拼接是数字；需要强转成 char
    System.out.println("" + (char) read1 + (char) read2 + (char) read3);

    fis.close(); // 必须关闭流
}
```

手动逐个读取太繁琐，用循环读取：

```java
while (true) {
    int i = fis.read();
    if (i == -1) {   // 读到末尾
        break;
    }
    System.out.print((char) i);
}
```

**注意**：如果文件中有中文，这样读会乱码——`read()` 每次只读 1 个字节，而 UTF-8 中汉字占 3 个字节，只读到了三分之一个汉字。

##### 3.1.3 每次读取多个字节

单位换算：1024 字节 = 1KB，1024KB = 1M，1024M = 1G。文件较大时逐字节读取效率太低，可以用字节数组一次读取多个字节。

`read(byte[] buffer)`：每次用字节数组读取数据，**返回本次读取到的字节个数**；没有数据可读时返回 **-1**。

```java
public static void main(String[] args) throws IOException {
    FileInputStream fis = new FileInputStream("IO\\src\\1.txt");

    byte[] bytes = new byte[1024]; // 每次最多读 1KB
    int read = fis.read(bytes);    // 实际读取到的字节个数
    System.out.println(read);

    // 注意：不能直接 new String(bytes)，数组没读满的部分会被旧数据/空字符补全
    // 后两个参数：从下标 0 开始，只转换 read 个字节
    String s = new String(bytes, 0, read);
    System.out.println(s);

    fis.close();
}
```

文件大小超过数组长度时，用循环边读边处理：

```java
while (true) {
    int len = fis.read(bytes); // len 是本次读取到的字节数
    if (len == -1) {
        break;
    }
    System.out.println(new String(bytes, 0, len));
}
```

**中文乱码问题仍可能存在**：如果数组的分界点恰好切在一个汉字的中间（汉字 3 字节被拆到两次读取中），拼接处就会乱码。

##### 3.1.4 一次读取全部字节

`readAllBytes()`（**JDK 11 及以后支持**）：一次性读取文件中的全部字节，再整体转成字符串，就不会出现半个汉字的乱码问题。

```java
public static void main(String[] args) throws IOException {
    FileInputStream fis = new FileInputStream("IO\\src\\1.txt");

    byte[] bytes = fis.readAllBytes();
    System.out.println(bytes.length);
    System.out.println(new String(bytes));

    fis.close();
}
```

**注意**：一次读取全部字节虽然能解决乱码，但**文件不能过大**，否则可能导致内存溢出。

#### 3.2 FileOutputStream（文件字节输出流）

**作用**：以内存为基准，把内存中的数据以字节形式写出到文件。

##### 3.2.1 创建输出流（默认覆盖模式）

创建输出流对象时，如果目标文件不存在会自动创建；每次写入会**先清空文件原有内容**，再写入新数据，不会叠加。

```java
public static void main(String[] args) throws Exception {
    // 不推荐：先 new File 再传入
    // FileOutputStream fos = new FileOutputStream(new File("IO\\lib\\2.txt"));

    // 推荐：直接传路径字符串
    FileOutputStream fos = new FileOutputStream("IO\\lib\\2.txt");

    fos.write(97); // 写出字节 97，文件中显示字符 a
    fos.write(98);

    fos.close();
}
```

##### 3.2.2 创建输出流（追加模式）

构造方法第二个参数传 `true`，写入时**不清空原内容**，新数据在旧数据后面追加。

```java
// FileOutputStream fos = new FileOutputStream(new File("IO\\lib\\2.txt"), true);
FileOutputStream fos = new FileOutputStream("IO\\lib\\2.txt", true);
fos.write(97);
fos.write(98);
fos.close();
```

##### 3.2.3 写入数据的三种方式

```java
public static void main(String[] args) throws Exception {
    FileOutputStream fos = new FileOutputStream("IO\\lib\\2.txt");

    // 1. 每次写一个字节
    // fos.write(97);
    // fos.write(98);

    // 2. 每次写一个字节数组：字符串用 getBytes() 转字节数组
    String message = "hello Java!";
    byte[] bytes = message.getBytes();
    fos.write(bytes);

    // 3. 写字节数组的一部分
    // 参数1：要写出的数组  参数2：开始位置  参数3：写出的长度
    fos.write(bytes, 6, 4); // 从下标 6 开始写 4 个字节 → "Java"

    fos.close();
}
```

#### 3.3 字节流复制文件

把源文件用输入流读取、用输出流写出，即可完成复制。字节流可以复制**任意类型文件**（图片、视频等）。

##### 方式一：readAllBytes 一次性复制

```java
public class FileCopy {
    public static void main(String[] args) throws Exception {
        // 1、定义流
        FileInputStream inputStream = new FileInputStream("IO\\lib\\C\\1.jpg");
        FileOutputStream outputStream = new FileOutputStream("IO\\lib\\D\\new.jpg");

        // 2、一次性读取源文件全部字节
        byte[] bytes = inputStream.readAllBytes();
        // 3、写出到目标文件
        outputStream.write(bytes);

        // 关闭流
        inputStream.close();
        outputStream.close();
        System.out.println("复制完成！！");
    }
}
```

##### 方式二：边读边写（推荐，适合大文件）

实际开发中建议用字节数组缓冲区**边读边写**，避免大文件导致内存溢出。

```java
public static void main(String[] args) throws Exception {
    FileInputStream inputStream = new FileInputStream("IO\\lib\\C\\1.jpg");
    FileOutputStream outputStream = new FileOutputStream("IO\\lib\\D\\new1.jpg");

    byte[] bytes = new byte[1024]; // 缓冲区
    while (true) {
        int len = inputStream.read(bytes); // 本次读取到的字节数
        if (len == -1) {
            break;
        }
        // 关键：写出时必须用 write(bytes, 0, len)，
        // 不能写整个数组，否则最后一次会把多余的旧数据也写进去
        outputStream.write(bytes, 0, len);
    }

    inputStream.close();
    outputStream.close();
    System.out.println("复制完成！！");
}
```

**注意**：

- 流只能操作**文件**，不能直接操作文件夹；
- 复制文件夹需要**递归遍历**目录，逐个复制内部文件。

#### 3.4 扩展练习：文件上传

模拟文件上传：用户输入要上传的文件路径，程序把文件复制到"服务器"目录（模块下的 server 文件夹）。

##### 基本思路

```java
public static void main(String[] args) throws Exception {
    Scanner sc = new Scanner(System.in);
    System.out.println("请输入您要上传文件的路径");
    String filePath = sc.next();

    FileInputStream inputStream = new FileInputStream(filePath);
    FileOutputStream outputStream = new FileOutputStream("IO\\lib\\server\\1.txt");

    byte[] bytes = new byte[1024];
    while (true) {
        int len = inputStream.read(bytes);
        if (len == -1) {
            break;
        }
        outputStream.write(bytes, 0, len);
    }

    inputStream.close();
    outputStream.close();
    System.out.println("上传完成！！");
}
```

##### 问题：目标文件名不能写死

上面的代码把目标文件写死为 `1.txt`，上传其他文件时文件名和后缀都不对。需要从源路径中截取**真实的文件名和后缀**。

截取文件名的方法：

- 方案 1：字符串 `substring` 截取，找到最后一个分隔符的索引：`filePath.substring(filePath.lastIndexOf("\\") + 1)`。
- 方案 2（推荐）：JDK 7+ NIO 的 `Path` 类，自动适配系统分隔符（`\` / `/`），语义清晰。

`java.nio.file.Path` 常用方法：

- `Paths.get(path)`：把字符串路径解析为 `Path` 对象；
- `getParent()`：返回文件所在目录（`Path` 类型），根路径返回 `null`；
- `getFileName()`：返回文件名（`Path` 类型），需 `toString()` 转字符串。

```java
public static void main(String[] args) {
    String path = "D:\\植物大战僵尸杂交版v0.10.2性能版.zip";

    Path path1 = Paths.get(path);
    System.out.println(path1);                  // D:\植物大战僵尸杂交版v0.10.2性能版.zip
    System.out.println(path1.getParent());      // 父目录 D:\
    Path fileName = path1.getFileName();
    System.out.println(fileName);               // 植物大战僵尸杂交版v0.10.2性能版.zip
    String subString = fileName.toString();     // 转成字符串方便拼接
    System.out.println(subString);
}
```

##### 升级后的文件上传

```java
public static void main(String[] args) throws Exception {
    Scanner sc = new Scanner(System.in);
    System.out.println("请输入您要上传文件的路径");
    String filePath = sc.next();

    // 截取源文件名（含后缀）
    String fileName = Paths.get(filePath).getFileName().toString();

    FileInputStream inputStream = new FileInputStream(filePath);
    FileOutputStream outputStream = new FileOutputStream("IO\\lib\\server\\" + fileName);

    byte[] bytes = new byte[1024];
    while (true) {
        int len = inputStream.read(bytes);
        if (len == -1) {
            break;
        }
        outputStream.write(bytes, 0, len);
    }

    inputStream.close();
    outputStream.close();
    System.out.println("上传完成！！");
}
```

---

### 四、IO 流资源释放

#### 4.1 为什么要释放资源

流使用完之后必须关闭。如果在关闭流之前代码抛出了异常，程序终止，关闭语句执行不到，资源就一直被占用。

```java
public static void main(String[] args) throws Exception {
    FileInputStream inputStream = new FileInputStream("IO\\lib\\C\\1.jpg");
    FileOutputStream outputStream = new FileOutputStream("IO\\lib\\D\\new.jpg");

    int i = 1 / 0;   // 此处抛异常，后面的读写、close 都不会执行

    byte[] bytes = new byte[1024];
    while (true) {
        int len = inputStream.read(bytes);
        if (len == -1) {
            break;
        }
        outputStream.write(bytes, 0, len);
    }
    inputStream.close();
    outputStream.close();
}
```

注意一种"复制成功的假象"：上面代码执行后目标文件可能存在，但大小是 **0 字节**——创建输出流时会先创建空文件，随后异常终止，根本没写入内容。真正的复制成功必须是目标文件有内容、大小与源文件一致。

#### 4.2 JDK 7 以前：try...catch...finally

`finally` 代码区的特点：**无论 try 中的代码正常执行还是出现异常，finally 中的代码都会执行**（除非 JVM 终止），因此适合用来释放资源。

```java
try {
    // 有可能产生异常的代码
} catch (异常类 e) {
    // 处理异常的代码
} finally {
    // 释放资源的代码
}
```

优化文件复制案例：

```java
public static void main(String[] args) {
    FileInputStream inputStream = null;  // 必须在 try 外声明，finally 才能访问
    FileOutputStream outputStream = null;
    try {
        inputStream = new FileInputStream("IO\\lib\\C\\1.jpg");
        outputStream = new FileOutputStream("IO\\lib\\D\\new.jpg");

        byte[] bytes = new byte[1024];
        while (true) {
            int len = inputStream.read(bytes);
            if (len == -1) {
                break;
            }
            outputStream.write(bytes, 0, len);
        }
        System.out.println("复制完成！！");
    } catch (Exception e) {
        System.out.println("出现异常了~~~");
    } finally {
        // 必须判空：如果流对象还没创建成功就异常，直接 close 会空指针
        if (inputStream != null) {
            inputStream.close();
        }
        if (outputStream != null) {
            outputStream.close();
        }
    }
}
```

#### 4.3 JDK 7 及以后：try-with-resources

JDK 7 提供了 **try-with-resources** 语法，资源用完后会**自动调用 close 方法释放**，代码简洁很多。

```java
try (资源对象1; 资源对象2;) {
    使用资源的代码
} catch (异常类 e) {
    处理异常的代码
}
```

优化文件复制案例：

```java
public static void main(String[] args) {
    try (
            FileInputStream inputStream = new FileInputStream("IO\\lib\\C\\1.jpg");
            FileOutputStream outputStream = new FileOutputStream("IO\\lib\\D\\new.jpg");
    ) {
        byte[] bytes = new byte[1024];
        while (true) {
            int len = inputStream.read(bytes);
            if (len == -1) {
                break;
            }
            outputStream.write(bytes, 0, len);
        }
        System.out.println("复制完成！！");
    } catch (Exception e) {
        System.out.println("出现异常了~~~");
    }
    // 无需手动 close，try 结束时自动释放
}
```

原理与要求：

- try 的 `()` 里面只能放**资源对象**（流对象等）；
- 能放进去的资源类都实现了 **`AutoCloseable`** 接口，都有 `close()` 方法；
- 资源放到 `()` 里后，用完会被自动调用 `close()` 完成释放。

---

### 本章小结

1. 字符集解决字符如何存储的问题：ASCII 英文占 1 字节；GBK 汉字占 2 字节；UTF-8 汉字占 3 字节。编码和解码字符集不一致就会乱码。
2. Java 中用 `getBytes()` 编码、`new String(bytes)` 解码，都可以传入字符集名称参数。
3. IO 流以内存为基准分输入/输出，按数据单位分字节流（可操作所有文件）和字符流（只能操作纯文本）；字节流类名以 `Stream` 结尾，字符流以 `Reader/Writer` 结尾。
4. `FileInputStream` 的 `read()` 逐字节读（返回 -1 表示结束）、`read(byte[])` 按数组读（返回读取个数）、`readAllBytes()` 一次读完（JDK 11+，大文件可能内存溢出）。
5. `FileOutputStream` 写入默认覆盖原文件，构造参数加 `true` 为追加；`write(byte[], off, len)` 可写数组的一部分。
6. 文件复制推荐"字节数组缓冲区 + 边读边写"，写出时必须用 `write(bytes, 0, len)`。
7. 上传文件时用 `Paths.get(path).getFileName()` 截取真实文件名。
8. 资源释放优先使用 try-with-resources（自动 close，资源类需实现 `AutoCloseable`）；JDK 7 以前用 finally 并注意判空。

---

<div style="page-break-after: always;"></div>

## 第20章 字符流、缓冲流与 IO 高级流

### 本章导读

字节流读取中文时可能读到半个汉字导致乱码，`readAllBytes()` 虽然不乱码但不适合大文件。Java 为此提供了**字符流**——专门为读写纯文本数据而生。本章在字符流基础上，依次学习：提高读写性能的**缓冲流**、解决不同编码乱码的**转换流**、方便输出的**打印流**、连类型一起读写的**数据流**、以对象为单位读写的**序列化流**，最后了解第三方 **Commons-io** 框架和 JDK 官方 `Files` 工具类对 IO 操作的简化。

---

### 一、字符流

字符流是专门为读取**文本数据**设计的：它以字符为单位读取，底层会自动按编码把字节拼成完整字符，不会出现读到半个汉字的问题。

#### 1.1 FileReader（文件字符输入流）

**作用**：以内存为基准，把文件中的数据以字符形式读入内存。

##### 每次读取一个字符

`read()` 返回字符的编码值（int），需要强转成 `char`；读到末尾返回 -1。

```java
public static void main(String[] args) {
    // try-with-resources 自动关闭流
    try (FileReader fileReader = new FileReader("IOzifuliu\\lib\\C\\1.txt")) {
        int read = fileReader.read(); // 读取一个字符，返回编码值
        System.out.println((char) read);
    } catch (Exception e) {
        System.out.println("出现异常了~~~~");
    }
}
```

##### 每次读取多个字符

用 `char[]` 缓冲区批量读取，`read(char[])` 返回本次读取到的字符个数，读到末尾返回 -1。

```java
public static void main(String[] args) {
    try (FileReader fileReader = new FileReader("IOzifuliu\\lib\\C\\1.txt")) {
        char[] chars = new char[1024]; // 每次最多读 1024 个字符
        while (true) {
            int len = fileReader.read(chars); // 本次读取的字符个数
            if (len == -1) {
                break;
            }
            // 只把本次读到的 len 个字符转成字符串
            System.out.print(new String(chars, 0, len));
        }
    } catch (Exception e) {
        System.out.println("出现异常了~~~~");
    }
}
```

#### 1.2 FileWriter（文件字符输出流）

**作用**：以内存为基准，把内存中的数据以字符形式写出到文件。

##### 覆盖写出与追加写出

- `new FileWriter(path)`：默认模式，清空原内容后写出。
- `new FileWriter(path, true)`：追加模式，在原内容后面续写。

FileWriter 的 5 个写数据方法：

```java
public static void main(String[] args) {
    // 第二个参数传 true 即为追加模式
    try (FileWriter fileWriter = new FileWriter("IOzifuliu\\lib\\C\\2.txt")) {
        // 1. write(int c)：写一个字符
        fileWriter.write(97);
        fileWriter.write('a');
        fileWriter.write('哈');

        // 2. write(String c)：写一个字符串
        fileWriter.write("我爱你中国");

        // 3. write(String c, int pos, int len)：写字符串的一部分
        fileWriter.write("我爱你中国", 3, 2); // 从下标3开始写2个字符 → "中国"

        // 4. write(char[] buffer)：写一个字符数组
        char[] chars = {'黑', '马', '程', '序', '员'};
        fileWriter.write(chars);

        // 5. write(char[] buffer, int pos, int len)：写字符数组的一部分
        fileWriter.write(chars, 2, 3); // 从下标2开始写3个字符 → "程序员"
    } catch (Exception e) {
        System.out.println("出现了异常~~~");
    }
}
```

##### 重要注意事项：必须刷新或关闭才生效

**字符输出流写出数据后，必须刷新流（`flush`）或者关闭流（`close`），写出去的数据才能真正生效。** 原因是字符流底层有缓冲区，数据先存在内存中。

```java
public static void main(String[] args) throws IOException {
    FileWriter fw = new FileWriter("IOzifuliu\\lib\\C\\4.txt");
    fw.write(97);
    fw.write("我爱你中国");

    fw.flush(); // 刷新：把内存缓冲区的数据立即写到文件，刷新后还能继续写
    fw.write("天天开心快乐！");

    fw.close(); // 关闭：也会先刷新缓冲区，但关闭后不能再写数据
}
```

##### 换行

FileWriter 不会自动换行，需要手动写换行符：

- Windows 换行：`"\r\n"`
- Mac、Linux 换行：`"\n"`

```java
public static void main(String[] args) {
    try (FileWriter fw = new FileWriter("IOzifuliu\\lib\\C\\denggao.txt")) {
        fw.write("登高");
        fw.write("\r\n");
        fw.write("风急天高猿啸哀，");
        fw.write("\r\n");
        fw.write("渚清沙白鸟飞回。");
        fw.write("\r\n");
        fw.write("无边落木萧萧下，");
        fw.write("\r\n");
        fw.write("不尽长江滚滚来。");
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

#### 1.3 综合案例：复制文本并转大写

需求：把 `LittleStar.txt` 的内容复制到 `NewLittleStar.txt`，同时将所有字母转为大写。

```java
public static void main(String[] args) {
    try (
            FileReader fr = new FileReader("IOzifuliu\\lib\\C\\LittleStar.txt");
            FileWriter fw = new FileWriter("IOzifuliu\\lib\\C\\NewLittleStar.txt")
    ) {
        char[] chars = new char[1024];
        while (true) {
            int len = fr.read(chars);
            if (len == -1) {
                break;
            }
            String str = new String(chars, 0, len);
            str = str.toUpperCase();      // 转大写
            fw.write(str);                // 写出
        }
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

---

### 二、缓冲流

#### 2.1 缓冲流的分类和作用

**缓冲流的作用：对原始流进行包装，提高原始流读写数据的性能。** 缓冲流不能单独使用，必须依赖原始流。

| 缓冲流 | 包装的原始流 |
| --- | --- |
| `BufferedInputStream` | 字节输入流 InputStream |
| `BufferedOutputStream` | 字节输出流 OutputStream |
| `BufferedReader` | 字符输入流 Reader |
| `BufferedWriter` | 字符输出流 Writer |

##### 性能提升的原理

缓冲流底层自带一个 **8KB（8192）的缓冲数组**：

- **读数据时**：先用原始输入流一次性读 8KB 数据存入缓冲流内部数组（"一次多囤点货"），程序再从这个数组中逐个/逐批取数据，减少与磁盘的交互次数。
- **写数据时**：先把数据写到缓冲流内部的 8KB 数组中（"先攒一车货"），数组存满后再通过原始输出流一次性写到目标文件（"一次性运走"）。

#### 2.2 字节缓冲流

```java
public static void main(String[] args) {
    try (
            FileInputStream inputStream = new FileInputStream("bufferDome\\lib\\C\\1.txt");
            BufferedInputStream bis = new BufferedInputStream(inputStream);   // 包装原始字节输入流
            FileOutputStream outputStream = new FileOutputStream("bufferDome\\lib\\C\\new1.txt");
            BufferedOutputStream bos = new BufferedOutputStream(outputStream) // 包装原始字节输出流
    ) {
        byte[] bytes = new byte[1024];
        while (true) {
            int len = bis.read(bytes); // 注意：读写都调用缓冲流的方法
            if (len == -1) {
                break;
            }
            bos.write(bytes, 0, len);
        }
        System.out.println("复制完成！！");
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

也可以用多态方式定义：

```java
InputStream inputStream = new FileInputStream("bufferDome\\lib\\C\\1.txt");
InputStream bis = new BufferedInputStream(inputStream);
OutputStream outputStream = new FileOutputStream("bufferDome\\lib\\C\\new1.txt");
OutputStream bos = new BufferedOutputStream(outputStream);
```

#### 2.3 字符缓冲输入流 BufferedReader

自带 8KB 字符缓冲池，提高字符输入流的读取性能。创建时需要在构造方法中传入一个原始字符输入流（如 `FileReader`）。

**新增功能：按行读取。**

- `String readLine()`：读取一行数据返回；读到文件末尾返回 `null`（注意不是 -1）。

```java
public static void main(String[] args) {
    try (
            FileReader fr = new FileReader("bufferDome\\lib\\C\\denggao.txt");
            BufferedReader br = new BufferedReader(fr)
    ) {
        String line;
        while ((line = br.readLine()) != null) { // 每次读一行，末尾返回 null
            System.out.println(line);
        }
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

#### 2.4 字符缓冲输出流 BufferedWriter

自带 8KB 字符缓冲池，提高字符输出流的写出性能。创建时传入原始字符输出流（如 `FileWriter`）。

**新增功能：换行方法 `newLine()`**，可跨平台自动使用对应系统的换行符。

```java
public static void main(String[] args) {
    try (
            FileWriter fw = new FileWriter("bufferDome\\lib\\D\\登高.txt");
            BufferedWriter bw = new BufferedWriter(fw)
    ) {
        bw.write("登高");
        bw.newLine(); // 换行，等价于自动写 \r\n 或 \n
        bw.write("风急天高猿啸哀，");
        bw.newLine();
        bw.write("渚清沙白鸟飞回。");
        bw.newLine();
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

#### 2.5 原始流与缓冲流性能测试

用 `System.currentTimeMillis()` 记录复制大文件前后的毫秒数求时间差，可以对比出缓冲流的性能优势。

```java
public static void main(String[] args) {
    copy1(); // 原始流 + 数组
    copy2(); // 缓冲流 + 数组
}

// 原始字节流（数组方式）
private static void copy1() {
    long startTime = System.currentTimeMillis();
    try (
            FileInputStream fis = new FileInputStream("D:\\test.zip");
            FileOutputStream fos = new FileOutputStream("bufferDome\\lib\\D\\new1.zip")
    ) {
        byte[] buf = new byte[1024];
        int len;
        while ((len = fis.read(buf)) != -1) {
            fos.write(buf, 0, len);
        }
    } catch (Exception e) {
        e.printStackTrace();
    }
    long endTime = System.currentTimeMillis();
    System.out.println("原始流数组耗时：" + (endTime - startTime) + "ms");
}

// 字节缓冲流
private static void copy2() {
    long startTime = System.currentTimeMillis();
    try (
            FileInputStream fis = new FileInputStream("D:\\test.zip");
            BufferedInputStream bis = new BufferedInputStream(fis);
            FileOutputStream fos = new FileOutputStream("bufferDome\\lib\\D\\new2.zip");
            BufferedOutputStream bos = new BufferedOutputStream(fos)
    ) {
        byte[] bytes = new byte[1024];
        int len;
        while ((len = bis.read(bytes)) != -1) {
            bos.write(bytes, 0, len);
        }
    } catch (Exception e) {
        e.printStackTrace();
    }
    long endTime = System.currentTimeMillis();
    System.out.println("缓冲流耗时：" + (endTime - startTime) + "ms");
}
```

#### 2.6 缓冲流综合案例

##### 案例 1：复制文本、转大写并加行号

需求：复制 `LittleStar.txt` 到新文件，所有字母转大写，并在每行开头加行号（格式 `1.`、`2.`...）。

思路：不一定边读边写，可以先把每行数据读到 `ArrayList` 中，处理完再统一写出。

```java
public static void main(String[] args) {
    try (
            FileReader fr = new FileReader("IOzifuliu\\lib\\C\\LittleStar.txt");
            BufferedReader br = new BufferedReader(fr);
            FileWriter fw = new FileWriter("IOzifuliu\\lib\\C\\NewLittleStar.txt");
            BufferedWriter bw = new BufferedWriter(fw)
    ) {
        ArrayList<String> list = new ArrayList<>();
        String line;
        while ((line = br.readLine()) != null) {
            list.add(line); // 先把每行存入集合
        }
        // 统一处理：加行号 + 转大写后写出
        for (int i = 0; i < list.size(); i++) {
            bw.write((i + 1) + "." + list.get(i).toUpperCase());
            bw.newLine();
        }
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

##### 案例 2：恢复《出师表》的文章顺序

需求：文件中每行以序号开头（如 `3.臣本布衣...`）但顺序被打乱，需按序号升序恢复到新文件。

思路：按行读入集合 → 按每行开头的序号排序 → 逐行写出。

用 `Collections.sort` + `Comparator` 实现：

```java
public static void main(String[] args) {
    try (
            BufferedReader br = new BufferedReader(new FileReader("bufferDome\\lib\\C\\出师表.txt"));
            BufferedWriter bw = new BufferedWriter(new FileWriter("bufferDome\\lib\\C\\new出师表.txt"))
    ) {
        ArrayList<String> list = new ArrayList<>();
        String s;
        while ((s = br.readLine()) != null) {
            list.add(s);
        }
        // 按每行 "." 前的序号（数字）升序排序
        Collections.sort(list, new Comparator<String>() {
            @Override
            public int compare(String o1, String o2) {
                String[] s1 = o1.trim().split("\\.");
                String[] s2 = o2.trim().split("\\.");
                return Integer.parseInt(s1[0]) - Integer.parseInt(s2[0]);
            }
        });
        for (String line : list) {
            bw.write(line);
            bw.newLine();
        }
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

用 `TreeSet` 实现（TreeSet 本身有序，但默认按首字符 ASCII 排序，遇到 10、11、12 这样的序号会排错，必须在构造器中自定义排序规则）：

```java
TreeSet<String> treeSet = new TreeSet<>(new Comparator<String>() {
    @Override
    public int compare(String o1, String o2) {
        String[] s1 = o1.split("\\.");
        String[] s2 = o2.split("\\.");
        // 按数字大小比较，而不是字符串逐字符比较
        return Integer.parseInt(s1[0]) - Integer.parseInt(s2[0]);
    }
});
```

---

### 三、转换流

#### 3.1 FileReader 的乱码问题

- FileReader 读取文件时，**默认只能按 UTF-8 编码**读取。
- 如果读取 GBK 编码的文件就会乱码：FileReader 遇到汉字默认按 3 个字节读取，而 GBK 中一个汉字只占 2 个字节，字节拼错自然乱码。

结论：

- 代码编码与文本文件编码**一致**时，字符流读取**不会乱码**；
- 两者编码**不一致**时，字符流读取**就会乱码**，需要转换流解决。

#### 3.2 转换流的两类

- **InputStreamReader（字符输入转换流）**：解决不同编码时字符流读取文本乱码的问题。
- **OutputStreamWriter（字符输出转换流）**：控制写出去的字符使用什么字符集编码。

#### 3.3 InputStreamReader（字符输入转换流）

**解决思路**：先获取文件的原始字节输入流，再按文件**真实的字符集**把它包装成字符输入流，这样读出的字符就不乱码了。

```java
public static void main(String[] args) {
    try (
            // 1. 原始字节输入流
            FileInputStream fis = new FileInputStream("StreamReaderDemo\\lib\\1.txt");
            // 2. 按真实编码（GBK）把字节流转换成字符流
            InputStreamReader isr = new InputStreamReader(fis, "GBK");
            // 3. 再包装成缓冲字符流，使用 readLine 按行读
            BufferedReader br = new BufferedReader(isr)
    ) {
        String line;
        while ((line = br.readLine()) != null) {
            System.out.println(line);
        }
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

#### 3.4 OutputStreamWriter（字符输出转换流）

**作用**：控制写出字符时使用的字符集编码。

**解决思路**：获取字节输出流，按指定字符集把它包装成字符输出流，之后写出的字符都会用该字符集编码。

```java
public static void main(String[] args) {
    try (
            // 1. 原始字节输出流
            FileOutputStream fos = new FileOutputStream("StreamReaderDemo\\lib\\2.txt");
            // 2. 按指定编码（GBK）转换成字符输出转换流
            OutputStreamWriter osw = new OutputStreamWriter(fos, "GBK");
            // 3. 包装成缓冲字符输出流
            BufferedWriter bw = new BufferedWriter(osw)
    ) {
        bw.write("你们是早晨八九点的太阳，");
        bw.newLine();
        bw.write("要好好学习天天向上！");
        bw.newLine();
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

---

### 四、打印流

- `PrintStream` / `PrintWriter`（打印流）。
- **作用**：更方便、更高效地打印数据出去，特点是"打印啥出去就是啥"（如打印 97 就是字符/数字 97 的样子，而不是字节）。
- 打印流只有输出流，没有输入流。

#### 4.1 PrintStream

```java
public static void main(String[] args) {
    try (
            PrintStream ps = new PrintStream("printDemo\\lib\\1.txt")
    ) {
        ps.println("Hello World");
        ps.println("，我是小哈！");
        ps.println(97);      // println(97) 写出的是 "97"
        ps.write(97);        // write(97) 写的是字节 97，显示为字符 a
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

#### 4.2 PrintWriter

```java
public static void main(String[] args) throws FileNotFoundException {
    PrintWriter pw = new PrintWriter("printDemo\\lib\\2.txt");
    pw.println("你好呀！");
    pw.println(97);
    pw.println("hello!");
    pw.write(97); // write 写字节，显示为 a
    pw.close();
}
```

#### 4.3 典型使用场景：输出语句重定向

项目上线后，控制台的输出语句可能造成干扰，可以把 `System.out` 的输出重定向到文件（日志）。

```java
public static void main(String[] args) {
    System.out.println("控制台正常打印");
    try (
            PrintStream ps = new PrintStream("printDemo\\lib\\logFile.txt");
    ) {
        // 把系统标准输出流改成自己的打印流，此后 System.out 的内容写入文件
        System.setOut(ps);
        System.out.println("存日志，捕输出，");
        System.out.println("控制台，任调度。");
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

#### 4.4 PrintStream 与 PrintWriter 的区别

- 打印数据的功能基本一样：使用方便、性能高效（核心优势）。
- `PrintStream` 继承自字节输出流 `OutputStream`，支持**写字节**数据。
- `PrintWriter` 继承自字符输出流 `Writer`，支持**写字符**数据。

---

### 五、数据流（了解）

如果想把**数据和数据的类型一并写到文件中**，读取时也连类型一并读出来，可以使用数据流：

- `DataOutputStream`：数据输出流，允许把数据及其类型一并写出。
- `DataInputStream`：数据输入流，读取数据输出流写出的数据。
- 数据流属于字节流，读取顺序必须与写入顺序完全一致。

#### 5.1 DataOutputStream

```java
public static void main(String[] args) throws Exception {
    DataOutputStream dos = new DataOutputStream(new FileOutputStream("DataDemo\\lib\\1.txt"));

    dos.writeInt(97);
    dos.write("\r\n".getBytes()); // write 接收字节，字符串要 getBytes()
    dos.writeBoolean(true);
    dos.write("\r\n".getBytes());
    dos.writeDouble(1.0);
    dos.write("\r\n".getBytes());
    dos.writeChar('男');

    dos.close();
}
```

#### 5.2 DataInputStream

```java
public static void main(String[] args) throws Exception {
    DataInputStream dis = new DataInputStream(new FileInputStream("DataDemo\\lib\\1.txt"));

    // 读取顺序、类型必须与写入时一一对应
    System.out.println(dis.readInt() + 1);   // 98
    System.out.println(dis.readBoolean());   // true
    System.out.println(dis.readDouble());    // 1.0

    dis.close();
}
```

---

### 六、序列化流

字节流以字节为单位读写，字符流以字符为单位读写，而**对象流以对象为单位读写**：可以把整个对象写入文件，也可以从文件中把对象读出来。

- **对象序列化**：把 Java 对象写入文件（或网络），使用 `ObjectOutputStream`。
- **对象反序列化**：把文件中的 Java 对象读回内存，使用 `ObjectInputStream`。

#### 6.1 序列化的前提：实现 Serializable 接口

对象要参与序列化，其类必须实现**标记接口** `java.io.Serializable`，否则抛出异常。

```java
// Serializable 是标记接口（内部没有任何方法）
public class Student implements Serializable {
    private String name;
    private int age;
    private String gender;
    private String password;

    public Student() {
    }

    public Student(String name, int age, String gender, String password) {
        this.name = name;
        this.age = age;
        this.gender = gender;
        this.password = password;
    }

    // set/get、toString 省略
}
```

#### 6.2 ObjectOutputStream（对象字节输出流）

```java
public static void main(String[] args) {
    try (
            ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream("ObjectDemo\\lib\\1.txt"))
    ) {
        Student s1 = new Student("小哈", 18, "男", "123456s");
        oos.writeObject(s1); // 序列化对象到文件
        System.out.println("序列化对象成功！！！");
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

#### 6.3 ObjectInputStream（对象字节输入流）

```java
public static void main(String[] args) {
    try (
            ObjectInputStream ois = new ObjectInputStream(new FileInputStream("ObjectDemo\\lib\\1.txt"))
    ) {
        // readObject 返回 Object，需要强转回真实类型
        Student o = (Student) ois.readObject();
        System.out.println(o);
        // Student{name='小哈', age=18, gender='男', password='123456s'}
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

#### 6.4 序列化注意事项

##### （1）transient 修饰符

如果对象的某个成员变量不需要参与序列化（如密码等敏感信息），在该变量前加 **`transient`** 修饰，反序列化后该字段为默认值（引用类型为 `null`）。

```java
public class Student implements Serializable {
    private String name;
    private int age;
    private String gender;
    private transient String password; // 不参与序列化
}
```

反序列化结果：

```text
Student{name='小哈', age=18, gender='男', password='null'}
```

##### （2）序列化版本号 serialVersionUID（了解）

实现 `Serializable` 接口后，类会默认生成一个 `serialVersionUID`（类似身份证号）用于标记类。例如 ArrayList 中：

```java
private static final long serialVersionUID = 8683452581122892189L;
```

序列化后如果修改了类的结构（增删成员变量等），再次反序列化时会因类的 `serialVersionUID` 与序列化时记录的不一致而报错。建议手动显式声明版本号，避免类的小改动导致反序列化失败。

#### 6.5 标记接口（知识拓展）

**标记接口（标签接口）** 是没有任何方法和字段的空接口，作用是向编译器 / JVM / 框架"打标签"，标识实现类具备某种特殊能力，让系统据此做差异化处理。

常见标记接口：

- **`Serializable`**：贴上标签后，JVM 知道这个类的对象可以序列化成字节流存文件、传网络；没贴标签则拒绝序列化。
- **`Cloneable`**：贴上标签后，对象可以调用 `clone()` 方法复制自己；没贴标签调用会报错。
- 也可以自定义标记接口（如 `VIP`），业务代码据此走专属逻辑。

---

### 七、IO 框架

#### 7.1 什么是框架

框架是为解决某类问题而编写的一套类和接口，可以理解成**半成品**，大多由第三方研发。

- **好处**：在框架基础上开发可以得到优秀的软件架构，提高开发效率。
- **形式**：一般把类、接口编译成 class 文件，再压缩成 `.jar` 文件发行。

#### 7.2 Commons-io 框架

Commons-io 是 Apache 开源基金组织提供的 IO 操作小框架，封装了 Java 对文件、数据操作的代码，对外提供更简单的文件操作和读写方式。

**导入步骤**：

1. 官网下载 jar 包（https://commons.apache.org/proper/commons-io/download_io.cgi）；
2. 在项目中创建 `lib` 文件夹，把 `commons-io-2.6.jar` 复制进去；
3. 在 jar 文件上右键 → Add as Library → 点击 OK；
4. 在类中导包使用。

**常用方法（`FileUtils` 工具类）**：

```java
public class Test1 {
    public static void main(String[] args) throws IOException {
        // 拷贝文件
        FileUtils.copyFile(new File("commons\\src\\C\\1.txt"),
                           new File("commons\\src\\C\\new1.txt"));
        // 拷贝文件夹（递归复制整个目录）
        FileUtils.copyDirectory(new File("F:\\...\\day09-字符集和IO流（字节流）"),
                                new File("commons\\src\\C\\day09"));
        // 写字符串到文件
        FileUtils.writeStringToFile(new File("commons\\src\\C\\new11.txt"), "你好呀！");
        // 读取文件为字符串
        String s = FileUtils.readFileToString(new File("commons\\src\\C\\1.txt"), "utf-8");
        System.out.println(s);
    }
}
```

#### 7.3 JDK 官方的 Files 工具类

JDK 自身也提供了简化 IO 的工具类 `java.nio.file.Files`：

```java
public class Test2 {
    public static void main(String[] args) throws Exception {
        // 读取文件所有行，返回 List<String>
        System.out.println(Files.readAllLines(Path.of("commons\\src\\C\\1.txt")));
        // 复制文件
        Files.copy(Path.of("commons\\src\\C\\1.txt"),
                   Path.of("commons\\src\\C\\120.txt"));
    }
}
```

---

### 本章小结

1. **字符流**（`FileReader`/`FileWriter`）以字符为单位读写纯文本，不会读到半个汉字；`FileWriter` 写出后必须 `flush()` 或 `close()` 数据才生效；换行用 `\r\n`（Windows）或 `\n`（Mac/Linux）。
2. **缓冲流**（`BufferedInputStream`/`BufferedOutputStream`/`BufferedReader`/`BufferedWriter`）包装原始流，靠底层 8KB 缓冲数组减少磁盘交互来提升性能，不能单独使用。
3. `BufferedReader` 新增 `readLine()` 按行读取（末尾返回 `null`）；`BufferedWriter` 新增 `newLine()` 跨平台换行。
4. **转换流** `InputStreamReader`/`OutputStreamWriter` 可以指定字符集，解决字符流读写非 UTF-8 文件的乱码问题。
5. **打印流** `PrintStream`（字节系）/`PrintWriter`（字符系）输出方便，`System.setOut()` 可把控制台输出重定向到文件。
6. **数据流** `DataOutputStream`/`DataInputStream` 把数据连同类型一起读写，读取顺序必须与写入一致。
7. **序列化流** `ObjectOutputStream`/`ObjectInputStream` 以对象为单位读写；类必须实现 `Serializable` 标记接口；`transient` 修饰的字段不参与序列化；`serialVersionUID` 用于版本校验。
8. 第三方 **Commons-io** 的 `FileUtils` 和 JDK 自带的 **`Files`** 工具类都提供了一行代码完成复制、读写的简化方法。

---

<div style="page-break-after: always;"></div>

## 第二十一章 特殊文件、日志技术与多线程

本章包含三大板块：

1. **特殊文件**：Properties 属性文件与 XML 文件的读写解析，常用于软件配置与数据传输；
2. **日志技术**：使用 Logback 框架替代 `System.out.println`，实现日志的分级输出与永久存储；
3. **多线程**：线程的创建、常用方法、线程安全问题、线程同步、线程通信与线程池。

---

## 一、特殊文件

### 1.1 特殊文件概述

IO 流可以读写文件中的数据，但之前接触的都是普通文本文件——里面的数据没有任何格式规范，用户可以随意编写，没有规律可言，不方便程序对文件中的数据进行处理。

在 Java 开发中还会遇到两类**有格式要求的特殊文本文件**，方便程序处理数据：

- **后缀为 `.properties` 的文件，称为属性文件**：可以很方便地存储键值对形式的数据，经常当做软件的配置文件使用。
- **XML 文件**：能够表示更加复杂的数据关系（比如多个用户的用户名、密码、家乡、性别等），也经常当做软件的配置文件使用，或用于网络中传输结构化数据。

学习特殊文件主要掌握三点：**如何创建、如何读取、如何写入**。

### 1.2 Properties 属性文件

#### 1.2.1 创建 properties 文件

- 属性文件后缀以 `.properties` 结尾。
- 文件里每一行都是一个键值对，键和值中间用 `=` 隔开，比如 `admin=123456`。
- `#` 表示注释信息，用来说明这一行配置的含义。
- 每一行末尾**不要习惯性加分号或空格**，否则分号、空格会被当做值的一部分。
- **键不能重复，值可以重复**。

```properties
#key = value  格式是标准的键值对格式
username = admin
age = 18
sex = 男
#sex = 女
```

Properties 本质上是一个 Map 集合（键值对集合），但一般不会当集合使用。它的**核心作用是代表属性文件**：通过 Properties 可以读写属性文件里的内容。

#### 1.2.2 读取 Properties 文件

读取方式有两种：

1. 使用字符流一行一行读取，再手动切割 `=`（较繁琐）；
2. 使用 JDK 提供的 `Properties` 类直接读取属性文件里的键值对数据（推荐）。

```java
import java.io.FileReader;
import java.util.Properties;

public class Test1 {
    public static void main(String[] args) throws Exception {
        // 创建一个 Properties 空集合（Map 接口的实现类）
        Properties properties = new Properties();
        // 加载（读取）配置文件
        properties.load(new FileReader("PropertiesDemo\\lib\\config.properties"));
        // 打印 Properties 集合
        System.out.println(properties); // {sex=男, age=18, username=admin}
    }
}
```

#### 1.2.3 Properties 特有的获取元素方法

```java
public static void main(String[] args) throws Exception {
    Properties properties = new Properties();
    properties.load(new FileReader("PropertiesDemo\\lib\\config.properties"));
    System.out.println(properties); // {sex=男, age=18, username=admin}

    // 根据键获取值
    System.out.println(properties.getProperty("username")); // admin
    System.out.println(properties.getProperty("age"));      // 18
    System.out.println(properties.getProperty("sex"));      // 男
    // 获得所有的键
    Set<String> keySet = properties.stringPropertyNames();
    System.out.println(keySet); // [sex, age, username]
}
```

常用 API：

| 方法 | 说明 |
| --- | --- |
| `load(Reader/InputStream)` | 从属性文件中加载键值对到 Properties 对象 |
| `getProperty(String key)` | 根据键获取对应的值 |
| `stringPropertyNames()` | 获取所有键的 Set 集合 |
| `setProperty(String key, String value)` | 设置键值对（相当于 Map 的 put） |
| `store(Writer/OutputStream, String comments)` | 把键值对写出到属性文件 |

#### 1.2.4 Properties 写数据

使用 `store` 方法可以把 Properties 集合中的键值对数据写出到属性文件，**默认覆盖原文件内容**：

```java
public static void main(String[] args) throws Exception {
    // 创建一个 Properties 空集合
    Properties properties = new Properties();
    properties.put("userName", "小哈叔");
    properties.setProperty("password", "123456");
    properties.setProperty("age", "18");
    properties.setProperty("sex", "男");
    properties.setProperty("address", "杭州下沙");
    System.out.println(properties);
    // 将集合数据写出到 properties 文件，第二个参数是注释说明
    properties.store(new FileWriter("PropertiesDemo\\lib\\config.properties"), "这是一个个人信息");
}
```

#### 1.2.5 Properties 文件中文乱码

- 先用文本编辑器打开文件，"另存为"时选择 **UTF-8** 编码；
- 再在 IDEA 中把文件编码设置为 UTF-8。

### 1.3 XML 文件

#### 1.3.1 XML 概述和作用

- XML 全称 **EXtensible Markup Language，可扩展标记语言**。
- 本质是一种数据格式，可以用来存储复杂的数据结构和数据关系。
- **作用：存储数据和传输数据，作为软件的配置文件**。

#### 1.3.2 XML 的特点

- XML 中的 `<标签名>` 称为一个标签（元素），一般成对出现：`<name>...</name>`。
- 标签名可以自己定义（可扩展），但标签必须正确嵌套。
- **XML 中只能有一个根标签**。
- 标签可以有属性，如 `<user id="A10010" color="红色">`。
- 存放 XML 格式数据的文件就是 XML 文件，后缀一般写成 `.xml`。

#### 1.3.3 XML 的创建与语法规则

创建一个后缀为 `.xml` 的文件即可，如 `hello_world.xml`。

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!-- xml 声明，表明这个文件是一个 xml 文件 -->
<!-- 根标签，只能有一个 -->
<users>
    <!-- 子标签可以存在多个，可以存在 0 个或 N 个属性 -->
    <user id="A10010" color="红色">
        <name>小哈</name>
        <age>18</age>
    </user>
    <user id="A10011" color="黑色">
        <name>小米</name>
        <age>23</age>
    </user>
</users>
```

语法规则：

1. **文档声明必须在第一行**：

   ```xml
   <?xml version="1.0" encoding="UTF-8" ?>
   <!-- version：XML 的版本号，该属性必须存在 -->
   <!-- encoding：本 XML 文件的编码 -->
   ```

2. 注释格式：`<!-- 注释内容 -->`。

3. XML 中书写 `<`、`&` 等字符可能与标签语法冲突导致报错，需要用**实体字符**替代：

   | 实体字符 | 代表符号 | 含义 |
   | --- | --- | --- |
   | `&lt;` | `<` | 小于 |
   | `&gt;` | `>` | 大于 |
   | `&amp;` | `&` | 和号 |
   | `&apos;` | `'` | 单引号 |
   | `&quot;` | `"` | 引号 |

4. 可以定义 **CDATA 数据区** `<![CDATA[ …内容… ]]>`，里面的内容可以随便写，不会被解析：

   ```xml
   <?xml version="1.0" encoding="UTF-8" ?>
   <users>
       <user id="A10010" color="红色">
           <name>小哈</name>
           <age>18 &lt; 19</age>
       </user>
       <user id="A10011" color="黑色">
           <name>小米</name>
           <age>23
               <![CDATA[
                   if(age > 18 && age < 30){
                       System.out.println("您的年龄合规！");
                   }
               ]]>
           </age>
       </user>
   </users>
   ```

5. **校验方法**：只要能在浏览器中正常打开 XML 文件，就说明文件没有语法错误。

#### 1.3.4 XML 的应用场景

- 本质是一种数据格式，可以存储复杂的数据结构和数据关系；
- 经常用作系统的**配置文件**；
- 或作为一种特殊的数据结构在**网络中传输**。例如：在淘宝输入顺丰运单号，淘宝发请求给顺丰，顺丰将订单数据以 XML 格式返回给淘宝。

#### 1.3.5 使用 Dom4j 解析 XML 文件

**使用程序读取 XML 文件中的数据，称为 XML 解析。** 程序员不需要自己写原始 IO 流代码解析 XML（难度大、繁琐），可以直接使用开源的解析框架，最知名的是 **Dom4j**（第三方开源框架）。

**引入 Dom4j 的步骤：**

1. 官网下载框架：https://dom4j.github.io/ ，建议使用高版本；
2. 在项目中创建 `lib` 文件夹；
3. 将 `dom4j-2.1.3.jar` 复制到 `lib` 文件夹；
4. 在 jar 文件上右键 → Add as Library → 点击 OK；
5. 在类中导包使用。

**Dom4j 的解析思想——文档对象模型（DOM）：** 把整个 XML 文档、每一个标签、每一个属性都当做对象来看待：

- `SAXReader`：Dom4j 提供的解析器，可以认为代表整个 Dom4j 框架；
- `Document` 对象：表示整个 XML 文档；
- `Element` 对象：表示标签（元素）；
- `Attribute` 对象：表示属性；
- 标签中的内容就是文本（Text）。

基本解析流程：

```java
public static void main(String[] args) throws Exception {
    // 1. 创建 SAXReader 解析器对象
    SAXReader saxReader = new SAXReader();
    // 2. 使用 saxReader 把需要解析的 XML 文件读成一个 Document 对象
    Document document = saxReader.read("xmlDemo\\src\\user.xml"); // 抛异常

    // 3. 获取根元素对象
    Element rootElement = document.getRootElement();
    System.out.println(rootElement.getName()); // users

    // 4. 获取根元素下的全部一级子元素
    List<Element> elements = rootElement.elements();
    for (Element element : elements) {
        System.out.println(element.getName());
    }

    // 5.1 获取当前元素下的某个子元素
    Element student = rootElement.element("student");
    System.out.println(student.getText()); // 学生

    // 5.2 如果下面有多个同名子元素（如 user），element 默认获取第一个
    Element user = rootElement.element("user");
    System.out.println(user.element("name").getText()); // 小哈

    // 6. 获取第二个 user 标签的 name 文本
    Element nameElment = elements.get(1).element("name");
    System.out.println(nameElment.getText()); // 小米

    // 7. 获取元素的属性值
    String idValue = user.attributeValue("id");
    System.out.println(idValue); // A10010

    // 8. 获取某个属性对象
    Attribute color = user.attribute("color");
    System.out.println(color.getName());   // color
    System.out.println(color.getValue());  // 红色

    // 9. 获取所有属性
    List<Attribute> attributes = user.attributes();
    for (Attribute attribute : attributes) {
        System.out.println("属性名：" + attribute.getName());
        System.out.println("属性值：" + attribute.getValue());
        System.out.println("------------------------------");
    }

    // 10. 获取子标签的全部文本
    System.out.println(user.elementText("name")); // 小哈
    System.out.println(user.elementText("age"));  // 18
}
```

常用 API 小结：

| 方法 | 说明 |
| --- | --- |
| `new SAXReader()` / `saxReader.read(路径)` | 创建解析器、读取 XML 为 Document 对象 |
| `document.getRootElement()` | 获取根元素 |
| `element.elements()` | 获取当前元素下所有一级子元素 |
| `element.element("标签名")` | 获取某个子元素（多个同名时取第一个） |
| `element.getText()` / `element.elementText("标签名")` | 获取元素文本 / 获取子标签文本 |
| `element.attributeValue("属性名")` | 获取属性值 |
| `element.attribute("属性名")` | 获取属性对象（再 getName/getValue） |
| `element.attributes()` | 获取所有属性对象 |

#### 1.3.6 综合案例：解析联系人 XML

需求：利用 Dom4j 将 `contacts.xml` 中的联系人数据解析出来，封装成 List集合并遍历输出。

XML 文件：

```xml
<?xml version="1.0" encoding="utf-8" ?>
<contactList>
    <contact id="1" vip="true">
        <name>张无忌</name>
        <gender>男</gender>
        <email>wuji@itcast.cn</email>
    </contact>
    <contact id="2" vip="false">
        <name>小昭</name>
        <gender>女</gender>
        <email>xiaozhao@itcast.cn</email>
    </contact>
    <contact id="3" vip="false">
        <name>灭绝师太</name>
        <gender>女</gender>
        <email>miejue@itcast.cn</email>
    </contact>
</contactList>
```

先定义 JavaBean，把 XML 中每一个 `contact` 看作一个实例对象：

```java
public class Contact {
    private Integer id;
    private boolean vip;
    private String name;
    private String gender;
    private String email;

    public Contact() {
    }

    public Contact(Integer id, boolean vip, String name, String gender, String email) {
        this.id = id;
        this.vip = vip;
        this.name = name;
        this.gender = gender;
        this.email = email;
    }

    // get / set .......

    @Override
    public String toString() {
        return "Contact{" +
                "id=" + id +
                ", vip=" + vip +
                ", name='" + name + '\'' +
                ", gender='" + gender + '\'' +
                ", email='" + email + '\'' +
                '}';
    }
}
```

解析并封装：每遍历一个 `<contact>` 就创建一个 Contact 对象，添加到 ArrayList 集合中。

```java
public static void main(String[] args) throws Exception {
    // 1. 获得整个文件的 Document 对象
    SAXReader saxReader = new SAXReader();
    Document document = saxReader.read("xmlDemo\\lib\\contacts.xml");

    // 2. 获取根标签
    Element root = document.getRootElement();
    // 3. 获取二级标签
    List<Element> elements = root.elements();

    // 4. 创建 ArrayList 集合存放遍历出的对象
    ArrayList<Contact> contacts = new ArrayList<Contact>();
    for (Element element : elements) {
        // 获取属性
        String id = element.attributeValue("id");
        String vip = element.attributeValue("vip");
        // 获取子标签的内容
        String name = element.element("name").getText();
        String gender = element.element("gender").getText();
        String email = element.element("email").getText();
        // 每遍历一个对象的信息就创建一个实例对象
        Contact contact = new Contact(Integer.parseInt(id), Boolean.parseBoolean(vip), name, gender, email);
        // 将实例对象添加到 contacts 集合中
        contacts.add(contact);
    }
    contacts.forEach(c -> System.out.println(c));
}
```

#### 1.3.7 把数据写入 XML 文件（了解）

Dom4j 也提供了往 XML 文件中写标签的方法，但用起来比较麻烦，不建议使用。更简单的做法是：自己用 `StringBuilder` 按标签格式拼接 XML 内容，再用 `BufferedWriter` 写到文件中。

目标 XML：

```xml
<?xml version="1.0" encoding="utf-8" ?>
<book>
    <name>我在人间晒太阳的日子</name>
    <author>小哈叔</author>
    <price>36.8</price>
</book>
```

```java
public class Test3 {
    public static void main(String[] args) {
        // 使用 StringBuilder 拼接 xml 格式数据
        StringBuilder sb = new StringBuilder();
        sb.append("<?xml version=\"1.0\" encoding=\"utf-8\" ?>\r\n");
        sb.append("<book>\n");
        sb.append("\t<name>我在人间晒太阳的日子</name>\n");
        sb.append("\t<author>小哈叔</author>\n");
        sb.append("\t<price>36.8</price>\n");
        sb.append("</book>");

        try (
                BufferedWriter bw = new BufferedWriter(new FileWriter("xmlDemo\\lib\\bool.xml"));
        ) {
            bw.write(sb.toString());
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

#### 1.3.8 约束 XML 的书写（了解）

**XML 约束**：限制 XML 文件中的标签或属性只能按照规定的格式书写。比如约束一个 XML 文件中只能写 `<书>`、`<书名>`、`<作者>`、`<售价>` 这几个标签，写其他标签就报错。

这类约束代码不需要自己编写，了解即可。约束文档分两类：

- **DTD 文档**
- **Schema 文档**（`.xsd` 结尾）

DTD 约束示例解释：

```java
<!ELEMENT 书架(书+)>               // 根标签是<书架>，并且书架中有子标签<书>（+ 表示一个或多个）
<!ELEMENT 书(书名、作者、售价)>      // <书>是一个标签，且其中有子标签<书名>、<作者>、<售价>
<!ELEMENT 书名(#PCDATA)>          // <书名>里面是普通文本
<!ELEMENT 作者(#PCDATA)>          // <作者>里面是普通文本
<!ELEMENT 售价(#PCDATA)>          // <售价>里面是普通文本
```

XML 文件中引入 DTD 或 Schema 约束文件后，其中的标签就受到约束文件的限制。

**本节小结**：Properties 适合存简单键值对配置；XML 适合存复杂层级数据，用 Dom4j 的 SAXReader 解析、用 Document/Element/Attribute 对象模型取值；写 XML 直接拼字符串即可。

---

## 二、日志技术

### 2.1 日志技术概述

日志用来**记录程序运行过程中的信息，并可以进行永久存储**。

日志技术的优势：

- 可以将系统执行的信息方便地记录到指定位置（控制台、文件、数据库）；
- 可以随时以开关的形式控制日志的启停，**无需修改源代码**。

目前记录日志常用输出语句：

```java
public class Test1 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String number = sc.next();
        test(number);
    }

    public static void test(String number) {
        try {
            int result = Integer.parseInt(number);
            System.out.println("输入的数字为：" + result);
        } catch (NumberFormatException e) {
            System.out.println("输入的数字有误，请输入一个整数~~~");
        }
    }
}
```

**输出语句的弊端：**

- 日志只能展示在控制台；
- 不能方便地记录到其他位置（文件、数据库）；
- 想取消日志必须修改源代码。

### 2.2 日志体系简介

日志框架是由牛人或第三方公司做好的实现代码，后来者可以直接使用，常见的有 JUL（`java.util.logging`）、Log4j、Logback 等。

如果各框架的 API 都不一样，学习成本会很高。为此行内提供了一套**日志接口（门面）**，所有日志框架都按照接口的 API 来实现：程序员只要会一套框架，其他框架就能通用，甚至可以在多套框架之间切换。

- **日志框架**：别人已经做好的实现代码，直接拿去使用。
- **日志接口**：设计日志框架的一套标准，日志框架需要实现这些接口。

注意：

- 因为对 Commons Logging 接口不满意，有人搞了 **SLF4J**；因为对 Log4j 的性能不满意，有人搞了 **Logback**。
- **Logback 是基于 SLF4J 日志规范实现的框架**。

### 2.3 Logback 日志框架

#### 2.3.1 快速入门

Logback 官网：https://logback.qos.ch/index.html 。Logback 分为 logback-core、logback-classic 等模块。

使用步骤：

1. 把 **`slf4j-api.jar`、`logback-core.jar`、`logback-classic.jar`** 三个 jar 包复制到模块下新建的 `lib` 文件夹，并 Add as Library；
2. 从资料中找到 `logback.xml` 配置文件，**复制到 src 目录下（必须是 src 目录）**；
3. 在代码中创建日志记录器对象：

   ```java
   public static final Logger LOGGER = LoggerFactory.getLogger("当前类名");
   ```

4. 使用日志对象输出不同级别的日志：

   ```java
   logger.trace(...)  // 一般用于追踪、调试
   logger.debug(...)  // 调试信息
   logger.info(...)   // 普通业务信息
   logger.warn(...)   // 警告信息
   logger.error(...)  // 错误信息（可携带异常对象）
   ```

#### 2.3.2 日志配置文件 logback.xml

此文件不需要记忆，备份后直接使用即可：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
    <!--
        CONSOLE：表示当前的日志信息输出到控制台
    -->
    <appender name="CONSOLE" class="ch.qos.logback.core.ConsoleAppender">
        <!--输出流对象 默认 System.out 改为 System.err-->
        <target>System.err</target>
        <encoder>
            <!--格式化输出：%d表示日期，%thread表示线程名，%-5level：级别从左显示5个字符宽度
                %msg：日志消息，%n是换行符-->
            <pattern>%d{yyyy-MM-dd HH:mm:ss.SSS} [%-5level]  %c [%thread] : %msg%n</pattern>
        </encoder>
    </appender>

    <!-- FILE：日志输出到文件 -->
    <appender name="FILE" class="ch.qos.logback.core.rolling.RollingFileAppender">
        <encoder>
            <pattern>%d{yyyy-MM-dd HH:mm:ss.SSS} [%thread] %-5level %logger{36} - %msg%n</pattern>
            <charset>utf-8</charset>
        </encoder>
        <!--日志输出路径，一般是项目的名字-->
        <file>D:/log/itheima-data.log</file>
        <!--指定日志文件拆分和压缩规则-->
        <rollingPolicy
                class="ch.qos.logback.core.rolling.SizeAndTimeBasedRollingPolicy">
            <!--通过指定压缩文件名称，来确定分割文件方式-->
            <fileNamePattern>D:/log/itheima-data-%i-%d{yyyy-MM-dd}-.log.gz</fileNamePattern>
            <!--文件拆分大小，日志大小到了1MB就压缩-->
            <maxFileSize>1MB</maxFileSize>
        </rollingPolicy>
    </appender>

    <!--
        控制日志的输出情况：开启日志、取消日志
        ALL  代表所有日志全部记录
        OFF  代表不记录任何日志
        debug   支持 debug、info、warn、error
        warn    支持 warn、error
        级别高低：debug < info < warn < error
    -->
    <root level="info"> <!--设置为 info 表示 info 以下的级别不做记录-->
        <appender-ref ref="CONSOLE"/>  <!-- 输出到控制台，不需要就删除 -->
        <appender-ref ref="FILE" />    <!-- 输出到文件，不需要就删除 -->
    </root>
</configuration>
```

- `<appender>`：定义日志的输出目的地（控制台 CONSOLE / 文件 FILE）；
- `<root level="...">`：设置日志的输出级别，并挂载需要的 appender。

#### 2.3.3 日志级别

日志级别指日志信息的类型，常见级别（优先级依次升高）：

```
trace < debug < info < warn < error
```

**记录规则：只有日志级别大于或等于配置文件中设置的级别，才会被记录。**

```java
配置 trace：trace、debug、info、warn、error 全部输出
配置 debug：debug、info、warn、error 输出
配置 info ：info、warn、error 输出
配置 warn ：warn、error 输出
配置 error：只输出 error
```

#### 2.3.4 案例：用户登录日志

```java
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

import java.util.Scanner;

public class UserLogin {
    // 创建一个专属的日志记录器（Logger）实例
    // 注意：一定要导入 org.slf4j 包下的 Logger 和 LoggerFactory
    public static final Logger LOG = LoggerFactory.getLogger(UserLogin.class);

    public static void main(String[] args) {
        String oKName = "小哈叔";
        String oKpassword = "123";
        int count = 3;
        while (true) {
            try {
                Scanner sc = new Scanner(System.in);
                System.out.println("请输入您的用户名");
                String inputUserName = sc.nextLine();
                System.out.println("请输入您的用户密码");
                String inputPassword = sc.nextLine();
                // 用户名和密码都一致则登录成功
                boolean flag = validateLogin(inputUserName, inputPassword, oKName, oKpassword);
                if (flag) {
                    LOG.info("用户" + oKName + "，登录成功~~~~");
                    break;
                }
                if (count != 0) {
                    LOG.info("用户第" + count + "次重试失败");
                    count--;
                } else {
                    LOG.info("用户重新登录次数用完！");
                    break;
                }
            } catch (Exception e) {
                // 捕获异常，避免程序崩溃；error 可以携带异常信息
                LOG.error("输入异常：" + e.getMessage());
            }
        }
    }

    /**
     * @param inputUserName 用户输入的用户名
     * @param inputPassword 用户输入的密码
     * @param okName        数据库中存的正确用户名
     * @param okPassword    数据库中存的正确密码
     * @return 返回 true 或者 false
     */
    public static boolean validateLogin(String inputUserName, String inputPassword,
                                        String okName, String okPassword) {
        // 验证用户名是否正确
        if (!inputUserName.equals(okName)) {
            LOG.info("用户输入的用户名错误~~");
            return false;
        }
        // 验证密码是否正确
        if (!inputPassword.equals(okPassword)) {
            LOG.info("用户输入的密码错误~~");
            return false;
        }
        // 用户名和密码都正确
        return true;
    }
}
```

**本节小结**：日志框架基于 SLF4J 接口实现，Logback 是常用实现；通过 `LoggerFactory.getLogger(类.class)` 获取日志对象，按 trace/debug/info/warn/error 分级输出；`logback.xml` 放在 src 下，控制输出位置、格式和级别阈值。

---

## 三、多线程

### 3.1 多线程概述

**什么是进程？** 默认一个正在运行的应用程序就是一个进程，比如正在运行的百度网盘、QQ。

**什么是线程？** 线程（Thread）是一个程序内部的一条执行流程，是**程序运行（CPU 调度）的最小单位**。

- **单线程**：程序中只有一条执行流程。

  ```java
  public static void main(String[] args) {
      for (int i = 1; i <= 10; i++) {
          System.out.println("任务1：" + i);
      }
      for (int i = 1; i <= 10; i++) {
          System.out.println("任务2：" + i);
      }
  }
  ```

- **多线程**：从软硬件上实现多条执行流程的技术，多条线程由 CPU 负责调度执行。

  ```java
  public static void main(String[] args) {
      for (int i = 1; i <= 5; i++) {
          System.out.println("主线程任务：" + i);
      }
      new Thread(() -> {
          for (int i = 1; i <= 10; i++) {
              System.out.println("子线程1：" + i);
          }
      }).start();
      new Thread(() -> {
          for (int i = 1; i <= 10; i++) {
              System.out.println("子线程2：" + i);
          }
      }).start();
  }
  ```

**多线程的应用与好处：** 12306 同时支持很多人购票、百度网盘同时下载多个文件，每个用户/任务互不影响——每条执行路径就是一条线程。**好处：提高程序的运行效率，提高资源利用率。** 消息通信、淘宝、京东等系统都离不开多线程。

Java 通过 `java.lang.Thread` 类的对象来代表线程。

### 3.2 线程的创建方式一：继承 Thread 类

步骤：

1. 定义子类 `MyThread` 继承 `java.lang.Thread`，重写 `run()` 方法；
2. 创建 MyThread 类的对象；
3. 调用线程对象的 `start()` 方法启动线程（启动后执行的还是 run 方法里的代码）。

```java
public class MyThread extends Thread {
    @Override
    public void run() {
        for (int i = 0; i < 10; i++) {
            // Thread.currentThread().getName() 获取当前线程的名字
            System.out.println(Thread.currentThread().getName() + "=" + i);
        }
    }
}
```

```java
public class Test2 {
    public static void main(String[] args) {
        // 创建线程对象
        MyThread myThread1 = new MyThread();
        MyThread myThread2 = new MyThread();
        MyThread myThread3 = new MyThread();
        // 启动线程
        myThread1.start();
        myThread2.start();
        myThread3.start();
    }
}
```

运行后会发现 MyThread 线程和 main 线程在相互抢夺 CPU 的执行权——**哪个线程先执行、哪个后执行无法控制，每次输出结果都可能不一样**。

**优缺点：**

- 优点：编码简单。
- 缺点：线程类已经继承了 Thread，**无法再继承其他类**，不利于功能扩展。

**注意事项：**

1. **启动线程必须调用 `start()` 方法，而不是 `run()` 方法**：
   - 直接调用 run 会被当成普通方法执行，相当于还是单线程；
   - 只有调用 start 才是启动一条新线程执行。
2. **不要把主线程任务放在启动子线程之前**，否则主线程先跑完，相当于单线程效果。主线程任务应与子线程交错：

   ```java
   public static void main(String[] args) {
       MyThread myThread1 = new MyThread();
       MyThread myThread2 = new MyThread();
       MyThread myThread3 = new MyThread();

       myThread1.start();
       myThread2.start();
       myThread3.start();
       // ====== 以下是主线程任务 ======
       for (int i = 1; i <= 100; i++) {
           System.out.println("主线程main输出：" + i);
       }
   }
   ```

### 3.3 线程的创建方式二：实现 Runnable 接口

Runnable 接口中只有一个 `run` 方法，Runnable 的实现类对象专门用来表示**线程要执行的任务**。

步骤：

1. 定义线程任务类 `MyRunnable` 实现 `Runnable` 接口，重写 `run()` 方法；
2. 创建 MyRunnable 任务对象；
3. 把 MyRunnable 任务对象交给 Thread 处理（`new Thread(任务对象)`）；
4. 调用线程对象的 `start()` 方法启动线程。

```java
public class MyRunnable implements Runnable {
    @Override
    public void run() {
        for (int i = 0; i < 10; i++) {
            System.out.println(Thread.currentThread().getName() + "=" + i);
        }
    }
}
```

```java
public static void main(String[] args) {
    MyRunnable myRunnable = new MyRunnable();
    // 把任务对象交给 Thread 线程对象
    Thread t1 = new Thread(myRunnable);
    Thread t2 = new Thread(myRunnable);
    Thread t3 = new Thread(myRunnable);
    // 开启线程
    t1.start();
    t2.start();
    t3.start();
}
```

**优缺点：**

- 优点：任务类只是实现接口，**可以继续继承其他类、实现其他接口，扩展性强**。
- 缺点：需要多创建一个 Runnable 任务对象；而且 `run()` 方法没有返回值，**线程执行完后不能直接返回执行结果**（需要返回结果要用方式三）。

**匿名内部类（Lambda）简化写法：**

```java
public static void main(String[] args) {
    // Runnable runnable = new Runnable() {
    //     @Override
    //     public void run() { ... }
    // };
    Runnable runnable = () -> {
        for (int i = 0; i < 10; i++) {
            System.out.println(Thread.currentThread().getName() + "=" + i);
        }
    };
    Thread t1 = new Thread(runnable);
    Thread t2 = new Thread(runnable);
    Thread t3 = new Thread(runnable);
    t1.start();
    t2.start();
    t3.start();
}
```

### 3.4 线程的创建方式三：Callable + FutureTask（有返回值）

前两种方式重写的 `run()` 方法都没有返回值：如果线程执行完毕后需要返回一些数据，就无法实现。

**JDK 5 提供了 `Callable` 接口和 `FutureTask` 类来创建线程，最大优点是线程执行完后有返回值。** Callable 接口中有一个 `call()` 方法，重写 call 方法就是线程要执行的代码，它有返回值：

```java
public T call() {
    ...线程执行的代码...
    return 结果;
}
```

步骤：

1. 定义类实现 `Callable<T>` 接口，重写 `call()` 方法，封装要做的事情和要返回的数据；
2. 把 Callable 对象封装成 `FutureTask`（线程任务对象）；
3. 把 FutureTask 交给 Thread 对象；
4. 调用 `start()` 启动线程；
5. 线程执行完毕后，通过 FutureTask 的 `get()` 方法获取线程执行的结果。

```java
// 1. 创建有返回值的线程任务
public class MyCallable implements Callable<String> {
    @Override
    public String call() throws Exception {
        for (int i = 0; i < 10; i++) {
            System.out.println(Thread.currentThread().getName() + "=" + i);
        }
        return "程序执行结束";
    }
}
```

```java
public static void main(String[] args) throws Exception {
    MyCallable myCallable = new MyCallable();
    // 2. 把 Callable 对象包装成 FutureTask（未来任务对象）
    FutureTask<String> futureTask1 = new FutureTask<>(myCallable);
    FutureTask<String> futureTask2 = new FutureTask<>(myCallable);
    // 3. 把任务对象交给 Thread
    Thread t1 = new Thread(futureTask1);
    Thread t2 = new Thread(futureTask2);
    t1.start();
    t2.start();

    // 4. 获取返回值
    // 注意：get() 有阻塞特点——如果执行到这里线程还没执行完，
    // 当前代码会暂停等待，直到线程执行完毕才获取结果
    String s1 = futureTask1.get();
    String s2 = futureTask2.get();
    // 返回结果一定在最后打印
    System.out.println(s1);
    System.out.println(s2);
}
```

**优缺点：**

- 优点：任务类只是实现接口，可继续继承类和实现接口，扩展性强；**可以在线程执行完毕后获取线程执行的结果**。
- 缺点：编码稍复杂。

**三种创建方式对比总结：**

| 方式 | 优点 | 缺点 |
| --- | --- | --- |
| 继承 Thread 类 | 编码简单 | 不能再继承其他类，扩展性差 |
| 实现 Runnable 接口 | 可继承其他类、扩展性强 | 无返回值，需多建任务对象 |
| Callable + FutureTask | 扩展性强，**有返回值** | 编码较复杂 |

### 3.5 Thread 的常用方法

| 方法 | 说明 |
| --- | --- |
| `void run()` | 线程任务方法，线程执行的代码写在这里 |
| `void start()` | 开启一条子线程执行 run 中的代码 |
| `String getName()` | 获取线程名称（线程默认名称为 `Thread-索引`，如 Thread-0、Thread-1） |
| `void setName(String name)` | 设置线程名称（构造器 `new Thread(任务, "名字")` 也可取名） |
| `static Thread currentThread()` | 获取当前正在执行的线程对象 |
| `static void sleep(long ms)` | 让当前线程睡眠指定毫秒数 |
| `void join()` | 等待调用该方法的线程执行完毕，当前线程再继续（间接影响执行顺序） |

```java
public class MyRunnable implements Runnable {
    // run 方法：线程任务方法
    @Override
    public void run() {
        for (int i = 0; i < 10; i++) {
            System.out.println(i);
            // sleep：让线程睡眠一段时间
            try {
                Thread.sleep(1000); // 每 1 秒执行一次
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
        }
    }

    public static void main(String[] args) {
        // start()：开启子线程执行 run 中代码
        new Thread(new MyRunnable()).start();

        // getName()/setName()：在实现接口的方式中，
        // 需要先用 currentThread() 获取当前线程对象再使用
        String name = Thread.currentThread().getName();
        System.out.println("线程的名字是：" + name);
        Thread.currentThread().setName("小哈叔");
        String modifName = Thread.currentThread().getName();
        System.out.println("更改后的线程的名字是：" + modifName);
    }
}
```

**join 方法：**

- 作用：间接控制线程的执行顺序——让调用 join 的线程先执行完，当前线程再往下走；但它无法决定某条线程一定最先执行。
- 面试点：join 能强行控制线程的执行顺序吗？**不能**，线程顺序没有任何方式可以强行控制。

```java
public static void main(String[] args) {
    // 线程1
    Thread t1 = new Thread(() -> {
        for (int i = 0; i < 10; i++) {
            System.out.println(Thread.currentThread().getName() + "=" + i);
        }
    });
    t1.start();
    try {
        // 让 t1 先执行完毕，main 线程再继续
        t1.join();
    } catch (InterruptedException e) {
        throw new RuntimeException(e);
    }
    // 线程2、线程3 在 t1 结束后才创建启动
    Thread t2 = new Thread(() -> {
        for (int i = 0; i < 10; i++) {
            System.out.println(Thread.currentThread().getName() + "=" + i);
        }
    });
    t2.start();
    Thread t3 = new Thread(() -> {
        for (int i = 0; i < 10; i++) {
            System.out.println(Thread.currentThread().getName() + "=" + i);
        }
    });
    t3.start();
}
```

> Thread 类还提供了 `yield`（礼让）、`interrupt`（打断）、守护线程（`setDaemon`）、线程优先级（`setPriority`）等控制方法，开发中很少使用。

### 3.6 线程安全问题

**线程安全问题：多个线程同时操作同一个共享资源时，可能出现业务安全问题。**

**取钱案例：** 小明和小红是夫妻，有一个共享账户余额 10 万元，两人同时来取 10 万元：

1. 小明线程只执行了"判断余额是否足够"（结果为 true），CPU 执行权就被小红抢走；
2. 小红也判断余额足够（结果也为 true），CPU 执行权又被小明抢走；
3. 小明已判断过余额，直接吐出 10 万，账户余额变为 0，CPU 被小红抢走；
4. 小红也已判断过余额，直接吐出 10 万，账户余额变为 **-10 万**。

结果：两个人各取走了 10 万，但账户里原本只有 10 万——这就是线程安全问题。

```java
public class MyRunnable implements Runnable {
    // 共享资源：银行账户里的钱
    public static Integer money = 100000;

    @Override
    public void run() {
        // 取钱
        if (money >= 100000) {
            // 余额足，可以取钱
            System.out.println(Thread.currentThread().getName() + "取钱成功~~~");
            // 模拟取钱时长
            try {
                Thread.sleep(10000);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            // 更新账户
            money = money - 100000;
        }
    }
}
```

```java
public static void main(String[] args) {
    MyRunnable myRunnable = new MyRunnable();
    // Thread 构造器可以直接指定线程名字
    Thread xiaoming = new Thread(myRunnable, "小明");
    Thread xiaohong = new Thread(myRunnable);
    xiaohong.setName("小红");

    xiaoming.start();
    xiaohong.start();

    // 等待子线程执行后查看最终账户金额
    try {
        Thread.sleep(1000);
    } catch (InterruptedException e) {
        throw new RuntimeException(e);
    }
    System.out.println("账户余额为：" + MyRunnable.money);
}
```

**线程安全问题出现的三个条件（同时满足）：**

1. 存在多个线程同时执行；
2. 同时访问一个共享资源；
3. 存在修改该共享资源的操作。

### 3.7 线程同步

#### 3.7.1 线程同步的思想

**线程同步就是解决线程安全问题的方案。**

同步思想：**让多个线程先后依次访问共享资源**，而不是同时争抢。简单说就是让多个线程按规矩、有顺序地使用同一个共享资源，避免争抢混乱、结果出错。

生活类比：

- 家里只有 1 个卫生间（共享资源），爸妈、孩子（多个线程）都要用，遵守"一人用完、下一人再进"的规则就是线程同步；
- 一张银行卡，你在手机转账、家人在 ATM 取钱（两个线程），不同步就可能出现"10 万元被两人各取走 10 万、余额变负数"的错误。

**常见方案——加锁：** 每次只允许一个线程加锁，加锁后才能进入访问共享资源，访问完毕自动解锁，其他线程才能再加锁进来。就像卫生间的门锁：进去反锁（加锁），其他人在门口等；出来开门（解锁），下一个人才能进。

#### 3.7.2 同步方式一：同步代码块

**作用：** 把访问共享资源的核心代码上锁，保证线程安全。

**原理：** 每次只允许一个线程加锁后进入，执行完毕自动解锁，其他线程才能进入。

**语法：**

```java
synchronized(同步锁) {
    访问共享资源的核心代码
}
```

> 注意：对于同时执行的多个线程来说，**同步锁必须是同一把（同一个对象）**，否则锁不住、会出 bug。

```java
public class MyRunnable implements Runnable {
    public static Integer money = 100000;
    // 空对象代表锁（不一定是 Object，只要是所有线程共享的唯一对象即可）
    public static final Object obj = new Object();

    @Override
    public void run() {
        // 多个线程同时执行，谁先拿到锁谁执行
        // synchronized (MyRunnable.class) { // 类名.class 也可以作为锁
        synchronized (obj) {
            if (money >= 100000) {
                System.out.println(Thread.currentThread().getName() + "取钱100000成功~~~");
                try {
                    Thread.sleep(500); // 模拟取钱时长
                } catch (InterruptedException e) {
                    throw new RuntimeException(e);
                }
                money = money - 100000;
            } else {
                System.out.println(Thread.currentThread().getName() + "取钱失败，余额不足~~");
            }
        }
    }
}
```

锁对象的选择建议：

- 锁对象必须唯一，但**不能随便选一个无关的唯一对象**——锁范围过大可能影响其他无关线程的执行，建议直接使用**共享资源**作为锁对象；
- 实例方法中可以用 `this` 作为锁对象（前提是多个线程用同一个任务对象）；
- 静态方法/静态共享场景建议使用 **`类名.class`**（字节码对象，全局唯一）作为锁对象。

#### 3.7.3 同步方式二：同步方法

**作用：** 把访问共享资源的核心方法整个上锁。

**语法：**

```java
修饰符 synchronized 返回值类型 方法名称(形参列表) {
    操作共享资源的代码
}
```

```java
public class MyRunnable implements Runnable {
    public static Integer money = 100000;

    @Override
    public void run() {
        drawMoney();
    }

    // 同步方法：默认锁对象是 this
    // 注意：如果创建了两个不同的任务对象（两把不同的 this 锁），仍然会出问题
    public synchronized void drawMoney() {
        if (money >= 100000) {
            System.out.println(Thread.currentThread().getName() + "取钱100000成功~~~");
            try {
                Thread.sleep(500);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            money = money - 100000;
        } else {
            System.out.println(Thread.currentThread().getName() + "取钱失败，余额不足~~");
        }
    }
}
```

**同步方法的隐式锁对象（底层原理）：**

- **实例同步方法**：默认用 **`this`** 作为锁对象——不同对象是不同的锁。如果小明、小红用了两个不同的 Runnable 任务对象，就会有两把锁，锁不住；
- **静态同步方法**：默认用 **`类名.class`** 作为锁对象——全局唯一，能锁住。

把方法改为 `static synchronized` 即可解决多任务对象的问题：

```java
public class MyRunnable implements Runnable {
    public static Integer money = 100000;

    @Override
    public void run() {
        quQian();
    }

    // 静态同步方法：默认锁对象是 MyRunnable.class
    public static synchronized void quQian() {
        if (money >= 100000) {
            System.out.println(Thread.currentThread().getName() + "，取钱成功！");
            try {
                Thread.sleep(500);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            money = money - 100000;
        } else {
            System.out.println(Thread.currentThread().getName() + "取钱失败，余额不足");
        }
    }
}
```

```java
// 即使两个线程用了不同的任务对象，静态同步方法也能锁住
MyRunnable myRunnable = new MyRunnable();
MyRunnable myRunnable1 = new MyRunnable();
Thread xiaoming = new Thread(myRunnable, "小明");
Thread xiaohong = new Thread(myRunnable1, "小红");
```

**同步代码块与同步方法怎么选？**

- **锁的范围**：同步代码块锁的范围更小（只包住核心代码），同步方法锁的范围是整个方法，更大；
- **可读性**：同步方法写法更简洁、可读性更好；
- 实际开发中只想锁核心几行代码时用同步代码块，整个方法都操作共享资源时直接用同步方法。

#### 3.7.4 同步方式三：Lock 锁（常用）

Lock 是 JDK 5 提供的显式锁定操作，比 synchronized 更灵活、更方便、更强大。Lock 是接口不能直接实例化，采用实现类 **`ReentrantLock`** 构建锁对象，需要**手动加锁和释放锁**：

```java
public class MyRunnable implements Runnable {
    public static Integer money = 100000;
    // Lock 锁需要手动获取和释放
    Lock lock = new ReentrantLock();

    @Override
    public void run() {
        // 加锁
        lock.lock();
        if (money >= 100000) {
            System.out.println(Thread.currentThread().getName() + "取钱100000成功~~~");
            try {
                Thread.sleep(500);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            money = money - 100000;
            lock.unlock(); // 释放锁
        } else {
            System.out.println(Thread.currentThread().getName() + "取钱失败，余额不足~~");
        }
    }
}
```

> 实际开发中建议把 `unlock()` 放在 `finally` 中，保证异常时锁也能释放。

**三种同步方式对比：** 同步代码块和同步方法是隐式锁（synchronized，自动加锁释放），Lock 是显式锁（手动 lock/unlock，更灵活可控）。

#### 3.7.5 死锁问题

**死锁：两个线程互相等待对方持有的锁释放，导致双方都无法继续执行。**

项目中如果出现死锁，服务器会卡住（宕机），重启后又能运行，然后再次死锁——只要有代码触发死锁路径，就会循环"宕机—重启—再宕机"。

**案例：** 两个工人（线程）需要同时拿到"扳手（bs）"和"螺丝刀（lsd）"两把工具才能干活：

- 张三先拿到扳手，准备去拿螺丝刀；
- 同时王五先拿到螺丝刀，准备去拿扳手；
- 张三等王五释放螺丝刀，王五等张三释放扳手 → 互相等待 → 死锁。

```java
public class Suosi {
    public static Object bs = new Object();   // 扳手
    public static Object lsd = new Object();  // 螺丝刀

    public static void main(String[] args) {
        Thread z3 = new Thread(new Runnable() {
            @Override
            public void run() {
                while (true) {
                    synchronized (bs) {            // 张三先拿扳手
                        synchronized (lsd) {       // 再拿螺丝刀
                            System.out.println(Thread.currentThread().getName() + "开始干活~~~");
                        }
                    }
                }
            }
        }, "张三");

        Thread w5 = new Thread(new Runnable() {
            @Override
            public void run() {
                while (true) {
                    synchronized (lsd) {           // 王五先拿螺丝刀
                        synchronized (bs) {        // 再拿扳手
                            System.out.println(Thread.currentThread().getName() + "开始干活~~~");
                        }
                    }
                }
            }
        }, "王五");

        z3.start();
        w5.start();
    }
}
```

程序打印几行后会卡死不动，因为两个线程互相等待对方释放锁。

**解决方案：**

- **方案 1：在外层再包一把锁**，保证两人只需要抢同一把"大锁"，拿到大锁后两把工具都归他用：

  ```java
  public static Object gongju = new Object(); // 外层总锁

  // 张三、王五的 run 中都改为：
  // synchronized (gongju) { synchronized (bs) { synchronized (lsd) { ... } } }
  ```

- **方案 2：统一加锁顺序**——把王五也改成"先拿扳手，再拿螺丝刀"，所有线程按相同顺序申请锁，就不会形成环路等待：

  ```java
  // 王五的 run 改为与张三完全一致：
  synchronized (bs) {
      Thread.sleep(100);
      synchronized (lsd) {
          System.out.println(Thread.currentThread().getName() + "，开始干活啦~~");
      }
  }
  ```

### 3.8 线程通信（了解）

**线程通信：** 当多个线程共同操作共享资源时，线程间通过某种方式互相告知自己的状态，相互协调，避免无效的资源争夺。

**经典模型——生产者与消费者：**

- 生产者线程负责生产数据；
- 消费者线程负责消费生产者生产的数据；
- 生产者生产完数据应通知消费者消费，然后等待消费者消费；消费者消费完也应通知生产者生产，然后等待生产者生产。

**基本框架：** 用一张桌子作为共享媒介，桌上有/无包子用布尔变量表示。

```java
public class Desk {
    // 桌子上的共享变量：false 表示没有包子
    public static boolean isBaoZi = false;
    // 唯一锁对象
    public static final Object obj = new Object();
}
```

**Object 类的等待与唤醒方法（必须在锁对象上调用）：**

| 方法 | 说明 |
| --- | --- |
| `void wait()` | 让当前线程等待并释放锁，直到被唤醒 |
| `void notify()` | 唤醒正在等待该锁的一个线程 |
| `void notifyAll()` | 唤醒正在等待该锁的所有线程 |

协作流程：消费者进来发现桌上没包子 → 唤醒厨师做包子（`notifyAll`）→ 自己等待（`wait`）；厨师被唤醒后做包子 → 做完唤醒消费者吃 → 自己等待……如此循环。

厨师（生产者）线程：

```java
public class ChuShi implements Runnable {
    @Override
    public void run() {
        while (true) {
            synchronized (Desk.obj) {
                if (Desk.isBaoZi == false) {
                    // 没有包子，厨师生产
                    Desk.isBaoZi = true;
                    System.out.println("厨师生产包子~~~");
                    // 通知消费者吃包子：唤醒等待 obj 锁的所有线程
                    Desk.obj.notifyAll();
                    try {
                        Thread.sleep(500); // 放慢打印速度
                        // 让当前线程等待（同时释放锁）
                        Desk.obj.wait();
                    } catch (InterruptedException e) {
                        throw new RuntimeException(e);
                    }
                } else {
                    // 桌上有包子，等待消费者吃完
                    Desk.obj.notifyAll();
                    try {
                        Desk.obj.wait();
                    } catch (InterruptedException e) {
                        throw new RuntimeException(e);
                    }
                }
            }
        }
    }
}
```

消费者线程：

```java
public class Consumer implements Runnable {
    @Override
    public void run() {
        while (true) {
            synchronized (Desk.obj) {
                if (Desk.isBaoZi) {
                    Desk.isBaoZi = false;
                    System.out.println("消费者吃包子~~~");
                    // 吃完通知厨师做包子
                    Desk.obj.notifyAll();
                    try {
                        Thread.sleep(500);
                        Desk.obj.wait();
                    } catch (InterruptedException e) {
                        throw new RuntimeException(e);
                    }
                } else {
                    // 桌上没包子，等待厨师做包子
                    Desk.obj.notifyAll();
                    try {
                        Desk.obj.wait();
                    } catch (InterruptedException e) {
                        throw new RuntimeException(e);
                    }
                }
            }
        }
    }
}
```

测试：

```java
public class Test {
    public static void main(String[] args) {
        Thread cs = new Thread(new ChuShi());
        Thread xfz = new Thread(new Consumer());
        cs.start();
        xfz.start();
    }
}
```

### 3.9 线程池

#### 3.9.1 线程池概述

**线程池就是一个可以复用线程的技术。** 它管理一组可复用的线程，避免频繁创建/销毁线程的性能开销，还可以控制并发线程数量，实现任务的高效运行。

**不使用线程池的问题：** 用户每发起一个请求，后台就创建一个新线程处理，下次新任务来了又要创建新线程——**创建新线程的开销很大，请求过多时会产生大量线程**，严重影响系统性能。

**工作原理：** 线程池内部维护着一组**工作线程（WorkThread）**和一个**任务队列（WorkQueue）**。新任务提交后，优先交给空闲的工作线程执行；没有空闲线程时，任务先进任务队列排队；队列满了才会创建新的临时线程。线程执行完任务后不销毁，回到池中等待下一个任务，从而实现线程复用。

#### 3.9.2 创建线程池

JDK 5 起提供了代表线程池的接口 `ExecutorService`，两种创建方式：

- 方式一：使用实现类 **`ThreadPoolExecutor`** 自己创建线程池对象；
- 方式二：使用工具类 **`Executors`** 调用静态方法返回不同特点的线程池对象。

ThreadPoolExecutor 构造器：

```java
public ThreadPoolExecutor(
    int corePoolSize,                    // 核心线程数
    int maximumPoolSize,                 // 最大线程数（核心 + 临时）
    long keepAliveTime,                  // 临时线程的最大空闲时间
    TimeUnit unit,                       // 空闲时间的单位
    BlockingQueue<Runnable> workQueue,   // 任务队列（阻塞队列）
    ThreadFactory threadFactory,         // 线程工厂，用来创建线程
    RejectedExecutionHandler handler)    // 任务拒绝策略
```

**四种任务拒绝策略：**

| 策略 | 行为 |
| --- | --- |
| `AbortPolicy` | 丢弃任务并抛出 `RejectedExecutionException` 异常（**默认策略**） |
| `CallerRunsPolicy` | 由提交任务的线程（如 main 主线程）直接调用任务的 `run()` 方法，绕过线程池执行 |
| `DiscardPolicy` | 默默丢弃任务，不抛异常（**不推荐**，任务丢了无感知） |
| `DiscardOldestPolicy` | 抛弃队列中等待最久的任务，再把当前任务加入队列 |

**两个关键问题：**

1. **临时线程什么时候创建？** 新任务提交时，发现核心线程都在忙、任务队列也满了，并且还可以创建临时线程（当前线程数 < maximumPoolSize），此时才创建临时线程。
2. **什么时候开始拒绝新任务？** 核心线程和临时线程都在忙、任务队列也满了，新任务再来时才开始拒绝。

#### 3.9.3 线程池处理 Runnable 任务

```java
public static void main(String[] args) {
    ThreadPoolExecutor executor = new ThreadPoolExecutor(
            3,                                  // 核心线程 3 个
            5,                                  // 最大线程 5 个（临时线程 2 个）
            2,
            TimeUnit.DAYS,                      // 临时线程空闲 2 天回收
            new ArrayBlockingQueue<>(5),        // 任务队列容量 5
            Executors.defaultThreadFactory(),
            new ThreadPoolExecutor.CallerRunsPolicy() // 拒绝策略
    );
    // 测试 5 人、8 人、9 人、11 人各自的执行情况
    for (int i = 0; i < 11; i++) {
        executor.execute(new Runnable() {
            @Override
            public void run() {
                System.out.println(Thread.currentThread().getName() + "===>执行任务~~~");
                try {
                    Thread.sleep(2000);
                } catch (Exception e) {
                    throw new RuntimeException(e);
                }
            }
        });
    }
    // 关闭线程池
    // executor.shutdown();      // 等所有任务执行完后再关闭
    List<Runnable> runnables = executor.shutdownNow(); // 立即关闭，返回未执行的任务
    System.out.println("剩余的线程任务有：" + runnables.size());
}
```

#### 3.9.4 线程池处理 Callable 任务

先准备 Callable 任务：

```java
import java.util.concurrent.Callable;

public class MyCallable implements Callable<String> {
    private int n;
    public MyCallable(int n) {
        this.n = n;
    }

    @Override
    public String call() throws Exception {
        int sum = 0;
        for (int i = 0; i < n; i++) {
            sum += i;
        }
        return Thread.currentThread().getName() + "求出的和是：" + sum;
    }
}
```

使用 `submit` 提交任务，返回 `Future` 对象，通过 `get()` 获取结果：

```java
public static void main(String[] args) throws ExecutionException, InterruptedException {
    ThreadPoolExecutor executor = new ThreadPoolExecutor(
            3, 5, 2, TimeUnit.DAYS,
            new ArrayBlockingQueue<>(5),
            Executors.defaultThreadFactory(),
            new ThreadPoolExecutor.CallerRunsPolicy()
    );
    // submit 会把 Callable 包装成 Future 对象
    Future<String> f1 = executor.submit(new MyCallable(10));
    Future<String> f2 = executor.submit(new MyCallable(20));
    Future<String> f3 = executor.submit(new MyCallable(30));
    Future<String> f4 = executor.submit(new MyCallable(40));
    // 获取线程执行 call 的结果（get 有阻塞效果）
    System.out.println(f1.get());
    System.out.println(f2.get());
    System.out.println(f3.get());
    System.out.println(f4.get()); // 核心线程被复用
    executor.shutdown();
}
```

#### 3.9.5 Executors 工具类创建线程池

Executors 是线程池工具类，提供多个静态方法返回不同特点的线程池对象。**注意：这些方法底层都是通过 ThreadPoolExecutor 创建的。**

**固定线程池 `newFixedThreadPool(n)`：** 创建固定数量线程的线程池，核心线程数 = 最大线程数；如果某个线程因执行异常而结束，线程池会**补充一个新线程**替代它。弊端是阻塞队列是**无界队列**，任务再多也会堆积（按固定线程数慢慢执行），官方不推荐大量使用。

```java
public static void main(String[] args) {
    ExecutorService executorService = Executors.newFixedThreadPool(5);
    for (int i = 0; i < 11; i++) {
        executorService.submit(new Runnable() {
            @Override
            public void run() {
                System.out.println(Thread.currentThread().getName() + "-执行完成");
                try {
                    Thread.sleep(1000);
                } catch (InterruptedException e) {
                    throw new RuntimeException(e);
                }
            }
        });
    }
    executorService.shutdown();
}
```

**单例线程池 `newSingleThreadExecutor()`：** 有且仅有一个线程；如果该线程异常结束，线程池也会补充一个新线程。使用无界队列，任务过多会堆积导致 OOM（内存溢出），企业不推荐。

```java
ExecutorService executorService = Executors.newSingleThreadExecutor();
```

**缓存线程池 `newCachedThreadPool()`：** 核心线程数为 0，最大线程数为 `Integer.MAX_VALUE`（约 21 亿），任务多就不断创建新线程；线程任务执行完后**空闲 60 秒会被自动回收**。线程数无上限可能耗尽系统资源，企业不推荐。

```java
ExecutorService executorService = Executors.newCachedThreadPool();
```

**延迟（定时）线程池 `newScheduledThreadPool(n)`：** 可以执行延迟任务或定时任务，是 Executors 中**唯一推荐使用**的：

```java
public static void main(String[] args) {
    ScheduledExecutorService scheduledExecutorService = Executors.newScheduledThreadPool(10);
    // 5 秒后执行一次任务
    scheduledExecutorService.schedule(new Runnable() {
        @Override
        public void run() {
            System.out.println("任务执行了~~~");
        }
    }, 5, TimeUnit.SECONDS);
    // 周期性执行：初始延迟 0，每隔 1 秒执行一次
    scheduledExecutorService.scheduleAtFixedRate(new Runnable() {
        @Override
        public void run() {
            System.out.println(new Date());
        }
    }, 0, 1, TimeUnit.SECONDS);
}
```

> 大型并发系统中使用 Executors 如果不注意无界队列/无限线程的陷阱，可能出现系统风险，生产环境推荐直接用 ThreadPoolExecutor 显式配置参数。

### 3.10 并发与并行

- **进程**：正在运行的程序（软件）就是一个独立的进程。线程属于进程，一个进程中可以同时运行很多个线程。
- 进程中的多个线程是**并发和并行**执行的。

**并发（Concurrency）：** CPU 能同时处理的线程数量有限，为了保证所有线程都能往前执行，CPU 会轮询为每个线程服务；由于 CPU 切换速度极快，给人"同时执行"的感觉。简单理解：**一个 CPU（厨师）在频繁切换执行多个任务（炒多个菜）**。

**并行（Parallelism）：** 在同一时刻，真的有多个线程在被多个 CPU 核心同时调度执行（同一时间有多个厨师各炒各的菜）。

**多线程到底怎么执行的？** 并发和并行同时进行：理论上靠并发（单核 CPU 快速切换多个线程），多核 CPU 的电脑也会用到真正的并行处理。

### 3.11 线程的生命周期

线程的生命周期就是线程从生到死经历的各种状态及状态转换。理解这些状态有利于提升并发编程的理解能力。

**Java 线程共定义了 6 种状态**，全部定义在 Thread 类的内部枚举类 `Thread.State` 中：

| 状态 | 名称 | 含义 |
| --- | --- | --- |
| `NEW` | 新建 | 线程对象已创建，但还未调用 `start()` |
| `RUNNABLE` | 可运行 | 调用 start 后，线程正在 JVM 中执行（可能正在运行，也可能正在等待 CPU 时间片） |
| `BLOCKED` | 锁阻塞 | 线程等待获取 synchronized 锁（被挡在同步代码块外） |
| `WAITING` | 无限等待 | 线程调用 `wait()`、`join()` 等方法后，无限期等待另一个线程唤醒 |
| `TIMED_WAITING` | 计时等待 | 线程调用 `sleep(ms)`、`wait(ms)` 等带超时的方法，等待指定时间后自动醒来 |
| `TERMINATED` | 终止 | 线程执行完毕，run 方法结束 |

典型状态转换：`NEW` →（start）→ `RUNNABLE` →（等锁）→ `BLOCKED` →（拿到锁）→ `RUNNABLE`；`RUNNABLE` →（在同步代码块中调用 `wait()`）→ `WAITING`，被 `notify/notifyAll` 唤醒后**若立刻拿到锁**回到 `RUNNABLE`，**若锁被其他线程抢走则进入 `BLOCKED`**，拿到锁后再回到 `RUNNABLE`（`join()` 等被等线程结束也会回到 RUNNABLE）；`RUNNABLE` →（`sleep(ms)`、`wait(ms)`）→ `TIMED_WAITING`，超时或被唤醒后同样按"是否拿到锁"回到 `RUNNABLE` 或 `BLOCKED`；最终 run 正常执行完或因未捕获异常终止 → `TERMINATED`。

**本章小结：** Properties 与 XML 是两种常用配置/数据文件，XML 用 Dom4j 解析；Logback 基于 SLF4J 实现分级日志输出；多线程有继承 Thread、实现 Runnable、Callable+FutureTask 三种创建方式；多线程操作共享资源会出现线程安全问题，用同步代码块、同步方法、Lock 锁解决，注意锁对象唯一和死锁避免；线程池复用线程、控制并发，推荐用 ThreadPoolExecutor 显式配置或 ScheduledThreadPool 做定时任务。

---

<div style="page-break-after: always;"></div>

## 第22章 网络编程

### 一、网络编程简介

#### 1.1 什么是网络编程

网络编程可以让设备中的程序与网络上其他设备中的程序进行数据交互（实现网络通信）。Java 在 `java.net.*` 包下提供了网络编程的解决方案。

#### 1.2 两种基本通信架构

- **CS 架构（Client 客户端 / Server 服务端）**：需要用户在电脑或手机上安装客户端软件，客户端通过网络连接服务器，服务器把数据发给客户端展示。
- **BS 架构（Browser 浏览器 / Server 服务端）**：不需要开发客户端软件，用户通过浏览器输入网址即可从服务器获取数据。

### 二、网络编程三要素

网络编程的三要素是：**IP 地址、端口、协议**。

#### 2.1 IP 地址

- **IP（Internet Protocol）**：全称"互联网协议地址"，是分配给上网设备的唯一标志。
- IP 地址有两种形式：**IPv4** 和 **IPv6**。

**IPv4**

- IPv4 地址一般由运营商直接分配，通过它可以找到网络上的主机。
- 在命令行窗口输入 `ipconfig` 可以查看本机 IP。

**IPv6**

- 共 128 位，号称可以为地球上每一粒沙子编号。
- 分成 8 段表示，每段由四位编码成一个十六进制数，段之间用冒号（`:`）分开。

**IP 域名**

- IP 地址难以记忆，可以使用域名代替，方便快速访问网站。
- 现在多数网站不允许直接用 IP 访问，只能用域名访问。
- 在命令行输入 `ping www.baidu.com` 可以查看某个网站对应的 IP。

**公网 IP 与内网 IP**

- **公网 IP**：可以连接互联网的 IP 地址（后期项目需要部署在公网 IP 上）。
- **内网 IP**：也叫局域网 IP，只能在组织机构内部使用。
- `192.168.` 开头的是常见局域网地址，范围为 `192.168.0.0 ~ 192.168.255.255`。

**特殊 IP 地址（重点记忆）**

- `127.0.0.1`、`localhost`：代表本机 IP，只会寻找当前所在的主机。

**IP 常见命令**

```bash
ipconfig          # 查看本机的 IP 地址
ping 域名/IP       # 检测当前电脑与指定 IP/域名是否连通
```

ping 命令出现回复提示，说明网络是连通的。

**InetAddress 类（代表 IP 地址）**

```java
public static void main(String[] args) throws Exception {
    // 获取本机的 IP 地址对象
    InetAddress localHost = InetAddress.getLocalHost();
    // 返回该 IP 地址对象对应的主机名和 IP 地址信息
    System.out.println(localHost.getHostName());
    System.out.println(localHost.getHostAddress());

    System.out.println("-----------------");
    // 获取指定 IP 地址或者域名的 IP 地址对象
    InetAddress host1 = InetAddress.getByName("www.jd.com");
    System.out.println(host1.getHostName());     // 对应的主机名
    System.out.println(host1.getHostAddress());  // 对应的 IP 信息

    System.out.println("-------12--------");
    InetAddress host2 = InetAddress.getByName("DESKTOP-VGRV7V0");
    System.out.println(host2.getHostName());
    System.out.println(host2.getHostAddress());

    System.out.println("---------------");
    // 在指定毫秒内，判断本机与该 IP 对应的主机是否能连通
    System.out.println(host2.isReachable(6000));
}
```

#### 2.2 端口

端口用于标记计算机设备上正在运行的应用程序，规定为一个 16 位二进制数，范围是 **0 ~ 65535**。

**端口分类**

- **周知端口**：0 ~ 1023，被预先定义的知名应用占用（如 HTTP 占用 80，FTP 占用 21）。
- **注册端口**：1024 ~ 49151，分配给用户进程或某些应用程序。
- **动态端口**：49152 ~ 65535，一般不固定分配，而是动态分配。

注意：自己开发的程序一般选择使用注册端口，且一台设备中不能出现两个程序端口号相同，否则会出错。

#### 2.3 协议

网络上通信的设备事先规定的连接规则、传输数据的规则，称为**网络通信协议**。

- **OSI 网络参考模型**：全球网络互联标准。
- **TCP/IP 网络模型**：事实上的国际标准。

传输层有两个核心通信协议：

##### UDP 协议（User Datagram Protocol，用户数据报协议）

- 特点：**无连接、不可靠**通信。
- 不事先建立连接，数据按照包发送，一包数据包含：自己的 IP、程序端口、目的地 IP、程序端口和数据（限制在 **64KB** 内）等。
- 发送方不管对方是否在线，数据中途丢失也不管，接收方收到数据也不返回确认，因此不可靠。

##### TCP 协议（Transmission Control Protocol，传输控制协议）

- 特点：**面向连接、可靠**通信。
- TCP 的最终目的：在不可靠的信道上实现可靠传输。
- 可靠传输的三个步骤：**三次握手**建立连接、传输数据进行确认、**四次挥手**断开连接。
- 三次握手的目的：确定通信双方收发消息都正常（全双工），保证数据传输的可靠性。
- 四次挥手的目的：确保双方数据的收发都已经完成。

##### UDP 与 TCP 对比

| 对比项 | UDP | TCP |
| --- | --- | --- |
| 连接 | 无连接 | 面向连接（三次握手） |
| 可靠性 | 不可靠 | 可靠（确认、重传） |
| 效率 | 通信效率高 | 相对不高 |
| 数据量 | 每包限制 64KB | 连接中可传输大量数据 |
| 典型场景 | 语音通话、视频直播 | 网页、文件下载、支付 |

实际上现在基本都使用 TCP。

### 三、UDP 通信编程

Java 提供 `java.net.DatagramSocket` 类实现 UDP 通信。

#### 3.1 UDP 一对一消息（单播）

**客户端（发送消息）**

```java
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;

public class Client {
    public static void main(String[] args) throws Exception {
        // 1.创建客户端对象（系统随机分配端口，也可以 new DatagramSocket(777) 指定端口）
        DatagramSocket socket = new DatagramSocket();
        // 2.创建数据包对象，封装要发出去的数据
        byte[] bytes = "我是一个客户端，我爱发消息hahaha".getBytes();
        // 参数1：要发送的数据；参数2：发送数据的字节个数；
        // 参数3：服务端的 IP 地址；参数4：服务端程序端口
        DatagramPacket packet = new DatagramPacket(bytes, bytes.length,
                InetAddress.getLocalHost(), 8888); // 发给本机 127.0.0.1
        // 3.正式发送数据包
        socket.send(packet);
        System.out.println("客户端数据发送完毕~~~");
        // 4.释放通信资源
        socket.close();
    }
}
```

**服务端（接收消息）**

```java
import java.net.DatagramPacket;
import java.net.DatagramSocket;

public class Server {
    public static void main(String[] args) throws Exception {
        // 1.创建服务端对象并注册端口
        DatagramSocket socket = new DatagramSocket(8888);
        // 2.创建数据包对象用于接收数据
        byte[] bytes = new byte[1024 * 64]; // 64KB
        DatagramPacket packet = new DatagramPacket(bytes, bytes.length);
        System.out.println("等待接收数据......");
        // 3.接收客户端发来的数据
        socket.receive(packet);
        // 4.从字节数组中解析接收到的数据
        int len = packet.getLength();
        byte[] data = packet.getData();
        String res = new String(data, 0, len);
        System.out.println("客户端发来消息：" + res);
        // 补充：获取发送方信息
        System.out.println(packet.getAddress().getHostAddress()); // 客户端 IP
        System.out.println(packet.getAddress().getHostName());    // 客户端主机名
        System.out.println(packet.getPort());                     // 客户端端口
        // 5.关闭通信连接
        socket.close();
    }
}
```

#### 3.2 UDP 多对多（多发多收）

**客户端**

```java
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;
import java.util.Scanner;

public class Client {
    public static void main(String[] args) throws Exception {
        Scanner sc = new Scanner(System.in);
        DatagramSocket socket = new DatagramSocket();
        while (true) {
            System.out.println("请输入您要发送的消息（exit退出）");
            String msg = sc.next();
            if (msg.equals("exit")) {
                System.out.println("程序已结束，欢迎下次使用~~~");
                break;
            }
            byte[] bytes = msg.getBytes();
            DatagramPacket packet = new DatagramPacket(bytes, bytes.length,
                    InetAddress.getLocalHost(), 8888);
            socket.send(packet);
            System.out.println("客户端数据发送完毕~~~");
        }
        socket.close();
    }
}
```

**服务端**

```java
import java.net.DatagramPacket;
import java.net.DatagramSocket;

public class Server {
    public static void main(String[] args) throws Exception {
        DatagramSocket socket = new DatagramSocket(8888);
        while (true) {
            byte[] bytes = new byte[1024 * 64]; // 64KB
            DatagramPacket packet = new DatagramPacket(bytes, bytes.length);
            System.out.println("等待接收数据......");
            socket.receive(packet);
            int len = packet.getLength();
            byte[] data = packet.getData();
            String res = new String(data, 0, len);
            String hostAddress = packet.getAddress().getHostAddress();
            String hostName = packet.getAddress().getHostName();
            int port = packet.getPort();
            System.out.println("IP地址为" + hostAddress + "客户端发来消息：" + res);
            System.out.println("主机名为：" + hostName);
            System.out.println("对方端口号为：" + port);
            System.out.println("-----------------------------");
        }
    }
}
```

#### 3.3 UDP 一对多（广播，扩展）

- 服务端代码与多对多版本完全相同。
- 客户端只需把 `DatagramPacket` 的目标 IP 改为广播地址 **`255.255.255.255`**；如果收不到消息，通常是路由器默认屏蔽了广播，可以改成网段广播地址试试。
- 广播默认不开启，需要手动调用 `socket.setBroadcast(true)`。

```java
DatagramSocket socket = new DatagramSocket();
socket.setBroadcast(true); // 手动开启广播
// ...
DatagramPacket packet = new DatagramPacket(bytes, bytes.length,
        InetAddress.getByName("255.255.255.255"), 8888);
socket.send(packet);
```

### 四、TCP 通信编程

Java 提供 `java.net.Socket`（客户端）和 `java.net.ServerSocket`（服务端）实现 TCP 通信，数据通过 **IO 流**传输。

注意：

- 服务端端口必须和客户端连接端口一致。
- 必须**先启动服务端**，再启动客户端；否则客户端报 `Connection refused: connect`。

#### 4.1 TCP 一对一

**客户端（发消息）**

```java
import java.io.OutputStream;
import java.net.Socket;

public class Client {
    public static void main(String[] args) throws Exception {
        // 1.创建客户端 Socket，通过服务器 IP、端口与服务端连接
        Socket socket = new Socket("127.0.0.1", 9999);
        // 2.获得字节输出流
        OutputStream os = socket.getOutputStream();
        // 3.通过字节输出流写出数据
        byte[] bytes = "hell TCP!!!".getBytes();
        os.write(bytes);
        // 4.关闭流和网络通信
        os.close();
        socket.close();
    }
}
```

**服务端（收消息）**

```java
import java.io.InputStream;
import java.net.ServerSocket;
import java.net.Socket;
import java.net.SocketAddress;

public class Server {
    public static void main(String[] args) throws Exception {
        // 1.创建 TCP 服务端对象 ServerSocket，端口与客户端一致
        ServerSocket ss = new ServerSocket(9999);
        // 2.等待客户端连接，获得对应的 Socket 对象
        Socket socket = ss.accept();
        // 3.获取发送方地址、输入流
        SocketAddress remote = socket.getRemoteSocketAddress();
        InputStream is = socket.getInputStream();
        // 4.读取流中的数据
        byte[] bytes = is.readAllBytes();
        System.out.println("IP地址为" + remote + "的客户发来消息：" + new String(bytes));
        // 5.关闭资源
        is.close();
        socket.close();
        ss.close();
    }
}
```

#### 4.2 TCP 多发多收

**客户端**

```java
import java.io.OutputStream;
import java.net.Socket;
import java.util.Scanner;

public class Client {
    public static void main(String[] args) throws Exception {
        Scanner sc = new Scanner(System.in);
        Socket socket = new Socket("localhost", 10086);
        OutputStream os = socket.getOutputStream();
        while (true) {
            System.out.println("请输入您要发送的消息（exit退出）");
            String msg = sc.nextLine();
            if (msg.equals("exit")) {
                System.out.println("欢迎下次光临~~");
                break;
            }
            os.write(msg.getBytes());
        }
        os.close();
        socket.close();
    }
}
```

**服务端**

```java
import java.io.InputStream;
import java.net.ServerSocket;
import java.net.Socket;
import java.net.SocketAddress;

public class Server {
    public static void main(String[] args) throws Exception {
        ServerSocket ss = new ServerSocket(10086);
        System.out.println("等待连接......");
        Socket socket = ss.accept();
        SocketAddress remote = socket.getRemoteSocketAddress();
        System.out.println(remote + "链接成功");
        InputStream is = socket.getInputStream();

        // 注意：不能用 readAllBytes()！
        // 客户端多次发送数据时，readAllBytes() 会等到连接关闭才返回全部数据，
        // 无法实时处理每条消息。
        byte[] bytes = new byte[1024 * 64]; // 64KB
        while (true) {
            int len = is.read(bytes);
            System.out.println("IP地址为" + remote + "的客户发来消息：" + new String(bytes, 0, len));
        }
    }
}
```

#### 4.3 TCP 多客户端实现（服务端用线程处理每个客户端）

服务端循环等待连接，每接到一个客户端 Socket，就交给一个独立子线程处理，这样服务端可以同时服务多个客户端。

```java
import java.net.ServerSocket;
import java.net.Socket;

public class Server {
    public static void main(String[] args) throws Exception {
        // 1.创建服务端对象
        ServerSocket ss = new ServerSocket(1088);
        // 2.循环等待多个客户端连接
        while (true) {
            System.out.println("等待连接。。。。。。");
            Socket socket = ss.accept();
            // 把接收到的客户端 socket 交给子线程处理
            new Thread(new MyRunnable(socket)).start();
        }
    }
}
```

```java
import java.io.InputStream;
import java.net.Socket;

public class MyRunnable implements Runnable {
    private Socket socket;

    public MyRunnable(Socket socket) {
        this.socket = socket;
    }

    @Override
    public void run() {
        try {
            System.out.println(socket.getRemoteSocketAddress() + "连接成功......");
            InputStream is = socket.getInputStream();
            byte[] bytes = new byte[1024];
            int len;
            while ((len = is.read(bytes)) != -1) {
                String msg = new String(bytes, 0, len);
                System.out.println(socket.getRemoteSocketAddress() + "说：" + msg);
            }
        } catch (Exception e) {
            System.out.println(socket.getRemoteSocketAddress() + "用户离开啦......");
        }
    }
}
```

### 本章小结

- 网络编程三要素：**IP 地址**（定位主机，`InetAddress`）、**端口**（定位程序，0~65535）、**协议**（UDP / TCP）。
- UDP：无连接、不可靠、效率高、单包 64KB 限制，核心类 `DatagramSocket` + `DatagramPacket`；支持单播、广播（`255.255.255.255`，需 `setBroadcast(true)`）。
- TCP：面向连接、可靠，核心类 `Socket` + `ServerSocket`，通过 IO 流传输数据；必须先启动服务端；多发多收时服务端不能用 `readAllBytes()`；多客户端场景下服务端要为每个 Socket 开启独立线程。

---

<div style="page-break-after: always;"></div>

## 第23章 单元测试、反射、注解与动态代理

### 一、单元测试 JUnit

#### 1.1 单元测试概述

所谓单元测试，就是针对最小的功能单元（**方法**）编写测试代码，对其进行正确性测试。

**在 main 方法中测试的问题：**

- 只能在 main 方法里编写测试代码去调用其他方法。
- 无法实现自动化测试，一个方法测试失败可能影响其他方法的测试。
- 无法得到测试报告，需要程序员自己观察测试是否成功。

```java
public class Demo1 {
    public static void main(String[] args) {
        getMaxIndex("hello");
        getMaxIndex(null);   // 如果 getMaxIndex 没处理 null，这里抛异常会直接中断，
        getSum(3, 2);        // 后面的 getSum 就测不到了
    }
    public static int getMaxIndex(String str) {
        // 如果这个判断关闭，传入 null 就会出空指针，影响 getSum 的测试
        // if (str == null) { return -1; }
        return str.length();
    }
    public static int getSum(int a, int b) {
        return a + b;
    }
}
```

#### 1.2 JUnit 框架

JUnit 是第三方开源的单元测试框架（IDEA 已集成，无需手工导入 jar 包）。

**优点：**

- 可以灵活编写测试代码，既能针对某个方法单独测试，也支持一键对全部方法自动化测试，且各方法相互独立。
- 不需要程序员人工分析结果，框架会自动生成测试报告（通过为绿色，失败为红色）。

**使用步骤：**

1. 将 JUnit 框架的 jar 包导入项目（IDEA 已集成，无需手工导入）。
2. 为业务类定义对应的测试类，为每个业务方法编写对应的**测试方法**——测试方法必须是：**公共、无参、无返回值**。
3. 测试方法上必须声明 **`@Test`** 注解，方法体内调用被测业务方法。
4. 选中测试方法右键"JUnit 运行"：通过显示绿色，失败显示红色。

```java
public class Demo2 {
    public static int getMaxIndex(String str) {
        if (str == null) {
            return -1;
        }
        return str.length();
    }
    public static int getSum(int a, int b) {
        return a + b;
    }
}
```

```java
import org.junit.jupiter.api.Test;

public class Demo2Test {
    @Test
    public void getMaxIndexTest() {
        System.out.println(Demo2.getMaxIndex("hello"));
        System.out.println(Demo2.getMaxIndex(null));
    }
    @Test
    public void getSumTest() {
        System.out.println(Demo2.getSum(1, 3));
    }
}
```

#### 1.3 断言（Assertions）

单元测试默认只判断方法内部是否抛异常，无法判断返回结果是否正确。**断言**就是给测试设定一个预期值，断言会判断预期值与实际返回结果是否一致，不一致就触发断言失败。

```java
import org.junit.jupiter.api.Assertions;
import org.junit.jupiter.api.Test;

public class Demo3 {
    public static int getMaxIndex(String str) {
        if (str == null) {
            return -1;
        }
        return str.length(); // 实际返回的是长度，而需求要的是最大索引（长度-1）
    }

    @Test
    public void getMaxIndexTest() {
        int maxIndex = getMaxIndex("abc");
        // 断言三个参数：参数1=预期值，参数2=实际值，参数3=断言失败时的提示信息
        // 期望 maxIndex 是 2，如果不是就抛出 AssertionError 并提示
        Assertions.assertEquals(2, maxIndex, "方法内部存在Bug");
    }
}
```

#### 1.4 JUnit 常用注解

| 注解 | 执行时机 |
| --- | --- |
| `@Test` | 标记一个测试方法 |
| `@BeforeEach` | 在每个测试方法执行**之前**执行一次 |
| `@AfterEach` | 在每个测试方法执行**之后**执行一次 |
| `@BeforeAll` | 在所有测试方法执行之前执行一次（有且仅有一次），方法必须是 **static** |
| `@AfterAll` | 在所有测试方法执行之后执行一次（有且仅有一次），方法必须是 **static** |

```java
import org.junit.jupiter.api.*;

public class Demo4 {

    @BeforeEach
    public void before() {
        System.out.println("before方法~~~");
    }

    @AfterEach
    public void after() {
        System.out.println("after方法~~~");
    }

    @BeforeAll
    public static void beforeAll() {
        System.out.println("~~~~~~beforeAll~~~~~~~");
    }

    @AfterAll
    public static void afterAll() {
        System.out.println("~~~~~~afterAll~~~~~~~~");
    }

    @Test
    public void test() {
        System.out.println("我是Test方法~~~");
    }

    @Test
    public void test1() {
        System.out.println("我是Test1方法~~~");
    }
}
```

#### 1.5 JUnit 应用场景示例

利用 `@BeforeEach` / `@AfterEach` 统一管理资源（如 IO 流的获取与关闭），每个测试方法专注于一种读取方式：

```java
import org.junit.jupiter.api.AfterEach;
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;

import java.io.FileInputStream;

public class Demo5 {
    FileInputStream fis;

    @BeforeEach
    public void before() throws Exception {
        fis = new FileInputStream("D:\\code\\beike\\JunitDemo\\lib\\1.txt");
    }

    @AfterEach
    public void after() throws Exception {
        fis.close();
    }

    // 测试读取一个字节
    @Test
    public void test01() throws Exception {
        while (true) {
            int len = fis.read();
            if (len == -1) {
                break;
            }
            System.out.print((char) len);
        }
    }

    // 测试读取一个字节数组
    @Test
    public void test02() throws Exception {
        byte[] bytes = new byte[1024];
        while (true) {
            int len = fis.read(bytes);
            if (len == -1) {
                break;
            }
            System.out.print(new String(bytes, 0, len));
        }
    }

    // 测试一次性读取所有
    @Test
    public void test03() throws Exception {
        byte[] bytes = fis.readAllBytes();
        System.out.println(new String(bytes));
    }
}
```

### 二、反射（Reflection）

#### 2.1 反射概述

反射就是：**加载类，并允许以编程的方式解剖类中的各种成分（成员变量、方法、构造器等）**。即通过类的字节码文件，获得类中的所有属性、方法、构造器并加以操作。

学习反射分四步：

1. 加载类，获取类的字节码：**Class** 对象
2. 获取类的构造器：**Constructor** 对象
3. 获取成员变量：**Field** 对象
4. 获取成员方法：**Method** 对象

#### 2.2 第一步：获取 Class 对象的三种方式

```java
import org.junit.jupiter.api.Test;

public class Demo1 {
    @Test
    public void test01() {
        // 方式一：类名.class
        Class<Demo1> aClass = Demo1.class;
        System.out.println(aClass.getName());
    }

    @Test
    public void test02() throws Exception {
        // 方式二：Class.forName("全类名")
        Class<?> aClass = Class.forName("Reflection.Demo1");
        System.out.println(aClass.getName());
    }

    @Test
    public void test03() throws Exception {
        // 方式三：对象.getClass()（Object 提供的方法）
        Demo1 demo1 = new Demo1();
        Class<? extends Demo1> aClass = demo1.getClass();
        System.out.println(aClass.getName());
    }
}
```

#### 2.3 第二步：获取构造器 Constructor

先准备一个构造器全部私有的 Student 类：

```java
public class Student {
    private String name;
    private Integer age;
    private String gender;

    private Student() {}

    private Student(String name, int age, String gender) {
        this.name = name;
        this.age = age;
        this.gender = gender;
    }

    @Override
    public String toString() {
        return "Student{name='" + name + "', age=" + age + ", gender='" + gender + "'}";
    }
}
```

**获取所有构造器**

```java
@Test
public void test02() throws Exception {
    Class<Student> aClass = Student.class;
    Constructor<?>[] constructors = aClass.getDeclaredConstructors();
    for (Constructor<?> constructor : constructors) {
        System.out.println(constructor);
    }
}
```

**获取无参构造器并创建对象**

```java
@Test
public void test03() throws Exception {
    Class<Student> aClass = Student.class;
    Constructor<Student> constructor = aClass.getDeclaredConstructor();
    constructor.setAccessible(true); // 私有构造器需要暴力反射
    Student student = constructor.newInstance();
    System.out.println(student);
}
```

**获取有参构造器并创建对象**

```java
@Test
public void test04() throws Exception {
    Class<Student> aClass = Student.class;
    // 传入形参的类型列表来定位构造器
    Constructor<Student> constructor =
            aClass.getDeclaredConstructor(String.class, int.class, String.class);
    constructor.setAccessible(true); // 暴力反射
    Student student = constructor.newInstance("小哈", 16, "男");
    System.out.println(student);
}
```

#### 2.4 第三步：获取成员变量 Field

**获取全部成员变量**

```java
@Test
public void test01() throws Exception {
    Class<Student> aClass = Student.class;
    Constructor<Student> constructor = aClass.getDeclaredConstructor();
    constructor.setAccessible(true);
    Student student = constructor.newInstance();
    // 获取全部成员变量
    Field[] fields = aClass.getDeclaredFields();
    for (Field field : fields) {
        System.out.println(field);
    }
}
```

**获取某个成员变量并修改值**

```java
@Test
public void testSet() throws Exception {
    Class<Student> aClass = Student.class;
    Constructor<Student> constructor = aClass.getDeclaredConstructor();
    constructor.setAccessible(true);
    Student student = constructor.newInstance();

    // getDeclaredField("属性名") 获取字段；set(对象, 新值) 修改字段值
    Field name = aClass.getDeclaredField("name");
    name.setAccessible(true); // 私有成员需要暴力反射
    name.set(student, "小哈");

    Field age = aClass.getDeclaredField("age");
    age.setAccessible(true);
    age.set(student, 18);

    Field gender = aClass.getDeclaredField("gender");
    gender.setAccessible(true);
    gender.set(student, "男");

    System.out.println(student);
}
```

**获取某个成员变量的值**

```java
// 在上面设置完值之后
Field name1 = aClass.getDeclaredField("name");
name1.setAccessible(true);
System.out.println(name1.get(student)); // field.get(对象) 取值

Field age1 = aClass.getDeclaredField("age");
age1.setAccessible(true);
System.out.println(age1.get(student));
```

#### 2.5 第四步：获取成员方法 Method

准备一个含私有方法的类：

```java
public class Student1 {
    private String name;
    private int age;

    private Student1() {}

    private Student1(String name, int age) {
        this.name = name;
        this.age = age;
    }

    private void eat() {                          // 无参方法
        System.out.println(this.name + "正在吃饭~~~");
    }

    private void run(String name) {               // 有参方法
        System.out.println(this.name + "在跑步~~~");
    }

    private int sum(int a, int b) {               // 有参有返回值方法
        return a + b;
    }

    @Override
    public String toString() {
        return "Student1{name='" + name + "', age=" + age + "}";
    }
}
```

**获取全部成员方法**

```java
@Test
public void testAll() throws Exception {
    Class<Student1> aClass = Student1.class;
    Constructor<Student1> constructor = aClass.getDeclaredConstructor(String.class, int.class);
    constructor.setAccessible(true);
    Student1 student1 = constructor.newInstance("小哈", 18);
    System.out.println(student1);

    Method[] methods = aClass.getDeclaredMethods();
    for (Method method : methods) {
        System.out.println(method);
    }
}
```

**获取并执行无参、有参、有返回值方法**

```java
@Test
public void testInvoke() throws Exception {
    Class<Student1> aClass = Student1.class;
    Constructor<Student1> constructor = aClass.getDeclaredConstructor(String.class, int.class);
    constructor.setAccessible(true);
    Student1 student1 = constructor.newInstance("小哈", 18);

    // 无参方法：getDeclaredMethod("方法名")
    Method eat = aClass.getDeclaredMethod("eat");
    eat.setAccessible(true);
    eat.invoke(student1); // invoke(对象) 执行方法

    // 有参方法：getDeclaredMethod("方法名", 参数类型...)
    Method run = aClass.getDeclaredMethod("run", String.class);
    run.setAccessible(true);
    run.invoke(student1, "湖边"); // invoke(对象, 实参...)

    // 有参有返回值方法：invoke 的返回值就是原方法的返回值（Object 类型，需要强转）
    Method sum = aClass.getDeclaredMethod("sum", int.class, int.class);
    sum.setAccessible(true);
    int value = (int) sum.invoke(student1, 2, 3);
    System.out.println(value);
}
```

#### 2.6 反射的作用

- 基本作用：可以得到一个类的全部成分然后操作。
- 反射可以破坏 Java 类的封装性（`setAccessible(true)` 暴力访问私有成员）。
- 最重要的用途：**适合做 Java 的框架**——主流框架基本都基于反射设计通用功能。

#### 2.7 反射案例：简易版保存对象框架

需求：对于任意一个对象，框架都能把对象的字段名和对应值保存到文件中（`key=value` 结构）。

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.lang.reflect.Field;

public class Demo {
    public static void main(String[] args) throws Exception {
        Star star1 = new Star("小哈", 18, 178.9, 52.5);
        saveObject(star1);
    }

    // 接收任意对象
    private static void saveObject(Object obj) throws Exception {
        FileWriter fw = new FileWriter("JunitDemo\\lib\\config.txt");
        BufferedWriter bw = new BufferedWriter(fw);

        // 通过反射获取对象的所有属性
        Class<?> aClass = obj.getClass();
        Field[] fields = aClass.getDeclaredFields();
        bw.write("==========" + aClass.getSimpleName() + "=========="); // getSimpleName() 纯类名
        bw.newLine();
        for (Field field : fields) {
            field.setAccessible(true); // 属性都是私有的，不暴力反射会报错
            String name = field.getName();
            Object value = field.get(obj); // field.get(对象) 获取值
            bw.write(name + "=" + value);
            bw.newLine();
        }
        bw.close();
        System.out.println("执行结束了");
    }
}
```

```java
public class Star {
    private String name;
    private int age;
    private Double height;
    private Double weight;

    public Star() {}

    public Star(String name, int age, Double height, Double weight) {
        this.name = name;
        this.age = age;
        this.height = height;
        this.weight = weight;
    }
}
```

### 三、注解（Annotation）

#### 3.1 注解概述

注解是 Java 代码里的特殊标记，比如 `@Override`、`@Test`。它的作用是：**让其他程序根据注解信息来决定怎么执行该程序**。

注解可以用在类上、构造器上、方法上、成员变量上、参数上等位置。

#### 3.2 自定义注解

**语法：**

```java
public @interface 注解名称 {
    public 属性类型 属性名() default 默认值;
}
```

示例：

```java
public @interface Limit {
    String name();
    boolean flag();
    String[] strs();
}
```

**使用注解：**

```java
@Limit(name = "我是注解", flag = true, strs = {"java", "html"})
public class Demo1 {
    @Limit(name = "我是注解", flag = true, strs = {"java", "html"})
    private String name;

    @Limit(name = "我是注解", flag = true, strs = {"java", "html"})
    public void test() {
    }
}
```

**特殊属性名 value 与默认值**

- 如果注解中只有一个 `value` 属性，使用注解时 `value` 名称可以省略。
- 属性可以用 `default` 设置默认值。

```java
public @interface Limit {
    String value();
    boolean flag() default false;
}
```

```java
@Limit("你好")
public class Demo2 {
    @Limit("你好")
    private String name;

    @Limit("你好")
    public void demo1() {}
}
```

#### 3.3 元注解

元注解指的是**修饰注解的注解**，常用两个：

- `@Target`：规定注解可以用在哪些位置（`ElementType.TYPE` 类、`ElementType.METHOD` 方法、`ElementType.FIELD` 字段等）。
- `@Retention`：规定注解的存活范围，`RetentionPolicy.RUNTIME` 表示一直存活到运行时（反射才能读到）。

```java
@Target({ElementType.TYPE, ElementType.METHOD})
@Retention(RetentionPolicy.RUNTIME)
public @interface Limit {
    String value();
    boolean flag() default false;
}
```

JUnit 的 `@Test` 本身也是这样定义的：

```java
@Retention(RetentionPolicy.RUNTIME)
@Target({ElementType.METHOD})
public @interface Test {
}
```

#### 3.4 注解的解析

注解解析就是判断类上、方法上、成员变量上是否存在注解，并把注解里的内容解析出来。

指导思想：**要解析谁上面的注解，就应该先拿到谁。**

- 解析类上的注解：先拿到 Class 对象。
- 解析方法上的注解：先拿到 Method 对象。
- `Class`、`Method`、`Field`、`Constructor` 都实现了 `AnnotatedElement` 接口，都具备解析注解的能力。

```java
@Test
public void test() {
    // 基于反射解析注解中的信息
    Class<Demo> aClass = Demo.class;
    // 获取类上面的指定注解
    MyTest4 annotation = aClass.getDeclaredAnnotation(MyTest4.class);
    System.out.println(annotation.value());
    System.out.println(annotation.aaa());
    String[] bbb = annotation.bbb();
    System.out.println(Arrays.toString(bbb));
}
```

#### 3.5 注解案例：模拟 JUnit 框架

需求：定义若干方法，只要加了 `@MyTest` 注解，运行时就自动触发该方法执行。

第一步，定义自定义注解（只能注解方法、运行时存活）：

```java
import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;

@Target(ElementType.METHOD)        // 只能注解方法
@Retention(RetentionPolicy.RUNTIME) // 一直存活到运行时
public @interface MyTest {
}
```

第二步，业务类中部分方法加注解：

```java
public class Demo {
    public void test01() {
        System.out.println("===test01===");
    }

    @MyTest
    public void test02() {
        System.out.println("===test02===");
    }

    public void test03() {
        System.out.println("===test03===");
    }

    @MyTest
    public void test04() {
        System.out.println("===test04===");
    }

    public void test05() {
        System.out.println("===test05===");
    }

    // 模拟 JUnit 的启动按钮
    public static void main(String[] args) throws Exception {
        Demo demo = new Demo();
        Class<Demo> aClass = Demo.class;
        Method[] methods = aClass.getDeclaredMethods();
        for (Method method : methods) {
            // 判断方法上是否存在 @MyTest 注解
            if (method.isAnnotationPresent(MyTest.class)) {
                method.setAccessible(true);
                method.invoke(demo); // 触发加了注解的方法执行
            }
        }
    }
}
```

### 四、动态代理

#### 4.1 为什么需要代理

对象如果嫌身上干的事太多（比如核心业务之外还要统计耗时、打日志、谈合同收钱），可以通过代理转移部分职责。对象有什么方法想被代理，代理就一定要有对应的方法——JDK 动态代理通过**接口**来约定需要代理的方法。

先定义接口和被代理类（源对象）：

```java
public interface Star {
    void sing(String name);
    void dance();
}
```

```java
public class BigStar implements Star {
    String name;

    public BigStar(String name) {
        this.name = name;
    }

    @Override
    public void sing(String name) {
        System.out.println(this.name + "正在唱" + name);
    }

    @Override
    public void dance() {
        System.out.println(this.name + "正在跳舞~~~");
    }
}
```

使用 `Proxy.newProxyInstance()` 创建代理对象：

```java
import java.lang.reflect.InvocationHandler;
import java.lang.reflect.Method;
import java.lang.reflect.Proxy;

public class ProxyUtil {
    public static void main(String[] args) {
        BigStar bigStar = new BigStar("杨超越"); // 被代理的对象（源对象）

        Star starProxy = (Star) Proxy.newProxyInstance(
                // 参数1：类加载器，写法固定：当前类.class.getClassLoader()
                ProxyUtil.class.getClassLoader(),
                // 参数2：代理对象需要实现的接口数组（JDK 动态代理基于接口）
                new Class[]{Star.class},
                // 参数3：InvocationHandler，指定代理对象要干的事
                new InvocationHandler() {
                    @Override
                    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
                        // proxy：代理对象（一般不用）
                        // method：正在被调用的原方法
                        // args：原方法的参数
                        System.out.println("谈费用，然后签合同~~~");      // 前置增强
                        Object invoke = method.invoke(bigStar, args);   // 执行源对象的原方法
                        System.out.println("收钱，打扫场地~~~");          // 后置增强
                        return invoke;
                    }
                });

        starProxy.sing("我和我的祖国");
        System.out.println("-------------------------");
        starProxy.dance();
    }
}
```

#### 4.2 案例：用动态代理统计方法耗时

某用户管理模块有登录、删除、查询功能，系统要求统计每个功能的执行耗时。

原始接口与实现类：

```java
public interface UserInterface {
    void login(String username, String password); // 用户登录
    void delUser(String username);                // 用户删除
    void findUser(String username);               // 用户查询
}
```

```java
public class UserManagerment implements UserInterface {
    @Override
    public void login(String username, String password) {
        if (username.equals("admin") && password.equals("123456")) {
            System.out.println("登录成功：" + username);
        } else {
            System.out.println("用户名密码错误~~~");
        }
    }

    @Override
    public void delUser(String username) {
        System.out.println("删除成功！" + username);
    }

    @Override
    public void findUser(String username) {
        System.out.println("查找成功！" + username);
    }
}
```

如果直接在每个方法里写计时逻辑，代码大量冗余（每个方法都要复制开始时间、结束时间、打印耗时）。把重复的计时逻辑交给代理对象统一执行：

```java
import java.lang.reflect.InvocationHandler;
import java.lang.reflect.Method;
import java.lang.reflect.Proxy;

public class ProxyUtil {
    public static void main(String[] args) {
        UserInterface proxy = ProxyUtil.createProxy(new UserManagerment());
        proxy.login("admin", "123456");
        System.out.println("---------------------");
        proxy.delUser("admin");
        System.out.println("---------------------");
        proxy.findUser("admin");
    }

    /**
     * @param user 没有增强的源对象
     * @return     增强后的代理对象
     */
    public static UserInterface createProxy(UserInterface user) {
        UserInterface userProxy = (UserInterface) Proxy.newProxyInstance(
                ProxyUtil.class.getClassLoader(),      // 类加载器
                new Class[]{UserInterface.class},      // 源对象实现的接口（JDK 代理必须依赖接口）
                new InvocationHandler() {
                    @Override
                    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
                        long start = System.currentTimeMillis();
                        Object invoke = method.invoke(user, args); // 调用源对象的原方法
                        long end = System.currentTimeMillis();
                        System.out.println(method.getName() + "方法耗时" + (end - start) + "毫秒");
                        return invoke;
                    }
                });
        return userProxy;
    }
}
```

### 本章小结

- **JUnit**：测试方法必须公共、无参、无返回值并加 `@Test`；`@BeforeEach/@AfterEach` 每个测试前后执行，`@BeforeAll/@AfterAll` 全局只执行一次且必须 static；用 `Assertions.assertEquals(预期值, 实际值, 提示)` 做断言。
- **反射**：三种方式获取 Class 对象（`类名.class`、`Class.forName(全类名)`、`对象.getClass()`）；`getDeclaredConstructor/Field/Method` 获取类的成分，私有成员需 `setAccessible(true)` 暴力反射；`newInstance()` 创建对象、`field.get/set` 读写字段、`method.invoke` 执行方法。反射是框架设计的基础。
- **注解**：`@interface` 定义注解，特殊属性 `value` 使用时可省略，`default` 设默认值；元注解 `@Target` 限定位置、`@Retention(RUNTIME)` 保证运行时可解析；通过 `AnnotatedElement` 接口的 `getDeclaredAnnotation` / `isAnnotationPresent` 配合反射解析注解。
- **动态代理**：`Proxy.newProxyInstance(类加载器, 接口数组, InvocationHandler)` 创建代理；在 `invoke` 方法中写前置/后置增强逻辑，并用 `method.invoke(源对象, args)` 调用原方法，可把计时、日志等重复逻辑从业务类中抽离。

---

# 附 录

<div style="page-break-after: always;"></div>

## 附录 A 练习题与参考答案

本附录汇总课程配套的两批练习：基础语法阶段的 11 道选择题与 11 道编程题，以及面向对象阶段的 8 道接口与多态综合题。每题均附参考答案与解析。

---

## 第一部分 选择题（基础语法）

### 1. 以下代码，会编译报错的是（ ）

```java
A. int a = 10 ; a += 13.14;
B. double a = 10;
C. char a = 97;
D. short a = 10 ;
   short b = 20 ;
   short c = a + b;
```

**答案：D**

**解析：** `short`、`char`、`byte` 类型的变量参与运算时，会先自动提升为 `int` 再计算，因此 `a + b` 的结果是 `int` 类型，赋值给 `short` 类型的 `c` 需要强制转换。A 选项中 `+=` 是扩展赋值运算符，底层自带强转，`a += 13.14` 等价于 `a = (int)(a + 13.14)`，不会报错。

### 2. 以下代码执行的结果不可能的是（ ）

```java
public static void main(String[] args) {
    Random r = new Random();
    int num = r.nextInt(6) + 6;
    System.out.println(num);
}
```

```
A. 10
B. 11
C. 12
D. 6
```

**答案：C**

**解析：** `r.nextInt(6)` 生成的是 0~5（含 0 不含 6）的随机整数，再加 6，结果范围是 6~11，不可能出现 12。

### 3.【多选】以下关于 JVM 的叙述，正确的是（ ）

```
A. JVM 运行于操作系统之上，它依赖于操作系统
B. JVM 运行于操作系统之上，它与操作系统无关
C. JVM 支持 Java 程序运行，它能够直接运行 Java 字节码文件
D. JVM 支持 Java 程序运行，它能够直接运行 Java 源代码文件
```

**答案：AC**

**解析：** JVM（Java 虚拟机）运行在操作系统之上，不同操作系统有不同版本的 JVM，它依赖操作系统；JVM 直接运行的是编译后的 `.class` 字节码文件，源代码 `.java` 必须先经 `javac` 编译。

### 4. 下面程序哪一句是错误的？（ ）

```java
public class Test2 {
    public static void main(String[] args) {
        short a, b, c;
        a = 1;
        b = 2;
        c = a + b;
    }
}
```

```
A. a = 1
B. c = a + b
C. a += 2
D. short a, b, c
```

**答案：B**

**解析：** `a`、`b`、`c` 都是 `short`，参与运算时自动提升为 `int`，`a + b` 的结果是 `int`，赋值给 `short` 类型的 `c` 需要强转：`c = (short)(a + b);`。

### 5. 以下变量声明不正确的是（ ）

```
A. int _a = 10;
B. int 0x = 1996;
C. char string = 'a';
D. byte S1994 = 15;
```

**答案：B**

**解析：** 变量名不能以数字开头，`0x` 以数字开头非法。变量名可以以字母、下划线 `_`、美元符 `$` 开头；`string` 不是关键字，可以作为变量名。

### 6. 以下代码运行结果是（ ）

```java
int i = 123, j = 125;
i = (i > j ? 123 : 125);
j = (i < j ? 123 : 125);
System.out.print("i:" + i + "j" + j);
```

```
A. i:123 j:125
B. i:125 j:123
C. i:123 j:123
D. i:125 j:125
```

**答案：D**

**解析：** 第一步 `123 > 125` 为 false，`i` 被赋值为 125；第二步 `i < j` 即 `125 < 125` 为 false，`j` 被赋值为 125。最终 `i:125j125`。

### 7. 以下关于数据类型的转换，说法错误的是（ ）

```
A. int a = 1; byte b = 1; System.out.println(a+b); 打印的值为 2
B. int 类型的数据转为 double 类型，需要强制转换
C. int 强制转成 short 砍掉 2 个字节，可能造成数据丢失
D. short h = 1; h = h + 1; 需要使用强制转换才能编译成功
```

**答案：B**

**解析：** `int` 转 `double` 是小范围转大范围，属于自动类型转换，不需要强转。大范围转小范围（如 `int` 转 `short`）才需要强制转换，且可能丢失数据。

### 8. 下面对变量名定义符合规范的是（ ）

```
A. private
B. 3a_b = 10
C. $zb
D. a+b
```

**答案：C**

**解析：** A 是 Java 关键字不能作变量名；B 以数字开头非法；D 含运算符 `+` 非法。`$` 可以作为变量名开头，C 合法。

### 9.【多选】以下关于运算符说法正确的有（ ）

```
A. && 短路与，符号左边是 false，右边不再运算
B. + 可以用来做加法运算，也可以当连接符
C. % 表示取整，/ 表示取余
D. i++ 就是先变量参与操作，之后变量做自增；++i 先变量做自增，之后变量参与操作
```

**答案：ABD**

**解析：** C 说反了：`%` 是取余（取模），`/` 是除法（取整）。其余三项均正确。

### 10.【多选】下面变量定义正确的是（ ）

```
A. int ￥1 = 1;
B. double d = 2.14D;
C. boolean b = "t";
D. char c = '2';
```

**答案：BD**

**解析：** A 中 `￥` 虽然是 Unicode 字符可以出现在标识符中，但该写法在题目语境中判为错误写法；B 中 `2.14D` 是 double 字面量的标准写法；C 中布尔类型只能赋 `true`/`false`，不能赋字符串；D 中字符 `'2'` 是合法的 char 字面量。

### 11.【多选】以下表达式结果为 true 的有（ ）

```java
A. int a = 8;
   byte b = 8;
   System.out.println(a == b);

B. int a = 97;
   char b = 'a';  // a~z 对应 97-122
   System.out.println(a == b);

C. int a = 10;
   long b = 10;
   System.out.println(a == b);

D. short a = 127;
   long b = 127;
   System.out.println(a == b);
```

**答案：ABCD**

**解析：** 基本数据类型比较时，`==` 比较的是数值本身；不同类型会先自动提升为同一类型再比较。`byte`/`char`/`short` 都会提升为 `int` 或 `long`，只要数值相等结果就是 true。字符 `'a'` 的编码值恰好是 97。

---

## 第二部分 编程题（基础语法）

### 编程题 1：两整数和差积

**需求：** 使用 `Scanner` 接收控制台输入的两个整数，计算并输出它们的和、差、积。

```
请输入第一个整数：5
请输入第二个整数：6
和：11
差：-1
积：30
```

**参考答案：**

```java
import java.util.Scanner;

public class Test1 {
    public static void main(String[] args) {
        // 创建 Scanner 对象
        Scanner sc = new Scanner(System.in);
        // 接收输入
        System.out.print("请输入第一个整数：");
        int a = sc.nextInt();
        System.out.print("请输入第二个整数：");
        int b = sc.nextInt();

        // 计算并输出
        System.out.println("和：" + (a + b));
        System.out.println("差：" + (a - b));
        System.out.println("积：" + (a * b));

        sc.close();
    }
}
```

### 编程题 2：随机数奇偶判断

**需求：** 使用 `Random` 生成一个 1~50 的随机整数，通过三元运算符判断该数是奇数还是偶数，并输出结果。

输出示例：`随机数：10，是偶数`

**参考答案：**

```java
import java.util.Random;

public class Test2 {
    public static void main(String[] args) {
        // 创建 Random 对象
        Random r = new Random();
        // 生成 1~50 随机数：nextInt(50) 是 0~49，+1 后为 1~50
        int num = r.nextInt(50) + 1;
        // 三元运算符判断奇偶：能被 2 整除是偶数
        String result = num % 2 == 0 ? "偶数" : "奇数";

        System.out.println("随机数：" + num + "，是" + result);
    }
}
```

**解析：** 对 2 取余为 0 即为偶数。JDK 17+ 也可使用 `r.nextInt(1, 51)` 直接生成 1~50 的随机数。

### 编程题 3：商品收银结算

**需求：**

1. 控制台录入商品单价、购买数量；
2. 计算商品总价，满 100 元立减 15 元；
3. 输出原价总价、优惠后实付金额。

**考察点：** 算术运算、赋值运算符、`Scanner` 录入、关系判断。

**参考答案：**

```java
import java.util.Scanner;

public class ShopPay {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入商品单价：");
        double price = sc.nextDouble();
        System.out.print("请输入购买数量：");
        int count = sc.nextInt();

        // 总价 = 单价 * 数量
        double total = price * count;
        // 满减逻辑：总价 >= 100 减 15，否则不优惠
        double pay = total >= 100 ? total - 15 : total;

        System.out.println("商品原价总价：" + total + " 元");
        System.out.println("优惠后实付金额：" + pay + " 元");
        sc.close();
    }
}
```

### 编程题 4：员工年龄职级划分

**需求：**

1. 录入员工年龄；
2. 用三元运算符划分：18 岁及以上为正式员工，18 岁以下为实习员工；
3. 同时判断是否满 30 岁，输出资深员工标识。

```
请输入员工年龄：25
员工身份：正式员工
```

**考察点：** 关系运算符、三元运算符、字符串拼接、`Scanner`。

**参考答案：**

```java
import java.util.Scanner;

public class StaffLevel {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入员工年龄：");
        int age = sc.nextInt();

        // jobType 职位类别
        String jobType = age >= 18 ? "正式员工" : "实习员工";
        // senior 资深员工标识：满 30 岁追加后缀，否则为空字符串
        String senior = age >= 30 ? "，属于资深员工" : "";

        System.out.println("员工身份：" + jobType + senior);
        sc.close();
    }
}
```

### 编程题 5：用户账号拼接

**需求：**

1. 录入用户姓名、用户编号；
2. 拼接格式：`编号_姓名` 作为系统登录账号；
3. 拼接固定前缀 `USER_` 统一规范账号。

```
请输入用户姓名：小哈
请输入用户编号：001
生成系统登录账号：USER_1_小哈
```

**考察点：** 字符串拼接、变量使用、控制台录入。

**参考答案：**

```java
import java.util.Scanner;

public class UserAccount {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入用户姓名：");
        String name = sc.next();
        System.out.print("请输入用户编号：");
        int id = sc.nextInt();

        // 拼接系统标准账号：USER_ 前缀 + 编号 + 下划线 + 姓名
        String account = "USER_" + id + "_" + name;
        System.out.println("生成系统登录账号：" + account);
    }
}
```

### 编程题 6：浏览量自增统计

**需求：**

1. 初始页面浏览量为 100；
2. 分别使用前置自增、后置自增模拟两次用户访问；
3. 输出每一次访问后的最终浏览量。

```
初始浏览量：100
后置自增取值：100，当前浏览量：101
前置自增取值：102，当前浏览量：102
```

**考察点：** `++i` 与 `i++` 的核心区别。

**参考答案：**

```java
public class ViewCount {
    public static void main(String[] args) {
        // 初始浏览量
        int view = 100;
        System.out.println("初始浏览量：" + view);

        // 后置自增：先取原值参与运算，再自增
        int v1 = view++;
        System.out.println("后置自增取值：" + v1 + "，当前浏览量：" + view);

        // 前置自增：先自增，再取新值参与运算
        int v2 = ++view;
        System.out.println("前置自增取值：" + v2 + "，当前浏览量：" + view);
    }
}
```

**解析：** `view++` 先把 100 赋给 `v1`，view 再变为 101；`++view` 先把 view 从 101 增到 102，再把 102 赋给 `v2`。

### 编程题 7：成绩等级评定

**需求：**

1. 录入学生浮点型分数；
2. 强制转换为整数分数；
3. 三元运算符判定：大于等于 60 及格，否则不及格。

```
请输入学生分数：89.5
取整后分数：89
评定结果：成绩及格
```

**考察点：** 强制类型转换、关系运算符、三元运算。

**参考答案：**

```java
import java.util.Scanner;

public class ScoreJudge {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入学生分数：");
        double score = sc.nextDouble();

        // 浮点转整数：强制类型转换，直接砍掉小数部分，数据可能丢失
        int intScore = (int) score;
        // 三元运算符判断是否及格
        String res = intScore >= 60 ? "成绩及格" : "成绩不及格";

        System.out.println("取整后分数：" + intScore);
        System.out.println("评定结果：" + res);
    }
}
```

### 编程题 8：工资补贴计算

**需求：**

1. 录入基础工资、交通补贴；
2. 使用复合赋值运算符 `+=` 合并总收入；
3. 输出最终实发工资。

```
输入基础工资：3600
输入交通补贴：200
员工月总收入：3800.0 元
```

**考察点：** 赋值运算符 `+=`、算术运算。

**参考答案：**

```java
import java.util.Scanner;

public class SalaryCalc {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("输入基础工资：");
        double base = sc.nextDouble();
        System.out.print("输入交通补贴：");
        double subsidy = sc.nextDouble();

        // 复合赋值运算：base = base + subsidy
        base += subsidy;
        System.out.println("员工月总收入：" + base + " 元");
    }
}
```

### 编程题 9：数字大小比对

**需求：**

1. 录入两个数值；
2. 通过关系运算符判断大小，输出最大值。

**考察点：** 关系运算符、三元取最大值。

**参考答案：**

```java
import java.util.Scanner;

public class NumCompare {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入第一个数值：");
        int a = sc.nextInt();
        System.out.print("请输入第二个数值：");
        int b = sc.nextInt();

        // 三元运算符求最大值
        int max = a > b ? a : b;
        System.out.println("两个数中最大值为：" + max);
    }
}
```

### 编程题 10：奶茶店结账

**需求：** 输入饮品单价、购买杯数，会员满 5 杯打 8 折，计算应付金额。

```
饮品单价：6.8
购买杯数：5
原价：34.0元  实付：27.200000000000003元
```

**考察点：** 算术运算、三元运算符、Scanner 录入。

**参考答案：**

```java
import java.util.Scanner;

public class CateringShop {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("饮品单价：");
        double price = sc.nextDouble();
        System.out.print("购买杯数：");
        int num = sc.nextInt();

        // 总价 = 单价 * 杯数
        double total = price * num;

        // 满 5 杯打 8 折
        double pay = num >= 5 ? total * 0.8 : total;

        System.out.println("原价：" + total + "元  实付：" + pay + "元");
    }
}
```

**解析：** `27.200000000000003` 是浮点数运算的精度误差。如需保留两位小数，可用 `String.format("%.2f", pay)` 格式化输出，或使用 `BigDecimal` 类进行精确运算。

### 编程题 11：酒店入住计费

**需求：** 输入房价、入住天数，周末入住每天加价 30 元。

```
房间单价：200
入住天数：10
是否周末入住(1是/0否)：1
入住总费用：2300元
```

**考察点：** 基础运算、条件判断。

**参考答案：**

```java
import java.util.Scanner;

public class HotelCost {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("房间单价：");
        int roomPrice = sc.nextInt();
        System.out.print("入住天数：");
        int day = sc.nextInt();
        System.out.print("是否周末入住(1是/0否)：");
        int flag = sc.nextInt();

        // flag 为 1 时每天加价 30 元
        int total = flag == 1 ? (roomPrice + 30) * day : roomPrice * day;

        System.out.println("入住总费用：" + total + "元");
    }
}
```

---

## 第三部分 接口与多态练习

### 通用规则

1. 接口只定义**行为规范**，不写实现；
2. 子类**实现接口**，必须重写所有抽象方法；
3. 用**接口类型引用**指向实现类对象，体现多态。

核心语法：`interface` 定义接口、`implements` 实现接口、接口引用指向子类对象。
多态优势：代码通用、易扩展（例如新增一种支付方式，不需要修改原有代码）。

### 练习 1：动物发声系统（入门）

**场景：** 动物园管理系统，统一让不同动物发出叫声。

**需求：**

1. 定义接口 `Animal`，包含抽象方法 `void makeSound()`；
2. 编写两个实现类 `Dog`、`Cat`，重写发声方法；
3. 测试类中用多态调用方法。

**参考答案：**

```java
// 1. 定义接口：规范行为
public interface Animal {
    // 抽象方法：所有动物必须实现发声
    void makeSound();
}

// 2. 实现类：狗
public class Dog implements Animal {
    @Override
    public void makeSound() {
        System.out.println("小狗：汪汪汪");
    }
}

// 实现类：猫
public class Cat implements Animal {
    @Override
    public void makeSound() {
        System.out.println("小猫：喵喵喵");
    }
}
```

```java
// 测试类：体现多态
public class Test1 {
    public static void main(String[] args) {
        // 多态核心：接口引用指向子类对象
        Animal animal1 = new Dog();
        Animal animal2 = new Cat();

        // 统一调用方法，自动执行子类的实现
        animal1.makeSound(); // 小狗：汪汪汪
        animal2.makeSound(); // 小猫：喵喵喵
    }
}
```

### 练习 2：统一支付系统（电商实战）

**场景：** 电商 APP 支持微信支付、支付宝支付，后台用统一代码调用支付功能。

**需求：**

1. 定义接口 `Pay`，包含抽象方法 `void pay(double money)`；
2. 实现类 `WechatPay`、`Alipay`；
3. 编写通用支付方法，接收 `Pay` 接口类型参数完成支付（多态参数）。

**参考答案：**

```java
// 支付接口：统一支付规范
public interface Pay {
    void pay(double money);
}

// 微信支付
public class WechatPay implements Pay {
    @Override
    public void pay(double money) {
        System.out.println("微信支付成功，金额：" + money + "元");
    }
}

// 支付宝支付
public class Alipay implements Pay {
    @Override
    public void pay(double money) {
        System.out.println("支付宝支付成功，金额：" + money + "元");
    }
}
```

```java
// 测试类
public class Test2 {
    // 通用支付方法：多态参数，可接收任意支付方式
    public static void doPay(Pay pay, double money) {
        pay.pay(money);
    }

    public static void main(String[] args) {
        doPay(new WechatPay(), 99.8);  // 微信支付成功，金额：99.8元
        doPay(new Alipay(), 199.5);    // 支付宝支付成功，金额：199.5元
    }
}
```

**解析：** 方法参数用接口类型 `Pay`，调用时传入任意实现类对象，这就是"面向接口编程"。新增支付方式（如云闪付）时只需新增实现类，`doPay` 方法无需改动。

### 练习 3：员工薪资计算（HR 系统）

**场景：** 公司 HR 系统计算全职员工、兼职员工的月薪。

**需求：**

1. 定义接口 `Employee`，抽象方法 `double getSalary()`；
2. 实现类 `FullTimeEmployee`（固定月薪 8000）、`PartTimeEmployee`（时薪 50，工作 100 小时）；
3. 用多态遍历员工数组，计算总工资。

**参考答案：**

```java
public interface Employee {
    // 获取薪资：抽象方法没有方法体，重写时需要 return 返回结果
    double getSalary();
}

// 全职员工
public class FullTimeEmployee implements Employee {
    @Override
    public double getSalary() {
        return 8000; // 固定月薪
    }
}

// 兼职员工
public class PartTimeEmployee implements Employee {
    @Override
    public double getSalary() {
        return 50 * 100; // 时薪 × 工时 = 5000
    }
}
```

```java
// 测试类
public class Test {
    public static void main(String[] args) {
        // 多态数组：接口类型存储所有员工（父类引用指向子类对象）
        Employee[] employees = {new FullTimeEmployee(), new PartTimeEmployee()};
        double total = 0;
        for (int i = 0; i < employees.length; i++) {
            Employee emp = employees[i];
            // 获取当前员工工资（return 把结果返回给调用者）
            double salary = emp.getSalary();
            total += salary;
            if (emp instanceof PartTimeEmployee) {
                System.out.println("兼职员工的薪资是：" + salary);
            } else if (emp instanceof FullTimeEmployee) {
                System.out.println("全职员工的薪资是：" + salary);
            }
        }
        System.out.println("公司总薪资支出：" + total);
    }
}
```

```
全职员工的薪资是：8000.0
兼职员工的薪资是：5000.0
公司总薪资支出：13000.0
```

**解析：** `instanceof` 用于判断对象的真实类型，从而区分员工身份做不同处理。

### 练习 4：智能设备控制（物联网）

**场景：** 智能家居系统，统一控制灯、空调的开关。

**需求：**

1. 定义接口 `SmartDevice`，两个抽象方法 `turnOn()`、`turnOff()`；
2. 实现类 `Light`、`AirConditioner`；
3. 用多态统一开关所有设备。

**参考答案：**

```java
// 智能设备接口
public interface SmartDevice {
    void turnOn();  // 开机
    void turnOff(); // 关机
}

// 灯
public class Light implements SmartDevice {
    @Override
    public void turnOn() {
        System.out.println("灯：已开启，亮度100%");
    }
    @Override
    public void turnOff() {
        System.out.println("灯：已关闭");
    }
}

// 空调
public class AirConditioner implements SmartDevice {
    @Override
    public void turnOn() {
        System.out.println("空调：已开启，制冷26℃");
    }
    @Override
    public void turnOff() {
        System.out.println("空调：已关闭");
    }
}
```

```java
// 测试类
public class Test4 {
    public static void main(String[] args) {
        // 多态创建对象
        SmartDevice light = new Light();
        SmartDevice ac = new AirConditioner();

        // 统一控制
        light.turnOn();  // 灯：已开启，亮度100%
        ac.turnOn();     // 空调：已开启，制冷26℃
        light.turnOff(); // 灯：已关闭
        ac.turnOff();    // 空调：已关闭
    }
}
```

### 练习 5：游戏角色攻击

**场景：** 小游戏后台，统一执行不同角色的攻击动作。

**需求：**

1. 定义接口 `GameRole`，抽象方法 `void attack()`；
2. 实现类 `Warrior`（战士）、`Mage`（法师）；
3. 用多态数组遍历所有角色，统一攻击。

**参考答案：**

```java
// 游戏角色接口
public interface GameRole {
    void attack();
}

// 战士
public class Warrior implements GameRole {
    @Override
    public void attack() {
        System.out.println("战士：用大剑挥砍攻击");
    }
}

// 法师
public class Mage implements GameRole {
    @Override
    public void attack() {
        System.out.println("法师：释放火球术攻击");
    }
}
```

```java
// 测试类
public class Test7 {
    public static void main(String[] args) {
        // 多态数组
        GameRole[] roles = {new Warrior(), new Mage()};
        // 统一执行攻击
        for (int i = 0; i < roles.length; i++) {
            roles[i].attack();
        }
    }
}
```

```
战士：用大剑挥砍攻击
法师：释放火球术攻击
```

### 练习 6：打印机打印（办公设备）

**场景：** 打印管理系统，控制不同打印机工作。

**需求：**

1. 定义接口 `Printer`，抽象方法 `void print(String content)`；
2. 实现类 `LaserPrinter`（激光打印机）、`InkPrinter`（喷墨打印机）；
3. 传入打印内容，多态调用打印功能。

**参考答案：**

```java
// 打印机接口
public interface Printer {
    void print(String content);
}

// 激光打印机
public class LaserPrinter implements Printer {
    @Override
    public void print(String content) {
        System.out.println("激光打印机打印：" + content);
    }
}

// 喷墨打印机
public class InkPrinter implements Printer {
    @Override
    public void print(String content) {
        System.out.println("喷墨打印机打印：" + content);
    }
}
```

```java
// 测试类
public class Test8 {
    public static void main(String[] args) {
        Printer p1 = new LaserPrinter();
        Printer p2 = new InkPrinter();

        p1.print("员工考勤表"); // 激光打印机打印：员工考勤表
        p2.print("会议纪要");   // 喷墨打印机打印：会议纪要
    }
}
```

### 综合题 1：电子产品充电管理

**场景：** 智能家居管理平台，统一管理手机、平板的充电与电量显示。

**需求：**

1. 定义接口 `Chargeable`，包含 `void charge()`（充电）和 `void showBattery()`（显示电量）两个方法；
2. 实现类 `Phone`、`Tablet`：属性 `battery`（电量），构造方法初始化电量；
3. 重写方法：充电后电量 +10，显示当前电量；
4. 用多态数组统一管理所有设备，批量充电并查看电量。

**参考答案：**

```java
// 充电接口（多方法规范）
public interface Chargeable {
    void charge();      // 充电
    void showBattery(); // 显示电量
}

// 手机类（属性 + 构造方法 + 实现接口）
public class Phone implements Chargeable {
    private int battery; // 电量

    public Phone(int battery) {
        this.battery = battery;
    }

    @Override
    public void charge() {
        battery += 10;
        System.out.println("手机充电中... 当前电量+10");
    }

    @Override
    public void showBattery() {
        System.out.println("手机剩余电量：" + battery + "%");
    }
}

// 平板类
public class Tablet implements Chargeable {
    private int battery;

    public Tablet(int battery) {
        this.battery = battery;
    }

    @Override
    public void charge() {
        battery += 10;
        System.out.println("平板充电中... 当前电量+10");
    }

    @Override
    public void showBattery() {
        System.out.println("平板剩余电量：" + battery + "%");
    }
}
```

```java
// 测试类（多态数组 + 批量处理）
public class Test1 {
    public static void main(String[] args) {
        // 多态数组：接口类型存储不同电子产品
        Chargeable[] devices = {new Phone(50), new Tablet(30)};

        // 统一遍历：充电 + 显示电量
        for (int i = 0; i < devices.length; i++) {
            Chargeable device = devices[i];
            device.charge();
            device.showBattery();
            System.out.println("-------------------");
        }
    }
}
```

```
手机充电中... 当前电量+10
手机剩余电量：60%
-------------------
平板充电中... 当前电量+10
平板剩余电量：40%
-------------------
```

### 综合题 2：企业员工考勤薪资系统

**场景：** HR 管理系统，正式员工、临时工分开计算工资并打卡，统一管理。

**需求：**

1. 定义接口 `Worker`，包含 `void clockIn()`（打卡）和 `double calculateSalary()`（计算工资）两个方法；
2. 实现类：
   - `OfficialWorker`（正式工）：属性 `baseSalary`（底薪 5000）；
   - `TempWorker`（临时工）：属性 `workDays`（工作天数）、`dailyWage`（日薪 200）；
3. 重写方法：打卡提示 + 对应薪资计算；
4. 多态数组统计公司总支出工资。

**参考答案：**

```java
// 员工接口
public interface Worker {
    void clockIn();            // 打卡
    double calculateSalary();  // 计算工资
}

// 正式员工
public class OfficialWorker implements Worker {
    private double baseSalary; // 底薪

    public OfficialWorker() {
        this.baseSalary = 5000; // 固定底薪
    }

    @Override
    public void clockIn() {
        System.out.println("正式员工：上班打卡成功");
    }

    @Override
    public double calculateSalary() {
        return baseSalary; // 月薪 = 底薪
    }
}

// 临时员工
public class TempWorker implements Worker {
    private int workDays;      // 工作天数
    private double dailyWage;  // 日薪

    // 构造方法：传入工作天数
    public TempWorker(int workDays) {
        this.workDays = workDays;
        this.dailyWage = 200;
    }

    @Override
    public void clockIn() {
        System.out.println("临时工：上班打卡成功");
    }

    @Override
    public double calculateSalary() {
        return workDays * dailyWage; // 工资 = 天数 × 日薪
    }
}
```

```java
// 测试类（综合实战）
public class Test3 {
    public static void main(String[] args) {
        // 多态数组：1 个正式工，1 个临时工（工作 20 天）
        Worker[] workers = {new OfficialWorker(), new TempWorker(20)};
        double totalSalary = 0;

        for (int i = 0; i < workers.length; i++) {
            Worker worker = workers[i];
            worker.clockIn();
            double salary = worker.calculateSalary(); // 多态动态计算工资
            totalSalary += salary;
            System.out.println("员工月薪：" + salary + "元");
            System.out.println("-------------------");
        }

        System.out.println("公司本月总薪资支出：" + totalSalary + "元");
    }
}
```

```
正式员工：上班打卡成功
员工月薪：5000.0元
-------------------
临时工：上班打卡成功
员工月薪：4000.0元
-------------------
公司本月总薪资支出：9000.0元
```

---
