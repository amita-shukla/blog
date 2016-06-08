#Let's Plant a Tree!
http://shuklaamita.blogspot.com/2016/01/lets-plant-tree.html

<div dir="ltr" style="text-align: left;" trbidi="on">
<div dir="ltr" style="text-align: left;" trbidi="on">
<div dir="ltr" style="text-align: left;" trbidi="on">
<div dir="ltr" trbidi="on">
<div class="separator" style="clear: both; text-align: center;">
<a href="http://4.bp.blogspot.com/-ajriRld_14w/VoqIpnNSJCI/AAAAAAAAAsw/FDBRk_-CLXw/s1600/1ff9c42b-52ba-429d-aaaf-f0c06bc1e894.jpg" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="320" src="http://4.bp.blogspot.com/-ajriRld_14w/VoqIpnNSJCI/AAAAAAAAAsw/FDBRk_-CLXw/s320/1ff9c42b-52ba-429d-aaaf-f0c06bc1e894.jpg" style="display: none;" width="299" /></a></div>
<br />
Trees seem like an interesting topic but scared to start? Lets start by learning the basics of trees and move on to play with them! Like the trees' structure in relevance to computer science, we need to start from the root.<br />
<div>
<br /></div>
<h2 style="text-align: left;">
What is a Binary Tree?</h2>
<div>
If you have not read about trees before, this will blow your mind. A recursive definition for trees.</div>
<blockquote class="tr_bq">
It is either empty, or consists of a root node which has its left and right trees, both of which are binary trees.</blockquote>
Somewhat like this:<br />
<div class="separator" style="clear: both; text-align: center;">
<a href="http://www.sqa.org.uk/e-learning/LinkedDS04CD/images/pic026.jpg" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" src="http://www.sqa.org.uk/e-learning/LinkedDS04CD/images/pic026.jpg" height="231" width="320" /></a></div>
<br />
Done with the textbook definition, why should we bother about binary trees?<br />
<br />
<h2 style="text-align: left;">
When to choose Trees over linear data structures like Arrays and Linked Lists?</h2>
<div>
This leads us to:</div>
<h3 class="western" style="orphans: 1; text-align: left;">
<span style="font-variant: normal;"><span style="color: black;"><span style="font-family: &quot;times new roman&quot;;"><span style="font-size: medium;"><span style="font-style: normal;">On
what basis we decide which data to use?</span></span></span></span></span></h3>
<h3>
 
 
 



<ul style="text-align: left;">
<li><div style="orphans: 1;">
<span style="color: black;"><span style="font-family: &quot;times new roman&quot;;"><span style="font-size: 14pt;">What
 needs to be stored</span><span style="font-weight: normal;"><span style="font-size: 14pt;">:&nbsp;</span></span></span></span><span style="font-weight: normal;"><span style="font-size: small;">Trees are mostly used for storing hierarchical data.</span></span></div>
</li>
<li><div style="orphans: 1; text-align: left;">
<span style="color: black;"><span style="font-family: &quot;times new roman&quot;;"><span style="font-size: 14pt;">Cost
 Of operations:&nbsp;</span></span></span><span style="font-weight: normal;"><span style="font-size: small;">Trees are suitable for operations such as search, insert, delete.</span></span></div>
</li>
</ul>
<table cellpadding="4" cellspacing="0" style="width: 100%px;">
 <colgroup><col width="51*"></col>
 <col width="51*"></col>
 <col width="51*"></col>
 <col width="51*"></col>
 <col width="51*"></col>
 </colgroup><tbody>
<tr valign="top">
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: 1px solid #000000; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0.1cm;" width="20%"><div align="left">
<br /></div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: 1px solid #000000; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0.1cm;" width="20%"><div align="left">
<b>Array (unsorted)</b></div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: 1px solid #000000; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0.1cm;" width="20%"><div align="left">
<b>Linked List</b></div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: 1px solid #000000; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0.1cm;" width="20%"><div align="left">
<b>Array (sorted)</b></div>
</td>
  <td style="border: 1px solid #000000; padding: 0.1cm;" width="20%"><div align="left">
<b>BST</b></div>
</td>
 </tr>
<tr valign="top">
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0cm;" width="20%"><div align="left">
<b>Search</b></div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0cm;" width="20%"><div align="left">
O(n)</div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0cm;" width="20%"><div align="left">
O(n)</div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0cm;" width="20%"><div align="left">
O(n)</div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: 1px solid #000000; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0.1cm; padding-top: 0cm;" width="20%"><div align="left">
O(lgn)</div>
</td>
 </tr>
<tr valign="top">
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0cm;" width="20%"><div align="left">
<b>Insert</b></div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0cm;" width="20%"><div align="left">
O(1)</div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0cm;" width="20%"><div align="left">
O(n)</div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0cm;" width="20%"><div align="left">
O(n)</div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: 1px solid #000000; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0.1cm; padding-top: 0cm;" width="20%"><div align="left">
O(lgn)</div>
</td>
 </tr>
<tr valign="top">
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0cm;" width="20%"><div align="left">
<b>Remove</b></div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0cm;" width="20%"><div align="left">
O(n)</div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0cm;" width="20%"><div align="left">
O(n)</div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: none; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0cm; padding-top: 0cm;" width="20%"><div align="left">
O(n)</div>
</td>
  <td style="border-bottom: 1px solid #000000; border-left: 1px solid #000000; border-right: 1px solid #000000; border-top: none; padding-bottom: 0.1cm; padding-left: 0.1cm; padding-right: 0.1cm; padding-top: 0cm;" width="20%"><div align="left">
O(lgn)</div>
</td>
 </tr>
</tbody></table>
<div align="left" style="orphans: 1;">
<br />
<br /></div>
<ul style="text-align: left;">
<li><div style="orphans: 1;">
<span style="color: black;"><span style="font-family: &quot;times new roman&quot;;"><span style="font-size: 14pt;">Memory
 Consumption:<span style="font-weight: normal;">&nbsp;</span></span></span></span><span style="font-weight: normal;"><span style="font-size: small;">BSTs, if efficiently built use O(lgn) space in average case and O(n) in the worst case.</span></span></div>
</li>
</ul>
<div style="text-align: left;">
<span style="font-size: small;"><span style="font-weight: normal;">Enough with the introduction, lets go about how to start programming with them.</span><span style="font-weight: normal;">We first of all need to learn how to create a tree. We know about several algorithms given in our textbooks, but we are seldom taught about how to start with them. So let's start!</span></span></div>
<div style="orphans: 1; text-align: left;">
<span style="color: black;"><span style="font-family: &quot;times new roman&quot;;"><span style="font-size: small; font-weight: normal;"><br /></span></span></span></div>
<div align="left" style="orphans: 1;">
<span style="color: black;"><span style="font-family: &quot;times new roman&quot;;"><span style="font-size: small; font-weight: normal;">This
is the implementation of a tree node:</span></span></span><br />
<!-- HTML generated using hilite.me --><br />
<div style="background: #ffffff; border-width: .1em .1em .1em .8em; border: none; overflow: auto; padding: .2em .6em; width: auto;">
<pre style="line-height: 125%; margin: 0;"><span style="font-size: small;"><span style="font-weight: normal;"><span style="color: #0000aa;">struct</span> node{
<span style="color: #00aaaa;">int</span> data;
<span style="color: #0000aa;">struct</span> node *left;
<span style="color: #0000aa;">struct</span> node *right;
};

<span style="color: #0000aa;">typedef</span> <span style="color: #0000aa;">struct</span> node *nodeptr;</span>
</span></pre>
</div>
<br /></div>
<div align="left" style="orphans: 1;">
<span style="font-weight: normal;"><span style="font-size: small;">Before calling a create function, we need to data field to label a tree node as well. So we modify the above declaration:</span></span><br />
<span style="color: black;"><span style="font-family: &quot;times new roman&quot;;"><span style="font-size: 14pt;"><span style="font-weight: normal;"><br /></span></span></span></span>
<br />
<div style="background: #ffffff; border-width: .1em .1em .1em .8em; border: none; overflow: auto; padding: .2em .6em; width: auto;">
<pre style="line-height: 125%; margin: 0;"><span style="font-size: small; font-weight: normal;"><span style="color: #0000aa;">struct</span> node{
<span style="color: #00aaaa;">int</span> label; <span style="color: #aaaaaa; font-style: italic;">//represents the node number of the tree (0 indexed)</span>
<span style="color: #00aaaa;">int</span> data;
<span style="color: #0000aa;">struct</span> node *left;
<span style="color: #0000aa;">struct</span> node *right;
};

<span style="color: #0000aa;">typedef</span> <span style="color: #0000aa;">struct</span> node *nodeptr;
</span></pre>
</div>
</div>
<div align="left" style="orphans: 1;">
<br /></div>
<div align="left" style="orphans: 1;">
<span style="font-weight: normal;"><span style="font-size: small;">Now, we will start creating a tree. We need a function that asks the user to enter the data for a node label. So we have the following prototype:</span></span></div>
<div align="left" style="orphans: 1;">
<div style="background: #ffffff; border-width: .1em .1em .1em .8em; border: none; overflow: auto; padding: .2em .6em; width: auto;">
<pre style="line-height: 125%; margin: 0;"><span style="font-size: small; font-weight: normal;"><span style="color: #00aaaa;">void</span> <span style="color: #00aa00;">createTree</span>(nodeptr);</span></pre>
</div>
</div>
</h3>
<h3 style="orphans: 1; text-align: left;">
<span style="color: black;"><span style="font-family: &quot;times new roman&quot;;"><span style="font-size: 14pt;">How
do we symbolize if a node is leaf?</span></span></span></h3>
<div style="text-align: left;">
We initialize its children with data = -1.</div>
In the main function, we need to create a root node:<br />
<div align="left" style="orphans: 1;">
<br />
<div style="background: #ffffff; border-width: .1em .1em .1em .8em; border: none; overflow: auto; padding: .2em .6em; width: auto;">
<pre style="line-height: 125%; margin: 0;"><span style="color: #00aaaa;">int</span> <span style="color: #00aa00;">main</span>(){
<span style="color: #00aaaa;">int</span> data = -<span style="color: #009999;">1</span>;
<span style="color: #00aaaa;">int</span> label = <span style="color: #009999;">0</span>;
printf(<span style="color: #aa5500;">"Provide data for the root node\n"</span>);
scanf(<span style="color: #aa5500;">"%d"</span>,&amp;data);
nodeptr root = getnode(label,data);
createTree(root);
printf(<span style="color: #aa5500;">"\n=====================Preorder Traversal====================\n"</span>);
pretrav(root);
<span style="color: #0000aa;">return</span> <span style="color: #009999;">0</span>;
}
</pre>
</div>
</div>
<div align="left" style="orphans: 1;">
<br /></div>
<div align="left" style="orphans: 1;">
<span style="color: black;"><span style="font-family: &quot;times new roman&quot;;"><span style="font-weight: normal;">Now
let's define the&nbsp;</span></span></span><span style="line-height: 16.25px;">createTree(nodeptr root)</span>&nbsp;function:
<!-- HTML generated using hilite.me --><br />
<span style="font-size: 14pt;"><br /></span>
<br />
<div style="background: #ffffff; border-width: .1em .1em .1em .8em; border: none; overflow: auto; padding: .2em .6em; width: auto;">
<pre style="line-height: 125%; margin: 0;"><span style="color: #00aaaa;">void</span> <span style="color: #00aa00;">createTree</span>(nodeptr root){
<span style="color: #0000aa;">if</span>(root == <span style="color: #00aaaa;">NULL</span>)
<span style="color: #0000aa;">return</span>;
<span style="color: #aaaaaa; font-style: italic;">//Initialize left and right subtrees, which are currently null</span>
nodeptr left = root-&gt;left;
nodeptr right = root-&gt;right;
<span style="color: #aaaaaa; font-style: italic;">//input the left child</span>
<span style="color: #00aaaa;">int</span> data = -<span style="color: #009999;">1</span>;
printf(<span style="color: #aa5500;">"Provide data for the left child of node %d (Enter -1 if current node is leaf)\n"</span>,root-&gt;label);
scanf(<span style="color: #aa5500;">"%d"</span>,&amp;data);
<span style="color: #0000aa;">if</span>(data != -<span style="color: #009999;">1</span>){
left = getnode(<span style="color: #009999;">2</span>*(root-&gt;label)+<span style="color: #009999;">1</span>,data);
root-&gt;left = left;
}
<span style="color: #aaaaaa; font-style: italic;">//input the right child</span>
data = -<span style="color: #009999;">1</span>;
printf(<span style="color: #aa5500;">"Provide data for the right child of node %d (Enter -1 if current node is leaf)\n"</span>,root-&gt;label);
scanf(<span style="color: #aa5500;">"%d"</span>,&amp;data);
<span style="color: #0000aa;">if</span>(data != -<span style="color: #009999;">1</span>){
right = getnode(<span style="color: #009999;">2</span>*(root-&gt;label)+<span style="color: #009999;">2</span>,data);
root-&gt;right = right;
}
createTree(left);
createTree(right);
}
</pre>
</div>
</div>
<div align="left" style="orphans: 1;">
<br /></div>
Like we see in the main function above, we first use the getnode() function to get the root node, ask the user to enter the data for root node, call the createTree() function, and then ask data for subsequent nodes.<br />
<div align="left" style="orphans: 1;">
As
you can see, this is a recursive function, after taking the data for
left and right nodes, you recur over the left and right subtrees.</div>
</div>
</div>
</div>
<div align="left" style="orphans: 1;">
As
you can see, the left and right child of the root node are only
initialized with data if data!= null, hence if the noed is leaf, we
enter data as -1.<br />
<br />
<br />
You can find the code above&nbsp;<a href="https://github.com/amita-shukla/programs/blob/master/TreeCreate.c" target="_blank">here</a>&nbsp;in C and&nbsp;<a href="https://github.com/amita-shukla/programs/blob/master/TreeNode.java" target="_blank">here</a>,&nbsp;<a href="https://github.com/amita-shukla/programs/blob/master/Tree.java" target="_blank">here</a>&nbsp;in java.</div>
</div>
