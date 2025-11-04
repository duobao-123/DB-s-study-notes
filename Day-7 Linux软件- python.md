# 多版本 python 切换、共存

conda下载：wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-aarch64.sh

# conda

conda 是一个开源的跨平台包管理和环境管理工具，核心功能是解决软件包依赖和多环境隔离问题，支持python、 Java多种编程语言。



## kali 安装conda

1. 下载conda，wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-aarch64.sh![image-20251104174554368](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251104174554368.png)

2. 安装 ![image-20251104174658021](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251104174658021.png)

3. 加载环境变量（启用）![image-20251104174731281](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251104174731281.png)

   > 如果是普通用户安装的conda，切换到root用户后，可以执行source /home/普通⽤户⽤户名/.zshrc，启用conda
   >
   > ![image-20251104174949873](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251104174949873.png)

## CentOS安装conda

1. 下载 ：wget https://repo.anaconda.com/miniconda/Miniconda3-py311_24.4.0-0-Linux-aarch64.sh 因为CentOS已停止维护，因此需要安装老版本conda才能见兼容
2. bash  Miniconda3-py311_24.4.0-0-Linux-aarch64.sh
3. 加载环境变量：source ～/.bashrc （CentOS默认的shell是bash ，因此加载环境变量是source ～/.bashrc



## conda的使用

### 安装和激活

1. 安装 python   “conda create -n py38 python=3.8”![image-20251104181425719](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251104181425719.png)
2. 查看已经安装的python  “conda env list"
3. 激活环境，执行“ conda activate py38"![image-20251104182456218](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251104182456218.png)
4. 验证当前版本 ，conda -V ![image-20251104182531818](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251104182531818.png)



### 取消环境（退出环境）

- Conda deactivate ,一直执行![image-20251104183414690](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251104183414690.png)



### 删除环境

- conda remove -n 环境名 -- all





