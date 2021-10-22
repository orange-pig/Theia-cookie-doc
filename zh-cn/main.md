## Theia关键概念

### 0. 面向有VS code Extension开发经验者

组成概念对比：
|概念|Theia|vs code|
|-|-|-|
|Extension| build-in extension| 无|
|plugin| plugin |extension|

界面概念对比：

TODO:配个对照图

|概念|Theia|vs code|描述|
-|-|-|-
|标题栏| Top Panel |  | 顶部固定大小的栏位，通常包括Logo、标题、3金刚键、菜单 |
|侧边栏| Side Bar(Left/right) | Activity Bar | 主界面两侧的垂直栏位，用于放置工具图标，显示消息通知。 |
|侧边栏面板| Side Bar(Left/right) | Sid Bar | 停靠在两侧侧边栏上的面板，可通过侧边栏放置按钮折叠和展开。 |
|状态栏| Status Bar | Status Bar | |
|标签面板| Main Panel | Editor Groups | 一般放置Editor标签的地方，是界面的主工作区。 |
|底部停靠面板| Bottom Panel | Panel | 底部外壳区域中的停靠面板。 与主面板相比，底部面板可以折叠和展开。 |

### 1. Extension(build-in)

在编译时与Theia共同编译的拓展，直接由IOC接口注入。

### 2. plugin

官方称API是vs code 拓展 的超集，但是有部分vs code的接口未实现。似乎是实现了大部分vs code的拓展API，但没有跟进vs code的更新。在其基础上另外添加了一些vs code的中还未采纳的接口设计，和他们自己对于接口的拓展API。

## 快速上手

todo

## 依赖库

### Phosphor.js

Theia的界面布局都使用的Phophor.js的库，现在这个项目已经存档两三年了。我们要进行Theia拓展和插件开发，需要对Phophor有一定的了解。

Phophor提供了一系列的布局组件来支持我们进行界面布局，所有的组件都是一个Wight。

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