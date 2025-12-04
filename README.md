# Ubuntu_option
# Ubuntu_option
1. <img width="1251" height="180" alt="image" src="https://github.com/user-attachments/assets/12d4c43c-aeb7-474e-987c-67ab0f7041eb" />

这是一个非常经典的问题！

错误信息中的 ^M 暴露了原因：这个脚本文件是 Windows 格式 的（带有回车符 \r\n），但 Linux 系统只认识 Unix 格式（只有换行符 \n）。

Linux 把 #!/bin/bash\r 当成了解释器路径，因为找不到在这个名字的文件，所以报错。

✅ 解决方法
你不需要重新写文件，只需要用下面这行命令帮你“洗”一下文件，去掉那个讨厌的 ^M：

在终端输入并运行：
```sh
sed -i 's/\r$//' install.sh
```
