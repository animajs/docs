# 项目初始化

用终端导航到你的workspace根目录，创建你的第一个项目"foobar"，运行：

    $ mkdir foobar && cd foobar

则已经创建好并进入了foobar目录，然后执行：

    $ amb init

会需要你配置几个基本信息：


    [?] Project name: foobar  //项目名字，默认值不改则直接Enter即可
    [?] Author: SMbey0nd <SMbey0nd@163.com>  //作者名字，默认值不改则直接Enter即可
    [?] Project Type: (Use arrow keys)  //项目模板选择，通过↑↓键和Enter来选择需要初始化的文件模板
    ❯ simple
      webapp
      hybrid

在这里，我们选择`simple`类型的项目初始化文件模板。

 > [文件模板是什么意思？该如何选择？](advance/template.md)


这时，我们发现项目基础文件已经初始化好了，如下：

    foobar //项目目录
      - spm_modules  //已安装的spm模块目录
        - ...
      - index.html  //根据文件模板初始化的html
      - index.css  //根据文件模板初始化的css
      - index.js  //根据文件模板初始化的js
      - package.json  //项目信息的配置文件，里面主要包含项目名、依赖模块、输出打包配置等信息。

我们打开package.json，发现`output`中配置了 `"./index.js"`, `"./index.css"`, `"./index.html"`, `"./img/*"` 4项。这意味着，amb在打包输出阶段，会分别将index.js、index.css、index.html以及img图片目录下的所有图片，按照amb中的配置，输出到dist目录内。

> 如何更改打包方式、输出形式以及目录？请浏览第5步：打包、发布。

接下来继续往下看，`dependencies`字段，记录了这个项目对Anima组件（也就是spm模块）的依赖。配置的`"anima-yocto": "1.0.1"`，意味着我们目前依赖了`anima-yocto`的`1.0.1`的版本。

> 这时，心细的你如果看一下`spm_modules`目录内，会发现已经有了`anima-yocto`在内的一系列目录。这意味着，我们依赖的`anima-yocto`系列组件已经默认就`安装完毕`了。

> 关于yocto：上面说到，我们已经安装了'anima-yocto'，那么这个yocto到底是什么呢？提到dom操作类库，我们首先可能会想到[zepto](http://zeptojs.com)。而[anima-yocto](http://spmjs.io/package/anima-yocto)，是一个理想的zepto替代方案，它`基于zepto`，并进行了很多`定制和优化`，包括但不限于整体的瘦身优化（比zepto默认包至少节省30%）、tap模块的重写和穿透解决、灵活的插件拆分机制等。关于yocto的更详细信息，可以[点击这里](http://gitlab.alibaba-inc.com/animajs/yocto)详细了解。

> 那么，如何安装新的组件？请浏览下面即将开始的第3步：安装Anima组件。
