windows使用以下步骤：

certutil -f -importpfx "这里改成p12放置地址\path\to\your\file.p12" NoExport

powershell -command "Add-VpnConnection -ServerAddress 这里改成VPN服务器IP地址 -Name 'My IKEv2 VPN' -TunnelType IKEv2 -AuthenticationMethod MachineCertificate -EncryptionLevel Required -PassThru"

powershell -command "Set-VpnConnectionIPsecConfiguration -ConnectionName 'My IKEv2 VPN' -AuthenticationTransformConstants GCMAES128 -CipherTransformConstants GCMAES128 -EncryptionMethod AES256 -IntegrityCheckMethod SHA256 -PfsGroup None -DHGroup Group14 -PassThru -Force"

安卓或harmony手机使用以下步骤：

将生成的 .sswan 文件安全地传送到你的 Android 设备。
从 Google Play，F-Droid 或 strongSwan 下载网站下载并安装 strongSwan VPN 客户端。
启动 strongSwan VPN 客户端。
单击右上角的 "更多选项" 菜单，然后单击 导入VPN配置。
选择你从服务器传送过来的 .sswan 文件。
注： 要查找 .sswan 文件，单击左上角的抽拉式菜单，然后浏览到你保存文件的目录。
在 "导入VPN配置" 屏幕上，单击 从VPN配置导入证书，并按提示操作。
在 "选择证书" 屏幕上，选择新的客户端证书并单击 选择。
单击 导入。
单击新的 VPN 配置文件以开始连接。
