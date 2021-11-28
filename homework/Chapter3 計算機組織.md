## 目錄
[3-1 中央處理器 (Central Processing Unit；CPU)](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter3%20%E8%A8%88%E7%AE%97%E6%A9%9F%E7%B5%84%E7%B9%94.md#3-1-%E4%B8%AD%E5%A4%AE%E8%99%95%E7%90%86%E5%99%A8-central-processing-unitcpu)  
[3-2 主記憶體](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter3%20%E8%A8%88%E7%AE%97%E6%A9%9F%E7%B5%84%E7%B9%94.md#3-2-%E4%B8%BB%E8%A8%98%E6%86%B6%E9%AB%94)  
[3-3 執行程式](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter3%20%E8%A8%88%E7%AE%97%E6%A9%9F%E7%B5%84%E7%B9%94.md#3-2-%E4%B8%BB%E8%A8%98%E6%86%B6%E9%AB%94)  
[3-4 匯流排及介面](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter3%20%E8%A8%88%E7%AE%97%E6%A9%9F%E7%B5%84%E7%B9%94.md#3-4-%E5%8C%AF%E6%B5%81%E6%8E%92%E5%8F%8A%E4%BB%8B%E9%9D%A2)  
[3-5 輸出入周邊設備](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter3%20%E8%A8%88%E7%AE%97%E6%A9%9F%E7%B5%84%E7%B9%94.md#3-5-%E8%BC%B8%E5%87%BA%E5%85%A5%E5%91%A8%E9%82%8A%E8%A8%AD%E5%82%99)  
[3-6 儲存裝置](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter3%20%E8%A8%88%E7%AE%97%E6%A9%9F%E7%B5%84%E7%B9%94.md#3-6-%E5%84%B2%E5%AD%98%E8%A3%9D%E7%BD%AE)  
[可參考影片](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter3%20%E8%A8%88%E7%AE%97%E6%A9%9F%E7%B5%84%E7%B9%94.md#%E5%8F%AF%E5%8F%83%E8%80%83%E5%BD%B1%E7%89%87)  

## 3-1 中央處理器 (Central Processing Unit；CPU)  
1. 是計算機的大腦，是一個電路極為複雜的晶片，用來執行儲存在記憶體的程式指令，控制數位資料的處理及運算。  
2. CPU 分為兩部分:  CU (控制單元) + ALU (算術邏輯單元)  
3. 另，中央處理器有一個極小的儲存裝置，稱為**暫存器(register)**  
* 暫存器的存取速度比主記憶體快，可大大增高CPU的效能  
*  **指令暫存器(Instruction Register)：** 儲存所執行指令  
*  **程式指標暫存器(Program Counter)：** 記錄目前程式正在執行的指令位址之  

4. 中央處理器和記憶體的連結架構圖  
![image](https://user-images.githubusercontent.com/91866985/143688618-6d03a761-3f7a-4c27-9e76-dd6d8361c065.png)

![image](https://user-images.githubusercontent.com/91866985/143688608-e8d2ddd3-e4d7-47c1-b7ff-59febdf52492.png)

5. 控制單元 (Control Unit；CU)  
* 負責控制電腦執行程式的流程。  
* 負責指揮各個系統單元執行所須進行的任務。  
* 必須協調各個系統單元間的運作。例如：它會  
   * (1)從記憶體將所須執行的程式指令搬到暫存器並對指令解碼，  
   * (2)然後交給算術邏輯單元運算，  
   * (3)再將運算結果放回暫存器或記憶體。  


7. 算術邏輯單元 (Arithmetic Logic Unit；ALU)  
* 是算術單元及邏輯單元的合稱，負責加法、減法、乘法及除法等數學運算。  
* 負責AND、OR、XOR(eXclusive OR；兩者相同為0、反之為1)及NOT等邏輯運算  
   * 邏輯運算用來做位元的操作，並用來判斷決定程式流程的某些條件是否成立。  
   * 通常是「大於條件」、「等於條件」及「小於條件」等，例如：判斷兩個數的大小等。  
   ![image](https://user-images.githubusercontent.com/91866985/143688766-cd5ad9dd-a617-448e-a50a-18f6dc896414.png)
![計算機概論-14](https://user-images.githubusercontent.com/91866985/143688796-09b870b5-6c39-448b-8897-3a78b33f3353.jpg)

8. 匯流排(bus)
* 中央處理器和記憶體的連結架構裡，有一些用來傳輸電子訊號的傳輸工具  
* 可分為三個:  
   * 控制匯流排(control bus): 讓控制單元可以操控算術邏輯單元的運算。  
   * 位址匯流排(address bus): 將所要執行的程式位址傳到中央處理器內的程式指標暫存器。  
   * 資料匯流排(data bus): 可供各單元間進行資料交換。  
 
 
## 3-2 主記憶體

1. 功能:
   * 記憶體是用來儲存數位資料以及運算後的結果
   * 在馮紐曼模式裡，記憶體同時儲存程式及資料，當操作不同程序時，只要**載入相對應的程式即可，不必另外改變硬體**
   
2. 記憶體依 **速度** 、 **單位價格** 及 **屬性** 可區分:  
![image](https://user-images.githubusercontent.com/91866985/143688879-ab73e6d7-2d5d-45c7-9e8e-e46894a89095.png)

* 暫存器 (register):  
   * 速度最快但單位價格最高。 
    
* 快記憶體取 (cache):  
   * 位於CPU內，介於CPU和記憶體間。
   * 速度比暫存器慢，單位價格較便宜，容量也比暫存器多。
   * 速度比主記憶體快，單位價格較貴，容量也比主記憶體少。  
   * CPU執行時，若每次都從主記憶體擷取資料，因主記憶體傳送資料到CPU的速度較慢，效率會較差，因此使用 **快取記憶體(cache)** 可提高CPU與記憶體間之頻寬。

*  **馮紐曼瓶頸 (von Neumann Bottleneck) ** 
   * 不論CPU與記憶體的速度有多快，整個系統的速度終將受限於匯流排(bus)的速度。  

3. 記憶體類別
* RAM (隨機存取記憶體)
   * 可隨機讀取資料，可讓使用者隨意改寫內容
   * RAM一旦關機後， 資料就不見了。
   * SRAM (靜態隨機存取記憶體) & DRAM (動態隨機存取記憶體) :  
      * SRAM (靜態隨機存取記憶體) :  
         * 以正反器(flip-flop gate)儲存資料。
         * 取名「靜態」的原因是因為只要電源維持住， 並不需要做更新(refresh)的動作。
         * 速度較快，價錢也貴些。

      * DRAM (動態隨機存取記憶體) :
         * 以電容器(capacitor)儲存資料。
         * 因電容器會隨時間逐漸失去電容量，因此須動態週期性地更新(refresh)內容，故取名為動態隨機存取記憶體。
         * 速度較慢，但價錢便宜許多。
         
      * 在相同的晶片面積下，DRAM容量大於SRAM四倍以上；但在速度上，SRAM卻是比DRAM快四倍以上。


* ROM (唯讀記憶體)
   * 可隨機讀取資料，使用者不可改寫
   * ROM在關機後，仍可維持資料內容，可用來儲存開機使用的程式。
   * PROM(可程式化的唯讀記憶體):
      * 可讓使用者儲存所需的程式，一旦儲存後，就不可再改寫。

   * EPROM(可擦拭及程式化的唯讀記憶體):
      * 可以改寫，但必須以紫外線照射來擦拭。

   * EEPROM(可以電子擦拭及程式化的唯讀記憶體):
      * 可直接從電腦進行改寫，最為方便，廣泛應用於BIOS晶片及快閃記憶體。

## 3-3 執行程式
* 擷取指令：CPU執行時，先由控制單元擷取(fetch)所要執行的指令，放在指令暫存器。
* 解碼指令：所抓到的東西都是二位元字串，每個指令可能包括指令動作及資料，當抓到指令時，可由查表法進行解碼(decode)動作。
* 執行指令：當找到該指令對應的運算動作，就交給算術邏輯單元來執行(execute)，執行完所得的結果再由控制單元協助儲存回記憶體。
* 生產線技術:
   * 為增進CPU效率，當算術邏輯單元正在執行時，控制單元會開始進行下一個擷取指令的動作  
   * 如同汽車工廠的生產線(pipeline)
   * 將CPU執行程式的流程，以生產線方式進行，稱為生產線技術(pipelining)，可大大提升CPU的執行效率  
![image](https://user-images.githubusercontent.com/91866985/143689389-9f7e9f1b-d465-4bbf-aa8d-6f7e210e29eb.png)


## 3-4 匯流排及介面
1. 電腦主機板上用來傳輸電子訊號的傳輸工具，稱為匯流排(bus)，包括：  
   * 系統匯流排：負責CPU與記憶體間的資料傳送。
   * 擴充匯流排：保留一些連接給使用者彈性使用。
   
2. 匯流排一次所能傳輸的資料量，稱為 **匯流排寬度(buswidth)** ，它會和CPU每次所能處理的位元數相容。 
 
3. 連接埠(port): 外部連接端
   * 序列埠(serial port)：每次傳一個位元
   * 平行埠(parallel port)：每次傳一組位元

4. ISA、PCI、AGP
5. PCI Express
6. PCI Express
7. USB (Universal Serial Bus；通用序列匯流排)
8. IEEE 1394 
* 高速序列匯流排的公定標準
* Apple命名為FireWire，Sony稱它為i.Link
* 提供隨插即用功能，提供個人電腦相容性的延伸介面，具有保證頻寬的傳輸模式，適用於消費性電子聲訊／視訊產品、儲存周邊及可攜式裝置
* IEEE 1394的資料傳輸速度為每秒400 Mb，新版的IEEE 1394b規格，傳輸速度為每秒3.2 Gb


## 3-5 輸出入周邊設備
(略)  

## 3-6 儲存裝置
* [傳統硬碟 vs. 固態硬碟](https://buzzorange.com/techorange/2018/01/19/hdd-vs-ssd/)

## 可參考影片:
* [Inside Your Computer](https://www.youtube.com/watch?v=Q2hmuqS8bwM)
* [Inside your computer - Bettina Bair](https://www.youtube.com/watch?v=AkFi90lZmXA)
* [Computer Basics: Getting to Know Laptop Computers](https://www.youtube.com/watch?v=6LIv2ocJXRk&list=PLpQQipWcxwt-xhJVJs7MCcU-XzWYVsTQt&index=8)
* [How computer memory works - Kanawat Senanan](https://www.youtube.com/watch?v=p3q5zWCw8J4)  
  
  
* 3C = Computer + Communication + Consumer electronics  
