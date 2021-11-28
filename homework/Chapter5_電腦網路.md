## 目錄:  
[5-1 電腦網路的用途](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter5_%E9%9B%BB%E8%85%A6%E7%B6%B2%E8%B7%AF.md#5-1-%E9%9B%BB%E8%85%A6%E7%B6%B2%E8%B7%AF%E7%9A%84%E7%94%A8%E9%80%94)  
[5-2 電腦網路的架構](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter5_%E9%9B%BB%E8%85%A6%E7%B6%B2%E8%B7%AF.md#5-2-%E9%9B%BB%E8%85%A6%E7%B6%B2%E8%B7%AF%E7%9A%84%E6%9E%B6%E6%A7%8B)  
[5-3 傳輸媒介](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter5_%E9%9B%BB%E8%85%A6%E7%B6%B2%E8%B7%AF.md#5-3-%E5%82%B3%E8%BC%B8%E5%AA%92%E4%BB%8B)  
[5-4 OSI與TCP/IP模型](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter5_%E9%9B%BB%E8%85%A6%E7%B6%B2%E8%B7%AF.md#5-4-osi%E8%88%87tcpip%E6%A8%A1%E5%9E%8B)  
[5-5 常見的網路設備](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter5_%E9%9B%BB%E8%85%A6%E7%B6%B2%E8%B7%AF.md#5-5-%E5%B8%B8%E8%A6%8B%E7%9A%84%E7%B6%B2%E8%B7%AF%E8%A8%AD%E5%82%99)  
[5-6 電信網路](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter5_%E9%9B%BB%E8%85%A6%E7%B6%B2%E8%B7%AF.md#5-6-%E9%9B%BB%E4%BF%A1%E7%B6%B2%E8%B7%AF)  
[5-7 無線網路](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter5_%E9%9B%BB%E8%85%A6%E7%B6%B2%E8%B7%AF.md#5-7-%E7%84%A1%E7%B7%9A%E7%B6%B2%E8%B7%AF)  
[可參考影片](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter5_%E9%9B%BB%E8%85%A6%E7%B6%B2%E8%B7%AF.md#%E5%8F%AF%E5%8F%83%E8%80%83%E5%BD%B1%E7%89%87)  

## 5-1 電腦網路的用途  
1. 訊息交換:  
* 訊息交換可以說是電腦網路發展的初衷之一。電腦網路最重要的特色就是封包交換（packet switching）。
* 所有透過電腦網路傳輸的資料，都必須切割成較小的片段後，再以「封包」（packet）的型式包裝，然後再進行傳輸。  

2. 資源分享  
* 資源分享也是電腦網路裡重要的應用。早期的分享以檔案交換為主， 透過如Gopher、FTP 和網路磁碟（如NFS和網路芳鄰）等方式進行。而隨著技術的進步，幾乎所有的資源都可以透過網路來分享。  


3. 電子商務  
* 透過網路做生意，也是現在網路上的重要用途之一。線上的商家販售產品給消費者的方式稱為B2C（Business to Customer） 類型的電子商務， 常見的購物網站如eBay、Yahoo! 奇摩、PCHome的商城都是屬於這種類型。


4. 娛樂


## 5-2 電腦網路的架構    
1. 依據線路連接的方式:也稱為「網路的拓樸」(network topology)，常見方式:
* 匯流排 (bus)  
 ![image](https://user-images.githubusercontent.com/91866985/143771628-2c8920cd-e6f0-47a6-933b-961046d8c1c7.png)  
   * 所有的網路裝置接在同一條線路上
   * 最簡單的連接方式
   * 一次只能有一台裝置傳送資料，否則會發生衝突 (collision)
   * 多人使用時，效率較差
   * 衝突發生時，資料必需要重新傳送
     * Ethernet的CSMA/CD機制:
       * 全名為Carrier Sense Multiple Access with Collision Detection
       * 主要解決衝突發的情況
       * CSMA/CD運作概念如下:
         * 任一主機傳送資料前，先偵測網路是否無人使用
         * 確認無人使用，則進行傳送，否則等待
         * 萬一傳送時仍然不幸發生碰撞(二台或以上裝置同時傳送)，則隨機暫停一段時間後，再重新嘗試  
   * 建置成本低廉，且不易故障  

* 環狀 (ring) 
![image](https://user-images.githubusercontent.com/91866985/143771824-24640798-fbe2-4264-a5a2-5ae18e90c6a6.png)  
   * 資料傳輸是單向的: 順時鐘或是逆時鐘擇一，因此，任二個裝置之間的傳輸路徑是固定的。
   * 可以避免衝突的發生
   * 網路負載高時，有比較好的傳輸效率
   * 網路故障時，較難找出問題點
   * 建置成本較高  

* 星狀 (star)  
![image](https://user-images.githubusercontent.com/91866985/143771904-6bab0cbd-4f10-43fe-a18f-5415887556a3.png)  
   * 最常見的區域網路架構
   * 中心點有一個特定的裝置: 通常是集線器或是交換器。
   * 所有的訊息都需要透過中心點進行傳輸
   * 中心點若使用交換器，可降低發生衝突的機率
   * 網路發生問題時，比較容易除錯
   * 中心點故障時，全部的裝置都無法連線  


* 網格 (mesh)  
![image](https://user-images.githubusercontent.com/91866985/143771932-a1c686bc-5f75-478e-ba0a-980e1a248ff5.png)  
![image](https://user-images.githubusercontent.com/91866985/143771935-54e5bf95-3c89-40a0-80c7-9492bef75b6f.png)  
   * 建置、管理和維護都是較為複雜的連線方式
   * 通常使用於廣域網路、網際網路
   * 每個裝置(節點)都需要擔任轉送的角色
   * 裝置需要通力合作，網路才得以正常運行
   * 彈性較大。網路故障時，可以嘗試改變路由，繞道傳輸  

2. 依據資源服務的提供者  
* 主從式(client-server)架構  
  * 「伺服器」及「用戶端」角色分明
  * 是大部份網路服務採用的方式

* 同儕式(peer-to-peer，P2P)架構  
   * 每個網路裝置可以同時是「伺服器」或是「用戶端」
   * 常見的應用如P2P檔案分享(如bittorrent或是emule)、線上影音串流(如ppstream)  

3. 依據建置的規模  
* 區域網路 – LAN，Local Area Network
   * 規模最小，涵蓋的範圍可能是房間、房屋、建築物，或是校園  
* 都會網路 – MAN，Metropolitan Area Network
   * 中等規模，涵蓋的範圍可能是同一個城市裡的不同建築   
* 廣域網路 – WAN，Wide Area Network
   * 規模最大，可以是跨城市甚至跨國的網路


## 5-3 傳輸媒介  
* 電話線
* 同軸電纜
* 雙絞線
* 光纖
* 電磁波  

## 5-4 OSI與TCP/IP模型  
* 網路裝置之間的語言，通常稱為「通訊協定」
* 國際標準組織(ISO)訂定OSI模型，對通訊協定進行管理與分級
* OSI模型一共有七層，由於較為複雜，因此網路系統在「實作」時，常使用TCP/IP模型
* TCP/IP模型只有四層
* OSI模型的1至7層可以對應到TCP/IP模型中的1至4層:
![image](https://user-images.githubusercontent.com/91866985/143772110-3c02176e-fa1d-4204-8af5-ad36c9b4b17b.png)  
* 資料傳輸與OSI  
   * 資料由上層往下層傳送的過程中，每一層會對訊息「加料」(增加標頭)，標頭的目的是紀錄各層所需的資訊
   * 經料由下層往上層接收的過程中，每一層會讀取其對應的標頭資訊，取得和處理標頭資料後，移除標頭後，再將剩餘的訊息向上繼續傳送  

* OSI模型的各層:
![image](https://user-images.githubusercontent.com/91866985/143772091-a16e3756-e920-4c58-a216-b7eda3b50936.png)  

1. 應用層 – Application Layer (第七層)  
* 最貼近使用者的一層
* 常見的應用層通訊協定
   * 收發Email – SMTP、POP3、IMAP
   * WWW網路瀏覽 – HTTP
   * 網路串流 – RTSP、RTP、RTCP
   * 電子佈告欄BBS – TELNET  


2. 表達層 – Presentation Layer (第六層)  
* 以標準化的方式處理使用者的資料
* 發送端:編碼、壓縮、加密等
* 接收端:解碼、解壓縮、解密等  

3. 交談(會議)層 – Session Layer (第五層)
* 主要負責對話的建立，常見的例子:
   * RPC (Remote Procedure Call) – 允許使用者執行遠端不同的函數呼叫
   * RTSP (Real-Time Streaming Protocol) – 建立多通道以分別傳輸聲音及影像等多媒體資料
   * SSL (Secure Socket Layer) – 建立多通道以傳送需要加密保護的各種資料  

4. 傳輸層 – Transport Layer (第四層)  
* 提供多種資料傳輸服務，包括
   * 多工(multiplexing) – 允許主機建立多條網路連線
   * 流量控制及雍塞控制
   * 連接導向與無連接導向連線
   * 可靠傳輸  
* 傳輸層輸出的資料傳輸單位為區段(segment)或是數據包(datagram)
* 常見的協定如TCP、UDP、SCTP等等

5. 網路層 – Network Layer (第三層)  
* 主要提供網路主機識別資訊及相關服務，包括:  
   * 網路位址 – 用以識別網路上的主機
   * 資料切割 – 將資料裁切為適合傳輸的封包，以Ethernet為例，每個封包的上限為1500位元組
   * 網路路由 – 將封包正確的傳送到目的地網路位址  
* 網路層輸出的資料傳輸單位為「封包」(packet)
* 常見的網路層協定如IPv4及IPv6

6. 資料連結層 – Data Link Layer (第二層)  
* 處理區域網路或是點對點的網路連線
* 提供的服務包括:  
   * 硬體實體位址
   * 包裝封包(framing)
   * 錯誤偵測或修正
   * 多重存取(multiple access)  
* 傳輸單位為頁框(frame)
* 常見的協定如Ethernet、無線網路802.11、PPP等  

7. 實體層 – Physical Layer (第一層)  
* 主要將資料轉為硬體訊號傳送
* 傳送的單位為位元(bit)
* 可能透過各種不同的傳輸媒介進行傳送，如電子訊號、光學訊號、或是電磁波


## 5-5 常見的網路設備  
* 網路設備的分級，和網路協定一樣，是使用OSI模型
* 強調: TCP/IP模型只有實作時使用，一般討論網路設備或是網路協定，都是使用OSI模型
* 網路上傳送的封包，包含OSI模型各層的資訊
* 而設備的分級取決於該設備可以處理到網路封包裡的哪一層協定的標頭
* 常見配備:  
   * 網路卡 – network interface card (第二層) 
   * 中繼器 – Repeater (第一層) 
   * 集線器 – Hub (第一層)
   * 橋接器 – Bridge (第二層)
   * 交換器 – Switch (第二層)
   * 路由器 – Router (第三層)
   * 無線網路存取點 – Wireless AP (至少是第二層)


## 5-6 電信網路  
1. 封包交換 VS 線路交換:  
![image](https://user-images.githubusercontent.com/91866985/143772539-64a36aaf-4000-455c-933f-a5e822bb9d3b.png)  

2. POTS/PSTN  
* 傳統的市內電話: POTS – Plain Old Telephone Service
* 公共電話交換網: PSTN – Public Switch Telephone Network
* 使用線路交換技術，所以通話前需要透過通話設定，保留對話使用的專屬線路。所以就算雙方都不講話，還是得付線路費用
，按時計費
* 傳輸的訊號為類比訊號  
3. 第一代行動通訊網路 (1G) ~ 第五代(5G)    
[1G 到 5G 的艱辛歷程：一部波瀾壯闊的行動通訊史](https://www.stockfeel.com.tw/1g-%E5%88%B0-5g-%E7%9A%84%E8%89%B1%E8%BE%9B%E6%AD%B7%E7%A8%8B%EF%BC%9A%E4%B8%80%E9%83%A8%E6%B3%A2%E7%80%BE%E5%A3%AF%E9%97%8A%E7%9A%84%E8%A1%8C%E5%8B%95%E9%80%9A%E8%A8%8A%E5%8F%B2/)  

   * 第一代行動通訊網路 (1G)  
      * 約於1980年代開始使用，使用無線傳輸，透過分割頻率的方式，讓多人同時講電話(frequency division multiple access，FDMA)
      * 就好像廣播電台或是無線對講機—使用相同頻率的人就可以聽到彼此的聲音
      * 但功率較低，所以需要廣設基地台以增加服務範圍
      * 傳輸類比訊號，且容易被監聽  
      * 使用「細胞群」式的網路架構
         * 每個基地台只負責臨近的區域
         * 使用者移動時，則依其區域，選擇不同的基地台服務
         * 後來發展的2G、3G、4G也是使用類似的概念
         ![image](https://user-images.githubusercontent.com/91866985/143772860-8c6dddcc-bcc4-4262-be9b-4b13a8323c8a.png)  

      * 使用的無線頻段必需經過申請核淮，才可使用

   * 第二代行動通訊網路 (2G)  
      * 採用數位方式進行傳輸
      * 提供簡訊的功能
      * 提供數據資料傳輸功能
      * 標準由3GPP這個組織維護
      * 提供較高速的數據資料傳輸
        * 俗稱2.5G的GPRS以及2.75G的EDGE
        * 採用封包交換技術
        * 但資料傳輸仍不夠快
![image](https://user-images.githubusercontent.com/91866985/143772871-7e5e17e9-24e5-43d2-8f94-8759b543ea99.png)

   * 第三代行動通訊網路 (3G)  
   * 第四代行動通訊網路 (4G)  
   * 第五代行動通訊網路 (5G)  
 

## 5-7 無線網路  


## 可參考影片:
* [Computer Basics: Connecting to the Internet](https://www.youtube.com/watch?v=93-3zmVvCGU)
* [Computer Networking Explained | Cisco CCNA 200-301](https://www.youtube.com/watch?v=tSodBEAJz9Y)
* [Computer Networks: Crash Course Computer Science #28](https://www.youtube.com/watch?v=3QhU9jd03a0)
