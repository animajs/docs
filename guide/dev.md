# 开发、调试

在上一步我们安装了anima的几个组件，那么就需要在项目中去使用他们了。还是以toast组件为例。

我们打开`src/index.js`，编辑内容：

````javascript
    var Toast = require('anima-toast'); //将安装好的组件引用起来

    //实例化，开始使用toast组件
    var toast = new Toast({
      content : 'Hello Anima World！',
      type : 'none'
    });
    toast.show();

````

保存后，运行`amb server`命令来运行和调试：

    $ amb server

命令行会返回 `server: listened on 8000`，此时本地会启动一个server，这个server的root即为你当前项目的根目录，打开 http://127.0.0.1:8000/index.html 即可直接运行项目根目录内的index.html，这样即可随时开发和调试前端文件。

>引申阅读：
 - amb server做了什么？
   - amb server运行后，会将其host的所有依赖组件进行解析，将这些文件外层临时包裹 define(function(...){...}); 区块，实现CMD，保证页面可以在runtime模式下正常运行。
 - [多个JS入口的配置]()
