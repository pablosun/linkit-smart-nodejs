# 拍照上傳至 MCS (草稿，未完成)

(本章節功能還尚未 release)

本篇 LinkIt smart 7688 , LinkIt smart 7688 Duo 皆可以適用.

## 準備事項

* 先準備好一條 usb OTG 線
* 準備好您的 web camera ( 本篇範例是使用羅技 C310)
* 將電源線插入PWR, web camera 插入 usb OTG 在插入 7688 上的 HOST 。

## 在 MCS 上要做的事情

* 進去 prototype 詳情頁面，點擊 `Add Data Channel now`:
![](imagedisplay01.png)
* 創建一個 display 形式的 datahchannel:
![](imagedisplay02.png)
* Data type 選擇 image，其他空格按照您的需求輸入，注意這時候打的 data channel id 就是等一下會用到的 `dataChnId` :
![](imagedisplay03.png)
* 回到 prototype 詳情頁面，點選 `create test device`:
![](imagedisplay04.png)
![](imagedisplay05.png)
* 進去 device 頁面後，就可以看到 `deviceId`, `deviceKey`:
![](imagedisplay06.png)


## 在 Device 端要做的事情

* ssh 進去您的 7688:
* 安裝 `fswebcam`:

```
opkg update
opkg install fswebcam
```
* 測試是否能拍一張照片:

```
fswebcam  -i 0 -d v4l2:/dev/video0  --no-banner  --jpeg 95  --save test.jpg
```
之後你就會看到你的根目錄下面有一個 test.jpg 的檔案。

* 編輯 app.js

```
vim app.js
```
* 將這段 code copy 進去:

``` js

```

* 返回你的 MCS 的 test device 那頁就可以看到成果囉!