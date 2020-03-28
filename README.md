# vue-cms

默认内置的指令:

    v-bind      缩写 ：
    v-on        缩写 @
    修饰符: .stop .prevent .capture .self .once .passive

    v-model     建立双向数据绑定；
    修饰符: .lazy .number  .trim

    v-text
    v-html
    v-show
    v-if
    v-else
    v-else-if
    v-for 
    v-slot
    v-pre
    v-cloak
    v-once

自定义指令：
    
    注册一个全局自定义指令 `v-focus`
    Vue.directive('focus', {
    // 当被绑定的元素插入到 DOM 中时……
    inserted: function (el) {
        // 聚焦元素
        el.focus()
    }
    })
    函数简写:
    在 bind 和 update 时触发相同行为
    Vue.directive('color-swatch', function (el, binding) {
        el.style.backgroundColor = binding.value
    })
    
    局部指令`v-focus`,组件中也接受一个 directives 的选项：
    directives: {
    focus: {
        // 指令的定义
        inserted: function (el) {
        el.focus()
        }
    }
    }

    钩子函数

组件：
    全局注册
    Vue.component(’组件的名称‘，’组件的模板对象‘)

    局部注册
    new Vue({
        el: '#app',
        components: {
            '组件的名称': 组件的模板对象,
            'component-b': ComponentB
        }
    })

路由：
后端路由、前端路由

    router-link
    参数匹配方式：query
    <router-link to="home?id=10&name=张三" tag="span">Home</router-link>
    参数匹配方式：params
    <router-link to="home/10/张三" tag="span">Home</router-link>

    路由写法
    var router = new VueRouter({
        routes: [
            { path:'/account',component:account }
            { path:'/login',component:login }
            { path:'/register',component:register }
        ]
    })

    路由嵌套写法
    var router = new VueRouter({
        routes: [
            { 
                path:'/account',
                component:account，
                children:[
                    {
                        { path:'login',component:login }
                        { path:'register',component:register }
                    }
                ]}
        ]
    })

    命名视图路由
    router-view
    <router-view><router-view>
    <div class="container">
        <router-view name="left"><router-view>
        <router-viewname="main"><router-view>
    </div>

    路由写法
    var router = new VueRouter({
        routes: [
            { path:'/',components:
                {
                    'default': header,
                    'left': leftbox,
                    'main': mainbox
                }
            } 
        ]
    })

监听事件
原生 onclick(click) onkeyup(keyup) ……

监听属性：watch         操作隐含的路由……
方法属性：methods   大量业务逻辑
计算属性：computed  简单数据操作

data：  存放私有数据
props： 存放父子组件传递数据
Vuex：  存放共享数据


import Vuex from 'vuex'
Vue.use(Vuex)

// Vuex 实例
var store = new Vuex.Store({
    // 跟实例中的date
    state{
        ……
    },
    // 跟实例中的methods
    mutations{
        ……
    },
    getters{

    }
})

Vue 生命周期
    开始初始化
    beforeCreate（加载前）
    初始化注入&校验
    created（加载）
    beforeMount（挂载前）
    创建vm.$el 并用其替换 ‘el'
    mounted（挂载）
    挂在完毕
    当data被修改
    beforeUpdate（渲染前）
    虚拟DOM重新渲染并应用跟新
    updated（数据绑定渲染）
    beforeDestroy（销毁前）
    销毁完毕
    destroyed（销毁）





test 组件

导航
Card
MainService
current
saving
Balance
Tramsaction


1、需求分析
    需求文档
    原型图 （工具：axure 墨刀）

2、概要设计
    数据库表设计（ER图， 表结构）
        ER图(Entity Relationship Diagram 也称实体-联系图)基本步骤
        1、实体
        2、关系
        3、字段 ERDPlus
    建表步骤
    1、一个实体一张表
    2、多对多关系一张表
    3、一对一、一对多、多对多、外键
    4、约束（主键、外键、索引、唯一、非空、默认值）
        拆表(常用字段，不常用字段分表)

3、详细设计
4、编码
5、测试
6、部署实施
7、运维


敏捷开发 
scrum 迭代周期 开发周期：2周 sprint
 
2天做需求 6-8天做开发  1-2天测试上线



