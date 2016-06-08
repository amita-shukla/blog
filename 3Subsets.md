#Find all possible subsets of a given set

http://shuklaamita.blogspot.com/2015/12/find-all-possible-subsets-of-given-set.html

<div dir="ltr" style="text-align: left;" trbidi="on">
<div>
The problem is: Given a set of distinct integers, S, return all possible subsets.</div>
<div>
<br /></div>
<div>
<span class="Apple-tab-span" style="white-space: pre;"> </span>Elements in a subset must be in non-descending order.</div>
<div>
<span class="Apple-tab-span" style="white-space: pre;"> </span>The solution set must not contain duplicate subsets.</div>
<div>
<span class="Apple-tab-span" style="white-space: pre;"> </span>Also, the subsets should be sorted in lexicographic order.</div>
<div>
<br /></div>
<div>
For example: For the set [1,2,3],</div>
<div>
The solution would be:</div>
<div>
[</div>
<div>
&nbsp; [],</div>
<div>
&nbsp; [1],</div>
<div>
&nbsp; [1, 2],</div>
<div>
&nbsp; [1, 2, 3],</div>
<div>
&nbsp; [1, 3],</div>
<div>
&nbsp; [2],</div>
<div>
&nbsp; [2, 3],</div>
<div>
&nbsp; [3],</div>
<div>
]</div>
<div>
<br /></div>
<div>
This problem can be approached by visualizing a tree:</div>
<br />
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [ &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;]<br />
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; / &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; \ &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;\<br />
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[1] &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[2] &nbsp; &nbsp; &nbsp; &nbsp;[3]<br />
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; / &nbsp; &nbsp; &nbsp;\ &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; |<br />
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[1,2]   [1,3] &nbsp; &nbsp; &nbsp;[2,3]<br />
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; |   <br />
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [1,2,3]<br />
<div>
&nbsp;<span class="Apple-tab-span" style="white-space: pre;">     </span> &nbsp;</div>
<div>
Start with an empty node. Then, take one element. Let it be at an index 'i' of the given set.</div>
<div>
The tree can be constructed by trying out the elements at the indexes after i.</div>
<div>
Each possibility makes a new branch.</div>
<div>
The branching ends when we have tried out all the possibilities.</div>
<div>
<br /></div>
<div>
The following code explains the above lines:<br />
<br /></div>
<!-- HTML generated using hilite.me --><br />
<div style="background: #ffffff; border-width: .1em .1em .1em .8em; overflow: auto; padding: .2em .6em; width: auto;">
<table><tbody>
<tr><td><pre style="line-height: 125%; margin: 0;"> 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27</pre>
</td><td><pre style="line-height: 125%; margin: 0;"><span style="color: #008800; font-weight: bold;">import</span> <span style="color: #0e84b5; font-weight: bold;">java.util.ArrayList</span><span style="color: #333333;">;</span>
<span style="color: #008800; font-weight: bold;">import</span> <span style="color: #0e84b5; font-weight: bold;">java.util.Collections</span><span style="color: #333333;">;</span>

<span style="color: #008800; font-weight: bold;">public</span> <span style="color: #008800; font-weight: bold;">class</span> <span style="color: #bb0066; font-weight: bold;">FindSubsets</span> <span style="color: #333333;">{</span>
 <span style="color: #008800; font-weight: bold;">static</span> ArrayList<span style="color: #333333;">&lt;</span>ArrayList<span style="color: #333333;">&lt;</span>Integer<span style="color: #333333;">&gt;&gt;</span> sets<span style="color: #333333;">;</span>

 <span style="color: #008800; font-weight: bold;">public</span> ArrayList<span style="color: #333333;">&lt;</span>ArrayList<span style="color: #333333;">&lt;</span>Integer<span style="color: #333333;">&gt;&gt;</span> <span style="color: #0066bb; font-weight: bold;">subsets</span><span style="color: #333333;">(</span>ArrayList<span style="color: #333333;">&lt;</span>Integer<span style="color: #333333;">&gt;</span> set<span style="color: #333333;">)</span> <span style="color: #333333;">{</span>

  Collections<span style="color: #333333;">.</span><span style="color: #0000cc;">sort</span><span style="color: #333333;">(</span>set<span style="color: #333333;">);</span>
  sets <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">new</span> ArrayList<span style="color: #333333;">&lt;</span>ArrayList<span style="color: #333333;">&lt;</span>Integer<span style="color: #333333;">&gt;&gt;();</span>
  sets<span style="color: #333333;">.</span><span style="color: #0000cc;">add</span><span style="color: #333333;">(</span><span style="color: #008800; font-weight: bold;">new</span> ArrayList<span style="color: #333333;">&lt;</span>Integer<span style="color: #333333;">&gt;());</span>
  backtrack<span style="color: #333333;">(</span>set<span style="color: #333333;">,</span> <span style="color: #0000dd; font-weight: bold;">0</span><span style="color: #333333;">,</span> <span style="color: #008800; font-weight: bold;">new</span> ArrayList<span style="color: #333333;">&lt;</span>Integer<span style="color: #333333;">&gt;());</span>

  <span style="color: #008800; font-weight: bold;">return</span> sets<span style="color: #333333;">;</span>
 <span style="color: #333333;">}</span>

 <span style="color: #008800; font-weight: bold;">public</span> <span style="color: #008800; font-weight: bold;">static</span> <span style="color: #333399; font-weight: bold;">void</span> <span style="color: #0066bb; font-weight: bold;">backtrack</span><span style="color: #333333;">(</span>ArrayList<span style="color: #333333;">&lt;</span>Integer<span style="color: #333333;">&gt;</span> set<span style="color: #333333;">,</span> <span style="color: #333399; font-weight: bold;">int</span> index<span style="color: #333333;">,</span>
   ArrayList<span style="color: #333333;">&lt;</span>Integer<span style="color: #333333;">&gt;</span> partial<span style="color: #333333;">)</span> <span style="color: #333333;">{</span>

  <span style="color: #008800; font-weight: bold;">for</span> <span style="color: #333333;">(</span><span style="color: #333399; font-weight: bold;">int</span> i <span style="color: #333333;">=</span> index<span style="color: #333333;">;</span> i <span style="color: #333333;">&lt;</span> set<span style="color: #333333;">.</span><span style="color: #0000cc;">size</span><span style="color: #333333;">();</span> i<span style="color: #333333;">++)</span> <span style="color: #333333;">{</span>
   ArrayList<span style="color: #333333;">&lt;</span>Integer<span style="color: #333333;">&gt;</span> subset <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">new</span> ArrayList<span style="color: #333333;">&lt;&gt;(</span>partial<span style="color: #333333;">);</span>
   subset<span style="color: #333333;">.</span><span style="color: #0000cc;">add</span><span style="color: #333333;">(</span>set<span style="color: #333333;">.</span><span style="color: #0000cc;">get</span><span style="color: #333333;">(</span>i<span style="color: #333333;">));</span>
   sets<span style="color: #333333;">.</span><span style="color: #0000cc;">add</span><span style="color: #333333;">(</span>subset<span style="color: #333333;">);</span>
   backtrack<span style="color: #333333;">(</span>set<span style="color: #333333;">,</span> i <span style="color: #333333;">+</span> <span style="color: #0000dd; font-weight: bold;">1</span><span style="color: #333333;">,</span> subset<span style="color: #333333;">);</span>
  <span style="color: #333333;">}</span>
 <span style="color: #333333;">}</span>
<span style="color: #333333;">}</span>
</pre>
</td></tr>
</tbody></table>
</div>
<div>
<br />
Get the code at:&nbsp;<a href="https://github.com/amita-shukla/programs/blob/master/FindSubsets.java">https://github.com/amita-shukla/programs/blob/master/FindSubsets.java</a></div>
</div>
