# Electron_App
# 1.Electron_App发布的详细步骤

1.首先,在github上创建一个空白的仓库,将其拉取到桌面上

2.两个重要的官方教程

1)创建electronApp的具体步骤:

https://www.electronforge.io/config/publishers/github

2)设置github令牌的具体步骤:

https://www.electronforge.io/

3.拉去一个官方仓库

npm init electron-app@latest my-app

4.运行app

```
cd my-app
npm start
```

此时,electronApp已经能够成功运行,如果运行不起来,那就是你的环境没配好,或者是一些其他的问题..

5.对项目进行打包,项目会打包到out文件夹中(out文件夹会自动生成)

npm run make

6.将的测试项目发布到github上

1)安装必要的依赖

npm install --save-dev @electron-forge/publisher-github

2)添加发布的信息

```js
在forge.config.js中添加一段信息:
publishers: [
    {
      name: '@electron-forge/publisher-github',//这个保持不变
      config: {
        repository: {
          owner: 'AAAAA',//下面这两个要改
          name: 'BBBBB'//git@github.com:AAAAA/BBBBB.git
        },
        prerelease: true
      }
    }
  ]
```



3)配置github上的令牌

4)发布

npm run publish

此时项目已经发布成功!

# 2.然后你可以同步一下,你的仓库
