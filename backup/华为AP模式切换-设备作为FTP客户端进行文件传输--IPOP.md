拓扑简图

 

配置前提

1. 需要网络路由可达，保证网络连通性。

2. 准备好可以作为FTP服务器的软件（以IPOP为例，软件可网上搜索下载）。

 

配置思路

1. 在PC上运行FTP软件作为FTP服务器，并设置其目录、用户名和密码。

2. 在设备上登录FTP服务器后使用二进制模式上传/下载文件。本文以下载为例进行详细介绍，对于上传则参考后面【知识扩展】中的内容即可。

 

操作步骤

一、搭建FTP服务器

提醒：需要临时关闭一下PC操作系统自带的防火墙（关闭方法可以根据操作系统的版本在网上查询）。

 

在PC上运行IPOP软件。如下图步骤所示，依次选择“服务-->FTP"，再点击“Home Dir"参数栏中的“browse”按钮设置一下FTP服务器的目录（应选择所要传输的文件所在的文件夹），然后点击“Start”按钮启动服务。

 

最后，按上图中的步骤5（点击“Config”按钮）设置一下FTP的用户名和密码（以设置用户名admin，密码123456为例）。

 

 

二、在设备上登录FTP服务器并使用二进制模式下载文件

提醒：要在用户视图下执行ftp命令。

 

<HUAWEI> ftp 169.254.1.100                               //169.254.1.100是FTP服务器的IP

Trying 169.254.1.100 ...

Press CTRL+K to abort

Connected to 169.254.1.100.

220 FTP Server ready.

User(169.254.1.100:(none)):admin                         //输入FTP登录用户名

331 Password required for admin.

Enter password:123456                                         //输入密码（提醒：密码字符不可见，输入完直接按回车）

230 User admin logged in.

 

[HUAWEI-ftp] binary                                             //使用二进制模式传输

200 Type set to I.

 

[HUAWEI-ftp] get test.dat                                     //test.dat为要传输的文件名（含扩展名）

200 Port command successful.

150 Opening data connection for test.dat.

226 File sent ok

FTP: 159 byte(s) received in 0.113 second(s) 1.40Kbyte(s)/sec.

Now begins to save file, please wait...

File has been saved successfully.

 

 

  

===============================================================================================

【知识扩展】
首次登录有密码修改提示如下
Warning: The default password poses security risks. You are advised to change the user name and password of the AP using the "ap username" command in the WLAN view of the AC. Or you can directly change this device here. Enter the password (plain-text password of 8-128 characters or cipher-text password of 48-188 characters that must contain at least one lowercase letter, one uppercase letter, and one digit): Error: The password length must not be less than 8 and not be more than 128.
Warning: The default password poses security risks. You are advised to change the user name and password of the AP using the "ap username" command in the WLAN view of the AC. Or you can directly change this device here. Enter the password (plain-text password of 8-128 characters or cipher-text password of 48-188 characters that must contain at least one lowercase letter, one uppercase letter, and one digit): Error: The password length must not be less than 8 and not be more than 128.
直接输入新密码 然后确认 二次验证就行
1. 如果要将设备上的文件上传到FTP服务器，在FTP客户端视图下使用put命令即可，示例如下：

    [HUAWEI-ftp] put test.dat

2. 关于登录设备命令行的方法，可以参考“【WLAN精品库】功能配置篇”中的“设备登录篇”。

3.  可以在用户视图下使用dir命令查看设备上存在的文件。 

4. 常用的“断开与FTP服务器的连接，并退回到用户视图”的命令是bye。


ap-mode-switch fat ftp Fat&CloudAP4050DE-M_V200R019C00SPC918.bin 192.168.100.155 admin admin123

[Huawei]
[Huawei]ap-mode-switch fat ftp Fat&CloudAP4050DE-M_V200R019C00SPC918.bin 192.168.100.155 admin admin123    
Warning: The system will reboot and start in fat mode of V200R019C00SPC918. Continue? (y/n)[n]:y
Warning: Do Not Power-off!
..............................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................

Info: system is rebooting ,please wait...

[Huawei]
Connection closed by foreign host.

Disconnected from remote host(192.168.100.191:22) at 12:31:19.

Type `help' to learn how to use Xshell prompt.
[c:\~]$ ssh 192.168.100.191


Connecting to 192.168.100.191:22...
Connection established.
To escape to local shell, press 'Ctrl+Alt+]

您好：

交换机缺省密码：

https://weiknow.gts.huawei.com/robot/services/a/AFA8BDEE8A4B97BCC5850300C8117830A9F36C889EE3A8F7

忘记console口密码：

https://weiknow.gts.huawei.com/robot/services/a/130DB87ECD7E763F7F5CC9C5490F1EAA5F13A21086581C6D

加载弱秘钥插件；

https://weiknow.gts.huawei.com/robot/services/a/AA25B93F05C5D03560ECF9B2A5CA4E99F75B5533147A32C4

路由器缺省密码：

https://weiknow.gts.huawei.com/robot/services/a/BE15AE2B5DF2959C9C386724E23D80B414B75EC49D2348B6

AC和AP缺省密码：

https://weiknow.gts.huawei.com/robot/services/a/806D88B13057848D499DA3F4A03E823F8C38E100DF35ABFA

WeiKnow，您的私人技术助理！AI问答加持，一站式解决技术问题：

https://weiknow.gts.huawei.com/robot/services/a/09563A799CCA143644846919A5C7D8A31CCF16841878B4F7
