# miboxs_root
mibox4(国际版)/miboxs root并修复播放问题


```
root流程
    home+返回长按接电源进入recovery
    通过刷update_miboxs_r3131_userdebug.zip
    adb root获取root
    live_setup.sh
        magisk

    adb reboot fastboot
        安装驱动https://github.com/pbatard/libwdi/releases/#release-b755

    fastboot flashing unlock
    fastboot flashing unlock_critical
    解包update_miboxs_r3131_userdebug.zip
        解除验证
            fastboot flash vbmeta --disable-verity --disable-verification E:\iso\mixboxs\vbmeta.img


    修复播放问题
        通过Multi Image Kitchen v4.0提取vendor.new.dat.br的3933的vendor_3933.img
        fastboot flash vendor F:\down\player6\miboxs_a9_3933\vendor_3933.img

```

