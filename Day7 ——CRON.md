# cron是什么？

是Linux系统中的**计划任务**，通过crontab可以让系统在指定时间执行命令/脚本。



# 系统计划任务

## 定义

针对整个系统生效的定时任务，通常用于系统级的自动化操作。

## 命令/配置方式

1. 方式1：编辑系统级配置文件 /etc/crontab (需root权限)![image-20251105170536099](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251105170536099.png)
2. 方式2 ：`/etc/cron.d/`目录下创建独立配置文件

# 字段

> 必须指定执行用户

![image-20251105153129413](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251105153129413.png)

- 字段1：分钟；取值范围是0-59
- 字段2：小时；取值范围是0-23
- 字段3：天；取值范围是1-31，*代表任意天
- 字段4：月；取值范围是1-12，*代表任意月
- 字段5：周；取值范围是0-6，0=周日
- 执行的用户
- 要执行的命令

## 场景

系统级维护，如系统日志清理、软件自动更新、全局备份等。



# 用户计划任务

## 定义

仅针对单个用户生效的定时任务，由用户自助管理

## 命令

> 无需sudo权限

- crontab -e 编辑当前用户的定时任务（当前用户无1.txt 文件，当命令触发时会自动创建）![image-20251105163353989](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251105163353989.png)

  >  **计划任务中要写绝对路径**

- crontab -l 查看当前用户的定时任务

![image-20251105155624520](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251105155624520.png)

- crontab -r 删除当前用户的所有的定时任务![image-20251105164603588](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251105164603588.png)



## 字段

![image-20251105165638345](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251105165638345.png)

> 分、时、日、月、周、执行命令 （无需指定用户，默认为当前用户）



## 配置位置

/var/spool/cron/crontabs/用户名，仅root用户和当前用户可访问。

## 场景

用户个人的自动化操作，如个人文件备份、日志记录等。



# 操作错误时问题研究

![image-20251105161930701](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251105161930701.png)



![image-20251105161902048](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251105161902048.png)

- systemctrl status  检查命令服务是否运行![image-20251105162143208](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251105162143208.png)

- ![image-20251105163319220](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251105163319220.png)

  成功



- ![image-20251105164039861](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251105164039861.png)

  > 权限拒绝，/var/spool/cron/crontabs/是系统存储用户级crontabs任务的目录，该目录默认仅对root用户和自身用户有读/写权限，避免普通用户越权查看或修改系统任务。普通用户自己用cat会被拒绝，即使是自己的任务文件。![image-20251105164427103](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251105164427103.png)
  >
  > ![image-20251105164441207](/Users/mac-waaagh/Library/Application Support/typora-user-images/image-20251105164441207.png)

  
