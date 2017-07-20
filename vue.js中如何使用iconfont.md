#vue.js中如何动态调用iconfont
----错误的示范
<i class="iconfont">{{data.icon}}</i>
最开始直接将数据放在i标签中，没法得到正确的图标样式，代码中展示的是直接调用出来的值
----正确的操作
<i class="iconfont" v-html="{{data.icon}}"></i>
将数据放在v-html指令中，数据可以得到很好的编译转化成想要的图标样式
