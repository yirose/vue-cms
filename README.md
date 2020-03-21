# vue-cms

Vue 指令：
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

定义私有组件：
    
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



路由：

后端路由：

前端路由：



