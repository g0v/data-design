<!--
Section tag replaced with div for Gitbook publishing
	<section class="red" data-type="chapter">-->
<div class="red" data-type="chapter">
<header>
  <div class="icon"><img src="../images/sections/04/inspect.png" /></div>
  <p>第九章</p>
  <h1>資料檢查的類型</h1>
  <p data-type="author">By Ian Tebbutt</p>
</header>

<!--<section data-type="sect1">-->
<p>在上一章，我們討論了資料清理和它所需要的步驟。在這一章，我們將會更深入討論資料檢查，與其它進行資料清理前後的驗證過程。</p>

<p>要對資料傳達的訊息產生信心，資料檢查是非常重要的過程。基本的資料清理步驟非常直接：假設你手上有很多筆資料，那麼每個欄位都應該有相對應合理的數值。舉例來說，年齡應該在0到120歲之間(而且多數人在80歲以內)；交易日期應該要在近期，通常在過去一兩年內，特別是當你處理的是網路(比方Twitter)所產生的資料。</p>

<p>無論如何，資料檢查雖然容易理解且十分重要，卻是個複雜的工作，因為資料產生錯誤的方式非常多種，資料也可能以預期外的格式呈現。</p>

<h2>資料檢查的時機When to Check</h2>

<p>舉例來說，有一個關於某電信公司顧客變更電話號碼的資料集。該公司從上百家小型的手機服務業者匯集這些資料，卻沒有對它做進一步的檢查，但是這個資料集仍然每日被使用著。這是個資料檢查的典型案例，假設你要追蹤不同年齡使用者的電話費，下面的例子呈現了這個資料的一些問題：</p>

<ul>
  <li>電話類別一欄混合了代碼和文字</li>
  <li>年齡欄中，0代表年齡未知，但會造成計算平均年齡的誤差；此外，112是正確的年齡嗎？</li>
</ul>

<table>
	<tbody>
		<tr>
			<th>記錄編號</th>
			<th>電話類別</th>
			<th>年齡</th>
			<th>新客戶</th>
			<th>價格</th>
		</tr>
		<tr>
			<td>1</td>
			<td>MOBILE</td>
			<td>0</td>
			<td>NO</td>
			<td>$12.45</td>
		</tr>
		<tr>
			<td>2</td>
			<td>Mobile</td>
			<td>47</td>
			<td>Y</td>
			<td>12 45</td>
		</tr>
		<tr>
			<td>3</td>
			<td>Land Line</td>
			<td>34</td>
			<td>YES</td>
			<td>37</td>
		</tr>
		<tr>
			<td>4</td>
			<td>LandLine</td>
			<td>23</td>
			<td>YES</td>
			<td>1.00</td>
		</tr>
		<tr>
			<td>5</td>
			<td>LL</td>
			<td>112</td>
			<td>Y</td>
			<td>$1K</td>
		</tr>
	</tbody>
</table>

<p>資料檢查最基本的原則是即早檢查、經常檢查。即早檢查指當資料最初被輸入時，就立即修正它們。例如，如果新客戶一欄應輸入Yes或No，但卻被鍵入其它資料，像是A或是空白鍵，那麼應即時提醒使用戶修正資料。如果沒有及早驗證，錯誤的資料可能會進到資料庫，即使你發現錯誤，在沒有向使用者確認正確資訊前也難以修正。有時候，你可以透過比對其它資料庫裡的相同欄位尋找對的資料來修正原始資料。但這是個 複雜的過程，也容易導致其它問題，因為你必須判斷另一個資料庫裡的資料是正確的。</p>

<p>如果你能夠順利地控制資料收集的過程，那將會帶給你極大的好處，因為資料檢查最容易的方法便是在資料輸入時立即檢查。這種類型的資料檢查又稱作「前端檢查」或是「客戶端檢查」，因為它發生在使用者正在輸入資料，而資料還未進入到資料庫時。最常見的方式，是將收集資料的程式或網頁設計成只接受有效的資料格式。你以往在網路上填寫表格時，應該已經遇過這類型的資料檢查。</p>

<figure><img alt="Form validation on the web" src="../images/sections/04/drop-phone.png" /></figure>

<p>例如，國家和州應該從建立的列表中選取。如果你處理的是國際性的資料，那麼州的選項應該跟著所選國家而改變。</p>

<figure><img alt="Country and state drop down lists" src="../images/sections/04/drop-states.png" /></figure>

<p>這樣一來，你的系統只允許對的資料格式被輸入。不過，這個方法並非完美。網路速度受阻的典型狀況，即是因為填入的資料直到最後提交時，才檢查出最初的輸入有誤。比較好的方法是在每筆輸入時都做檢查，但這個方法的缺點是程式比較難寫，並且會導致檢查指令連續不斷地送到伺服器端，同時資料有誤的警訊則不斷回送到使用者端。折衝的方法是，在流覽器一端先進行簡單的資料檢查和驗證，把比較複雜的部分留給伺服器端檢查。某些資料的檢查只能在伺服器端進行，最常見的像是安全性檢查，例如信用卡驗證。</p>

<p>為了縮短資料準備的時間，其它好的調查表格設計有：</p>

<ul>
	<li>	先決定好你希望姓名如何被輸入。例如，使用者是否可以在姓名後加上小(Jr)、獸醫師(DVM)、博士(PhD)、會計師(CPA)等稱謂，或你希望稱謂與姓名分開輸入。如果是後者，你是否希望職業別的稱位與姓名後綴，像是小、二世、三世分開輸入？還有，你是否希望姓與名輸入在不同欄位？
	</li>
	<li>
將電話與日期的欄位設定成只能以你指定的方式儲存(本章稍後會對日期的部分詳述)。決定你是否要收集辦公室電話的分機號碼，如果要，幫分機另外設一個欄位。
	</li>
</ul>

<h2>不要相信任何人</h2>

<p>不管你的表格設計得多完美，也不論你在前端用了多少驗證的程序，經驗告訴我們絕對不要相信使用者輸入的資料。如果資料是由人所輸入的，那麼就有可能發生錯誤。即使已經有做使用者端檢查，也一定要在資料送出後進行伺服器端或<a class="glossterm" target="_blank" href="glossary01.html#check-back-end">後端檢查back-end checks</a>。這樣做有很多好的理由。比方說，如果你並沒有設計資料收集的工具，而你的資料來自不同的前端程式，有些有進行完善的用戶端檢查，有些則無，因此一些不乾淨或沒檢查的資料，就在整合這些資料集時進入你的系統。本章之初所舉的電信公司的例子，就是因為擁有太多的資料提供者，彼此因疏忽而產生紊亂的資料集。只要在前端多付一些心力，將能節省我們的時間，減輕我們清理資料時的挫折，並且提供我們較乾淨的資料集。</p>

<p>第二個黃金定律是，非到必要時，不設計文字輸入的欄位。舉例來說，某些國家習慣將地址資料分成數個欄位，例如第一行、第二行、城市、州、國家、郵遞區號。但在英國收集地址時，通常只需輸入郵遞區號以及門牌號碼，透過這兩個資料便可以查到正確的地址。用這個方法，不但郵遞區號可以被自動驗證，而且地址資料因為不是使用者以文字輸入，也能確保它的正確性。但在其它國家，我們仍需使用文字欄位，連帶地也產生許多檢查的手續。</p>

<p>資料中的逗號會產生許多問題，因為許多資料格式是用逗號來區別不同的欄位(即CSV逗號分隔值)，一個額外的逗號會產生多出來的欄位，導致原有欄位的資料被向右移。為此，最好不要直接從程式中剪貼資料，而是另存檔案，然後用另一個程式來讀取這個檔案。</p>

<table>
	<tbody>
		<tr>
			<th>稱號</th>
			<th>名字</th>
			<th>姓氏</th>
			<th>地址第一行</th>
			<th>地址第二行</th>
			<th>城市</th>
			<th>州</th>
			<th>國家</th>
			<th>&nbsp;</th>
		</tr>
		<tr>
			<td>Bill</td>
			<td>Short</td>
			<td>&nbsp;</td>
			<td>13</td>
			<td>A The Street</td>
			<td>Hastings</td>
			<td>VIC</td>
			<td>AUS</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>Mr</td>
			<td>William</td>
			<td>Tall</td>
			<td>27 The Close</td>
			<td>&nbsp;</td>
			<td>Guildford</td>
			<td>VIC</td>
			<td>AUS</td>
		</tr>
	</tbody>
</table>

<p>上列第二筆資料，因為多了一個逗號，使得資料往右邊移了一欄。這個錯誤雖然容易用人眼辨視出來，但是對於自動化的系統卻十分困難。一個好的檢查方法是人工查看是否有資料超出了最後一個欄位。這個例子也強調結合電腦和人工檢查資料的重要性。有時，快速地用眼睛掃描過資料，能夠讓結果大為不同。</p>

<h2>資料格式和檢查</h2>

<p>處理數字資料時，你應該注意幾個問題。這些數字是否合理？如果你處理的是金錢，一筆$1,000,000是正確的價格嗎？或是有人輸入了錯誤的數字？同樣的，如果價錢是0或是負數，是否代表這個產品是被贈送出去的，或是有人付錢來移除它？此外，為了在會計上平衡收支，許多價格資料會用負數表示。</p>

<p>除此之外，檢查出數字資料中的空白和字母也很有幫助。不過，貨幣以及負數可能會讓操作變得困難。如下例所示，這些是各種表示貨幣的有效方式，裡面包含了非數字的符號。</p>

<div data-type="example">
<p>$-1,123.45<br />
(1123.45)<br />
-US$1123.45<br />
-112345E-02</p>
</div>

<p>數字中帶有字母並不一定有誤，同時，負數也有不同格式。</p>

<p>日期的呈現也有許多值得檢查的問題。第一個問題是國際間存在著不同的日期格式。如果日期顯示為1/12/2013，在美國代表2013年1月12日，但在英國則是12月1日。幸運的話，你可能會取得國際通用的格式，顯示為2014-01-12，這種標準化格式的額外好處是，即使它儲存為文字，依然能夠被排序
(<a href="http://whatis.techtarget.com/definition/ISO-date-format">http://whatis.techtarget.com/definition/ISO-date-format</a>)。無論如何，你可能沒那麼幸運，因此檢查並確保你知道日期是用什麼格式是非常重要的，尤其是當你的資料輸入者來自於不同國家且使用不同格式時。如果你在設計資料輸入的表單，一個解決日期格式的好方法，是設置月曆讓使用者從中選取日期，而非手動輸入。或者，你也可以在表格旁，指明你要的日期格式給使用者參考。</p>

<figure><img alt="Examples of input fields" src="../images/sections/04/birthdate.png" /></figure>

<p>另一個可能遇到資料檢查的情況，是在分析並驗證他人的資料，以確認該視覺圖表和數據的正確性時。這有可能發生在工作上，當你需要證明其它人的分析結果，或是在線上看到公開的圖表，且附有原始資料讓你可以試著進行自己的分析。在這兩種狀況下，第一步可以先快速檢查每個數據的總和。接著，再以批判的眼光檢查視覺圖表，比如，這個圖表是否能支持原本的論證，或是與之相抵觸。除了需要將錯誤檢查出來，還必須判斷視覺圖表是否能有效地幫助理解。檢查他人的資料不但能夠增加你資料檢查的經驗，同時也是查看他人分析報告時必須先進行的工作。</p>

<h2>資料版本Data Versions</h2>

<p>另一個資料檢查過程中會遭遇的問題來自資料版本。</p>

<p>當程式和系統隨時間變化，資料欄位會增加、移除、甚至連資料收集的目的都會產生改變。舉例來說，澳洲的郵遞區號是四碼，以四個字元來儲存，但是其它系統已經改用更準確的五位元SLA地區代碼。當這些來自不同系統的資料整合在一起時，五位元的SLA經常被刪減以符合四位元的郵遞區號。要檢查出這種資料變化並不容易，雖然郵遞區號和SLA地區代碼都有公開對照表，但是，要判斷為什麼有些四位元的地區資料無法符合兩種代碼，需要費一番精力。</p>

<p>某些資料欄位與你的視覺圖表或最終報告雖無直接關係，卻能提供你關於資料收集的重要訊息，你也應該考慮收集這些資料，比方說這些資料是何時被建立的。如果在資料集被建立後，才增加新的欄位，原有的資料在這個新欄位應是空白的。這時，如果有人沒有妥善地處理資料，並把空白欄位以0取代，這將會拉低該欄的平均值，並嚴重影響你的圖表。此時如果你有資料建立的日期，你將可以查出誤輸為0的欄位，改正為「缺失資料」(missing data)，以此來修正資料集。同樣的問題也可能發生在當部分資料被刪除時。刪除的情形相對少見，不過有時資料會因時間推移而改變其收集目的，如果目的改變了，理解該資料將會極具挑戰性。</p>

<table>
	<tbody>
		<tr>
			<th>金額</th>
			<th>付款方式</th>
			<th>伺服器ID</th>
			<th>建立日期</th>
		</tr>
		<tr>
			<td>$100</td>
			<td>CC</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>$143</td>
			<td>Cash</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>$27</td>
			<td>Amex</td>
			<td>237</td>
			<td>3/1/2013</td>
		</tr>
		<tr>
			<td>$45</td>
			<td>Cash</td>
			<td>467</td>
			<td>3/1/2013</td>
		</tr>
	</tbody>
</table>

<p>以上表格呈現了原有資料加入兩個新的欄位&mdash;伺服器ID和建立日期&mdash;後的樣子。新欄位很有可能是在2013年3月1日建立的，因此，如果你的分析僅限於該日以後的資料，那麼你可以從這個資料集追蹤銷售點或伺服器。但是，這個資料集沒有該日以前的伺服器ID，所以如果你想要看2013年1月1日的資料，你就必須從其它地方找尋資料。</p>

<p>資料檢查另一個重要的問題，是資料欄位與其數值的意義可能因為時間而改變。在最完美的狀況下，資料所有的改變都被詳實地記錄下來，因此你會正確地知道每一筆資料的意義。但現實的情形是資料的改變很少被完整記錄。因此，另一個理解資料真正意義的好方法，是向處理資料的行政人員以及操作系統的使用者請教。</p>

<p>以上僅是一些讓你能夠清楚了解你的資料，並且意識到可能的錯誤的步驟。在下一章，我們將討論其它混淆資料的隱藏性錯誤，和判斷這些潛在問題的方法。</p> 
</div>
<!--</section>
</section>-->
