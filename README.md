# API_without_Doc
針對沒有文件的 API，如何設計爬蟲呢？

動態網頁執行請求及丟出回應的套路：

(1) 處理 GET 請求

(2) 從 DB 讀取資料

(3) 將資料轉成 HTML 或其他格式

(4) 發送 HTML 給使用者

以上 (3)-(4) 大部分因為 JS 的客戶端語言發展，已經由伺服器轉資料格式，轉為由瀏覽器代為處理。
由伺服器發出 HTML Template，藉由 Ajax 請求加載內容，再由瀏覽器客戶端語言選染其 HTML Template。

意即，DB 不再作轉會資料成為 HTML 的步驟，它僅僅需要包裝資料，透過 API 傳送至網頁。

而爬蟲角度而言，會得到沒有內容的 HTML Template。

# Selenium 套件

此套件用於解決如上問題，解決方案如下：

1. 呼叫追蹤程式

2. 載入廣告

3. 呼叫廣告的追蹤程式

4. 接著，圖像和 CSS 及文字資料將被載入。

5. 設計上，要約束搜索範圍和條件，否則自己的伺服器會不堪負荷。
（若使用套件爬蟲執行探勘網頁，每個搜尋可能發出100個請求以及下載了 600 kB 資料）

# 直接呼叫 API，藉以載入資料

直接呼叫 API，僅僅需要發出一個請求與 60 kB 格式的資料。

範例：

      https://query.nytimes.com/svc/add/v1/sitesearch.json?q=python&spot=true&optiones=true
      
# 無文件 API 的文件

6. 改用 API 呼叫，則對自己做的機器人，可以自己寫文件，獲得幫助。

透過載入此網站的多個網頁，從網路分頁過濾出目標 API call，一但如此，便能將整個網站架構，識別出其呼叫和接受欄位與回傳欄位。

* HTTP methods

* Input || Request
  
  - path-param
  - header(including cookies)
  - body

* Output || Response
  
  - header(including cookies)
  - body in formats
  - fields
 





