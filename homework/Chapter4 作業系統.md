## 目錄
[4-1 作業系統簡介](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter4%20%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1.md#4-1-%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1%E7%B0%A1%E4%BB%8B)  
[4-2 各類作業系統](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter4%20%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1.md#4-2-%E5%90%84%E9%A1%9E%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1)  
[4-3 CPU排班法](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter4%20%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1.md#4-3-cpu%E6%8E%92%E7%8F%AD)  
[4-4 記憶體管理](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter4%20%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1.md#4-4-%E8%A8%98%E6%86%B6%E9%AB%94%E7%AE%A1%E7%90%86)  
[4-5 檔案系統](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter4%20%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1.md#4-5-%E6%AA%94%E6%A1%88%E7%B3%BB%E7%B5%B1)  
[4-6 熱門作業系統介紹](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter4%20%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1.md#4-6-%E7%86%B1%E9%96%80%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1%E4%BB%8B%E7%B4%B9)  
[4-7 行動裝置作業系統](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter4%20%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1.md#4-7-%E8%A1%8C%E5%8B%95%E8%A3%9D%E7%BD%AE%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1)  
[可參考影片](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter4%20%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1.md#%E5%8F%AF%E5%8F%83%E8%80%83%E5%BD%B1%E7%89%87)  


## 4-1 作業系統簡介
1. 作業系統 (Operating System , OS )是一個程式，負責管理電腦裡的硬體及周邊設備，扮演介於使用者與電腦硬體的中間人。
2. 提供使用者一個方便又有效率的環境，使其能夠執行程式。
3. 電腦系統大致可分為：
   * 硬體(微處理器、記憶體及輸出入設備)
   * 作業系統
   * 應用軟體(常用文書處理軟體、電玩、系統程式等)
   * 使用者(人或其他電腦)

4. 不同裝置的考量:
   * 大型系統: 要同時提供諸多使用者，所以強調效能方面、分配資源，例如訂票系統和購物網。
   * 個人電腦: 單一使用者掌控，除了效能之外，資源分配就顯得較不重要。

5. 作業程式的功能:
* 應防止因使用者執行程式而導致的錯誤或不正確操作的發生。
* 不同程式使用到的資源及控制若有交集的部分，應由作業系統來負責。
* 作業系統是一個在電腦內部隨時都在執行的核心程式(kernel)，其他則歸類為應用程式。
* 整個作業系統是一群程式的集合，其中最重要的部分就是常駐在記憶體的核心程式。
* 核心程式負責把其他部分的作業系統(非常駐程式)在必要時從磁碟中載入至記憶體中。
* 不論使用何種作業系統，當按下電腦電源時，核心程式就負責把其他作業系統載入到記憶體中，此過程稱為開機(boot)

![image](https://user-images.githubusercontent.com/91866985/143690163-bb701c7b-ba16-4771-90b6-9d2abdb48b32.png)

6. 作業系統負責的工作主要有五大項目: 

* 中央處理器管理(排定優先次序):
   * CPU是整個計算機的核心，當多個程式同時發出CPU需求，作業系統要負責讓CPU充分發揮功能，提高使用效率。
   * 當有一程序(process)處於等待狀況，作業系統就讓CPU進行其他程序運算，不能讓CPU閒置。
   * 若有一程序優先順序較目前CPU進行的程序高，作業系統須負責將CPU優先給順序高的程序使用。


* 記憶體管理:
   * 將有限的記憶體資源進行合理分配，使每一個程序都能滿足，並提昇效能
   * 讓每個程序都能獨立執行，也要使每個程序共享公共的程序和資料，以避免重複的程式片段和資料佔用，節省記憶體空間
   * 當程序執行時記憶體空間不夠，作業系統要能做出適當處理，讓目前執行的程序能夠繼續進行。
   *  **要防止使用者程序及程序執行時所需要的資料破壞作業系統本身。** 


* 檔案管理: 
   * 主記憶體空間有限，大部分的程序和資料，及作業系統本身都是放在輔助記憶體。
   * 作業系統的檔案管理工作：標示輔助記憶體的資料檔案，有條理地組織訊息，使檔案能夠合理存取與控制，使用者能夠方便而安全地使用。

* 周邊設備管理: 隨插即用(plug-and-play)，並提供簡易的使用者介面程式

* 程序管理:
   * 每一個程序在作業系統中對應著一個程序控制表(PCB)，記載著該程序的相關資訊及狀態。
   * 當程序進入系統後，會被放在工作佇列(job queue)中。
   * 就緒並等待執行的程序會被存放在就緒佇列(ready queue)，作業系統負責不斷將這些程序交給CPU進行運算。


![image](https://user-images.githubusercontent.com/91866985/143690264-d25fb534-eba0-4495-aba3-331b9aea0a5c.png)


## 4-2 各類作業系統
1. 手動操作階段(早期電腦使用)  
* 特色:
   * 使用者獨占計算機的所有資源，並直接使用硬體。  
   * 執行程式時，要先將計算機初始化，然後啟動控制開關。  
* 輸入:
   * 將程式、資料和與工作相關的控制訊息打洞在打孔紙內，依序輸入計算機。
   * 裝置可能是讀卡機和磁帶機  
* 輸出
   * 計算機接收到輸入之後，開始執行作業。一段時間之後(可能是數分鐘、數小時、數天)產生輸出。
   * 裝置則為印表機、打孔機或磁帶機  
* 除錯：若程式執行有誤，須檢測記憶體和暫存器裡的值。  

 
2. 批次系統 (batch system)  
* 作業之間的轉接自動化: 一個工作到下一個工作時，負責自動控制轉換
* 縮短了作業間等待CPU的時間，較能發揮計算機的處理能力
* 作業系統常駐在 **記憶體** 中
* 過程:
   * 作業員把若干相同或類似的工作集合為一整批(batched)，讀入主記憶體的緩衝區，再轉到磁帶上。
   * 由系統監控程式接手，負責將磁帶上的每個作業循序讀入主記憶體中，交給CPU去運算處理。
   * 一個作業接著一個作業運作，直到整批全部完成，再把下批作業讀入磁帶，以同樣的方式進行處理
* 由於 Iuput/Output 緩慢的關係，CPU仍經常處於閒置等待的狀態。
* 批次系統已經允許把所有工作一起放在磁碟中，若能直接存取多件工作，作業系統就可以進行 **工作排班(job scheduling)** ，進而增進效率。
* 批次系統讓使用者不必理解計算機的每個細節，就能進行處理。  

3. 多元程式規劃系統 (multiprogramming)  
* 目的: 增進CPU的使用率，只要還有程序需要CPU，CPU就不會閒置等待。  
( 程序: 一個程式被載入記憶體中並執行時 )  
* 程序的生命週期:  
![image](https://user-images.githubusercontent.com/91866985/143768203-b031d4cc-7804-49c1-b01b-5b86b1ac532e.png)  
   * 只要程序進入等待狀態，CPU就轉移到其他工作運作，若原本在等待的程序已經變成就緒，就有機會再重新得到CPU資源
   * 所有工作進入系統後，都放在工作池(job pool)，多元程式規劃必須為使用者「決定執行優先順序」，將多個程序放置在記憶體中
* 當多個程序需要執行時，會先放到大型儲存裝置的工作池中，等候被執行：
   * 1. 工作排班(job cheduling)：負責把程序從工作池中選出，載入到記憶體內以便執行。
   * 2. 處理器排班(CPU scheduling)：程序進入記憶體後仍須等待，此時使用CPU排班，從記憶體中挑選已就緒的程序，將CPU分配給它使用。  
* CPU在程序之間來回運轉狀況:
![image](https://user-images.githubusercontent.com/91866985/143769666-b993d2de-2dba-4c40-bd3c-b070e49d372b.png)
   * CPU首先為P0進行運算，P0進入等待狀況時，作業系統提出中斷或者系統呼叫，接著CPU改為P1進行運算，如此來回轉換。

4. 分時系統
* 將CPU的時間「切割成很多小時段」，CPU在各程序或使用者間不停切換執行。
* 頻繁的切換使每個使用者都以為自己和CPU是持續運作
![image](https://user-images.githubusercontent.com/91866985/143769759-7e0f3bbf-0031-40d1-a292-ba2f089184c7.png)
* 特色: 有效且公平的排程是作業系統設計的重點
   * 同時性: 可同時有若干使用者連結到同一台計算機上進行運算。
   * 獨立性: 不同的使用者之間不會相互干擾。
   * 即時性: 每一個使用者都可即時得到計算機的回應。
* 比較:
   *  多元程式規劃系統倚靠事件觸發(eventdriven)
   *  分時系統則是倚靠時間觸發(time-driven)。


5. 個人電腦系統: 個人系統的目標在於增進使用者操作方便，並提昇CPU回應速度，避免使用者等待。  
* DOS磁碟作業系統: 是微軟最早的作業系統產品，用在IBM相容個人電腦上，使用者以指令方式操控電腦。
* Mac OS: 是第一個圖形化介面的個人電腦作業系統，適用於蘋果電腦上。
* Windows: 微軟推出的Windows 1.0是PC上的第一個圖形化作業系統。
* Linux: 根據大型電腦作業系統UNIX所發展，早期只有命令列模式，現在也有了圖形化使用者介面。



6. 多處理器系統(multiprocessor system)

7. 分散式系統

8. 即時系統

## 4-3 CPU排班
1. 先到先處理

2. 最短工作先處理

3. 優先權排班

4. 依序循環排班



## 4-4 記憶體管理
## 4-5 檔案系統
## 4-6 熱門作業系統介紹
## 4-7 行動裝置作業系統






## 可參考影片:
* [Computer Basics: Connecting to the Internet](https://www.youtube.com/watch?v=93-3zmVvCGU)
* [Computer Networking Explained | Cisco CCNA 200-301](https://www.youtube.com/watch?v=tSodBEAJz9Y)
* [Computer Networks: Crash Course Computer Science #28](https://www.youtube.com/watch?v=3QhU9jd03a0)
