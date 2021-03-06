## memory
这是后期合成软件Adobe After Effects的层存储脚本,你可以将AE中任何层(包括合成层)保存下来,以便在其他工程中,在其他版本的AE中,甚至在其他电脑中生成新的层

## 环境要求
Windows系统, AE版本为CC,CC2014,CC2015,CC2017

## 界面演示
支持动态预览元素内容, 支持窗口大小自适应, 同时拥有方便的**右键菜单**来节省界面空间  
![screenshot7](https://raw.githubusercontent.com/smallpath/memory/master/screenshot/1.gif)  
![screenshot8](https://raw.githubusercontent.com/smallpath/memory/master/screenshot/2.gif)  
![screenshot1](https://raw.githubusercontent.com/smallpath/memory/master/screenshot/1.PNG)  

## 功能
1. 脚本界面支持预览动画,可以设置预览动画的帧率和帧数
2. 支持一切层,包括形状层,文字层,图片音频层,甚至`合成层`
3. 支持一切属性,包括层本身属性以及层内部属性组,例如插件,遮罩,文字动画器,形状效果器,图层样式等等
4. 支持图片和音频,即使他们被移动或删除,脚本也可以正确生成
5. 由语言版本不同造成的表达式报错将被自动修复,支持英文,中文,日文三种语言
6. 支持自定义预设,脚本提供插件,遮罩,动画器等9种属性组的自由搭配选项
7. 存储得到的数据兼容于AE任何版本,例如,用本脚本在CC2015上存储的一个工程,可以在CC上正确地生成

## 安装
进入 [版本页面](https://github.com/smallpath/memory/releases), 下载最新版本的`Sp_memory.zip`  
请将`Sp_memory.jsx`脚本放置在你的AE脚本文件夹中, 通常在`path\to\ae\Support Files\Scripts\ScriptUI Panels`   
在AE中打开`窗口`菜单中的`Sp_memory.jsx`即可  

!> 下载下来的压缩包中包含三个拥有预览动画的素材包用于演示, 请在解压后, 在脚本界面上`右键->导入组`并全选素材文件

## 常见使用问题

### 版本相关
- memory推荐的AE版本是?
  - AE CC2017, 它存储预览的速度是之前的十倍以上, 很适合经常存储素材的用户
- CC2015无法使用表达式翻译,怎样解决?
  - AE CC2015砍掉了脚本权限, 所有依赖表达式的脚本均无法工作, 建议使用其他版本
- v3.1版本的进度条在windows上几秒钟就停止响应了,如何解决?
  - 这与脚本以及AE无关, 而是由windows自行控制, 提高windows注册表中的hungAppTimeout的值即可
- 脚本可以成功运行在mac平台的AE上, 为什么文档中却说不支持mac平台?
  - mac版AE的性能非常弱, 会在文件大于50M时出现磁盘I/O断崖式下跌的现象, 导致脚本停止响应
  - 详细的数据是, 7M文件只需7秒, 70M文件则需要7分钟, 100M的文件半个小时也无法写完.
  - 因此, 不建议在mac上使用本脚本 
- 脚本如何升级?
  - 右键v3.1脚本, 设置中**检查更新**即可, 建议经常使用脚本的用户将**启动时检查更新**也勾选上
  - 如果没有找到设置中的**启动时检查更新**, 那么说明你使用的并不是最新的脚本

### 错误相关
- 弹窗中错误提示数字看不懂, 代表什么意思?
  - 首先, v3.1将错误暴露给了用户, 打开源脚本查看对应行数的代码即可, 非最新版本的报错将不会被处理
  - 另外, `Sp_memory/tempFile/error.txt`包含脚本的运行时错误, 请在上报错误时一并提交文件内容
- 脚本无法新建组与保存层,错误代码提示1251  
  - win8-win10用户请使用管理员权限运行AE  
  - 如果是首次使用脚本,请在AE中打开`编辑->预选项->一般`,勾选`允许脚本访问文件与网络`  
- AE CC2015.3 使用Memory无法存储, 错误代码提示1321
  - memory v3.0不向上兼容, 只有经过测试的版本才会加上支持. 开发版本已经添加了CC2015.3, 请查看脚本安装部分进行安装

### 使用相关
- 手动存储每一个合成非常麻烦, 有更好的办法吗?
  - 可以通过`右键->自动存储每一层`功能来批量存储`Motion Graphics`合成层
- 我存储的素材如何备份?
  - 直接备份脚本同目录的`Sp_memory`文件夹即可
- v3版本无法预览之前存储的元素,应该怎样解决?
  - `右键->重载组内预览动画`,即可进行预览动画的生成
- v2支持CS3至CC2017,为什么v3只支持CC至CC2017?
  - 因为预览特性对AE环境非常苛刻,目前只有CC及以上版本能够通过测试
  - 但是,v3存储的元素,一样能够正确导出到v2中并进行层的生成
- 是否有更多的`Motion Graphics`素材包以供下载?
  - 因为版权原因, 只提供三个素材包作为示范, memory只作为一个存储生成层的平台, 不提供原始素材包

## 脚本使用教程
>[文字教程](TUTORIAL.md)

## 版本更新记录
>[更新历史](LOGS.md)

## 开发
- [x] Node.js > v4.0
- [x] Yarn.js

```
# 安装依赖
yarn

# 开发
yarn run dev

# 构建
yarn run build
```
windows上开发时, 建议对AE窗口使用`ctrl + \`快捷键, 否则自动刷新每次都会缩放AE窗口

## 反馈
脚本使用中遇到任何问题, 请[新开issue](https://github.com/smallpath/memory/issues/new), 或联系smallpath2013@gmail.com
