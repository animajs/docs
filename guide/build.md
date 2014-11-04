# 打包、发布

在本地开发完成后，我们需要将项目部署到开发测试环境，进行联调，这时候需要进行`开发测试环境的构建`。
打开命令行，直接运行构建命令：

    $ amb build

命令运行完成后，可以发现，本地项目目录中多了一个"dist"目录，现在项目总目录如下：

    foobar
      - dist
         - foobar
           - 0.1.0
             - index-debug.css //打包后的debug模式
             - index.css //打包后的压缩模式
             - index-debug.js
             - index.js
             - index.html
      - spm_modules
        - ...
      - index.html
      - index.css
      - index.js
      - package.json

>可以发现，dist目录中包含了`name/version`这样两级目录结构，看起来可能会感觉比较冗长。想去掉的话，可以在`package.json`中的spm项内配置`"pathmap": "%{{{name}}/{{version}},}p"`，重新`amb build`即可。

>注意：我们打开`dist`内的`index.html`文件，可以发现，js是像这样直接引用的：`<script src="index.js"></script>` 。而没有用到我们熟悉的`seajs.use`。这是因为，我们在package.json中定义的`"buildArgs": "--include standalone"`配置了打包采用`standalone模式`，这个模式在最终代码层已经不需要seajs的支持，而可以通过独立的模块解析器来解析依赖模块了。
>因此，对于amb打包出来的文件，我们在html里只需用script标签直接引用即可。不需要做其他额外的操作。

>引申：[关于各种打包模式的详细介绍](http://sorrycc.gitbooks.io/spm-handbook/content/package.json/buildArgs.html)

恭喜你，我们的项目进行到这里，基本全部完成了！后续的静态文件发布等工作，就不需要在这里写了吧：）


