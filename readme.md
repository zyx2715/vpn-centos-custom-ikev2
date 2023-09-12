windows使用以下步骤：

certutil -f -importpfx "这里改成p12放置地址\path\to\your\file.p12" NoExport

powershell -command "Add-VpnConnection -ServerAddress 这里改成VPN服务器IP地址 -Name 'My IKEv2 VPN' -TunnelType IKEv2 -AuthenticationMethod MachineCertificate -EncryptionLevel Required -PassThru"

powershell -command "Set-VpnConnectionIPsecConfiguration -ConnectionName 'My IKEv2 VPN' -AuthenticationTransformConstants GCMAES128 -CipherTransformConstants GCMAES128 -EncryptionMethod AES256 -IntegrityCheckMethod SHA256 -PfsGroup None -DHGroup Group14 -PassThru -Force"

安卓或harmony手机使用以下步骤：

将生成的 .p12 文件安全地传送到你的 Android 设备。
启动 设置 App。
进入 安全 -> 高级 -> 加密与凭据。
单击 安装证书。
单击 VPN 和应用用户证书。
选择你从服务器传送过来的 .p12 文件。
注： 要查找 .p12 文件，单击左上角的抽拉式菜单，然后浏览到你保存文件的目录。
为证书输入名称，然后单击 确定。
进入 设置 -> 网络和互联网 -> VPN，然后单击 "+" 按钮。
为 VPN 配置文件输入名称。
在 类型 下拉菜单选择 IKEv2/IPSec RSA。
在 服务器地址 字段中输入 你的 VPN 服务器 IP （或者域名）。
注： 它必须与 IKEv2 辅助脚本输出中的服务器地址 完全一致。
在 IPSec 标识符 字段中输入任意内容（例如 empty）。
注： 该字段不应该为必填。它是 Android 的一个 bug。
在 IPSec 用户证书 下拉菜单选择你导入的证书。
在 IPSec CA 证书 下拉菜单选择你导入的证书。
在 IPSec 服务器证书 下拉菜单选择 (来自服务器)。
单击 保存。然后单击新的 VPN 连接并单击 连接。
