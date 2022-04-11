## Observe Api

Browser Apis that can observe information about the DOM

我们常常使用 addEventListener 添加事件监听器监听各种用户操作（click, mousemove, input...）
那非用户触发的事件，比如元素的不可见到可见，元素大小的改变，属性和子节点的修改，如何监听？

#### Intersection Observer 交叉观察器

传统方式监听一个元素是否可见：scroll 事件+getBoundingClientRect()
Chrome 51+ 提供新的 API，IntersectionObserver API , 自动观察元素是否 visible，定义 visible 的本质是目标元素和 viewport 产生交叉区

```
let io = new IntersectionObserver(callback, option)
// 指定观察元素，可以多次调用观察多个元素
io.observe(element)
// 停止观察某个元素
io.unobserve(element)
// 停止观察器
io.disconnect()
// callback 的参数为entries数组，对应多个IntersectionEntry 对象
```

##### IntersectionObserver

-   IntersectionObserver.root(只读)
    所监听对象的具体祖先元素(element), 如果未传入值或值为 null，则默认使用顶级文档的视窗。
-   IntersectionObserver.
