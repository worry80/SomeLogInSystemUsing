# Manjaro里面的网易云音乐相关(2020.12.8记录)
## 输入中文的问题
* 原因：网易云中的libgtk-x11.so.2 和系统中的gtk2冲突，导致无法输入中文
* 解决：将/opt/netease/neteae-cloud-music/libs中的libgtk-x11.so.2删除即可
## 顶栏没有托盘图标的问题(gnome)
* 原因：对gnome的不支持
* 解决：向/opt/netease/netease-cloud-music.bash中添加export 
XDG_CURRENT_DESKTOP=Unity，让网易云音乐以为是unity桌面，从而显示托盘图标
