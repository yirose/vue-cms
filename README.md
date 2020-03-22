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


后端路由：

前端路由：



