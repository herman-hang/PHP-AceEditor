注意：本项目为二次开发，原作者：https://github.com/yynan555/php_online_coding

本项目简介：在原基础上做了汉化，以及在登录安全方面小幅度改动，用户体验比原来好了很多，如果修改有不妥的地方，欢迎各位朋友指点。

# PHP-Ace-Editor
该项目是以PHP为基础，实现在浏览器中对服务器代码进行在线编辑和查看。

# 界面
![编辑目录及文件](https://www.yundaohang.net/tuoguan/jiemian.png "php在线代码编辑器")
# 编辑器快捷键
```php
查询错误 : Alt-E
查询报错详情 : Alt-Shift-E
全选内容 : Ctrl-A
转到行 : Ctrl-L
折叠 : Alt-L|Ctrl-F1
打开 : Alt-Shift-L|Ctrl-Shift-F1
块折叠 : F2
折叠块 : Alt-F2
折叠其他 : Alt-0
打开全部 : Alt-Shift-0
查询下一个 : Ctrl-K
查询上一个 : Ctrl-Shift-K
选择或查询下一个 : Alt-K
选择或查询上一个 : Alt-Shift-K
查找 : Ctrl-F
重写 : Insert
开始选择 : Ctrl-Shift-Home
取消选择 : Ctrl-Home
选择上 : Shift-Up
父标签 : Up
选择结束 : Ctrl-Shift-End
定位末行 : Ctrl-End
选择下 : Shift-Down
向下 : Down
选择字左边 : Ctrl-Shift-Left
转到字左边 : Ctrl-Left
选中左边内容 : Alt-Shift-Left
光标到左边 : Alt-Left|Home
向左选择 : Shift-Left
向左 : Left
选择字右边 : Ctrl-Shift-Right
转到字右边 : Ctrl-Right
选中右边内容 : Alt-Shift-Right
光标到右边 : Alt-Right|End
向右选择 : Shift-Right
向右 : Right
向下选中代码块 : Shift-Pagedown
转到下一个代码块 : Pagedown
向上选中代码块 : Shift-Pageup
转到上一个代码块 : Pageup
向上滚动 : Ctrl-Up
向下滚动 : Ctrl-Down
向左选中行内容 : Shift-Home
取消向左选中行内容 : Shift-End
光标定位多条 : Ctrl-Alt-E
补充选中 : Ctrl-Shift-E
跳转到匹配 : Ctrl-\|Ctrl-P
选择匹配 : Ctrl-Shift-\|Ctrl-Shift-P
扩展匹配 : Ctrl-Shift-M
删除行 : Ctrl-D
复制粘贴当前行 : Ctrl-Shift-D
行排序 : Ctrl-Alt-S
注释行 : Ctrl-/
块包围注释 : Ctrl-Shift-/
向上修改数字 : Ctrl-Shift-Up
向下修改数字 : Ctrl-Shift-Down
替换 : Ctrl-H
撤销 : Ctrl-Z
返回 : Ctrl-Shift-Z|Ctrl-Y
向上添加行 : Alt-Shift-Up
上移动线 : Alt-Up
向下添加行 : Alt-Shift-Down
下移动线 : Alt-Down
删除 : Delete
退格键 : Shift-Backspace|Backspace
剪切或删除 : Shift-Delete
移至行开始 : Alt-Backspace
删除行至结束 : Alt-Delete
删除行开始 : Ctrl-Shift-Backspace
删除行内容至末尾 : Ctrl-Shift-Delete
删除字左 : Ctrl-Backspace
删除字右 : Ctrl-Delete
向左缩进 : Shift-Tab
向右缩进 : Tab
向左块缩进 : Ctrl-[
向左右缩进 : Ctrl-]
相邻位置转换 : Alt-Shift-X
转大写 : Ctrl-U
转小写 : Ctrl-Shift-U
选中行 : Ctrl-Shift-L
打开命令面板 : F1
上面添加光标 : Ctrl-Alt-Up
下面添加光标 : Ctrl-Alt-Down
在上面添加光标 : Ctrl-Alt-Shift-Up
在下面添加光标 : Ctrl-Alt-Shift-Down
选择前 : Ctrl-Alt-Left
选择后 : Ctrl-Alt-Right
选择下一步之前 : Ctrl-Alt-Shift-Left
选择下一步之后 : Ctrl-Alt-Shift-Right
分割选区切换为行 : Ctrl-Alt-L
格式化 : Ctrl-Alt-A
查询全部 : Ctrl-Alt-K
保存 : Ctrl-S
关闭 : Ctrl-W
退出 : Esc
到下一行 : Shift-Return
当前选中全部 : Alt-J
设置菜单 : Ctrl-Q
快捷键使用 : Ctrl-Alt-H
```
# 代码自动补全
文件位置: Config/autoCompleter.php

# 功能
- 基于Jstree的文件及文件夹查看、添加、删除、移动、复制操作
- 文件内容在线查看和编辑
- 文件及文件夹上传
- 用户访问IP、访问文件和尝试输入密码次数限制
- 用户修改密码
- 用户操作日志记录
- 用户登录及修改密码邮件通知
- 引入数据库管理工具(adminer)

# 目录

	php_online_coding/
		├── App       // 应用文件
			├── Controller // 业务处理
			├── Core       // 核心文件
			├── Lib        // 引用库文件
			└── View       // 视图文件
		├── Cache     // 缓存文件
		├── Config    // 配置文件
		├── Log       // 用户操作日志
		├── plugins   // 第三方插件库
		├── public    // 静态资源文件
		├── index.php // 入口文件

# 使用
- 1，将该项目放到服务器，使其可以被客户端访问的路径中（例如：【你的域名】/xiaohang）。
- 2，进入Config/app.php，设置该编辑器可以在线访问的服务器文件夹路径 和 登录密码。（如果是linux系统，需要将该项目 和 需要修改的路径设置权限为777）
```php
<?php
return [
    // 注意: 修改配置中的 访问目录(*access_dirs) 后, 需要重新登录.

    // 用户默认密码, 配置用户后默认使用本密码登录, 之后可以自行修改密码
    'default_password' => '123456',
    // 如果用户修改密码，但是忘记，可以进入 Cache/User 文件夹, 里面文件命名方式为 md5('用户名'), 可以点击查看对应文件中信息是否为该用户, 对其进行 删除 或 修改

    // 公共访问文件夹
    'public_access_dirs' => [
        // 'D:\WWW\test'
    ],

    //允许访问IP列表(如果空则没有IP限制)例如 某个具体的IP: '127.0.0.1' 或 IP范围'127.0.0.1/24'
    'public_access_ips' => [
    ],

    // 允许用户尝试密码次数 不填则可以无限次尝试
    'password_attempts_num' => '5',

    // 用户表 , 配置用户与其相对应的可访问文件和ip
    'users' => [
        [
            'name' => 'admin',
            'access_dirs' => [$_SERVER['DOCUMENT_ROOT']], // 该用户可以访问的文件夹
            'access_ips' => [], // 该用户可以进行登录的IP
            'super_user' => false, //是否可以修改本项目 ,请慎重指定(默认有访问数据库权限)
            'email' => ''
        ],
/*         [
            'name' => 'user1',
            'access_dirs' => ['D:/WWW/test'], // 该用户可以访问的文件夹
            'access_database_able' => true, // 是否具有操作数据库能力(super_user 拥有该权限)
            'access_ips' => [], // 该用户可以进行登录的IP
            'email' => ''
        ], */
    ],

    // mailable 允许发送email 在用户登录的时候会给超级管理员和自己发送邮件, 需配合users中的email进行发送邮件
    // 在配置完成邮箱以及用户邮箱账号, 会在以下两种情况为用户对应邮箱发送消息:
    // 1, 用户登录 (为该用户 和 super_user发送 包括登录时间,登录网站,登录IP及简单地理信息等信息)
    // 2, 用户修改密码 (为该用户发送邮件 ,其中包含修改后的账号密码)
    'email_host' => '',
    'email_username' => '',
    'email_password' => '',

    // 文件相关
    // 不可编辑文件类型 后缀名列表
    'unable_suffix' => 'pdf xls xlsx crt pem cer ppt pptx doc docx zip gz tar rar fla jar apk mp3 mp4 rmvb',
    // 用于显示图片的类型 后缀名列表
    'img_suffix' => 'jpg png jpeg gif bmp ico',
];
```
- 3，在浏览器中访问该项目！。

# 注意
1. 该项目只是用于学习、开发及测试阶段。安全性，效率等问题还有待提高。
2. 使用功能详细的配置项功能可以在 Config/app.php 中查看配置

# 个人公众号
更多开源组件、项目请走传送门
![微信公众号](https://www.yundaohang.net/tuoguan/wx.png "个人公众号")

# 感谢
感谢 [jQuery](https://github.com/jquery/jquery) 、[ace](https://github.com/ajaxorg/ace) 、 [jstree](https://github.com/vakata/jstree) 、 [layer](https://github.com/sentsin/layer) 、[H-ui 前端框架](http://www.h-ui.net/) 、[adminer](https://github.com/vrana/adminer)
