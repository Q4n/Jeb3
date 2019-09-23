# JEB 3.6 Demo Crack 记录

这个是我自己尝试用师傅的code来Crack Jeb 3.6 的一些记录

> 侵删

> 原作者的项目貌似是idea的开发环境, 我就取了他的代码, 用eclipse搞了遍...
>
> `/src/PathJar.java`

### Begin
在.iml文件中有版本说明 `jeb-demo-3.6-beta.0.201906031751-JEBDecompilerDemo-121820464987384330` 

这里附上下载链接 [jeb-demo-3.6-beta](http://jebbuilds2.s3.amazonaws.com/jebdemo/jeb-demo-3.6-beta.0.201906031751-JEBDecompilerDemo-121820464987384330.zip)

### 依赖的包

> 1. javassist 从网上下, 然后导入
> 2. com.pnfsoftware 这个是在 Jeb中的 bin/app 目录下, 我没有深究, 全部 .jar 导入......

代码中其他地方也没啥好改的, 将Jeb放在对应的地方就行, 接着运行项目

此时在同目录下生成 com 目录, 这个就是他输出的文件

### Patch

我们需要自己手动patch一个文件 `com\pnfsoftware\jeb\client\Licensing.class`

修改其中的一个局部变量`build_type`的值为 0xFE, 它的值原本是 0x80

打开010, 直接搜索0x80, 我这里的是有两个连在一起的0x80的byte, 修改前面那个byte为0xFE, 完工!

### 重新打包

将jar重新打包一遍, 覆盖原来的`bin\app\jeb.jar` 

Enjoy urself !