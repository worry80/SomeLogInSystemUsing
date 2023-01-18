# Manjaro 安装ibus-rime输入法
* 安装软件包
~~~
sudo pacman -S ibus ibus-rime
~~~

* 编辑配置文件
~~~
sudo vim ~/.xprofile
~~~
* 添加以下内容
~~~
export GTK_IM_MODULE=ibus
export XMODIFIERS=@im=ibus
export QT_IM_MODULE=ibus
ibus-daemon -d -x
~~~

* 设置中添加内容
~~~
设置-键盘-输入源-汉语（中国）-中文（Rime）
~~~