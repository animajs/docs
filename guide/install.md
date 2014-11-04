# 安装Anima组件

> 除了yocto外，我还想安装别的组件，怎么办？下面以`anima-toast`组件为例来介绍

我们首先进入到项目中，运行amb install来安装anima-toast组件的最新稳定版本：

    $ amb install anima-toast --save

其中的`--save`参数，意味着安装的组件依赖信息会自动保存到`package.json`的`dependencies`字段内。

在安装完毕后，你会发现`spm_modules`目录中出现了`anima-toast`目录（以及其它几个目录）。对，这代表了toast组件以及这个组件的依赖都已经自动安装完毕了。

接着，我们只要在业务代码中通过`require('anima-toast')`的方式就可以来引用这个组件了。

>需要更多的组件？[点击这里](http://animajs.org/#widget/) 或者直接到 http://spmjs.io 搜索关键字"`anima`"查询。所有组件都可以直接用`amb install`的方式安装。截至目前为止，仓库中已经有`80+`个Anima组件了。

如果需要钱包的样式怎么办？打开项目目录中的`index.html`，挂载`Anima UI`样式：

````html
<link rel="stylesheet" type="text/css" href="https://a.alipayobjects.com/anima/dpl/1.2.2/amui.css" media="all">
````

觉得整个库引进去太大了？那么你可以依然以amb的方式安装样式：

    $ amb install anima-ui --save

安装后，可以直接在业务JS中通过`require('anima-ui')`来引用全部CSS样式，也可以通过`require('anima-ui/build/util/flexbox.css')`来引用其中的某一个样式子模块。

在CSS中可以通过`@import 'anima-ui/build/util/flexbox.css';`方式来引用同样的样式。

>注意：在JS中通过`require`方式引入CSS之后，构建时候会自动安装`import-style`工具来加载CSS 。

>对于Anima UI库的详细说明，以及最新版本信息，请[点击这里查看](http://animajs.org/#animaui/http://aliceui.org/mobile/)。
