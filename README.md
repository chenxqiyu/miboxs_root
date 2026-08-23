# miboxs_root
mibox4(国际版)/miboxs root并修复播放问题

```
Android 8

r363 Downgrade/Unbrick Image:
https://mega.nz/file/615mGbSa#4ZuUah3yCinB_VWHpGMtEXaZYFzH7RKhjb5jtVhhg4w

r699 [RELEASE]
https://android.googleapis.com/packages/ota-api/xiaomi_oneday_oneday/cf1bcb02c65dae169a2313ef62d9d0c63a91588d.zip

Android 9

r2205 [OTA1 BETA0]
https://android.googleapis.com/packages/ota-api/xiaomi_oneday_oneday/efb7b83f37bb7c4273c366fa4ab237e47d8908e3.zip

r2216 [OTA1 BETA1]
https://android.googleapis.com/packages/ota-api/xiaomi_oneday_oneday/b045f83bafa03c2d0809fe6470a24c2192a338fe.zip

r2224 [OTA1 BETA2]
https://android.googleapis.com/packages/ota-api/xiaomi_oneday_oneday/d0b56c3ce4c1cea99c45856da9b194f56a8b53a3.zip

r2231 [RELEASE]
https://android.googleapis.com/packages/ota-api/xiaomi_oneday_oneday/84eeea378c7cbd03adb8240382717aa457ef6ea5.zip

r2582 [OTA2 BETA1]
https://android.googleapis.com/packages/ota-api/xiaomi_oneday_oneday/12e5455a8679c24c78bbbc77c63788c3a76eba7c.zip

r2596 [OTA2 BETA2]
https://android.googleapis.com/packages/ota-api/xiaomi_oneday_oneday/7a65e28754f99c0126b58b25652b97ab5a97926f.zip

r2603 [OTA2 BETA3]
https://android.googleapis.com/packages/ota-api/xiaomi_oneday_oneday/040153935c0e6f69ceae9eae1cbe222654e991f7.zip

r2604 [RELEASE]
https://android.googleapis.com/packages/ota-api/xiaomi_oneday_oneday/f69263555adae4e86c9896e34e30a93601de8e2f.zip

r2696 [RELEASE]
https://android.googleapis.com/packages/ota-api/xiaomi_oneday_oneday/811d10683084df7512b6cd56d137d53193c81856.zip

r3015 [OTA4 BETA0]
https://android.googleapis.com/packages/ota-api/package/11516e231b07ae14df0ae960cde690b601b2dddb.zip

r3091 [BETA]
https://android.googleapis.com/packages/ota-api/package/c5b22f23a38e07c9a8637c54df1d5f55470d71e7.zip

r3131 [BETA USERDEBUG] (VIDEO PLAYBACK BROKEN)
https://android.googleapis.com/packages/ota-api/package/ea3ec819034d1b00667fe6731914be43ae7a0276.zip

r3138 [BETA]
https://android.googleapis.com/packages/ota-api/package/f7f6b68bc80941aee1628b8bf005e1943b5f29cb.zip

r3139 [RELEASE]
https://android.googleapis.com/packages/ota-api/package/6f179c6fb4fe79ec1acebc3434f93232e0351100.zip

r3386 [OTA5 BETA0]
https://android.googleapis.com/packages/ota-api/package/56c7ee1e719ec842dff99dd4af0011f6fc6c7cdb.zip

r3409 [RELEASE]
https://android.googleapis.com/packages/ota-api/package/414e9608ca8a685244e4ee15e8628c98d255e51b.zip

r3595 [RELEASE]
https://android.googleapis.com/packages/ota-api/package/5cabec120b0378853b3d89a58c0171ac3e965046.zip

r3933 [RELEASE - BUILT SEP 28 2021]
https://android.googleapis.com/packages/ota-api/package/05be380dea3b2891a1fd3df98b138981689239ba.zip
```

```
root流程
    home+返回长按接电源进入recovery
    通过刷update_miboxs_r3131_userdebug.zip
    adb root获取root
    root文件push /data/local/tmp
    chmod a+x live_setup.sh
    ./live_setup.sh
    重启后每次开机都需要操作一篇获取root
    
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

这样就具有临时root+硬件能力播放正常的miboxs了

