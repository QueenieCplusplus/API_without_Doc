# API_without_Doc
針對沒有文件的 API，如何設計爬蟲呢？

動態網頁執行請求及丟出回應的套路：

(1) 處理 GET 請求

(2) 從 DB 讀取資料

(3) 將資料轉成 HTML 或其他格式

(4) 發送 HTML 給使用者

以上 (3)-(4) 大部分因為 JS 的客戶端語言發展，已經由伺服器轉資料格式，轉為由瀏覽器代為處理。
由伺服器發出 HTML Template，藉由 Ajax 請求加載內容，再由瀏覽器客戶端語言選染其 HTML Template。

而爬蟲角度而言，會得到沒有內容的 HTML Template。

# Selenium 套件

此套件用於解決如上問題。


