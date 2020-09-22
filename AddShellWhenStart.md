# 添加开机启动脚本
* 创建脚本（以test.sh为例）
~~~
touch test.sh
~~~
* 添加脚本内容（以修改鼠标灵敏度为例）
~~~
#! /bin/sh

xset mouse 1.4
~~~
* 设置可执行权限
~~~
sudo mv test.sh /etc/init.d
# 设置脚本权限（为脚本增加可执行权限）
sudo chmod 755 /etc/init.d/test.sh
~~~
* 添加开机启动项
~~~
cd /etc/init.d
sudo update-rc.d test.sh defaults 99
# 这里如果想删除该启动项， 使用sudo update-rc.d -f test.sh remove命令
~~~
