---
layout: post
title:  "2019-08-25-云乐汇融科 -前端开发规范"
date:  2019-08-25 20:58:39 +0800
categories: 学习笔记
tag:  前端开发
---

* content
{:toc}
## 快速开始

我们将通过一个简单的 Demo 来阐述 Vue 规范，在此之前，我们假设您已经：

- 熟悉 ECMAScript2015
- 熟悉 Vue
- 熟悉 Vue/cli
- 熟悉 ElementUI
- 熟悉 webStorm

---

## 项目目录

```

    // 严禁修改
    |- build
    // 严禁修改
    |- config
    |- src
        // 未封装请求类之前的文件夹，即将删除
        |- api
        // 静态文件夹，可放置图片    
        |- assets
        // 公共组件
        |- components
        // 静态数据
        |- constants
        // 路由
        |- router
        // Vuex模块
        |- store
        // 样式
        |- styles
        // 工具
        |- utils
        // 校验
        |- vaildate
        // 组件
        |- views
        // 严禁修改
        |- App.vue
        // 严禁修改
        |- main.js
    // 严禁修改
    |- static
    

```

## 全局

全局代码结尾处必须用;结尾

### 字符串

全局禁止使用‘+’，拼接字符串，使用‘${}’

### 引号

全局除需要转义情况可以使用“”，其余情况禁止使用“”

### 引入

引入模块首字母大写的驼峰命名，并在其上方使用单行注释，表明其含义

```

    // Xxx引入
    import Xxx from '@/xxx'

```

### 方法

全局除特殊情况下可以使用function，其余情况全部使用箭头函数

### ===

全局除需要对于类型可以使用===，其余情况全部使用==

### map forEach for

1. 全局除特殊情况下可以使用map/forEach，其余情况全部使用for
2. for循环嵌套不得超过两层

### if

全局if判断嵌套不得超过三层

### console.log()

全局提交代码时，禁止提交带有console.log()代码，如有特殊需求，在代码上方使用TODO注释标识，并表明原因

```

    // TODO 原因
    console.log();

```

### 被注释代码

如被注释代码，无用不得提交，如有用且暂时无用，必须用TODO注释，表明含义

## 命名

### 文件夹命名

首字母小写的驼峰命名

```

    |- xxxXxx

```

### 变量命名

1. 首字母小写的驼峰命名，并在其上方使用单行注释，表明其含义
2. 所有变量必须在return中初始化      

**禁止使用null**  

```

    // xxx表单
    xxxForm:{}
    // xxxModal 默认false
    xxxModal:false
    // xxx下拉数据
    xxxOptions:{}
    // xxxFlag 默认false
    xxxFlag:false 
    // xxx字段
    xxxXxx:''

```

### 下拉数据命名

首字母小写的驼峰命名，并在其上方使用单行注释，表明其含义        
选项中，必须用label描述其含义，必须用value表示其唯一标识
**禁止使用null** 

```

    // xxx下拉数据
    xxxOptions:[
        {label:xxx,value:xxx},
        {label:xxx,value:xxx},
        {label:xxx,value:xxx}
    ]

```

### 方法命名

1. 首字母小写的驼峰命名，并在其上方使用类注释，表明其含义        
2. 首个单词必须是动词
3. 类注释方法简介后，空一行
4. 方法首个{后，空一行       

```

    /**
     * 获取详细数据
     *
     * @param id
     * @returns {string}
     */
     getDetailData (id) {
     
        return '';
     }

```

## 组件

### 组件命名

1. 首字母大写的驼峰命名，基础组件表明Form、Table等
2. 所有组件都是其父组件xxxList的子组件

```

    |- XxxList.vue
    |- XxxForm.vue
    |- XxxTable.vue

```

### 组件模板

```

    <template>
        <section>
        </section>
    </template>
    <script>
        /**
         * 组件功能简介
         *
         *@date 最后修改事件
         *@author 最后修改者姓名 汉语拼音小写全拼
         */
        export default {
            name: '组件名',
            data() {
                return {}
            },
            methods:{},
            mounted(){}
        }
    </script>
    <style scoped>
    
    </style>

```

### 组件钩子顺序

```

    name
    component
    data
    computed
    watch
    methods
    mounted

```

## 工具类

### 请求模块

全局请求已经封装，如有问题请联系我，严禁任何人修改       

调用 

```

    // Get
    this.$http.ajaxGet('xxx', {}).then((result) => {});
    // Post
    this.$http.ajaxPost('xxx', {}).then((result) => {});
    // Put
    this.$http.ajaxPut('xxx', {}).then((result) => {});
    // Delete
    this.$http.ajaxDelete('xxx', {}).then((result) => {});

```

### 操作数据/对象

全局已经加入lodash，如有问题请联系我，严禁任何人修改       

调用

```

    this.$lodash.xxx;

```

### 日期时间格式化

全局已经加入moment，如有问题请联系我，严禁任何人修改

调用

```

    this.$moment(xxx).format('YYYY-MM-DD HH:mm:ss');
    this.$moment(xxx).format('YYYY-MM-DD hh:mm:ss');
    this.$moment(xxx).format('YYYY-MM-DD HH:mm');
    this.$moment(xxx).format('YYYY-MM-DD hh:mm');
    this.$moment(xxx).format('YYYY-MM-DD HH');
    this.$moment(xxx).format('YYYY-MM-DD hh');
    this.$moment(xxx).format('YYYY-MM-DD');
    this.$moment(xxx).format('YYYY-MM');
    this.$moment(xxx).format('YYYY');

```

### localStorage

全局已经对localStorage进行封装，如有问题请联系我，严禁任何人修改

调用

```
    
    this.$localStorage.setItem();
    this.$localStorage.getItem();
    this.$localStorage.removeItem();
    this.$localStorage.clear();

```

### 过滤器

必须严格使用Vue过滤器格式      

例子
```

    /**
     * 24小时制时分秒格式化
     */
    Vue.filter('time_HH_MM_SS', function (val) {
    
    	return moment(val).format('YYYY-MM-DD HH:mm:ss');
    })

```

## 路由

全局通过Map定义路由，在其上方使用单行注释，表明xxx模块 - xxx

```

    // 平台及商户管理 - 平台管理列表
    urlMap.set('/xxx', 'xxx/xxx/xxx.vue')

```

## CSS

全局使用sass，支持sass所有特性

```
    
    // 主样式表
    |- main.scss
    // 工具样式表
    |- func.scss
    // 根样式表
    |- reset.scss

```

### 主样式表

如需修改ElementUI固有样式，可以在此表中修改，但必须写清注释

```

    /* xxx样式修改 */

```

### 工具样式表

如需要定宽度，可以在工具样式表中查找，如没有可以添加

```

    /* 宽度100px */
    .w100 {
        width : 100px !important;
    }

```

### 根样式表

禁止修改

>
以上只是简单的Demo，具体实践中一定要活学活用，还有更多好玩的用法等着你来探索

