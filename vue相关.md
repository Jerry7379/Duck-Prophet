# Vue相关
1. vue中的虚拟dom和diff算法
    vue中的diff算法使用的是snabbdom这个第三方库，由于传统的js或者jq，操作一次就会去更新一次，效率比较低。
    虚拟dom：用js模拟真实dom结构。改变数据会重新生成一个js虚拟dom结构，两个虚拟dom做比较（diff）算法，找出差异，一次更新所有差异。
    diff算法：就是去比较两个虚拟dom之间的差异。越快找出差异，渲染越快。
    + 只比同一层级，不跨级比较
    + 先比标签名，标签名不同，直接删除，不进行深层次比较。
    + 标签名相同，再去比较key值，key值相同说明是同一个节点，不继续深度比较。
    + for循环生成虚拟dom的key，自动生成的key每次都不一样，由于标签名相同，key值不同，diff算法比较费时间。所以需要把for训混生成的dom的key值给固定。
2. vue-router
    vue-router是vue官方的查件，成为路由，是管理单页面应用的路径的。
    npm i vue-router -D
    第二步： 在main.js中配置路由，先引入路由需要用到的组件和创建路由的方法。
    路由管理有两种模式 createWebHashHistory 路径通过#的方式进行管理        createWebHistory 路径通过/的方式进行管理，需要后端配合处理。
    ```import {createRouter} from 'vue-router'
    import home from './components/home.vue'
    const router = [{
        path: '/',
        name: 'home',
        component: home
    }]
    ```
    第三步： 把路由注入到vue实例中，这样vue就有了$router， $route的属性
    const routes = createRouter({
        history: createWebHistory(),
        routes: router
    })
    createApp(App).use(routes).mount('#app')
    第四步： 在app.vue中使用router-view显示不同的路由组件，类似于slot插槽。
    router的跳转    可以使用router-link进行跳转，相当于a标签
        <router-link to="/home">home</router-link>
    动态路由    同一个路由，可以传递不同的参数，就是动态路由 { path: '/list/:id', name: 'list', component: list }
        动态路由的参数在this.$route.params中获取
        设置缺省路由，把这个放在最后面，路由是从上到下匹配的，都匹配不上就是404 { path: '/:patchMatch(.*)*', name: '404', component: com404 }
    路由参数定义的匹配规则
        path: '/list/:order(\\d+)'  // 参数只能匹配数字
        path: '/list/:order*'   // *0个以上 + 一个以上? 0个或1个
3. vue3相较于vue2的提升 __TODO__
4. proxy与object.defineProperty的对比 __TODO__