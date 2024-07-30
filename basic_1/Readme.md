### XML是什么？
 - 英文：Extensible Markup Language
 - 中文：可扩展标记语言
 - 作用：作为编程中通用的数据标记方式
 - 文件：xxx.xml
 - 特点：格式化、可解析、可传输的数据标记方式
 

```xml
<student>
    <name>Mike</name>
    <age>18</age>
    <score>98</score>
</student>
```

### XML现在的应用？
 - 主要作用应用开发的配置描述
```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

### 如何声明XML？
```xml
<?xml version="1.0" encoding="UTF-8"?>
```

### XML的根标签
```xml
<?xml version="1.0" encoding="UTF-8"?>
<student>
</student>
```
- ```<student>```就是xml文件的根标签
- 根标签在一个xml文件中有且只能有一个根标签
- 根标签内部的所有标签都是根标签的子标签
- 每个标签在整个XML结构中叫做节点
- 一个标签内部的标签叫做这个标签的子标签
- 子标签的上一级标签叫做这个子标签的父标签
- 子标签相对于父标签必须有缩进以表示其父子结构关系
- XML本质上就是由无限父子关系的标签组成的数据结构(树形结构)
```xml
<student>
    <name>Mike</name>
    <age>18</age>
    <score>
        <chinese>86</chinese>
        <math>77</math>
        <english>91</english>
    </score>
</student>
```

```json
{
  "name": "Mike",
  "age": 18,
  "score": {
    "chinese": 86,
    "math": 77,
    "english": 91
  }
}
```

### 标签名的使用规范？
1. 语义化明确
```xml
   <mn>13800000000</mn>
```
2. 使用英文
```xml
   <姓名>小明</姓名>
```
3. 单词分割用-
```xml
   <mobile_phone>13800000000</mobile_phone>
```
4. 结构中所有标签尽量不重名
```xml
   <score>
      <score>86</score>
   </score>
```
5. 不要带有特殊符号
```xml
   <+score>77</+score>
```
6. 父子关系的标签，子标签要有缩进
```xml
<score>
<chinese>86</chinese>
<math>77</math>
<english>91</english>
</score>
```
7. 可以用```<!--内容-->```进行注释
```xml
<!--学生分数-->
<score>
    <chinese>86</chinese>
    <math>77</math>
    <english>91</english>
</score>
```
8. 可以合理使用属性对标签进行描述
```xml
<!--学生分数-->
<score class="1" id="123456">
    <chinese>86</chinese>
    <math>77</math>
    <english>91</english>
</score>
```
9. 特殊符号处理
    1. 字符实体 
```xml
<achievement>
    <score>
        <mark>A</mark>
        <range>&gt;= 4 and &lt;= 4.5</range>
    </score>
    <score>
        <mark>B</mark>
        <range>&gt;= 3 and &lt; 4</range>
    </score>
    <score>
        <mark>C</mark>
        <range>&gt;= 2 and &lt; 3</range>
    </score>
    <score>
        <mark>F</mark>
        <range>&lt; 2</range>
    </score>
</achievement>
```
   2. CDATA
```xml
<achievement>
    <score>
        <mark>A</mark>
        <range><![CDATA[>= 4 and <= 4.5]]></range>
    </score>
    <score>
        <mark>B</mark>
        <range><![CDATA[>= 3 and < 4]]></range>
    </score>
    <score>
        <mark>C</mark>
        <range><![CDATA[>= 2 and < 3]]></range>
    </score>
    <score>
        <mark>F</mark>
        <range><![CDATA[< 2]]></range>
    </score>
</achievement>
```

- [字符实体查询地址](https://www.w3school.com.cn/charsets/ref_html_8859.asp)

10. 数据集合中的元素内的子标签必须保证同一个顺序
```xml
<students>
    <student>
        <name>Mike</name>
        <age>18</age>
        <score>
            <chinese>86</chinese>
            <math>77</math>
            <english>91</english>
        </score>
    </student>
    <student>
        <name>Rose</name>
        <age>17</age>
        <score>
            <chinese>91</chinese>
            <math>88</math>
            <english>94</english>
        </score>
    </student>
</students>

```