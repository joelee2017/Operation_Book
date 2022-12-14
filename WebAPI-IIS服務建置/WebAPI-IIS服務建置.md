WebAPI-IIS服務建置



## 步驟一：安裝 ASP.NET Core 3.1 Windows Hosting Bundle

1. [官網](https://dotnet.microsoft.com/download/dotnet-core/3.1) 下載 ASP.NET Core 3.1 Windows Hosting Bundle。

   ![image-20221214084743399](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214084743399.png)

2. 打開 dotnet-hosting-x-win.exe安裝檔，打勾同意授權條款後，點選安裝 > 開始安裝 > 安裝完成。



## 步驟二：安裝IIS

1. 控制台 > 程式集 > 開啟或關閉Windows功能。

![image-20221214101432063](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214101432063.png)

2. 找到 Internet Information Services，打勾 Web 管理工具和 World Wide Web服務，點選確定，等待它套用完成後關閉。

![image-20221214101531066](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214101531066.png)

4. 直接搜尋 IIS 服務管理員或者，C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools\Internet Information Services (IIS) 管理員。

![image-20221214101739691](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214101739691.png)

5. 打開 Internet Information Services (IIS) 管理員。

![image-20221214102147212](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214102147212.png)

## 步驟三：新增站台

1. 對站台按滑鼠右鍵，點選「新增網站」。

![image-20221214085729834](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214085729834.png)

2. 輸入站台名稱，並選擇網站要放的路徑，這邊建議可以新增一個資料夾放。然後連接埠80 Port 已經被初始網站用走了，所以可以設一個別的Port。

![image-20221214090139506](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214090139506.png)

## 步驟四：打包專案

1. 回到專案，在Visual Studio的方案總管頁籤，找到要發佈的專案，並按右鍵，點選發佈

![image-20221214090449588](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214090449588.png)

2. 新新增發佈設定檔「資料夾」

   ![image-20221214090706111](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214090706111.png)

3. 發佈目標選擇「資料夾」，然後資料夾路徑選擇，剛剛 IIS 新增的站台路徑，選擇完後點選完成。

![image-20221214091436210](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214091436210.png)

![image-20221214091633545](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214091633545.png)

5. 點選發佈。

![image-20221214091055904](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214091055904.png)

## 步驟五：打開網站

1. 將部署好的程式放置在建立好的 IIS 站台底下，回到 IIS，選擇剛剛新增的站台，並點右邊動作頁籤上的瀏覽按鈕。

![image-20221214100242439](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214100242439.png)

2. 於瀏覽器輸入剛剛建立的站台及port、方法進行測試 http://localhost:8084/weatherforecast。

回應結果

![image-20221214100659875](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214100659875.png)

回應 200 成功

![image-20221214100747932](D:\Book\WebAPI-IIS服務建置\image\WebAPI-IIS服務建置\image-20221214100747932.png)