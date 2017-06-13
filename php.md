## 入门
- echo
- 字符串
    + 连接符 `.`
    + `""` 中的变量会执行
    + `''` 中的变量不会执行
- 每行末尾必须加 `;`
- 注释 `//` *任意位置*
- 集成环境 WAMPServer
    + 修改apache配置文件
        * apache —— httpd.conf —— ctrl+f —— documentroot —— 2处
    + 修改wamp配置文件
        * wampmanager.ini —— ctrl+f —— menu.left—— Type: item; Caption: "code 目录"; Action: shellexecute; FileName: "E:/code"; Glyph: 2
        * wampmanager.tpl —— ctrl+f —— menu.left —— Type: item; Caption: "code 目录"; Action: shellexecute; FileName: "E:/code"; Glyph: 2
- 多站点配置
    + wamp\bin\apache\apache2.4.23\conf\extra\httpd-vhosts.conf
    + 设置apache配置文件
        * httpd.conf —— ctrl+f —— httpd-vhost —— 去掉`#`
        * apache默认是组织外部访问的
        * httpd.conf —— ctrl+f ——
- 自定义端口
    + httpd.conf
    + 80
    + Listen
    + ServerName localhost
- 数据类型
    + 8种原始类型 —— 4种标量类型、2种复合类型、2种特殊类型