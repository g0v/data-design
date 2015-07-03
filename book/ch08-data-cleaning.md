<!--
Section tag replaced with div for Gitbook publishing
	<section class="violet" data-type="chapter">-->
<div class="violet" data-type="chapter">
<header>
  <div class="icon"><img src="../images/sections/04/cleaning.png" /></div>
  <p>Chapter 8</p>
  <h1>資料清理Data Cleaning</h1>
  <p data-type="author">By Marit Brademann and Dyanna Gregory</p>
</header>

<!--<section data-type="sect1">-->
<p>現在你手上有一個資料集(dataset)，你準備好清理它了。但這是什麼意思呢？資料清理(data cleaning)具體而言是什麼，我們又要如何進行呢？Now that you have a prepped dataset, you&rsquo;re ready to get it clean. What does that mean though? What exactly are clean data and what do we have to do get them that way?</p>

<p>清理資料時，我們要檢查並辦別出不正確的資訊，像是錯誤的數字或是錯字等，然後決定是否要修正它們(如果它們可以被修正)，或是直接刪除它們。如同資料準備的過程，許多Well, when we clean data, we&rsquo;re going through and identifying incorrect information &mdash; wrong numbers, misspellings, etc. &mdash; and deciding whether to correct them (if they are correctable) or to remove them altogether. Like in data preparation, many <a class="glossterm" target="_blank" href="glossary01.html#cleaning-data">資料清理data cleaning</a> 的任務同時包含電腦計算和人工檢查兩個步驟。人工檢查尤其重要，因為我們需要進一步確認電腦所判斷為可能錯誤的資料是否真的為誤。有些電腦判斷為有問題的資料，可能只是較極端的數據，所以你應該持續參與資料清理的過程，不要讓電腦獨自運作，否則有用的資料可能被刪除！tasks are a combination of computerized tasks and manual work, since it is important for you to review the potential errors the computer identifies to see if they are, in fact, errors. Some of the items your computer flags as problems may turn out to just be extreme observations so it&rsquo;s critical that you remain involved in the process. Don&rsquo;t just automate it all or you risk the possibility of deleting valid data! </p>

<h2>如何清理資料So What Do We Do?</h2>

<p>讓我們從一些最基本的資料清理開始。接下來將用excel為例，但你也可以使用其它的制表軟體或是資料處理軟體來進行以下步驟。常用的程式列在Let&rsquo;s start with some of the most basic data cleaning procedures. We&rsquo;re going to use Excel for many of these these examples, but you can use any spreadsheet or data manipulation software to perform these procedures. A list of programs is available in the <a href="app01.html">附件</a>中.</p>

<h2>範圍檢查Range Checks</h2>

<p><a class="glossterm" target="_blank" href="glossary01.html#check-range">檢查資料範圍(Range checks)</a> 是非常簡單明瞭的步驟，用來檢查數值資料集中的資料是否不超出邊界值，並且在可接受的數值範圍內。以下面的作業成績為例。假想你是一位大學教授，而你的助教輸入了學生們這學期的作業成績。你想要確保成績輸入無誤，因此你打開資料，並把第一個作業的成績(依1-100評分)該欄依大小排列。前幾排顯示如下： are a very straightforward procedure that we use on numeric fields to see if any values in the dataset are above or below the most extreme acceptable values for that variable. Let&rsquo;s use an example of homework scores. Pretend that you&rsquo;re a college professor and your teaching assistants entered the first set of homework scores for the semester. You want to make sure they entered everything correctly, so you go into the dataset and sort by the column that contains the scores for the first homework, graded on a scale of 0-100. You see the first few rows:</p>

<table>
	<tbody>
		<tr>
			<th>學生ID</th>
			<th>作業一成績</th>
		</tr>
		<tr>
			<td>679372531</td>
			<td>980</td>
		</tr>
		<tr>
			<td>673540288</td>
			<td>99</td>
		</tr>
		<tr>
			<td>674082892</td>
			<td>97</td>
		</tr>
		<tr>
			<td>673923590</td>
			<td>96</td>
		</tr>
	</tbody>
</table>

<p>這裡有一個成績顯示為980分，很可能是助教不小心在98分後面誤加了0。你應該標記它並且向你的助教確認正確的成績。There is a score of 980, so one of the TAs probably accidentally typed a zero after a score that should have been 98. You would want to flag the record and ask the TAs what the actual score should have been. </p>

<p>即使所有數值都在正常的範圍內，用檢視的方式進行資料範圍檢查，也可能透露其它可能的問題，。Visual scans of data during range checks can also reveal other potential problems even within the official bounds of the data:</p>


<table>
	<tbody>
		<tr>
			<th>學生ID</th>
			<th>作業一成績</th>
		</tr>
		<tr>
			<td>674472019</td>
			<td>78</td>
		</tr>
		<tr>
			<td>679029425</td>
			<td>75</td>
		</tr>
		<tr>
			<td>671822390</td>
			<td>74</td>
		</tr>
		<tr>
			<td>671278927</td>
			<td>9</td>
		</tr>
	</tbody>
</table>

<p>在這組成績裡，有一個成績特別地低，很有可能原本的成績是90。因此，它應該要被標記起來並檢查資料來源。這是一個很好的例子，說明了人工參與資料清理的過程是非常重要的，尤其是那些權重極高的變項，比如學生的成績或是一個研究計畫的主要變項。但是，人工檢查資料集中的所有變項可能曠時費日，尤其當資料集非常巨大時，而且，並不是所有變項都同樣重要。因此，你必須決定哪個變項需要人工特別檢查，哪些又可以交由電腦處理。Here, one score is much lower than the others. In this situation, it is possible that the score should have been entered as a 90 instead. This is another record that would make sense to flag and check with the source record. This is a good example of why it is important to be personally involved in the data checking process for variables that carry a lot of weight, like student grades or primary outcome variables for research projects. However, hand-checking all the variables in a dataset can be very time-consuming, especially if the dataset is large. Additionally, not all variables are created equal: it is up to you to decide which variables require involved personal attention and which can be checked automatically.</p>

<div data-type="warning"><p>範圍檢查可以在任何範圍內執行， 即使小如0和1之間的小數點。比如華氏體溫，正常人的體溫多數位於97.0與99.0之間，有人偏高，有人偏低。透過範圍檢查 你可以檢查出變項裡的數值是否過低或過高。，  Range checks will work no matter what your range is. Maybe you&rsquo;re expecting a decimal between 0 and 1, or your variable is normal body temperature in Fahrenheit so you&rsquo;re expecting mostly values between 97.0 and 99.0, allowing for people that run cold and hot. You can always look and see if there are values stored in that variable group that are too low or high.</p></div>

<p>你也可以使用「篩選(Filter)」指令來辨認一變項中所有超出正常可接受的數值。但是，該指令無法檢查出相對異常但仍在範圍內的數值。以上述作業成績為例， You can also use &ldquo;Filter&rdquo; commands to check for all values that are outside the acceptable range of a variable. However, this doesn&rsquo;t catch values that are inside your range but that look &ldquo;off&rdquo; based on the rest of your data. Here, a basic range <a class="glossterm" target="_blank" href="glossary01.html#filter ">篩選filter</a> 指令能辨認出980為異常，但無法判斷9為異常。如果你使用篩選進行範圍檢查，你最好同時使用其它方法來對變項進行總體檢查，如此才能過濾出所有可能異常的數值。would detect the &ldquo;980&rdquo; score but not the &ldquo;9&rdquo; score. If you use filtering to do your range checks, it is a good idea to also use another method to look at the overall distribution of your data to catch any values that might seem &ldquo;strange&rdquo; in comparison to your other values.</p>

<h2>錯字檢查Spell Check</h2>

<p>錯字檢查是另一個針對資料集是否有誤的基本檢查。我們建議你一項一項地檢查，而非一次性的檢查整個資料集。因為在一變項中被視為錯誤的寫法，在另一變項中極可能被視為正確。姓氏是個很好的例子，如果你的資料集有一欄為姓氏，電腦很可能警告許多姓氏是錯誤拼法，即便它們正確無誤。如果你一項一項地檢查，你將可以較快地檢查完整個資料集。在資料準備一章學生調查的案例中，學生們填寫了主修科目。假設有一個學生因為熬夜而誤將「數學」填成「樓學」，電腦只針對主修科目這個欄位進行錯字檢查時，將可很快地辨認出錯字，讓你能夠更正為「數學」或是「數學系」，看你選用哪一個字彙。Spell Check is another basic check that you can use to find problems in your dataset. We suggest doing this field-by-field rather than trying to do it across the whole dataset at once. The reason for this is that a word that might be considered a misspelling in one variable could be a valid word for another variable. A good example of this is the first name field. If you have a dataset with a first name field, many of those entries could trigger a spell check alert even though they are legitimate names. If instead you focus on a single field at a time, you can more quickly work through the dataset. In the example from the data preparation chapter where students were listing their major on a survey, say one of the students had just pulled an all-nighter and accidentally typed &ldquo;Mtahmeitcs&rdquo; instead of &ldquo;Mathematics.&rdquo; A spell check on the &ldquo;Major&rdquo; field in your dataset would quickly identify the misspelling and you could change it to &ldquo;Math&rdquo; or &ldquo;Mathematics,&rdquo; depending on which controlled vocabulary term you chose. </p>

<h2>樣式比對/正規表示法 Pattern Matching/Regular Expressions</h2>

<p>另一個較為進階的資料檢查是Another slightly more advanced type of data check involves <a class="glossterm" target="_blank" href="glossary01.html#matching-pattern">樣式比對(pattern matching)</a>。這種檢查法可以用來檢查諸如email地址的欄位。這種方法涉及正規表示法(regular expressions，又作regex)，這是一種表達方式，能讓電腦知道：「在這欄中我只要符合某種特定樣式的資料，所有不符合的都標示出來。」定義樣式的方法依不同程式而有所差異，如果你從未寫過這樣的程式，你可能會覺得它看起來有些複雜。但是如果你曾經在程式中寫過星號「＊」作為檢索的萬用字元，那正是正規表示法，你已經稍微認識它了。This is the sort of check that you can use, for example, to make sure all the entries in a field are an email address. This involves something called regular expressions (often shortened to regex), which give you a way of telling the computer, &ldquo;I only want things that look like {this} to be stored in that variable. Tell me if something in there doesn&rsquo;t look like {this}.&rdquo; The way that you indicate what {this} should be varies from program to program and can look a little complicated if you&rsquo;ve never worked with it before. If you have ever used an asterisk (*) as a wildcard for searching, that&rsquo;s actually part of a regex expression, so you already know a piece of it! </p>

<p>在Excel中也有樣式比對的選項，和一些十分有用的進階篩選功能。參考There are also pattern matching options in Excel and some advanced filter options that sometimes work even better. Check the <a href="app01.html" target="_blank">資源resources section</a> 中關於正規表示法、Excel篩選，以及樣式比對的更多細節。for links to more on regex and Excel filters and pattern matching.</p>

<h2>組合檢查Combination of Fields</h2>

<p>你也可以綜合幾個欄位進行檢查。有時，這樣的檢查是必須的，因為你需要同時檢查數個欄位才能判斷資料是否有誤。如果你有在使用線上銀行，你已經在不知不覺中進行組合檢查了。你的線上銀行會同時顯示許多資料，你必須同時檢視它們才能讀懂，如果它們讓你感到疑惑，你心裡馬上會有警覺。你的線上銀行會同時顯示交易對象、交易金額、使用貨幣、信用卡或debit card刷帳、交易日期和帳戶餘額。這些所有的資料都是這組資料集的一部分。當你登入你的線上銀行並確認所有資料正確無誤時，你正是在進行組合檢查。如果交易金額與你預期的有所不同，或是與餘額不符，你心裡將會有所警覺，並去電銀行查清問題點。You can also use combinations of fields for data checking. This is sometimes actually necessary because you have to look at all the fields together to tell if one or more of the fields are incorrect. If you do any of your banking online, you do this all the time without even realizing it. Your online bank record shows you several different fields that all have to make sense together, and if they don&rsquo;t, red flags immediately go up in your mind. You have the source of the transaction, the amount of the transaction, the unit of currency that it&rsquo;s in, if it&rsquo;s a credit or a debit, the date the transaction occurred and the total balance of your account afterwards. All of these items are part of a dataset, and you&rsquo;re doing a check on that dataset every time you pull up your account online to make sure everything looks okay. If the amount of the transaction was different from what you were expecting or the total of your account after the transaction was off, you would mentally flag it and call the bank to see what was up.</p>

<p>網路銀行和其它的資料集是一樣的，某些資料需要綜合起來檢視。假想你在針對醫院病患進行醫學研究，你追蹤病患每日服用的藥品並記錄三種資料：藥品種類、藥品劑量和劑量單位。舉例來說，資料「阿斯匹靈、500、毫克」代表該病患每日服用阿斯匹靈500毫克。想像你看到一筆資料是「嗎啡、200、磅」，你會有什麼反應？給病患服用嗎啡並不奇怪，而劑量200毫克也還是合理的用藥，因此數字本身並不會讓人疑惑，但是即使是一磅的嗎啡都有可能致死，顯然問題出在單位上。你應該會檢查病患資料，或是尋問輸入資料的人以確認正確的單位。 It&rsquo;s the same with any other dataset. There may be fields that have to make sense together. Imagine that you&rsquo;re working on a medical study of hospital patients and you&rsquo;re tracking the medications they take daily by using three separate fields for medication type, the amount of the quantity of medication being administered, and the unit of the medication. So, for example, if the dataset read, &ldquo;Aspirin, 500, mg&rdquo; that would mean the patient took 500 mg of aspirin each day. Now imagine that you received a record that said, &ldquo;Morphine, 200, lbs.&rdquo; What would your reaction be? It&rsquo;s logical that a hospital patient would be taking morphine and 200mg is a reasonable dosage, so the number alone wouldn&rsquo;t raise flags, but even 1lb of morphine would kill someone so there&rsquo;s definitely a problem there. You would probably want to go back to the patient&rsquo;s record or to whoever entered the data to get the correct units.    </p>

<p>如果你的資料都是自由輸入，你將會得到無限多個組合。這時，你應該盡早檢查你的資料集，並判斷哪些資料可以一起進行組合檢查，那麼你便可以定期地檢查資料是否有誤。此外，因為組合檢查是一個費時的工作，你必須先判斷這個資料組合的準確度有多重要，看是要產生一個準確的視覺圖表，或是進行統計分析，或只是一個初略報告。If any of these fields are free response, there are an infinite number of combinations that you can receive.  As such, you should go through your dataset early and identify groups of variables like this that need to work together so you can check records periodically as they come in for problems. Again, since this can be a time-consuming process, you need to decide how critical the cleanliness of these particular fields is to your  end result, be it a specific visualization, a statistical analysis, or a general report.</p>

<h2>沒有進行資料清理的後果是？What Happens if We Don&rsquo;t Clean Our Data?</h2>

<p>因為許多資料清理的過程非常費時，你經常需要先決定哪些變項值得清理，以及應該使用哪種清理方法。但如果我們跳過資料清理的步驟，讓它仍是「髒資料」，會有什麼後果呢？這個問題很難回答，因為這取決於你的資料集有多「髒」。運氣好的話，你的資料集並不太髒，而你的結果報告所受影響不大。運氣不好的話 你將會因為資料集裡的錯誤沒有透過資料清理而被修正而得到錯誤的結果。As many of these cleaning procedures can be time-intensive, you will often have to decide which variables are worth cleaning, and which procedures you can justify using. But what if we just skip the data cleaning process altogether and leave the data &ldquo;dirty&rdquo;? The answer to that isn&rsquo;t easy because it all depends how dirty your data are in the first place. At best, you&rsquo;ll get lucky and your data will be minimally dirty and you won&rsquo;t have any real impact on your end report. At worst, your results will be incorrect due to errors in your dataset that you could have potentially corrected if you had gone through data cleaning procedures.</p>

<p>Of course, your data may be in relatively good shape to begin with. If that&rsquo;s the case, you might be able to ignore the cleaning process with little impact on your end product. However, until you at least go through the basic checks involved in data cleaning, there&rsquo;s no real way for you to know how clean or dirty your data are. That said...</p>

<h2>Accept That Most Datasets are Never 100% Clean</h2>

<p>Data cleaning is just like house cleaning&mdash;you won&rsquo;t ever catch everything. As hard as you may try, you can&rsquo;t force people to input 100% correct data, and we make errors ourselves as we work with data. You want your data to be as accurate as possible, but there will always be a little dust in the corners so it&rsquo;s important to accept that datasets are never perfect and to develop a sense for what is &ldquo;good enough&rdquo; for your purposes.</p>

<p>For example, you have a list of 1,000 contacts from your database of 100,000 contacts and you notice that 2 of the 1,000 have the first and last names together in one field. Do you take on a project of combing through and correcting all 100,000 records?</p>

<p>It depends.</p>

<p>You may make a formal decision that the data are either clean enough for your purposes or too dirty for what you want to accomplish. This really depends on the variable in question and what your intended end output is. If you&rsquo;re responsible for checking that students correctly reported their majors for an internal report and you think that there was a 0.01% error rate, that&rsquo;s probably of a much lower concern than if you&rsquo;re checking a variable that is of critical importance to a safety report and you think there&rsquo;s a possibility of a 5% error rate. Over time, you&rsquo;ll get a better sense of how clean or dirty a dataset is, relatively speaking, and how labor-intensive the cleaning process will be for a particular group of variables. At that point, it&rsquo;s good to consult the key stakeholders for the end product to see how much cleaning they agree is sensible to pursue. You should always aim to have your data as clean as possible but always remember that it won&rsquo;t be 100% perfect.</p>

<p>Data preparation and cleaning have costs. If you hire someone to do this work for you, the cost is financial. If you&rsquo;re going to do it yourself, it costs you or someone on your team time (and maybe a little sanity). So if you&rsquo;ll never use a phone or fax number or need to refer to someone as Reverend, you may make the decision to delete those variables, stop collecting them, or just not worry about cleaning them in the future.</p>

<h2>After Data Cleaning: Please Be Kind and Document!</h2>

<p>Once we&rsquo;ve cleaned our data, we&rsquo;re left with a brand new problem: how can we (and others!) verify that what we&rsquo;ve done is correct and that we haven&rsquo;t corrupted the data by making these changes? After all, the processed data may look vastly different from the raw data we started out with.</p>

<p>The simple answer is to document everything, particularly if you think you might want to share your data later on with a statistician or other researchers. When you&rsquo;re cleaning your data, it&rsquo;s always a good idea to save any changes as an entirely separate file: this way you&rsquo;re always able to go back and look at what changed between the raw and processed data, what rows and columns were dropped, etc. It also ensures that you can go back to the unprocessed data if you ever want to slice things up a different way that might involve different cleaning procedures.</p>

<p>You should be careful to write a set of instructions as you go, documenting exactly what was done in each step to identify bad data and which data points were removed. It&rsquo;s crucial to write this while you&rsquo;re actually cleaning your data: it&rsquo;s always easier to document as you go than it is to try and remember every step that you took after all is said and done. If you&rsquo;re using point-and-click software to manage your data (like Excel), you should take special care to record exactly what steps were taken in cleaning the data since everything is done by hand, rather than by computer code that can be easily re-run later on. A good rule of thumb is that if you aren&rsquo;t able to easily follow the instructions you wrote and end up with the same results a second time, you shouldn&rsquo;t expect anyone else to be able to.</p>

<p>Regardless of how you choose to do it, good documentation of your cleaning procedures ensures that you can always justify why certain data points were removed and others weren&rsquo;t and that others are able to verify that the data were cleaned competently and correctly. Additionally, if you think you might want to share the data with a statistician later on for further analysis, being able to see both the raw data and what operations were done on those data will make the statistician&rsquo;s job much easier and quicker.</p>
</div>
<!--</section>
</section>-->
