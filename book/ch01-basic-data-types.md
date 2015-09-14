<!--
Section tag replaced with div for Gitbook publishing
	<section class="blue" data-type="chapter">-->
<div class="blue" data-type="chapter">
<header>
  <div class="icon"><img src="../images/sections/02/abacus.png" /></div>
  <p>第一章</p>
  <h1 id="basic-data-types">基礎資料型態</h1>
  <p data-type="author">作者: Michael Castello</p>
</header>

<!--<section data-type="sect1">-->
<p>瞭解你能如何處理許多不同型態的資料相當重要，如此你才能為你的需求找到蒐集資料的最佳方式。人們以許多不同的方式來詮釋資料，在這裡我們主要使用四種測量尺度(level of measurement)，包含標稱型(nominal)、序數型(ordinal)、區間型(interval)以及比率型(ratio)。</p>

<h2>測量尺度</h2>

<p>想像你正在雜貨店中購物，一邊穿梭在貨架間，一邊將需要的商品放入購物籃中，裡面已經裝了一些鮮食、乳製品、冷凍食品以及罐頭，這時如果你想列一個清單整理這些商品來自於哪個貨架，這些資料將屬於標稱型。"nominal"這個單字出自於拉丁文中的"nomen"，意思是"關於名稱的"，因此由個別資料以及其所屬的類別名稱所組成的資料，我們稱之為"標稱型資料"。標稱型資料是無序的(unordered)，舉例來說，我們不能將一個產品的分類與奶製品在數學上做大小的比較。</p>

<h3>標稱型</h3>

<p>標稱型資料可數且常用來計算百分比，但不能計算其平均數，就像我們能指出購物籃內的多少商品或多少比例的商品是來自乳製品區，但卻不能計算籃中商品中來自哪個區域的平均值。</p>

<p>當有些資料只能被分為兩類，我們稱它為二元(dichotomous)
。一個只能回答"是"或"否"問題的答案是二元資料，比如我們在購物時，蒐集產品有無特價的資料將屬於一種二元資料。</p>

<figure><img alt="Percent of basket" src="../images/sections/02/ch02-01-percent-basket.png" /></figure>

<h3>序數型</h3>

<p>最後，你準備結帳並想找一排能夠最快速結完帳的隊伍，沒有仔細地計算每一排隊伍有多少等候的顧客，你大略地將隊伍分成短、中、長三種，這種資料除了類別以外還有天生的順序性，我們稱之為序數型資料(ordinal data)。在問券中，會以選項是"非常同意"、"同意"、"中立"、"不同意"、"非常不同意"的問題來蒐集序數型資料，雖然我們常給予這些選項一個對應的數值來方便分析(例如以1代表非常不同意，5表示非常同意)，但這些數值並沒有數學上的意義，而且這樣的賦值方法是武斷的，我們可以使用任何有序的數字來表達這些選項，舉例來說，你也可以用5來代表非常不同意，用1來代表非常同意。</p>

<aside data-type="sidebar">
  <p>選擇不同的數值來代表類別將會影響你如何解讀你的分析結果，但只要保持數值有序，你可以選用任何你想要的集合。</p>

  <p>最常見的賦值方法是以0或1為起始點。</p>
</aside>


<figure><img alt="Scales" src="../images/sections/02/number-order.png" /></figure>

<p>就像標稱型資料，序數型資料可數並可以計算其百分比，但對於序數型資料能否計算百分比仍有不同聲音。反對的一方認為，就算將類別賦值，依然沒有數學上的實質意義，每個數值只是代表一個特定的類別，而沒有計數的功能。</p>

<p>支持的一方認為，如果相鄰類別間的差距近似相等(例如"非常不同意"與"不同意"的差距近似於"不同意"與"中立")，而且使用相鄰的數值來代表這些類別，則可以用平均數來解釋對類別的賦值。</p>

<aside data-type="sidebar">
有些領域非常不鼓勵對序數型資料進行運算，但在有些領域卻是很常見的做法，在使用前務必了解參考你領域中其他人的用法。
</aside>

<h3>區間型</h3>

<p>序數型資料介紹到這邊，讓我們回到商店來，你已經在排隊的隊伍中等待了一會兒，看了看你的手錶，你從11:15開始排隊，而現在已經11:30。一天中的時間屬於區間型資料(interval data)，區間型資料因其相鄰點間的區間相等而得名，以時間為例，每一分鐘為六十秒，11:15至11:30的間隔等於12:00至12:15的間隔。</p>

<p>區間資料是具數值屬性的，你可以對它做數學運算，但它並不具有有意義的"0"，換句話說，數值為0並不代表你所量測的事物不存在，例如0:00並不表示時間不存在，它只是代表一天的開始。其他在生活中常見的例子是紀年與溫度，西元0年並不代表時間在此刻之前不存在，溫度0度(華氏或攝氏)也不代表熱不存在。</p>

<h3>比率型</h3>

<p>時間已經來到11:30，你想著，我已經排了15分鐘的隊了???當你開始這樣想時，你想到的正是比率型資料。比率型資料亦是具數值屬性，除了比率型資料中"0"有意義之外，大致上與區間型資料十分雷同，比率型資料中的"0"表示量測之物不存在，例如0分鐘、0個人排隊、購物籃裡有0件乳製品，上述例子中，"0"確切的表達沒有任何指涉之物的存在，這跟我們先前討論過的區間型資料是不同的，另外，我們常碰到的比率型資料還有身高、體重、年齡、錢等。</p>

<p>區間型資料與比率型資料可以是離散或連續的，離散意思是所測量之物只能有特定數量(通常是整數)，沒有任何可能值介於這些數量間，例如排隊的人數，並不會有1/3個人這樣的數值出現，但你可以計算平均值，意思是我們可以說每行隊伍平均排了4.25個人，但實際人數仍會是一個整數。連續則是表示資料可以是區間內的任何值，你可以買1.25磅的起司或排隊7.75分鐘，請注意這並不表示任何數字都是可能的值，只有特定區間內的數字才能成為可能的值，例如你無法排隊負數分鐘或買負數磅的起司，但這並不影響它的連續性。</p>

<aside data-type="sidebar">
為了表達的方便，我們經常將連續的資料四捨五入(或其他捨入方法)，但這並不影響資料的連續性，資料仍然連續，不是離散。
</aside>

<p>複習一下，在商店的收據上，你能分辨出收據上的資訊是屬於上述的哪一種測量尺度嗎?</p>

<table>
	<tbody>
		<tr>
			<th colspan="5">日期: 06/01/2014 時間: 11:32am</th>
		</tr>
		<tr>
			<th>項目</th>
			<th>區域</th>
			<th>道</th>
			<th>數量</th>
			<th>成本 (US$)</th>
		</tr>
		<tr>
			<td>橘子&mdash;磅</td>
			<td>農產品</td>
			<td>4</td>
			<td>2</td>
			<td>2.58</td>
		</tr>
		<tr>
			<td>蘋果&mdash;磅</td>
			<td>農產品</td>
			<td>4</td>
			<td>1</td>
			<td>1.29</td>
		</tr>
		<tr>
			<td>乾酪&mdash;磅</td>
			<td>乳製品</td>
			<td>7</td>
			<td>1</td>
			<td>3.49</td>
		</tr>
		<tr>
			<td>脫脂牛奶&mdash;加侖</td>
			<td>乳製品</td>
			<td>8</td>
			<td>1</td>
			<td>4.29</td>
		</tr>
		<tr>
			<td>豌豆&mdash;袋</td>
			<td>冷凍食品</td>
			<td>15</td>
			<td>1</td>
			<td>0.99</td>
		</tr>
		<tr>
			<td>四季豆&mdash;袋</td>
			<td>冷凍食品</td>
			<td>15</td>
			<td>3</td>
			<td>1.77</td>
		</tr>
		<tr>
			<td>番茄</td>
			<td>罐頭</td>
			<td>2</td>
			<td>4</td>
			<td>3.92</td>
		</tr>
		<tr>
			<td>馬鈴薯</td>
			<td>罐頭</td>
			<td>3</td>
			<td>2</td>
			<td>2.38</td>
		</tr>
		<tr>
			<td>蘑菇</td>
			<td>罐頭</td>
			<td>2</td>
			<td>5</td>
			<td>2.95</td>
		</tr>
	</tbody>
</table>

<h2>變數類型與資料類型</h2>

<p>如果在網路或書上找尋"資料"的相關資料，經常可以發現變量被描述為上述的一種資料類型，請注意，許多變量並不只只屬於一種類型，反而常因為蒐集資料方法的不同，而屬於不同類型。</p>

<p>以年齡為例，年齡經常被以比率型資料蒐集，但也可以以序數型資料蒐集，例如在問卷中"請問您屬於以下哪個年齡層?"，如此一來，我們就不會有每個受試者的年齡資料，只會知道有多少受試者屬於18-24、25-34或其他年齡層。你可能會為了一個健康研究蒐集參與者確切的膽固醇值，或者只單純的問受試者膽固醇值是否偏高，這樣的一個變量便擁有兩種不同的資料蒐集方式及資料類型。</p>

<p>一個通用的法則是，你可以由含有較多細節的測量尺度轉換為較少細節的測量尺度，反之則不可。在蒐集資料時，你如果可以蒐集區間型或比率型資料，那必定可以蒐集標稱型或序數型資料，但是如果資料天生屬於標稱型資料，就如雜貨店中的區域，它不能被以序數型、區間型或比率型資料蒐集，然而很多被以序數型資料蒐集的變量，都也能以區間型或比率型資料蒐集。</p>

<table>
	<tbody>
		<tr>
			<th>Ordinal Level Type</th>
			<th>Corresponding Interval/Ratio Level Measure</th>
			<th>Example</th>
		</tr>
		<tr>
			<td>Ranking</td>
			<td>Measurement that ranking is based on</td>
			<td>Record runners&rsquo; marathon times instead of what place they finish</td>
		</tr>
		<tr>
			<td>Grouped scale</td>
			<td>Measurement itself</td>
			<td>Record exact age instead of age category</td>
		</tr>
		<tr>
			<td>Substitute scale</td>
			<td>Original measurement the scale was created from</td>
			<td>Record exact test score instead of letter grade</td>
		</tr>
	</tbody>
</table>

<p>這樣的法則也適用於你在分析或視覺化所擁有的資料時使用It&rsquo;s important to remember that the general rule of &ldquo;you can go down, but not up&rdquo; also applies during analysis and visualization of your data. If you collect a variable as ratio data, you can always decide later to group the data for display if that makes sense for your work. If you collect it as a lower level of measurement, you can&rsquo;t go back up later on without collecting more data. For example, if you do decide to collect age as ordinal data, you can&rsquo;t calculate the average age later on and your visualization will be limited to displaying age by groups; you won&rsquo;t have the option to display it as continuous data.</p>

<p>When it doesn&rsquo;t increase the burden of data collection, you should collect the data at the highest level of measurement that you think you might want available later on. There&rsquo;s little as disappointing in data work as going to do a graph or calculation only to realize you didn&rsquo;t collect the data in a way that allows you to generate what you need!</p>

<h2>Other Important Terms</h2>

<p>There are some other terms that are frequently used to talk about types of data. We are choosing not to use them here because there is some disagreement about their meanings, but you should be aware of them and what their possible definitions are in case you encounter them in other resources.</p>

<h3>Categorical Data</h3>

<p>We talked about both nominal and ordinal data above as splitting data into categories. Some texts consider both to be types of categorical data, with nominal being unordered categorical data and ordinal being ordered categorical data. Others only call nominal data categorical, and use the terms &ldquo;nominal data&rdquo; and &ldquo;categorical data&rdquo; interchangeably. These texts just call ordinal data &ldquo;ordinal data&rdquo; and consider it to be a separate group altogether.</p>

<h3>Qualitative and Quantitative Data</h3>

<p>Qualitative data, roughly speaking, refers to non-numeric data, while quantitative data is typically data that is numeric and hence quantifiable. There is some consensus with regard to these terms. Certain data are always considered qualitative, as they require pre-processing or different methods than quantitative data to analyze. Examples are recordings of direct observation or transcripts of interviews. In a similar way, interval and ratio data are always considered to be quantitative, as they are only ever numeric. The disagreement comes in with the nominal and ordinal data types. Some consider them to be qualitative, since their categories are descriptive and not truly numeric. However, since these data can be counted and used to calculate percentages, some consider them to be quantitative, since they are in that way quantifiable.</p>

<p>To avoid confusion, we&rsquo;ll be sticking with the level of measurement terms above throughout the rest of this book, except in our discussion of long-form qualitative data in the survey design chapter. If you come across terms &ldquo;categorical,&rdquo; &ldquo;qualitative data,&rdquo; or &ldquo;quantitative data&rdquo; in other resources or in your work, make sure you know which definition is being used and don&rsquo;t just assume!</p>
</div>
<!--</section>
</section>-->