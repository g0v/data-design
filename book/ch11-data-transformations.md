<!--
Section tag replaced with div for Gitbook publishing
	<section class="yellow" data-type="chapter">-->
<div class="yellow" data-type="chapter">
<header>
  <div class="icon"><img src="../images/sections/04/camera.png" /></div>
  <p>Chapter 11</p>
  <h1>Data Transformations 資料轉換</h1>
  <p data-type="author">By Kiran PV</p>
</header>

<!--<section data-type="sect1">-->
<div data-type="warning">
   <p>This chapter covers more advanced statistical concepts than some of the others but we wanted to include a brief introduction to data transformations in case you encounter them. If you need to do your own transformation, check out the resources in our <a href="app01.html">Appendix</a> for additional tips.</p>

    <p>相較於其他章節而言，本章節涵蓋較多進階統計概念，但我們想將資料轉換的簡介納入待用。若您需實做資料轉換，可參閱 <a href="app01.html">附錄</a>，有更多的資源及指點。</p>
</div>

<p>When you take a digital photo, sometimes the picture comes out in a way that makes certain features hard to see. Maybe the colors are too dark or too light, the photo is blurry, or the objects in the image are too small and you want to zoom in on them. You can pop the photo into something like Instagram or Photoshop, tweak it, apply a filter or two, and transform the picture so it&rsquo;s much clearer and easier to understand.</p>

<p>有時，以數位相機拍下相片之後，才會發現相片中的某些重點難以辨識。也許是因為色調過暗或過亮、成像模糊、主題物品太小必需放大，諸如此類。為了讓相片主旨更加達意，一般常見的方式是把相片載到 Instagram 或 Photoshop 之中加以調整、加上一兩層濾鏡，或是裁切修改等等。</p>

<p>Sometimes we need to transform data, too. You might get a set of data where, if you visualize it as is, there will be parts that are difficult to see. Also, if you&rsquo;re going to do statistical testing of your data, many common tests make specific assumptions about the distribution of the data (e.g. that the data are normally distributed). In the real world, we often come across data that don&rsquo;t meet these assumptions. Data transformations are one way to handle both of these problems. Here, we&rsquo;ll talk about some of the more common transformations so that when you encounter these terms in the future you&rsquo;ll have an idea what was done to the data.</p>

<p>資料的轉換也其實偶有需求。你可能從某處取得某些資料集，在視覺化處理之後，依然會有有難以呈現的部份。若要對資料集進行統計測試，更有許多測試方法只能適用於其假定的分佈（像是常態分佈）。在真實世界中，我們取得的資料集，經常無法對上這些假定條件。資料轉換，則可以用來對付前述兩類問題。在本篇章中，為了讓你在未來與到這些問題時稍有概念，我們會盡量談及常被使用的轉換方法。</p>

<p><a class="glossterm" href="glossary01.html#transformation-data" target="_blank">Data transformations</a> are one of the common manipulation procedures which can reveal features hidden in the data that are not observable in their original form. We can transform the distribution of data to make it easier to see and so that any required assumptions of statistical tests are met. We usually do this by replacing one variable with a mathematical function operating on that variable. For example, you could replace a variable <em>x</em> by the logarithm of <em>x</em> or by square root of <em>x</em>.</p>

<p>在資料集中，無法直接觀察得知的重點，透過 <a class="glossterm" href="glossary01.html#transformation-data" target="_blank">資料轉換</a> 這種手段， 操弄之後，便能將資料集中所隱藏的重點彰顯出來。我們亦可以調整資料分佈，使其較容易被觀察，或使其能滿足統計測試所需的前提。一般的作法，是將其中某項變數代換為該變數的一元函數。比方說，將變數 <em>x</em> 換為其對數，或是取其平方。</p>

<div data-type="warning">
<p>Never perform the transform directly on your original data! Either create an additional column to hold the new values for each variable you&rsquo;re transforming or make a copy of your entire dataset.</p>
</div>

<div data-type="warning">
    </p>注意！進行轉換時，切勿直接修改原始資料。務必將原資料集另行備份，或是增加新欄位來存放變數轉換之後的結果，不要直接更改原始變數。</p>
</div>

<h2>常態分佈與資料的傾斜度 Normal Distribution and Skewness in Data</h2>

<p>One of the most frequently-encountered assumptions of statistical tests is that data should be <a class="glossterm" href="glossary01.html#distribution-normal" target="_blank">normally distributed</a>. You may have heard of the normal distribution referred to as a &ldquo;bell curve&rdquo; before; this is because a normal distribution takes the shape of a bell, with the data spread around a central value. Some of the data examples that commonly follow a normal distribution are related to human measurements such as height, weight, life span, and scores on IQ tests.</p>

<p>
在統計測試中最為常見的前提，便是資料應為 <a class="glossterm" href="glossary01.html#distribution-normal" target="_blank">常態分佈</a>。您可能看過「鐘形曲線」這名詞被用來代稱常態分佈，那是因為常態分佈確實畫出來像個鐘，資料的值集中在中間。人的身高、體重、壽命、智力測驗分數等等，這類測量資料，一般都認為是常態分佈。
</p>

<p>Unlike a normal distribution, which is symmetric around the mean value, <a class="glossterm" href="glossary01.html#data-skewed" target="_blank">skewed data</a> tend to have more observations either to left side or to right side. Right skewed data have a long tail that extends to right whereas left skewed data will have a long tail extending to the left of the mean value. When data are <i>very</i> skewed, it can be hard to see the extreme values in a visualization. If you notice that your data distribution is skewed, you might consider transforming it if you&rsquo;re doing statistical testing or if the data are difficult to visualize in their original state.</p>

<p>
常態分佈，是以其平均值為中心，呈現對稱的形狀，相對而言，<a class="glossterm" href="glossary01.html#data-skewed" target="_blank">偏斜的資料</a> 則會在一側得到較多的觀測資料。向右偏斜的資料集，會有長尾向右方有延伸，而向左斜的資料集的長尾則是向左方延伸。當資料非常偏斜之時，就算透過視覺化呈現，也很難看出其極端的值為何。若你需要進統計測試、或視覺化的工作，在注意到手邊的資料分佈有點偏斜之後，可考慮進行轉換。
</p>

<h3>常態分佈 Normal Distribution</h3>

<figure><img alt="Normal distribution" src="../images/sections/04/normal-distribution.png" /></figure>

<h3>左偏斜 Left Skew</h3>

<figure><img alt="Left skew" src="../images/sections/04/left-skew.png" /></figure>

<h3>右偏斜 Right Skew</h3>

<figure><img alt="Normal distribution" src="../images/sections/04/right-skew.png" /></figure>

<h2>以抽樣來了解轉換效果 Understanding Transformations Using Sample Data</h2>

<p>Let&rsquo;s use the population and land area of the 50 US states from 2012 to see how transformations work on actual data. The first step in transformation is to evaluate the distribution of the data. Then you can decide what transformation is appropriate (if one is needed). We can start by constructing a histogram of the population data and a scatterplot of the population-area data to get a better sense of how they&rsquo;re distributed.</p>

<p>
接下來我們使用美國五十州的人口與土地的真實資料做為範例，來進行資料轉換吧。首先，是評估一下資料的分佈，如此方能推知轉換是否合適（或必要）。為了更進一步了解資料的分佈，我們可以先建立人口資料的直方圖，與人口面積資料的散布圖。
</p>

<figure><img alt="Untransformed population values" src="../images/sections/04/untransformed-population-values.png" /></figure>

<p>The histogram above shows that the distribution of population values is right skewed. This is reasonable to expect because the majority of states&rsquo; populations lie in the range of 1-10 million. If we want to do statistical testing that relies on a normal distribution assumption, these data will need to be transformed.</p>

<p>上面這張直方圖，顯示人口數目的分佈向右偏斜。這算是合理，因為多數州的人口總數都落在一到一千萬之間。若我們想對此資料進行的統計測試，有要求資料集應為常態分佈的話，那這項資料進就必須先經過轉換。</p>

<figure><img alt="Population scatter plot" src="../images/sections/04/population-scatter.png" /></figure>

<p>In the scatter plot above, you can see that most of the data points are clustered in the bottom left corner of the graph, making it hard to see how population and land area are related. We can&rsquo;t just scale the graph differently to &ldquo;zoom in&rdquo; on that corner because we&rsquo;d knock California and Alaska off the chart. We can, however, use transformations to help make the data easier to view.</p>

<p>
在這張散布圖當中，明顯可見到多數的資料點都聚集在圖的左下角，人口數與土地之間的關聯性，也因此較難以觀察得知。雖然可以對左下角做局部縮放，但那麼做的話，加州及阿拉斯加，就會超出圖表的範圍了。不過，為了讓資料觀察較為容易，我們可以進行資料轉換。
</p>

<p>There are many transformation methods that can be applied in either of these situations, but let&rsquo;s look at a couple of the common ones to see how they can affect both a visualization and the shape of a distribution.</p>

<p>有很多資料轉換的方法能對付這類情況，但現在我們就針對幾個常見的方法，看看它們對視覺呈現及資料分佈的形狀有何影響。</p>

<h3>對數轉換 Log Transform</h3>

<p>To do a <a class="glossterm" href="glossary01.html#transformation-log" target="_blank">logarithmic transformation</a>, you calculate the log of each value in the dataset and use those transformed values rather than your raw data. Log transforms tend to have a major effect on distribution shape, and in visualizations can bring extreme outliers closer to the rest of the data so graphs aren&rsquo;t stretched out as much. You can either use natural logs (<em>ln</em>) or logs with base 10. The graphs below show the histogram of population data after a natural log transformation is applied and what the scatterplot looks like if you use a natural log transformation on both the population and land area variables.</p>

<p>進行<a class="glossterm" href="glossary01.html#transformation-log" target="_blank">對數轉換</a>的方式，是逐一計算資料集中每個數字的對數值，並使用其結果當做新資料。一般而言，對數轉換對於修改資料分佈的形狀相當有效，在視覺化呈現時，位於極外側的異常值會被拉到接近其他資料點的位置，讓整張圖看來不會扯得那麼開。做自然對數或以 10 為底數都可以。以下兩張圖顯示了經過自然對數轉換之後的人口資料直方圖，以及人口土地資料的散布圖。</p>

<figure><img alt="Log transformed population values" src="../images/sections/04/log-transformed.png" /></figure>

<figure><img alt="Log transformed scatter plot" src="../images/sections/04/log-scatter.png" /></figure>

<h3>平方根轉換 Square Root Transform</h3>

<p>The <a class="glossterm" href="glossary01.html#transformation-square" target="_blank">square root transformation</a> uses the square root of each value instead of the log, and has a more moderate effect on the distribution shape. The two graphs below show the histogram of population data and the scatterplot of population by land area, both after square root transformation is applied .</p>

<p>所謂<a class="glossterm" href="glossary01.html#transformation-square" target="_blank">平方根轉換</a>，就是資料集中數字逐一取平方根，相較於取對數，它對於改變分佈形狀的效果較為溫和一些。以下兩張圖顯示了經過平方根轉換之後的人口資料直方圖，以及人口土地資料的散布圖。</p>

<figure><img alt="Square root transformed population values" src="../images/sections/04/square-root.png" /></figure>

<figure><img alt="Square root transformed population values" src="../images/sections/04/sqrt-scatter.png" /></figure>

<h2>選擇正確的轉換 Choosing the Right Transform</h2>

<p>As you develop a better understanding of different transformation methods, you might wonder how to pick between them. The answer to this question is not straightforward and although there are formal statistical methods for selecting a transformation, we often need to use trial-and-error combined with knowledge of different transformations. A general strategy is to apply some of the most frequently used transforms such as log, square root, square, reciprocal, and cube root, and then choose the best one after observing the results.</p>

<p>在學習不同資料轉換方法之時，你可能會疑惑於如何選擇正確的方法。但這問題不好回答，雖然有許多制式的統計法則，通常還是需要在熟習轉換法的知識之後，再以嘗試錯誤方法挑選。要說簡單而通用的選擇策略，就是套幾種常用的，例如對數、平方根、平方、倒數、立方，觀察轉換結果之後，再選用結果較好的。</p>

<p>Looking at the transformed histograms above, the log transformed data seems to be a better fit to the normal distribution while the square root transformed data still carries the right skew. In this example, if you&rsquo;re doing a statistical test that has assumes the data are normally distributed, the log transformation would be a better method to use than the square root transformation.</p>

<p>一瞥前例的直方圖，經過對數轉換的資料，其形狀似乎較接近常態分佈，而以平方根轉換過的資料，還有一些些向右偏斜。以此例而言，若你所選擇的統計測試，假定其資料為常態分佈，則比起平方根轉換，對數轉換是較好的方法。</p>

<p>On the other hand, if your primary purpose in the example above is to visualize the relationship between state population and land area, the square root transformation does a better job of spreading out the data and making it easier to view than the log transformation.</p>

<p>另一方面，如果處理資料的目的是進行視覺化，以前述州人口數及土地面積範例而言，平方根轉換後的資料仍然夠散開，對於呈現的效果比對數轉換更好。</p>

<h2>通用轉換方法 Common Transformations</h2>

<table>
	<tbody>
		<tr>
			<th>Method</th>
			<th>Math Operation</th>
			<th>Good for:</th>
			<th>Bad for:</th>
		</tr>
		<tr>
			<td>Log</td>
			<td>ln(x)<br />
			log<sub>10</sub>(x)</td>
			<td>Right skewed data<br />
			log<sub>10</sub>(x) is especially good at handling higher order powers of 10 (e.g. 1000, 100000)</td>
			<td>Zero values<br />
			Negative values</td>
		</tr>
		<tr>
			<td>Square root</td>
			<td>&radic;<span style="text-decoration:overline;">x</span></td>
			<td>Right skewed data</td>
			<td>Negative values</td>
		</tr>
		<tr>
			<td>Square</td>
			<td>x<sup>2</sup></td>
			<td>Left skewed data</td>
			<td>Negative values</td>
		</tr>
		<tr>
			<td>Cube root</td>
			<td>x<sup>1/3</sup></td>
			<td>Right skewed data<br />
			Negative values</td>
			<td>Not as effective at normalizing as log transform</td>
		</tr>
		<tr>
			<td>Reciprocal</td>
			<td>1/x</td>
			<td>Making small values bigger and big values smaller</td>
			<td>Zero values<br />
			Negative values</td>
		</tr>
	</tbody>
</table>

<table>
	<tbody>
		<tr>
			<th>方法</th>
			<th>數學運算</th>
			<th>優於</th>
			<th>劣於</th>
		</tr>
		<tr>
			<td>對數</td>
			<td>ln(x)<br />
			log<sub>10</sub>(x)</td>
			<td>向右偏斜的資料<br />
			log<sub>10</sub>(x) 對於 10 的高次方數字特別好用 (1000、100000 等等)</td>
			<td>零、負數</td>
		</tr>
		<tr>
			<td>平方根</td>
			<td>&radic;<span style="text-decoration:overline;">x</span></td>
			<td>向右偏斜的資料</td>
			<td>負數</td>
		</tr>
		<tr>
			<td>平方</td>
			<td>x<sup>2</sup></td>
			<td>向左偏斜的資料</td>
			<td>負數</td>
		</tr>
		<tr>
			<td>立方根</td>
			<td>x<sup>1/3</sup></td>
			<td>向右偏斜的資料<br />負數</td>
			<td>不若對數轉換那麼有效果</td>
		</tr>
		<tr>
			<td>倒數</td>
			<td>1/x</td>
			<td>將大值變小、小值變大。</td>
			<td>零、負數</td>
		</tr>
	</tbody>
</table>

<h2>關於轉換的注意事項 <h2>Caveats about Transformation</h2>

<p>Since data transformation methods involve the application of a mathematical function to your data, you need to be careful when reporting or interpreting any insights derived from the transformed data because a transformation changes the unit of the data. For example, when we apply a logarithmic function to a population variable, the unit of measurement becomes the log of the population. When you&rsquo;re sharing results, your audience may assume that the calculated numbers or visualizations they&rsquo;re seeing are based on raw data, so if the values have been transformed, you should clearly communicate what transformation was used, as well as what units the data are being displayed in.</p>

<p>由於資料轉換本質上就是對資料套用數學函數，轉換過後的單位也就隨著變了，對於如何解釋轉換後資料的意義，得格外注意。例如，取了人口數的對數之後，單位顯然就不再是人口數了，而是「人口數的對數」。當你分享資料分析成果時，你的讀者可能會假設那些數字或視覺化呈現，都是以原始資料。若那些數值是轉換之後的結果，你應明確地標示所使用的轉換方法，以及視覺化呈現所使用的數值單位。
</p>

<div data-type="warning">
<p>If you use transformed data to calculate statistical values like means, you should back-transform the final results and report them in their original units. To back-transform, you just do the <i>opposite</i> of the mathematical function you used in the first place. For example, if you did a square root transformation, you would <a class="glossterm" href="glossary01.html#transformation-back" target="_blank">back-</a><a class="glossterm" href="glossary01.html#transformation-back" target="_blank">transform</a> by squaring your end result.</p>
</div>

<div data-type="warning">
<p>若你對轉換過的資料取統計函數，像是平均值，那你應將最終的結果進行反向轉換，轉回原單位，再做報告。所謂的<a class="glossterm" href="glossary01.html#transformation-back" target="_blank">反向轉換</a>，就是套用原轉換用數學函數的反函數。舉例來說，若一開始套用了平方根轉換，那麼其反向轉換的方法就是取平方。</p>
</div>

<p>You may not see transforms every day, but when you do, it&rsquo;s helpful to know why they were used and how they affect your data. It&rsquo;s important to be able to see different parts of the picture when working with data, and transformations give you another tool to help you do just that!</p>

<p>轉換的資料多半不會每天都出現。但當你見到時，通曉轉換方法更能有助於理解其轉換後資料受何影響。在處理資料之時，能於摸索不同部份而後通曉全局，是十分重要的。資料的轉換，則是能讓你通達的重要工具。</p>

</div>
<!--</section>
</section>-->
