# MSI-B460M-WIFI-10600-6600XT-BCM94352Z

hackintosh: OpenCore + MSI B460M Mortar + i5 10600 + 6600XT+BCM94352Z(��������AX200)

## ��־��¼:

- 2022-08-10��׼����װ macOS 12.5 & OpenCore 0.8.0
- 2022-08-14���ѳɹ���װ macOS 12.5 & OpenCore 0.8.0

## Ӳ������

| ����        | �ͺ�                           | �۸� | ����       |
| ----------- | ------------------------------ | ---- | ---------- |
| CPU         | Intel i5 10600                 | 1075 | �Ա�: ɢƬ |
| ����        | ΢�� MSI MAG B460M MORTAR WiFi | 400  | ����       |
| �Կ�        | ���� RX 6600XT 8G ��ӥ         | 1899 | ����       |
| �ڴ�        | ���� ���� DDR4 2666MHz 8G * 2  | 300  | ������Ӫ   |
| SSD         | WD SN550 500G                  | 350  | ������Ӫ   |
| ����        | ɵ�ϳ���K88                    | 253  | �Ա�       |
| ��Դ        | ����V7  700W ȫģ�� +������    | 295  | ����       |
| CPU ����    | ��˼�� CR1400                  | 0    | ���丽��   |
| WiFi + ���� | BCM94352Z                      | 85   | ����       |

������10��U����ͨ�õ�

## ������֤

- [X] CPU���̺߳ͱ�Ƶ
- [X] UHD630
- [X] RX6600XT
- [X] �Կ�������
- [X] ˯�߻���
- [X] �ػ�
- [X] WIFI
- [X] ����
- [X] ��̫����֧��2.5G����
- [X] ��Ƶ���
- [X] �������˷�����
- [X] USB�˿�
- [X] iMessage, Facetime,
- [X] Handoff
- [X] Airdrop

## ���޸�BUG

##### 1.����ƻ��Logoʱ����ʾ����

�ݹ۲����ΪRX6000ϵ��macOS�������⣬����������������ϵͳ�ָ���ʾ��Ŀǰ���޽����ʽ

##### ����USB�˿�ʧЧ

USB�Ѷ��ƣ���˿��������������˲��ֶ˿ڣ�����������[USB����](#USB����)

## ��װ����

**����ֱ��ʹ��**

1. ׼���þ����ļ���������ֱ��ʹ�õ��Ǻڹ�С����mac12.5�����ļ�
2. ����[����EFI�ļ�](https://github.com/GitHubYingDeng/MSI-B460M-WIFI-10600-6600XT/archive/refs/heads/main.zip)����ѹ����EFIĿ¼���ļ����Լ���EFIĿ¼
3. Bios���ô� `D.T.M`��΢���Դ���ƻ��һ�����ã����ر� `ResizeBar`(Ĭ�Ϲأ����������ʹ��GPU-Z�鿴))
4. �ο��ڹ�С����[��װ�̳�](https://mp.weixin.qq.com/s/Vs0uxeQNh2dPxnC76KPNbA)
5. �ο�[�˴�](https://dortania.github.io/OpenCore-Install-Guide/config.plist/comet-lake.html#platforminfo)��������ʽ���� `config.plist`���룬i7������ʹ��iMac20,1���ͣ�i9ʹ��iMac20,2����
6. Win+Mac˫ϵͳ���ϵͳʱ�������
   ��Windows������

```
Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1
```

7. ����Ĭ��������
   ��OC��������ʱ�����̵�Ctrl+Enter����ϵͳ���´�������Ĭ�Ͼ�ѡ�и���

## ע������

- ������δ��������������WIFI�Ȼ��ڣ����ܻῨ��������������,���ʹ�ð���AX200��������ʹ����λ���е�[EFI](https://github.com/Spectrelai/Hackintosh-B460M-MORTAR-WIFI)
- ������Ҫ��֤Ψһ�ԣ�������ܻ�Ӱ��Handoff��iMessage��FaceTime����

EFI�ļ�������

| �ļ�                              | ��;                                           |
| --------------------------------- | ---------------------------------------------- |
| BOOT/BOOTx64.efi                  | OpenCore �װ��Դ������ܣ�������                |
| OC/ACPI/SSDT-AWAC.aml             | ACPI ���ܼ��·�                                |
| OC/ACPI/SSDT-EC-USBX-DESKTOP.aml  | ACPI ���ܼ��·�                                |
| OC/ACPI/SSDT-PLUG.aml             | ACPI ���ܼ��·�                                |
| OC/Bootstrap/Bootstrap.efi        | OpenCore �װ��Դ������ܣ�������                |
| OC/Drivers/HfsPlus.efi            | �װ�����������������ɾ�����������Ǳ���ġ�     |
| OC/Drivers/OpenRuntime.efi        | ͬ�ϣ����������                               |
| OC/Kexts/AppleALC.kext            | ���������������������Ҫ������������ҪһЩ���� |
| OC/Kexts/Lilu.kext                | ���������������                               |
| OC/Kexts/LucyRTL8125Ethernet.kext | ������������                                   |
| OC/Kexts/NVMeFix.kext             | ����������Ҳ�������Ǳ����                     |
| OC/Kexts/SMCProcessor.kext        | VirtualSMC ����ز����������������            |
| OC/Kexts/SMCSuperIO.kext          | ͬ��                                           |
| OC/Kexts/USBMap.kext              | USB ӳ��                                       |
| OC/Kexts/VirtualSMC.kext          | ��������������                                 |
| OC/Kexts/WhateverGreen.kext       | �Կ���ر�������                               |
| OC/Kexts/XHCI-unsupported.kext    | ��Ͻ�� USB ���������                        |
| OC/OpenCore.efi                   | �Դ���������                                   |
| OC/Tools/OpenShell.efi            | Tools ������ʵ��ɾ�����                     |
| OC/config.plist                   | **�ص�༭�ļ�**                         |

## ���Ʋο�˵��

### USB����

���ƶ˿ڱ�

| ���� | ����             | λ��                     |
| ---- | ---------------- | ------------------------ |
| HS01 | USB2.0           | �������������USB-A�� 1  |
| HS02 | USB2.0           | �������������USB-A�� 2  |
| HS03 | USB2.0           | �������USB-C����USB-A�� |
| HS04 | USB2.0 Type-C    | �������USB-C��          |
| HS05 | USB2.0           | ������չ��JUSB3 1        |
| HS06 | USB2.0           | ������չ��JUSB3 2        |
| HS07 | USB2.0 Type-C    | ������չ��JUSB4          |
| HS08 | ��������         | ��������                 |
| HS09 | USB2.0           | �������PS2����USB-A�� 1 |
| HS10 | USB2.0           | �������PS2����USB-A�� 2 |
| HS11 | ����USB2.0Hub    | ������չ��JUSB1-2        |
| HS12 | ����΢�ǵ�Ч���� | ��������                 |
| SS01 | USB3.0           | �������������USB-A�� 1  |
| SS02 | USB3.0           | �������������USB-A�� 2  |
| SS03 | USB3.0           | �������USB-C����USB-A�� |
| SS04 | USB3.0 Type-C    | �������USB-C��          |
| SS05 | USB3.0           | ������չ��JUSB3 1        |
| SS06 | USB3.0           | ������չ��JUSB3 2        |
| SS07 | USB3.0 Type-C    | ������չ��JUSB4          |

����˿�˵����

- HS08�������˿ڣ������������������ʧЧ
- HS11���ڲ�USB2.0Hub�˿ڣ����δʹ��JUSB1-2��չ�����������
- HS12��΢�ǵ�Ч�˿ڣ�mac��û�����䣬������

Ĭ�����Σ�HS11, HS12, SS01, SS02

���Ĭ�ϵ�USB���Ʋ�������Ľӿ�ʹ��������ɸ��ݴ˱����¶���USB�˿ڣ�Ԥ�õ�USBMap.kext�����ñ����ж˿ڣ��ڴ˻����Ͽ���ȥ�����˿ڵĲ���ֱ�ӽ��ж���ѡ��

#### ���Ʋ���

1. ����˵�����ض��Ƴ���[USBMap](https://github.com/corpnewt/USBMap)
2. ���û��Python�����������ذ�װ[Python](https://www.python.org/downloads/)
3. ����USBMapInjectorEdit.command(macOS)��USBMapInjectorEdit.bat(Windows)
4. ����EFI�ڵ�USBMap.kext
5. ���ݳ���˵��ѡ������Ҫ�Ķ˿ڣ���macOS���ƣ���ѡ�˿������ܳ���**15��**
6. �޸���ɺ��˳����򣬴�ʱԭUSBMap.kext������޸�

�ο��̳̣�

- https://github.com/Spectrelai/Hackintosh-B460M-MORTAR-WIFI/tree/main/EFI/OC/Kexts
- https://github.com/maemual/MSI-B460M-10700-5500XT
- https://github.com/myqqiu/Hackintosh-B460M-MORTAR-i5-10500-iGPU-UHD630
- https://dortania.github.io/OpenCore-Install-Guide/
- https://github.com/abner-xu/efi
- https://apple.sqlsec.com/
- https://www.bilibili.com/video/BV1uf4y1X7MT
