# 插件化方案 demo multiflutter

更新：
* 5.21 1.2 demo更新使用前执行 `pre_ci_build.sh`
* 3.4   解决1.2 flutter 内存问题
* 12.28 更新1.0版本内存问题，产物在 https://github.com/Natoto/fixFlutterEngine 
* 11.28 更新了methodchannel的循环引用
* 最新版本0.11.9官方号称解决了循环引用，然而在多插件情况下，还是有泄漏

---
流程

1. 在现有iOS工程基础上添加flutter

2. 将编译产物Flutter.framework.zip至于工程Resource目录下

3. 在执行build脚本之后，添加自己的脚本，将Flutter.framework.zip解压出来，并替换掉之前编译的产物Flutter.framework

4. 结束


---
为什么要替换Flutter.framework,本版本解决了以下问题

* 0.9.4版本存在内存泄漏问题，打开了就不支持释放
* 不支持动态化方案
* 不支持动态下发脚本代码（flutter ios热更新）

### flutter engine构建产物下载地址
https://github.com/Natoto/fixFlutterEngine 
