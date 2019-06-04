1. Go to project folder in the terminal, run command `npm init -y`, `npm install babel-cli@6 babel-preset-react-app@3`
2. Create a folder called `src` and run command `npx babel --watch src --out-dir public/javascripts --presets react-app/prod`
3. Now this command starts an automated watcher for JSX.

在使用Windows上使用较老版本的nodejs，如何我使用的v8.9其自带的npx的版本为9.7，在Windows上使用会存在：“Path must be a string. Received undefined”的错误。通过 GitHub 上的 issue 可以知道改问题已经在最新版的npx中解决了，可以通过npm手动升级到最新版解决。

npm i -g npx
　　但是运行npx -v后我们发现还是老版本的npx在运行新下载的npx并没有生效，这就是Windows环境变量的锅了。安装node时node的安装目录是在系统变量的path中，而node全局安装包的目录是在用户的path中，系统查询可执行文件的属性是先查询系统path变量，然后再查询用户path变量。所以node安装目录下的npx就覆盖了node全局安装目录下的npx。解决方法是把用户变量下path中node全局安装的路径复制到系统变量的path中。（如果自己没有修改过node全局安装目录的话这个路径一般是：”C:\Users{your_user_name}\AppData\Roaming\npm”),注意一定要把这个路径放在node安装目录前面，因为查找是从上到下查找的。
之后就可以开心的使用npx了。
