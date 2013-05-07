Sublime Text 2是我用过的感觉最好的代码编辑器，UI和插件管理都很棒，而且现在处于无限期可以免费试用中，Ubuntu也是我最喜欢的Linux操作系统。因为Sublime Text并不是需要安装，所以缺少Ubuntu桌面运行的一些基本配置，比如不能将它加入桌面侧边的启动器。

而Ubuntu上也没有快捷方式的说法，而通过软件中心安装的软件就有图标，并能加入到启动器上，这是因为它们有一个desktop配置文件的缘故。这些配置文件在/usr/share/applications这个文件夹下面，既然这样，随便打开一个配置文件，然后依葫芦画瓢，写了个Sublime Text的desktop文件：

    #!/usr/bin/env xdg-open
    [Desktop Entry]
    Name=Sublime Text 2
    Comment=Sublime Text 2
    Exec=/home/serho/tools/"Sublime Text 2"/sublime_text
    Icon=/home/serho/tools/Sublime Text 2/Icon/48x48/sublime_text.png
    Terminal=false
    Type=Application
    Categories=Application;Development;
    StartupNotify=true


需要修改的只有几处:

        Name:就是名称了
        Comment：相当于注释
        Exec：可执行文件的路径
        Icon：图标路径，Sublime Text默认是带了各种型号的图标的

其他几个设置主要就是类别等，如果你将这个配置文件放到/usr/share/applications文件夹下，你就可以通过Ubuntu的软件管理在相应的类别下找到软件了。把上面文件保存，比如sublime-text.desktop，并给与可执行权限，然后双击就可以打开Sublime Text了，同时启动器上的图标也可以固定了。

当然，上面只是个示例，任何类似的软件都可以这样添加快捷方式，关于Linux Desktop Entry文件的各种配置参数和实现方法，可以看来自IBM的这篇文章。