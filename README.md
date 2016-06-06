#Welcome to Scribble, Amita Shukla's blog

<div dir="ltr" style="text-align: left;" trbidi="on">
<div class="separator" style="clear: both; text-align: left;">
Maintaining a blog is a real problem. And when using a custom template, it gets really difficult to even make a single change, as it may reflect somewhere else, if any careless action is made.</div>
<div class="separator" style="clear: both; text-align: left;">
<br /></div>
<div class="separator" style="clear: both; text-align: left;">
Out of the one change, a major (though it seemed trivial) problem that I faced was to change the default size of the pictures in the posts. Previously, the default behaviour of this blog post was to resize the picture on the home page to the post area.&nbsp;</div>
<div class="separator" style="clear: both; text-align: left;">
This led to extremely large and blurred pictures.&nbsp;</div>
<div class="separator" style="clear: both; text-align: left;">
<br /></div>
<div class="separator" style="clear: both; text-align: left;">
And when it comes to the look of your page. What does wonders is:&nbsp;</div>
<h3 style="clear: both; text-align: center;">
<span style="font-weight: normal;">CSS !!</span></h3>
<div class="separator" style="clear: both; text-align: center;">
<a href="https://2.bp.blogspot.com/-DNLmmOlaZP8/V1Rg8-JI4kI/AAAAAAAABMY/I843zqOZC5MHJ9IVKzyzAoUAws2oeTMTQCLcB/s1600/blog_css.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" src="https://2.bp.blogspot.com/-DNLmmOlaZP8/V1Rg8-JI4kI/AAAAAAAABMY/I843zqOZC5MHJ9IVKzyzAoUAws2oeTMTQCLcB/s1600/blog_css.png" /></a></div>
<br />
First I needed to find out the class that surrounds this image.<br />
<br />
After search (using ctrl + f ) in the 'template' section, we can find classes like <code>post-image</code>, <code>img</code> .<br />
These classes are most likely to affect the image in the blog.<br />
<br />
I found out the code as :<br />
<br />
<pre class="lang-xml prettyprint prettyprinted" style="background-color: #eff0f1; border: 0px; color: #393318; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; font-size: 13px; margin-bottom: 1em; max-height: 600px; overflow: auto; padding: 5px; width: auto; word-wrap: normal;"><code style="border: 0px; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; margin: 0px; padding: 0px; white-space: inherit;"><span class="pln" style="border: 0px; color: #303336; margin: 0px; padding: 0px;">.post-image img{
    max-width:100%;
    height:auto;
}</span></code></pre>
I changed the attributes here, as:<br />
<br />
<pre class="lang-xml prettyprint prettyprinted" style="background-color: #eff0f1; border: 0px; color: #393318; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; font-size: 13px; margin-bottom: 1em; max-height: 600px; overflow: auto; padding: 5px; width: auto; word-wrap: normal;"><code style="border: 0px; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; margin: 0px; padding: 0px; white-space: inherit;"><span class="pln" style="border: 0px; color: #303336; margin: 0px; padding: 0px;">.post-image img{
    max-width:50%;
    height:auto;
 }</span></code></pre>
<div>
<br /></div>
This is because I realized that this is the setting for images in individual posts, where the images were displayed normally.<br />
And voila! it worked.<br />
But this caused another problem, all the images were shifted to the left!<br />
<br />
To fix this, I decided to make it up by coding CSS to bring images to the center area of the surrounding <code>div</code>. This is done by :<br />
<br />
<pre class="lang-xml prettyprint prettyprinted" style="background-color: #eff0f1; border: 0px; color: #393318; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; font-size: 13px; margin-bottom: 1em; max-height: 600px; overflow: auto; padding: 5px; width: auto; word-wrap: normal;"><code style="border: 0px; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; margin: 0px; padding: 0px; white-space: inherit;"><span class="pln" style="border: 0px; color: #303336; margin: 0px; padding: 0px;">.post-image img{
    display:block;
    margin-left:auto;
    margin-right:auto;
    max-width:50%;
    height:auto;
}</span></code></pre>
Lets review what these properties do.<br />
<br />
<h4 style="text-align: left;">
<span style="font-weight: normal;">display</span></h4>
<div>
<span style="font-weight: normal;">The display property controls how an element is displayed in accordance with the parent element. The display property can be of two types: block and inline.</span></div>
<div>
<span style="font-weight: normal;"><br /></span></div>
<div>
<span style="font-weight: normal;">Block means that the element will acquire a complete block, that is, will take up the whole area in which it is extended, from left to right. e.g. div</span></div>
<div>
<span style="font-weight: normal;">Inline means, that the element will be lined up with the surrounding text. e.g. span.</span></div>
<div>
<span style="font-weight: normal;"><br /></span></div>
<div>
<span style="font-weight: normal;">Here the img is block that means it takes up the whole space.</span></div>
<div>
<span style="font-weight: normal;"><br /></span></div>
<h4>
<span style="font-weight: normal;">margin</span></h4>
<div>
<span style="font-weight: normal;">The margin specifies the space around the elements, outside the border. It can be margin-top, margin-bottom, margin-left, margin-right.</span></div>
<div>
<span style="font-weight: normal;">To bring the image to the center, I defined the left and right margin to auto. The auto property lets the margin to be calculated by the browser. Using this, we align the image element in the center horizontally.</span></div>
<div>
<span style="font-weight: normal;"><br /></span></div>
<div>
As I could not find this fix anywhere else, I added it on <a href="http://stackoverflow.com/a/37643409/3858467" target="_blank">Stack Overflow</a>.</div>
</div>

