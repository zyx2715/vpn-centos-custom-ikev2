windows使用以下步骤：

certutil -f -importpfx "这里改成p12放置地址\path\to\your\file.p12" NoExport

powershell -command "Add-VpnConnection -ServerAddress 这里改成VPN服务器IP地址 -Name 'My IKEv2 VPN' -TunnelType IKEv2 -AuthenticationMethod MachineCertificate -EncryptionLevel Required -PassThru"

powershell -command "Set-VpnConnectionIPsecConfiguration -ConnectionName 'My IKEv2 VPN' -AuthenticationTransformConstants GCMAES128 -CipherTransformConstants GCMAES128 -EncryptionMethod AES256 -IntegrityCheckMethod SHA256 -PfsGroup None -DHGroup Group14 -PassThru -Force"
