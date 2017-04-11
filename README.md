>Google的原则：不作恶。

>程序员的原则：不挖坑。

>写代码的正确方式：**战战兢兢，如履薄冰。**

## 前言
程序员是一个创造力强，个人色彩浓厚的职业，不同的人，代码的风格习惯千差万别，这个时候，就需要标准来约束程序员的代码，越是庞大的项目越应该如此。规范越早引入越好，规范的约束永远不嫌多。

## 好的原则
- 约定优于配置
- 不要太过于依赖注释，注释只是业务的补充，**良好的代码结构和命名**能够能够避免很多不必要的注释
- 清晰原则：清晰胜于技巧 （代码是给人看的，其次才是在机器上运行的，10行复杂的代码不如30行清晰的代码）
- 吝啬原则：除非确无它法,不要编写庞大的程序（动不动就上千行的代码不要再出现了！！！）
- 健壮原则：健壮源于透明和简洁


## 命名规范
### 文件及目录
- 目录结构：js目前是按照一级、二级页面划分的
- 目录：`aaa_bbb`，采用linux命名规范，因为window不区分大小写
- js文件:`aaaBbb`，驼峰命名法
- 组件文件（特别是单文件组件）：`AaaBbb`,大写的驼峰命名法
- css：`aaa_bbb.css`，`aaa_bbb.scss`，`aaa_bbb.less`
- **争议** ：二级页面的样式文件放在css下面还是就近放在二级页面的目录下。

### 变量
- class：`aaa-bbb`
- 常量：`AAA_BBB`
- 函数：`aaaBbb(){}`
- 类名 `class AaaBbb`
- 变量声明，`let`与`const`。
    - 尽量使用`const`。
    - 只有在变量值会改变的情况下使用`let`声明。

### action，store，路由等
- 路由：和目录结构统一。
- `store`：目录结构+下划线如`/order/indent`->`order_indent`。
- `action`的方法名须有该模块（目录）的前缀,保证唯一性。后面采恭动词+名词的形式。小写下划线方式连接。用如`/order/indent`下的action,获取订单模板：`order_indent_get_template_list`，
- `actionType`的常量须有该模块的前缀。
- `reduers`的名字须有该模块的前缀，同actions，小写下划线方式连接。
- 以上如果太长则使用缩写，如服务时间管理`Service_Mission_Manage`缩写是SMM。
- `react-route`的path用小写，_连接单词`<Routepath="service_mission_manage">。
`

> Tips：3是一个很奇妙的数字，目录结构，对象设计，路由层次等，尽量不要超过3层，保证工程的**扁平化**

## 数据处理
### 使用moment.js进行日期处理
```
moment("12-25-1995", "MM-DD-YYYY");
moment("2010-10-20 4:30", "YYYY-MM-DD HH:mm");
moment().format("dddd, MMMM Do YYYY, h:mm:ss a");
```

### 价格处理(后面可能上)
使用big.js进行价格处理
```
0.1 + 0.2                  // 0.30000000000000004
x = new Big(0.1)
y = x.plus(0.2)            // '0.3'
Big(0.7).plus(x).plus(y)   // '1.1'
```

### 分支管理与命名（暂定）
在后台不明确的情况下，前端请严格遵循`Git Flow`工作流规范。
![image](http://upload-images.jianshu.io/upload_images/1416338-2b5d1a64e15419d7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- feature分支：feature+需求号，如`feature1916`

## 编码规范
基于以下编码规范定制。
- [JavaScript编码规范](https://github.com/77ircloud/FET/wiki/JavaScript%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83)
- [React JSX 编码规范](https://github.com/77ircloud/FET/wiki/React-JSX-%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83)

## 编码规范校验
暂时是主要基于下面两个定制的，后期将独立成单独的包。提交的代码必须要通过`eslint`及`stylelint`的校验。

- React校验 [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react)
- css/scss校验 [stylelint-config-standard](https://github.com/stylelint/stylelint-config-standard)

## Code Review规范（待完善）
