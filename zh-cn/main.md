## Theia关键概念

### 0. 对标 vs code

|概念|Theia|vs code|
|-|-|-|
|Extension| build-in extension| 无|
|plugin| plugin |extension| 

### 1. Extension(build-in)

在编译时与Theia共同编译的拓展，直接由IOC接口注入。

### 2. plugin

官方称API是vs code 拓展 的超集，但是有部分vs code的接口未实现。似乎是实现了大部分vs code的拓展API，但没有跟进vs code的更新。在其基础上另外添加了一些vs code的中还未采纳的接口设计，和他们自己对于接口的拓展API。

## 资源

### 图标资源

图标使用 [octicons](https://github.com/primer/octicons)和 [fontawesome icon](https://fontawesome.com)。优先使用 octicons，fontawesome icon作为剩余的补充。

在文本中配图标：
```
$(fontawesomeClassName)
```
使用动画图标，动画有两种类型```spin``` ``` pulse```：
```
$(fontawesomeClassName~typeOfAnimation)
```
更多的动画图标用法的文档[在这](http://fontawesome.io/examples/#animated)

## 接口

[接口文档](./interface.md)