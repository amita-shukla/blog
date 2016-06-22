#How To Host Images on the Web conveniently
http://shuklaamita.blogspot.com/2016/01/how-to-host-images-on-web-conveniently.html

<div dir="ltr" style="text-align: left;" trbidi="on">
<div>
In this post we talk about how to host images on the web so that it can be viewed by everybody.

<br />
<div>
As I was developing my blog, I had to post my photograph for the 'About Me' section.</div>
<div>
I went on to write my content as:<br />
<br /></div>
</div>
<div>
<pre><code><b>&lt;div class="textwidget"&gt;</b>
<b>&lt;img height="240" src="" style="margin-bottom: 10px;" width="240" /&gt; &lt;br /&gt;
&lt;br /&gt;
Hello I am &lt;strong&gt;Amita Shukla&lt;/strong&gt;...blah blah blah... This blog is a</b></code></pre>
<pre><code><b>place where I want to share all the things that I learn every now and then.</b></code></pre>
<pre><code><b>blah blah blah...&lt;br /&gt;
&lt;center&gt; &lt;/center&gt;
&lt;/div&gt;</b>
</code></pre>
</div>
<div>
<br />
The main problem here was the attribute '<b>src</b>'. For displaying the image, I needed it to host somewhere on the web, so that I can provide the link here.


</div>
<h4 style="text-align: left;">
The Failed Attempt</h4>
The main problem here was the attribute 'src'. For displaying the image, I needed it to be hosted somewhere on the web, so that I can provide the link here.<br />
The first idea was Google Drive. I uploaded the image, and acquired the shareable link. But, as I placed the link, an&nbsp;<b>aria-hidden&nbsp;</b>tag was automatically put, set to&nbsp;<b>true</b>. This tag automatically made the image hidden for public viewing.<br />
<div>
<br />
<h4 style="text-align: left;">
<a href="http://s1159.photobucket.com/" target="_blank">Photobucket</a>&nbsp;paved the way!</h4>
</div>
<div>
<div>
I decided to try Photobucket, and quickly created an account.</div>
<div>
It has a very nice and clean interface. I uploaded the image. As soon as I selected the image, a few options flashed below in blue.</div>
<div>
One of the options was 'Links'.</div>
<div>
Clicking on the option provided me with the links that can be hosted on several interfaces, such as Email,IM, Blogs, HTML, Forums etc.<br />
<br />
<div class="separator" style="clear: both; text-align: center;">
<a href="http://4.bp.blogspot.com/-iK89vvb5cvc/VppfHBKQoMI/AAAAAAAAAww/JYX_Z8BNOc8/s1600/Links-Photo-Sharing.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="270" src="http://4.bp.blogspot.com/-iK89vvb5cvc/VppfHBKQoMI/AAAAAAAAAww/JYX_Z8BNOc8/s400/Links-Photo-Sharing.png" width="400" /></a></div>
<br /></div>
<div>
<br />
I quickly clicked on the HTML option that handed me with the following code:</div>
</div>
<div>
</div>
<div>
<br />
<pre><code>
<b>&lt;center&gt;
&lt;a href="http://s1159.photobucket.com/user/amitashukla0906/media/Amita-Shukla_</b></code></pre>
<pre><code><b>zpsxjmxhbdt.jpg.html" target="_blank"&gt;&lt;img src="http://i1159.photobucket.com/</b></code></pre>
<pre><code><b>albums/p632/amitashukla0906/Amita-Shukla_zpsxjmxhbdt.jpg" border="0" alt="</b></code></pre>
<pre><code><b>photo Amita-Shukla_zpsxjmxhbdt.jpg"/&gt;&lt;/a&gt;
&lt;/center&gt;</b></code></pre>
<div>
<br /></div>
<div>
<br /></div>
Thanks PhotoBucket!</div>
<div>
<div>
</div>
<div>
</div>
</div>
</div>
