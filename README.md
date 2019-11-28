# Script
对圈X的脚本进行远程调用 *支持QunaX正式版1.0、1.03，tf(157)以前版本(最新版本再次禁用了远程订阅的js脚本)* ，目前使用的订阅基本上是[@NobyDa](https://github.com/NobyDa/Script)的订阅，主要区别如下：

>1.添加wps脚本支持国际版(当然国内版本也支持)
2.增加收集的部分脚本

## 使用教程： ##
### QuanX1.0版本 ###
直接将订阅链接加入：

进入Quantumult X，点击右下角三菱按钮，找到Rewrite模块-点击 引用，粘贴链接``https://raw.githubusercontent.com/YinbingSong/Script/master/QuantumultX/Js.conf``；

### QuanX1.0.3版本和TF(157)之前的版本 ###
1.在你 Fork 后的仓库下新建 unblockremote.js
unblockremote.js 内容为：

>var body = $response.body;

>body = '\/*\n@supported 你的QuantumultX设备ID填这里\n*\/\n' + body;

>$done(body);


2.使用WorkingCopy同步 fork 到本地

3.配置 rewrite_local
编辑QuantumultX 配置文件（进入 Quantumult X App，点击右下角三菱按钮，找到配置文件模块，点击编辑） ，找到 [rewrite_local]，并在 [rewrite_local] 添加：

>^https:\/\/(raw.githubusercontent|\w+\.github)\.(com|io)\/.*\.js$ url script-response-body YinbingSong/unblockremote.js

4.配置 hostname

编辑QuantumultX 配置文件（进入 Quantumult X App，点击右下角三菱按钮，找到配置文件模块，点击编辑），找到 hostname =，并在 hostname = 后面添加：

>raw.githubusercontent.com, *.github.io,


5.引用远程JS.conf

进入Quantumult X，点击右下角三菱按钮，找到Rewrite模块-点击 引用，粘贴链接``https://raw.githubusercontent.com/YinbingSong/Script/master/QuantumultX/Js.conf``；

**本脚本库引用资源部分来自网上，如有侵权，请告知，我会立即删除相关资源。**
