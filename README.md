# gosend.ahk

- 为 go-send 提供 Windows 快捷键操作，非常方便
- 在 Windows 里，我本来打算直接用 AHK 来访问服务器，但发现很麻烦，
特别是连 urlencode 都要自己实现。因此改成 AHK 与 go-send-cli 配合，
结果非常理想，gosend.ahk 的内容非常简单，一共只有 10 行代码。


## 安装方法

- 安装并正确设置 go-send-cli (https://github.com/ahui2016/go-send-cli)
- 安装 AutoHotkey (https://www.autohotkey.com)
- 下载本程序源码里的文件 gosend.ahk 
- 双击 gosend.ahk (会出现在系统托盘)


## 使用方法

- 按 Win+S 即可发送剪贴板内的文字内容。
- 如果复制**一个**文件，按 Win+F 即可发送该文件，按 Win+S 可发送该文件的位置(路径)。
- gosend.ahk 默认使用我的 demo 服务器，只是方便试用体验，真正使用还是需要用户自行搭建服务器的。
- 用户自行搭建服务器后，请修改 gosend.ahk 里的网址。


## 关于 clip 云剪贴板

- Win+S 快捷键实际上是调用了 go-send-cli 的 `-clip` 功能
- `-clip` 专门用来收集剪贴板的文本内容，有独立的页面 (https://send.ai42.xyz/clips) 因此不用担心污染主页面的信息流
- `-clip` 有独立的条数限制，默认上限 100 条(可自由设置)，当接收到第 101 条消息时，会自动删除最老的一条消息
- https://send.ai42.xyz/clips 相当于一个简单版的云剪贴板，优点是：
  - 受密码保护，就算电脑被别人使用，他没有密码就看不到剪贴板内容列表
  - 安全，数据在自己的服务器里
  - 开源，代码清晰简单，不用担心剪贴板软件有后门
  - 同样由于开源，可定制性高
  - 多终端共享（比如电脑发送，手机接收，或者手机发送，服务器接收）