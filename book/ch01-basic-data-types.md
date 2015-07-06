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
Some fields strongly discourage the use of ordinal data to do calculations like this, while others consider it common practice. You should look at other work in your field to see what usual procedures are.
</aside>

<h3>Interval</h3>

<p>Enough ordinal data for the moment&hellip; back to the store! You&rsquo;ve been waiting in line for what seems like a while now, and you check your watch for the time. You got in line at 11:15am and it&rsquo;s now 11:30. Time of day falls into the class of data called interval data, so named because the interval between each consecutive point of measurement is equal to every other. Because every minute is sixty seconds, the difference between 11:15 and 11:30 has the exact same value as the difference between 12:00 and 12:15.</p>

<p>Interval data is numeric and you can do mathematical operations on it, but it doesn&rsquo;t have a &ldquo;meaningful&rdquo; zero point &ndash; that is, the value of zero doesn&rsquo;t indicate the absence of the thing you&rsquo;re measuring. 0:00 am isn&rsquo;t the absence of time, it just means it&rsquo;s the start of a new day. Other interval data that you encounter in everyday life are calendar years and temperature. A value of zero for years doesn&rsquo;t mean that time didn&rsquo;t exist before that, and a temperature of zero (when measured in C or F) doesn&rsquo;t mean there&rsquo;s no heat.</p>

<h3>Ratio</h3>

<p>Seeing that the time is 11:30, you think to yourself, &ldquo;I&rsquo;ve been in line for fifteen minutes already&hellip;???&rdquo; When you start thinking about the time this way, it&rsquo;s considered ratio data. Ratio data is numeric and a lot like interval data, except it <em>does</em> have a meaningful zero point. In ratio data, a value of zero indicates an absence of whatever you&rsquo;re measuring&mdash;zero minutes, zero people in line, zero dairy products in your basket. In all these cases, zero actually means you don&rsquo;t have any of that thing, which differs from the data we discussed in the interval section. Some other frequently encountered variables that are often recorded as ratio data are height, weight, age, and money.</p>

<p>Interval and ratio data can be either discrete or continuous. Discrete means that you can only have specific amounts of the thing you are measuring (typically integers) and no values in between those amounts. There have to be a whole number of people in line; there can&rsquo;t be a third of a person. You can have an <em>average</em> of, say, 4.25 people per line, but the actual count of people has to be a whole number. Continuous means that the data can be any value along the scale. You can buy 1.25 lbs of cheese or be in line for 7.75 minutes. This doesn&rsquo;t mean that the data have to be able to take all possible numerical values &ndash; only all the values within the bounds of the scale. You can&rsquo;t be in line for a negative amount of time and you can&rsquo;t buy negative lbs of cheese, but these are still continuous.</p>

<aside data-type="sidebar">
For simplicity in presentation, we often round continuous data to a certain number of digits. These data are still continuous, not discrete.
</aside>

<p>To review, let&rsquo;s take a look at a receipt from the store. Can you identify which pieces of information are measured at each level (nominal, ordinal, interval, and ratio)?</p>

<table>
	<tbody>
		<tr>
			<th colspan="5">Date: 06/01/2014 Time: 11:32am</th>
		</tr>
		<tr>
			<th>Item</th>
			<th>Section</th>
			<th>Aisle</th>
			<th>Quantity</th>
			<th>Cost (US$)</th>
		</tr>
		<tr>
			<td>Oranges&mdash;Lbs</td>
			<td>Produce</td>
			<td>4</td>
			<td>2</td>
			<td>2.58</td>
		</tr>
		<tr>
			<td>Apples&mdash;Lbs</td>
			<td>Produce</td>
			<td>4</td>
			<td>1</td>
			<td>1.29</td>
		</tr>
		<tr>
			<td>Mozzarella&mdash;Lbs</td>
			<td>Dairy</td>
			<td>7</td>
			<td>1</td>
			<td>3.49</td>
		</tr>
		<tr>
			<td>Milk&mdash;Skim&mdash;Gallon</td>
			<td>Dairy</td>
			<td>8</td>
			<td>1</td>
			<td>4.29</td>
		</tr>
		<tr>
			<td>Peas&mdash;Bag</td>
			<td>Frozen</td>
			<td>15</td>
			<td>1</td>
			<td>0.99</td>
		</tr>
		<tr>
			<td>Green Beans&mdash;Bag</td>
			<td>Frozen</td>
			<td>15</td>
			<td>3</td>
			<td>1.77</td>
		</tr>
		<tr>
			<td>Tomatoes</td>
			<td>Canned</td>
			<td>2</td>
			<td>4</td>
			<td>3.92</td>
		</tr>
		<tr>
			<td>Potatoes</td>
			<td>Canned</td>
			<td>3</td>
			<td>2</td>
			<td>2.38</td>
		</tr>
		<tr>
			<td>Mushrooms</td>
			<td>Canned</td>
			<td>2</td>
			<td>5</td>
			<td>2.95</td>
		</tr>
	</tbody>
</table>

<h2>Variable Type Vs. Data Type</h2>

<p>If you look around the internet or in textbooks for info about data, you&rsquo;ll often find variables described as being one of the data types listed above. Be aware that many variables aren&rsquo;t exclusively one data type or another. What often determines the data type is how the data are collected.</p>

<p>Consider the variable age. Age is frequently collected as ratio data, but can also be collected as ordinal data. This happens on surveys when they ask, &ldquo;What age group do you fall in?&rdquo; There, you wouldn&rsquo;t have data on your respondent&rsquo;s individual ages &ndash; you&rsquo;d only know how many were between 18-24, 25-34, etc. You might collect actual cholesterol measurements from participants for a health study, or you may simply ask if their cholesterol is high. Again, this is a single variable with two different data collection methods and two different data types.</p>

<p>The general rule is that you can go down in level of measurement but not up. If it&rsquo;s possible to collect the variable as interval or ratio data, you can also collect it as nominal or ordinal data, but if the variable is inherently only nominal in nature, like grocery store section, you can&rsquo;t capture it as ordinal, interval or ratio data. Variables that are naturally ordinal can&rsquo;t be captured as interval or ratio data, but can be captured as nominal. However, many variables that get captured as ordinal have a similar variable that can be captured as interval or ratio data, if you so choose.</p>

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

<p>It&rsquo;s important to remember that the general rule of &ldquo;you can go down, but not up&rdquo; also applies during analysis and visualization of your data. If you collect a variable as ratio data, you can always decide later to group the data for display if that makes sense for your work. If you collect it as a lower level of measurement, you can&rsquo;t go back up later on without collecting more data. For example, if you do decide to collect age as ordinal data, you can&rsquo;t calculate the average age later on and your visualization will be limited to displaying age by groups; you won&rsquo;t have the option to display it as continuous data.</p>

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