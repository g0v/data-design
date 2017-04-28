<!--
Section tag replaced with div for Gitbook publishing
	<section class="green" data-type="chapter">-->
<div class="green" data-type="chapter">
<header>
  <div class="icon"><img src="../images/sections/05/print-web.png" /></div>
  <p>Chapter 16</p>
  <h1>紙本 vs 網頁、靜態 vs 互動</h1>
  <p data-type="author">Sarah Rigdon</p>
</header>

<!--<section data-type="sect1">-->
<p>無論是在為靜態或是互動環境設計圖形，有幾項重點須在開始之前釋疑一番。首先，什麼才算是所謂「靜態」設計和「互動」設計呢？</p>

<h2>定義「紙本 vs 網頁」 「靜態 vs 互動」</h2>

<p>你可以為紙本或網頁設計<a class="glossterm" href="glossary01.html#graphic-static" target="_blank">靜態圖形</a>，或同時使用靜態設計。採用靜態圖形設計，除了滑動滾輪和點撃放大以外無須其他操作，能令讀者不作任何輸入即可檢視一切你想要呈現的資訊。因此靜態圖形通常所展示的都是無需頻繁更迭的資訊。</p>

<p>你也可以為紙本或網頁設計互動圖形，或一併採用互動設計。<a class="glossterm" href="glossary01.html#graphic-interactive" target="_blank">互動圖形</a>通常能為提供讀者更深入的資訊。説到這裡，你可能會想：「互動式的紙本」？<s>唉喲！不錯哦！這個屌！</s>是的、沒錯、正確，雖然並不像網頁裡的互動圖形般時常出現，但還是有如以下例子的「紙本」：</p>

<ul>
	<li>互動設計</li>
	<li>藝術裝置</li>
	<li>手翻書/動畫卡</li>
	<li>立體書</li>
</ul>

<p>所以，靜態設計不為紙本所獨佔，動態設計亦非網頁的專利。</p>

<p>One more thing: the antonym to static isn&rsquo;t interactive. It&rsquo;s changing, moving, or dynamic. <a class="glossterm" href="glossary01.html#graphic-motion" target="_blank">Motion graphics</a> don&rsquo;t require viewer interaction, but they&rsquo;re not static, either. Any given cable news network will give you examples of these. Do they display necessary information? Not usually. Adding motion to infographics can keep viewers&rsquo; attention, at least at first. But over the course of a segment or a show, viewer fatigue sets in. Motion graphics often look impressive, but you should always ask whether motion is necessary for conveying the information and be wary of overusing it.</p>

<p>Now let&rsquo;s shift gears and talk about some of the core design concepts you should consider when creating static and interactive print-based and web-based graphics.</p>

<h2>色彩調配</h2>

<p>就配色而言，在定奪你的專屬色盤前還有一大堆問題要先解決，如果是作紙本印刷的話就更為重要。是全彩的作業環境呢，還是採用黑白呢？若是採用全彩環境的話，你可能要考慮為此額外衍生的成本與黑白印刷相比是否更有效益。畢竟灰階及二階印刷仍是主流媒介之一。全彩印刷真的必要嗎？</p>

<p>How many colors are available for the print job? What kind of paper are you working with? Colors work differently with news print, magazine, and printer paper. Or are you getting fancy and putting the graphic on merchandise? A good merchandising company will work with you to make sure your t-shirts, totes, buttons, or stickers look great, but you&rsquo;ll want to anticipate these concerns in advance.</p>

<p>On the web, a lot of these restrictions go away, but not all. Many designers have to work within a website&rsquo;s color palette. They have to ask questions such as: does the website&rsquo;s green color scheme completely clash with this bright pink graphic? Does it subtly complement the branding and logo design? The answers to each of these can have an impact on how the viewer receives the final design.</p>

<h2>尺寸大小</h2>

<p>Step back and take a look at the space you&rsquo;re working with. You have to consider size for both print and the web.</p>

<p>With print, you have the page size constraining your graphics, but that can also be a blessing because you only need to design for a single width and height.</p>

<p>On the web, you can often include image-zooming functionality or allow viewers to open a larger version of a graphic in a separate browser tab, but you should consider the effects that zooming and scrolling can have on a user&rsquo;s experience. A well-designed graphic should provide key information in a clear and elegant manner with minimum effort required by the user.</p>

<p>Mobile devices are also a concern, as more people are using cell phones and tablets to browse the web. Keep in mind that nearly two-thirds of cell-phone&nbsp;owners now use their phones to browse the web, and twenty percent use their phones to do <em>most</em> of their web browsing.<span contenteditable="false" data-type="footnote">Cell Internet Use 2013. Pew Research Internet Project. &quot;Main Findings.&quot; Duggan and Smith. 16 September 2013: http://www.pewinternet.org/2013/09/16/main-findings-2/</span>&nbsp;It&rsquo;s hard to see a lot of detail on a tiny touchscreen, but you don't want users to have to squint to understand your graphic! You could build a responsive graphic &mdash; one that automatically changes its layout according to the dimensions of the viewer&rsquo;s screen size &mdash; or you could design a completely different graphic specifically for display on small mobile devices. Given the state of mobile web browsing trends, it&rsquo;s something you should consider when publishing a visualization on the web.</p>

<figure><img alt="Pie chart on different width screens" src="../images/sections/05/ch19-01-pie-on-mobile.png" /></figure>

<figure><img alt="Bar chart on mobile device" src="../images/sections/05/ch19-02-column-chart-on-mobile.png" /></figure>

<p>Many mobile devices (and increasingly, laptop and desktop monitors) have high-resolution displays, often referred to as <em>retina</em> displays. A static image designed at the standard web resolution of 72 dpi (dots per inch) will usually look blurry when viewed on a retina display. You&rsquo;ll need to make double-resolution retina versions of your image-based graphics if you want them to look sharp on, say, a modern iPad. You can also create them using web fonts and SVGs, and they will always look crisp, no matter what the screen resolution. One downside to this is that some older browsers (notably Internet Explorer 8 and below) do not natively support SVG format.</p>

<div data-type="sidebar">
<h3>甚麼是可縮放向量圖形（SVG）？</h3>

<p>可縮放向量圖形（<b>S</b>calable <b>V</b>ector <b>G</b>raphic, <b>SVG</b>）是一款顯示向量圖形的「網頁友善」格式，因圖形是以數學公式計算描繪形狀，所以可無限縮放而不會産生馬賽克。向量圖像即使不斷放大依然能保持清晰鋭利，與點陣圖像（bitmap images，又作「柵格圖像」 raster graphics）不同，位圖是以儲存像素陣列内的顏色資訊産生圖像。故此點陣圖以高解像度檢視時會顯得模糊不清，但因其所儲存的色彩資訊組合非常複雜故屬必然現象。舉例來説，一張照片可謂是點陣圖的絶妙儲存實例，而一個簡單的圓形則是向量圖的經典繪圖實例。</p>

<figure><img alt="Bitmap vs. vector images" src="../images/sections/05/ch19-03-raster-vector.png" /></figure>

<p>Many of the tools for building web-based interactive charts and graphs (such as <a href="http://d3js.org/" target="_blank">D3.js</a>) use SVGs to render visualizations, especially interactive ones. Most of the static infographics, however, are published in bitmap image formats, such as JPEG or PNG.</p>
</div>

<p>Size doesn&rsquo;t just refer to how big an image appears. Pay attention to the size of your file as well. People all around the world use mobile devices to browse the web. Not only can it take a long time to download a large image across a mobile network, but in some parts of the world, each megabyte of data is an added cost. Be nice to your viewers and work to reduce your final image size.</p>

<h2>頁面排版</h2>

<p>With static images, the point is to provide everything you want to convey in one or more frames. There are no mouseovers, you can&rsquo;t click around and select certain details and un-select certain others (e.g., show only state rodeos from 1988 to 1996). Make sure that your key points are visible. If you&rsquo;re creating a static version of an interactive graphic, keep in mind that you might not be able to show everything that was accessible in your original interactive graphic. If possible, provide URLs so that your readers can also access the raw data and the interactive version of your graphic. That way, they&rsquo;ll have the option to dig deeper and find more information about the parts of the data that didn&rsquo;t make it into the print version.</p>

<p>With interactive graphics, make sure to test any clickable controls that manage the interaction. Are there buttons or slides off to the side, or are they a part of the graphic? Does the viewer have to scroll around to see everything with several options engaged? Test your graphic in different browsers to make sure it all fits&mdash;and functions&mdash;the way you want.</p>

<h3>有關網頁上靜態圖形的二三事</h3>

<p>These aren&rsquo;t necessarily interactive, save in that viewers can enlarge them. Because the graphic itself doesn&rsquo;t change, the main considerations of layout still apply. But just by being on the web, static graphics give us more interactivity than print. For example, they can be linked to their data source, another related graph, or a different web page. Mobile screen sizes still remain a challenge for static graphics specifically because their layout doesn&rsquo;t change to accommodate smaller screen real estates or different width-to-height ratios.</p>

<figure><img alt="Complex map on mobile device" src="../images/sections/05/map-on-mobile.png" />
<figcaption>文字標籤和影像細節或許在大尺寸螢幕清晰鋭利，但在行動裝置上則可能會産生閱讀上的困難。</figcaption>
</figure>

<p>雖然在靜態圖像内列出的超連結無法直接點撃，優秀的作者通常會在圖像之後補充參考來源連結以提高閱讀便利性。</p>

<figure><img alt="Citing sources" src="../images/sections/05/ch19-05-link-position.png" /></figure>

<h3>權衡互動功能之必要</h3>

<p>Making interactive graphics is getting easier all the time with new software and applications. Interactivity can be not only extremely impressive but also useful, highlighting different types of information more effectively than a static image ever could. But sometimes, you&rsquo;ll come across an interactive image that actually makes the information more confusing. Other times, you&rsquo;ll come across an interactive image that seems neat at first, but as you play with it, you realize it&rsquo;s just bells and whistles. You&rsquo;re not learning anything new, and the information could just as clearly have been presented in a static image. What a let-down!</p>

<p>為甚麼要在<s>龍蝦三爭霸時非得炸三隻龍蝦</s>非必要的圖形互動上大費周章呢？互動性是設計師工具箱內的一大法寶啊。互動性設計 Interactivity should be used when it improves upon a static graphic or adds value to the information and does something that the static image alone could not.</p>

<p>例如以下列棒形圖為例：</p>

<figure><img alt="Pointless hover" src="../images/sections/05/ch19-06-pointless-hover.png" /></figure>

<p>上圖所示的互動功能（如：滑鼠滑入的特效）在讀取資訊方面對讀者來説並非必要。In the figure above, the interactive labels (e.g., the hover effects) aren&rsquo;t necessary for the viewer&rsquo;s comprehension. The labels can be added to the chart <em>before</em> hovering, which makes the chart easier to understand and requires less effort from the viewer. When you&rsquo;re presenting a small, simple chart with a single variable, interactivity can actually detract from your message.</p>

<div data-type="note">
<p>There are plenty of amazing use cases where interactivity adds value to a visualization, but you shouldn&rsquo;t make yours interactive just because it looks cool. Make sure you&rsquo;re actually improving the user&rsquo;s experience. For example, interactivity can help greatly enhance any graphic that illustrates a rich data set you want the user to explore. Let&rsquo;s say you want to show how different groups of consumers drink coffee. An interactive visualization might allow your user to filter by demographic groups and explore coffee consumption patterns.</p>
</div>

<p>Interactive graphics can add a lot of value when you have a rich dataset that you want the user to explore. For example, let&rsquo;s say that you want to know how different groups of consumers drink coffee. An interactive visualization might allow you to filter by demographic groups and explore coffee consumption patterns.</p>

<figure><img alt="Interactive exploration" src="../images/sections/05/ch19-07-interactive-exploration.png" /></figure>

<p>In static graphics, you can&rsquo;t rely on visual effects like movement or color changes to make your point. On the other hand, while interactive graphics can incorporate visual effects to show trends across time, they do introduce room for technical difficulties. Be mindful of compatibility across computer systems and browsers. Some of the more complex interactive visualizations require a lot of computational power and can be slow on less-powerful machines such as smart phones. Visualizations made using Flash won&rsquo;t render on iPhones or iPads, and those made using SVGs won&rsquo;t work in Internet Explorer 8 or below. Interactive visualizations built for a computer with a mouse may be difficult or impossible to use on touchscreen devices if the creator forgets to test and optimize the graphics for touch-based interactions.</p>

<p>Any medium for sharing a visualization &mdash; whether static or interactive &mdash; will have its strengths and its limitations. Think about your story, your audience, and how readers are likely to view your visualizations. Ask for feedback and continue to iterate on your process. And if you&rsquo;re looking for some friendly feedback and suggestions, you can post your works-in-progress on <a href="http://helpmeviz.com/">HelpMeViz</a>.</p>
</div>
<!--</section>
</section>-->
