<!--
 * @Author: ~~梁小鱼~~
 * @Date: 2021-04-26 16:39:31
 * @LastEditTime: 2021-04-27 17:23:33
 * @LastEditors: Please set LastEditors
 * @Description: 基于elementUI的下拉树组件
 * @FilePath: \test-package\README.md
-->
### 说明

* 此插件是基于elementUI开发的下拉树组件
* 目前不支持单选,暂只支持多选

### 安装
```
npm i ele-tree-select -S
```

### 使用

在 main.js 中引入
```
import EleTreeSelect from 'ele-tree-select'
import 'ele-tree-select/lib/ele-tree-select.css'
Vue.use(EleTreeSelect)
```

### 属性

属性|说明|类型|是否必传|默认值|可选值
:---:|:--:|:---:|:---:|:---:|:---:
props|配置选项|object|否|见下面配置选项|--
code|作为组件的唯一标志返回|string|否|--|--
treeData|作为组件的数据传入，如果开启懒加载，需要将异步获取的数据组装成树型数据传入|array|是|--|--
clearable|是否可清空选项|boolean|否|true|false
accordion|是否每次只打开一个同级树节点展开|boolean|否|false|true
multipleChoice|是否多选，暂时只支持多选|boolean|否|true|true
lazy|是否使用懒加载|boolean|否|false|true
checkStrictly|多选时是否父子节点不互相关联|boolean|否|true|false
filterable|是否可搜索|boolean|否|false|true
placeholder|设置搜索框的placeholder|string|否|查找关键字|--


### props配置选项（同elementUI的tree组件的配置选项）

参数|说明|类型|默认值
:-:|:-:|:-:|:-:
value|--|string|id
label|--|string|title
children|--|string|children
isLeaf|--|string|leaf

### 事件

事件名称|说明|回调参数
:-----:|:--:|:---:
lazyLoad|懒加载时触发的事件|node:点击的节点对象，resolve：在异步请求结束后需要resolve请求的结果，code：对应上面的code属性
getCheckedData|获取选中项的value|value：选中节点的value，code：对应上面的code属性
getCheckedItem|获取选中节点的对象|data：选中节点的对象，code：对应上面的code属性

### 方法

方法名称|说明|参数
:-----:|:--:|:--:
clear|清空所有选中的数据|--
removeTag|移除指定的选中项|value：props里面value映射的字段