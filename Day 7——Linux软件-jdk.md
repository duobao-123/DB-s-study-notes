# Linux软件-jdk

## 下载

> - 方法1 ：找到 JDK 安装包的文件链接https://repo.huaweicloud.com:8443/artifactory/java-local/jdk/8u172-b11/jdk-8u172-linux-arm64-vfp-hflt.tar.gz，在Linux中使用wget命令下载安装包。![image-20251104161916480](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251104161916480.png)
>
>   
>
> - 方法2: 先下载jdk安装包，通过SFTP/scp传输到kali



## 安装

- tar xzvf jdk安装包![image-20251104162056868](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251104162056868.png)

  

- 确认jdk的路径。 将jdk软件包移动到/opt中 ![image-20251104162457541](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251104162457541.png)

- 执行 update-alternatives 进行配置。

  



## 切换版本

- 通过update- alternatives -- config Java 来查看系统中有几个java版本![image-20251104171316652](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251104171316652.png)

  >  图中 有2个，按enter保留当前选项，或者输入数字编号。

- 查看当前是哪个版本，执行Java - version

  > ![image-20251104171345255](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251104171345255.png)



## **为什么这里面的操作都要加上update- alternatives呢？**



> update-alternatievs  是软件版本切换工具 。当你需要切换软件版本时，使用该工具可以简单切换，否则要手动更改环境变量，改可执行文件等。![image-20251104171943294](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251104171943294.png)
>
> 


## wget怎么理解？

- Linux中的命令工具，用于从网上下载文件
- 核心功能
  - 下载文件：可以从http、https、ftp等协议中的网址下载文件，比如下载安装包、文档、软件源码等
  - 断点传输：如果下载终端，使用 -c 可继续下载
  - 后台下载：加上 -b 可后台下载
  - 
