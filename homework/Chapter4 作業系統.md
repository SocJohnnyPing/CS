## 目錄
[4-1 作業系統簡介](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter4%20%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1.md#4-1-%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1%E7%B0%A1%E4%BB%8B)  
[4-2 各類作業系統](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter4%20%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1.md#4-2-%E5%90%84%E9%A1%9E%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1)  
[4-3 CPU排班法](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter4%20%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1.md#4-3-cpu%E6%8E%92%E7%8F%AD)  
[4-4 記憶體管理](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter4%20%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1.md#4-4-%E8%A8%98%E6%86%B6%E9%AB%94%E7%AE%A1%E7%90%86)  
[4-5 檔案系統](https://github.com/SocJohnnyPing/CS/blob/main/homework/Chapter4%20%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1.md#4-5-%E6%AA%94%E6%A1%88%E7%B3%BB%E7%B5%B1)  
4-6 熱門作業系統介紹  
4-7 行動裝置作業系統  

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
* 進行大量運算時，各處理器可以一起分擔工作。  
* 但是!! 添加四顆CPU為原來的五倍，但效能不一定就會變成原來的五倍
  *  多處理器同時運作時，要多費功夫保持處理器間的溝通合作正常
  *  無法呈現等倍數成長，但還是能增進效能  
* 生產線的模式 for 增進效能:
  * 一起運作可達到「容錯(fault tolerance)」的目的
  * 各個工作適當分配在不同的處理器上，若其中一個處理器發生問題，系統也不會因此中止，只是速度會變得較慢  

7. 分散式系統  
* 電腦是分散的，電腦間並不共享資源或時脈，每一個電腦都有自己的記憶體及作業系統，彼此間依靠網路傳輸交換資料
* 雖然電腦會透過網路連線使用其他電腦的資料或元件，但是使用者並不會有任何感覺，像是只對單一電腦交談一樣
* 例: Web Service  

8. 即時系統  
* 計算機要能即時回應外部事件的要求，並於規定時間內完成對該事件的處理，還要控制所有的即時設備與工作能夠協調執行。
* 適用於使用者對處理器操作或資料傳輸，有嚴謹的時間限制  
* 通常用在「專門應用範圍的控制裝置」，感應器將資料傳送給電腦，電腦必須將資料加以分析，並且控制感應器
* 例如: 控制科學實驗、醫學影像系統、或者是工業工程控制  
* 特色:
   * 即時時鐘管理: 用以完成定時工作或者延遲工作，以利與其他工作協調。
   * 過載保護: 當工作太多導致計算機來不及處理時，須有完善的服務策略(例如：使用緩衝區)。
   * 高度可靠性: 須保障計算機發生問題時，系統仍然正常工作，通常使用的解決方式就是多處理器。  

9. 手持系統  
(略)

## 4-3 CPU排班  
* CPU排班的決策時間點
![image](https://user-images.githubusercontent.com/91866985/143770256-5dd2c3f5-6894-4e4b-bcba-66a1681ede54.png)  
  * 新程序產生時
  * 程序從執行狀態變成等待狀態(譬如有I/O要求)。
  * 程序從執行狀態變成就緒狀態(譬如有中斷發生時)。
  * 程序從等待狀態變成就緒狀態(譬如I/O要求得到回應)。
  * 程序中止時。  
* 排班模式:  
   * 不可搶先排班(nonpreemp tive):
     * 排班方式確保已享有CPU資源的程序能夠一直用，不管其他程序的狀態，直到程序自己跳到其他非執行的狀態，才進行排班。   

   * 可搶先排班(preemptive):
     * 時時刻刻都要注意所有程序的狀態，若有程序進入就緒狀態，就要相互比較已就緒程序與正在使用CPU程序的優先順序。  
* CPU排班演算法的評估標準:  
   * CPU使用率：理論上CPU使用率最好達100%，但實際應用上，CPU不可能到達此極限。  
   * 產能(throughput)：CPU越忙碌，產能就越高。產能是衡量單位時間CPU可完成多少程序  
   * 回復時間(turnaround time)：指一個程序從進入電腦開始至CPU執行所花費的單位時間。  
   * 等待時間：算計程序會花多久的時間在就緒佇列中等待。  


1. 先到先處理(FCFS)  
* 把CPU分給第一個需要CPU資源的程序。
* 可用有「先進先出(first in first out)」特性的佇列來排置程序。CPU會先運算佇列中的第一個程序，並將它從就緒佇列中踢除；當有新程序需CPU資源時，就被串接到就緒佇列的末端。
* 排班方式是不可搶先的  


2. 最短工作先處理(SJF)  
* 當CPU排班在挑選下一個執行程序時，會檢視所有需要CPU資源的程序各會花多少時間完成工作。最短的程序就能先得到CPU資源，其餘則等下一次挑選時再行比較。
* 如果有兩個以上的程序所需時間相同，則採用「先到先服務」的方式挑選。  
* CPU執行某工作時，若有新程序產生:
   * 可搶先:比較新程序的所需時間。若較目前執行程序的剩餘時間短，新程序則可搶走CPU。
   * 不可搶先: 新程序須等目前正在執行的程序完成。  
* 若單純考慮使平均等待時間降到最低，最短工作先處理的方式是最理想的。
* 雖然將一個短程序排到前面，會使長程序擠到後面而增加其等待時間，然而卻可以大大減低短程序的等待時間。
* 難處：實際執行時，很難精準預測每一個程序將花多少時間來完成工作。  

   
3. 優先權排班  
* 優先權(Priority Scheduling)是指為程序們階級化，標上優先順序。
* 先到先處理的方式並無優先權概念，而最短工作先處理的方式，則屬優先權的特例。
* 優先權可計算的面向:
   * 所需時間
   * 記憶體需求
   * 程序大小
   * 程序重要性  
* 優先權排班也可分成可搶先及不可搶先兩種
* 優先權排班會因程序始終得不到CPU資源，而變成「飢餓(starvation)」狀況。
* 工作繁重的電腦系統可能會有一連串高優先權的程序不斷進入就緒佇列，而導致低優先權的程序永遠癡癡等待。
* 解決方式：將等待時間也列入優先權設定的考量。設定等待超過一定時間，就提升該程序的優先權

4. 依序循環排班(Round Robin Scheduling):為了分時系統而設計   
* 基本精神與先到先處理相同，但在使用時先設定好間隔時間(time slice)
* 所有程序放在先進先出的佇列裡，首先CPU排班從佇列裡挑第一個程序執行，然後開始進行倒數，時間到時，就讓CPU處理佇列裡下一個程序  
* 規則:
   * 程序所需時間＜間隔時間：程序一執行完畢，就自動交出CPU，執行下一個程序。
   * 程序所需時間＞間隔時間：倒數完畢時，作業系統須將目前執行的內容及狀態記錄下來，寫進 **程序控制表(PCB)** 中，然後把該程序放到佇列的尾端，從佇列開頭拿取下一個程序執行。  
* 執行次數越多，代表程序轉進轉出CPU的次數越多，就會花較多時間讀取及寫入程序控制表。
* 若時間間隔設定太小，會導致執行次數太多；若時間間隔設定太大，排班方式會與先進先出相同。
* 通常使用「二八原則」：讓20%的程序所需時間大於時間間隔，而80%的程序所需時間會小於時間間隔。  

5. 無論採用何種排班方式， 當程序需要資源時，都會循著以下順序：
* 請求資源 / 使用資源 / 釋放資源
* 在多元程式規劃(multiprogramming)中，程序進到「等待」狀態後，因其所請求的資源，可能被其他同樣在等待狀態中的程序佔用，從此陷入等待狀態無法跳脫，稱為死結(Deadlock)
* 在死結中的程序，由於每個程序都在等待其他程序觸發事件，但卻沒有程序可以先觸發事件，導致所有程序癱瘓，最終呈現餓死(starvation)的狀態。


## 4-4 記憶體管理  
* 功能:
   * 記憶體管理：要把記憶體分割(partition)成各個區塊，分配給各程序，甚至是各使用者使用。  
   * 記憶體位址定位：負責把程式所使用的邏輯位址(logical address)與記憶體裡的實際位址(physical address)做映射(mapping)工作。  
   * 記憶體保護與共享：要保護好作業系統所使用的記憶體區塊不會被程序破壞。  
![image](https://user-images.githubusercontent.com/91866985/143770746-3a3ab199-6f64-424c-aef0-b801c9cdea54.png)  

1. 界線位址保護法  
* 界線位址保護法是靠「界線暫存器」及「基底暫存器」來防止使用者破壞作業系統的保護機制。
* 若作業系統放置在高位址區域，界線暫存器就用來保護作業系統區塊最下界。
* 當CPU存取應用程式區塊時，會先檢查存取的邏輯位址是否小於界線暫存器。若存取位址比界線暫存器內的值還高，則發出錯誤中斷訊息，要求作業系統做出錯誤處理；若沒問題，則再加上基底暫存器的值形成實際位址。


2. 動態載入  
* 動態載入是指常式(routine)只有在被呼叫的時候才會載入，也就是說，將所有的常式以可重定位載入的方式存放在磁碟空間內。
* 主程式存放在記憶體中，執行時，若需呼叫其他常式，先查看是否已經存在記憶體內。如果沒有，則呼叫重疊定位連結程式，將需要的程式或資料載入記憶體中，以便執行。  


3. 覆蓋  
* 覆蓋能讓大小超過記憶體容量的程式執行。
* 是指最主要的部分會存放在記憶體中，而只有在特定時候才需要用到的指令或資料，則只有被用到時，才會放在記憶體中，其他時候就被覆蓋掉。
* 藉著舊的指令被覆蓋，才有空間存放新的指令。  
* 假設一編譯器在處理程式時：
   * 第1次處理的程式碼有80KB
   * 第2次處理的程式碼有70KB
   * 所建立的符號表有20KB，會被呼叫到的常式有30KB。
* 一共有200KB。假設記憶體只有150KB，可採用覆蓋技術。  
* 除了符號表和常式會一直用到之外，第1次處理的程式碼跟第2次處理的程式碼分別獨立使用一次，因此：
   * 第1次處理：第1次載入符號表、常式、第1次處理的程式碼、再加上覆蓋所使用到的覆蓋驅動程式(10KB)，一共是140KB。
   * 第2次處理：跳到重疊驅動程式，把第2次處理程式碼覆蓋在第1次處理程式碼的區塊上，然後控制權交給第2次處理程式碼，第2次的程式大小也只有130KB。
  ![image](https://user-images.githubusercontent.com/91866985/143770885-aea33984-55ac-4ced-ba99-3882d365aaca.png)  


4. 置換  
* 程序可能會在記憶體與磁碟之間置換(swapping)備份儲存。
![image](https://user-images.githubusercontent.com/91866985/143770900-6cee956c-ab28-4c3f-9f79-428cef970243.png)  
* 可搭配優先順序排班來使用，當較高優先順序程序到來，低優先順序的程序就先置換到磁碟，等高優先順序結束執行，再置換低優先順序程序進來。
* 由於程序在記憶體上進進出出，因此也被稱作「轉進轉出(roll-in-roll-out)」方式。
* 原則上，任一時間點應該都要有一程序在記憶體中被執行。
* 使用洋蔥皮演算法  


## 4-5 檔案系統  
* 指負責存取和管理檔案資料的軟體。
* 對使用者而言，檔案系統應該要具有操作簡單、安全可靠、能夠共享或是保密等特性。
* 對作業系統而言，檔案系統要能管好檔案使用空間，使存取更有效率等。
* 檔案系統中，最重要的兩個部分就是檔案與目錄結構。
* 檔案屬性:
   * 名稱
   * 識別符號
   * 型態
   * 位置
   * 大小
   * 時間日期  
* 檔案的基本操作:  
   *  建立檔案：首先，在磁碟中找到空間存放這個檔案；接著，在目錄中增添一個新的檔案項目。
   *  寫入檔案：做系統呼叫，給予參數設定。在目錄中會儲存指標指到檔案結尾，寫檔時依照指標目前位置把新資料加在後頭，最後儲存最新的指標位置。
   *  讀取檔案：做系統呼叫，指定要讀的檔案及其位置。目錄裡也存放指標指向下次將被讀的位置，若有資料又被讀出，再更新指標位置。
   *  刪除檔案：搜尋目錄找到檔案所在位置，釋放檔案佔用空間，並將登記在目錄裡的檔案項目刪除。  

* 目錄結構的操作功能:  
   *  搜尋：由於檔案有不同的屬性，因此可根據某一屬性特色進行檔案的搜尋。
   *  建檔：當有新檔案被建立時，目錄必須要能夠為其增加一個檔案項目。
   *  刪除檔案：當檔案被刪除時，必須要把該檔案相關的資訊刪除。
   *  更改檔名：當檔案名稱被使用者改變時，目錄結構裡所記載的檔案資訊也必須一起改變。  

*  目錄型態:  
   * 單層目錄
   ![image](https://user-images.githubusercontent.com/91866985/143771031-f0414211-073e-477b-9039-4d254fded74a.png)  

   * 雙層目錄
   ![image](https://user-images.githubusercontent.com/91866985/143771041-6cd35bfc-3125-4d66-99f9-169a37baba87.png)  
   
* 絕對路徑和相對路徑:
   * 絕對路徑: 是指由根部開始，一路指定目錄夾直到該檔案所在的目錄。  
   * 相對路徑: 是由當前目錄去定義要開啟的檔案所在的位置。
![image](https://user-images.githubusercontent.com/91866985/143771082-2edd0067-a004-4a2a-93c9-cbd72a807e4b.png)  


## 4-6 熱門作業系統介紹
(略)  
## 4-7 行動裝置作業系統
(略)  
