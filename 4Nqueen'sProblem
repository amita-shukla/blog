#Solve the N queen's problem using backtracking
http://shuklaamita.blogspot.com/2015/12/solve-n-queens-problem-using.html

<div dir="ltr" style="text-align: left;" trbidi="on">
<div dir="ltr" style="text-align: left;" trbidi="on">
<div dir="ltr" style="text-align: left;" trbidi="on">
<h3 style="text-align: left;">
Problem Statement:</h3>
<div style="text-align: left;">
<span style="font-weight: normal;">Given a NxN chess board, find a way to place N queens in such a way that no queen is in danger from another.</span></div>
<div style="text-align: left;">
<div style="text-align: left;">
A queen is said to be in danger from another when both the queens share the same row, column or diagonal.</div>
<div style="text-align: left;">
One of the solutions to the 4-Queen's Puzzle is:</div>
<div style="text-align: left;">
<br /></div>
<div class="separator" style="clear: both; text-align: center;">
<a href="http://4.bp.blogspot.com/-qrch24vNM4Q/VoVttnOzI9I/AAAAAAAAAr0/8woPBuzHis8/s1600/NQueen.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" src="http://4.bp.blogspot.com/-qrch24vNM4Q/VoVttnOzI9I/AAAAAAAAAr0/8woPBuzHis8/s1600/NQueen.png" /></a></div>
<br />
Solutions to this problem exist for all natural numbers N, with N=2 and N=3 as exception.<br />
<br />
This is a classic example of a problem that can be solved using a technique called <b>Recursive Backtracking</b>.<br />
<br />
<h3 style="text-align: left;">
Strategy:</h3>
<div>
How do we go about solving this problem&nbsp;programmatically?</div>
<div>
We can try all possible places one by one. But, we can observe, that we do not need to go beyond a certain limiting condition, when we realize that a solution is not possible.</div>
<div>
<br /></div>
<div>
<div>
<ul style="text-align: left;">
<li>Take one row at a time.</li>
<li>Now, given a row, consider one column at a time and check if it is "safe" to place the queen in the cell.</li>
<li>If we find the column is safe, then place the queen, and make a recursive call to place the queen on the next row.</li>
<li>If we can’t find one, backtrack by returning from the recursive call, and try to find another safe column in the previous row.</li>
</ul>
</div>
</div>
<div>
<div>
So, the main routine is <code> findSafeColumn(int row) </code> </div>
<div>
<br /></div>
</div>
</div>
</div>
</div>
<div style="background: #ffffff; border-width: .1em .1em .1em .8em; border: none; overflow: auto; padding: .2em .6em; width: auto;">
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
21</pre>
</td><td><pre style="line-height: 125%; margin: 0;"><span style="color: #008800; font-weight: bold;">private</span> <span style="color: #008800; font-weight: bold;">static</span> <span style="color: #333399; font-weight: bold;">void</span> <span style="color: #0066bb; font-weight: bold;">findSafeColumn</span><span style="color: #333333;">(</span><span style="color: #333399; font-weight: bold;">int</span> row<span style="color: #333333;">)</span> <span style="color: #333333;">{</span>
 <span style="color: #008800; font-weight: bold;">if</span> <span style="color: #333333;">(</span>row <span style="color: #333333;">==</span> <span style="color: #333333;">(</span>boardSize<span style="color: #333333;">))</span> <span style="color: #333333;">{</span>
  addBoard<span style="color: #333333;">();</span>
  <span style="color: #008800; font-weight: bold;">return</span><span style="color: #333333;">;</span>
 <span style="color: #333333;">}</span>
 
 <span style="color: #888888;">// iterate over each column</span>
 <span style="color: #008800; font-weight: bold;">for</span> <span style="color: #333333;">(</span><span style="color: #333399; font-weight: bold;">int</span> col <span style="color: #333333;">=</span> <span style="color: #0000dd; font-weight: bold;">0</span><span style="color: #333333;">;</span> col <span style="color: #333333;">&lt;</span> boardSize<span style="color: #333333;">;</span> col<span style="color: #333333;">++)</span> <span style="color: #333333;">{</span>
  <span style="color: #008800; font-weight: bold;">if</span> <span style="color: #333333;">(</span>isSafe<span style="color: #333333;">(</span>row<span style="color: #333333;">,</span> col<span style="color: #333333;">))</span> <span style="color: #333333;">{</span>
   placeQueen<span style="color: #333333;">(</span>row<span style="color: #333333;">,</span> col<span style="color: #333333;">);</span>
   
   <span style="color: #888888;">// move on to next row</span>
   findSafeColumn<span style="color: #333333;">(</span>row <span style="color: #333333;">+</span> <span style="color: #0000dd; font-weight: bold;">1</span><span style="color: #333333;">);</span>

   <span style="color: #888888;">// when we have got here, means backTracked.</span>
   <span style="color: #888888;">// now remove the queen you have placed so as </span>
   <span style="color: #888888;">//to check the next col</span>
   removeQueen<span style="color: #333333;">(</span>row<span style="color: #333333;">,</span> col<span style="color: #333333;">);</span>
  <span style="color: #333333;">}</span>   
 <span style="color: #333333;">}</span>
<span style="color: #333333;">}</span>
</pre>
</td></tr>
</tbody></table>
</div>
<div>
<br />
This is the main outline of the whole program.</div>
<div>
<br /></div>
<div>
Line 2 forms the base case, that is, if the variable row becomes equal to the size of the board, then the present configuration can be added as one of the solutions.<br />
The method <code> addBoard() </code> does exactly that.<br />
<br />
The methods <code> placeQueen() </code> and <code> removeQueen() </code> will be described later.<br />
<br />
<h3 style="text-align: left;">
How to implement the chess board?</h3>
We can implement a chess board using a 2-D boolean array, like,<br />
<br />
private static boolean[][] board;<br />
<br />
We also keep track of the board size, as we need it at many places later.<br />
<br />
private static int boardSize;<br />
<br />
<h3 style="text-align: left;">
Implementing <code> placeQueen() </code>, <code> removeQueen() </code> , and <code> isSafe()</code></h3>
It seems a 2- dimentional array is sufficient to implement placeQueen() and removeQueen functions as follows:<br />
<br />
private void placeQueen(int row, int col) {<br />
<span class="Apple-tab-span" style="white-space: pre;"> </span>board[row][col] = true;<br />
}<br />
private void removeQueen(int row, int col) {<br />
<span class="Apple-tab-span" style="white-space: pre;"> </span>board[row][col] = false;<br />
}<br />
<br />
But, the method isSafe() becomes too complex.<br />
<br />
A workaround this problem is introducing the following data structures (array of booleans):<br />
<br />
private static boolean[] colEmpty;<br />
private static boolean[] upDiagEmpty;<br />
private static boolean[] downDiagEmpty;<br />
<br />
An entry in one of these arrays is<br />
<span class="Apple-tab-span" style="white-space: pre;"> </span>true if no queen is placed in the corresponding column or diagonal,<br />
<span class="Apple-tab-span" style="white-space: pre;"> </span>false otherwise<br />
<span class="Apple-tab-span" style="white-space: pre;"> </span><br />
But now we need to map these boolean arrays to our 2 dimentional board:<br />
<table cellpadding="0" cellspacing="0" class="tr-caption-container" style="float: left; text-align: left;"><tbody>
<tr><td style="text-align: center;"><a href="http://4.bp.blogspot.com/-qiH-64xzPN4/VoV85r-YqyI/AAAAAAAAAsQ/OprNx8Q_AXM/s1600/DownDiag.png" imageanchor="1" style="clear: left; margin-bottom: 1em; margin-left: auto; margin-right: auto;"><img border="0" src="http://4.bp.blogspot.com/-qiH-64xzPN4/VoV85r-YqyI/AAAAAAAAAsQ/OprNx8Q_AXM/s1600/DownDiag.png" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">upDiagonal = row + col</td></tr>
</tbody></table>
<br />
<table><tbody>
<tr><td><br /></td><td></td></tr>
</tbody></table>
<br />
<br /></div>
<div style="text-align: left;">
</div>
<br />
<div class="separator" style="clear: both; text-align: center;">
<br /></div>
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: 1em; margin-right: 1em; text-align: left;"><tbody>
<tr><td style="text-align: center;"><a href="http://3.bp.blogspot.com/-znpNqpsZHR8/VoV85sEp0hI/AAAAAAAAAsM/CVq84A0BCEg/s1600/UpDiag.png" imageanchor="1" style="clear: left; margin-bottom: 1em; margin-left: auto; margin-right: auto;"><img border="0" src="http://3.bp.blogspot.com/-znpNqpsZHR8/VoV85sEp0hI/AAAAAAAAAsM/CVq84A0BCEg/s1600/UpDiag.png" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">downDiagonal = (boardSize - 1) + row - col</td></tr>
</tbody></table>
<div class="separator" style="clear: both; text-align: left;">
<br /></div>
<div class="separator" style="clear: both; text-align: left;">
We use these additional arrays as follows:</div>
<div class="separator" style="clear: both; text-align: left;">
<br /></div>
<div style="background: #ffffff; border-width: .1em .1em .1em .8em; border: none; overflow: auto; padding: .2em .6em; width: auto;">
<table><tbody>
<tr><td><pre style="line-height: 125%; margin: 0;">1
2
3
4
5
6</pre>
</td><td><pre style="line-height: 125%; margin: 0;"><span style="color: #008800; font-weight: bold;">private</span> <span style="color: #008800; font-weight: bold;">static</span> <span style="color: #333399; font-weight: bold;">void</span> <span style="color: #0066bb; font-weight: bold;">removeQueen</span><span style="color: #333333;">(</span><span style="color: #333399; font-weight: bold;">int</span> row<span style="color: #333333;">,</span> <span style="color: #333399; font-weight: bold;">int</span> col<span style="color: #333333;">)</span> <span style="color: #333333;">{</span>
 board<span style="color: #333333;">[</span>row<span style="color: #333333;">][</span>col<span style="color: #333333;">]</span> <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">false</span><span style="color: #333333;">;</span>
 colEmpty<span style="color: #333333;">[</span>col<span style="color: #333333;">]</span> <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">true</span><span style="color: #333333;">;</span>
 upDiagEmpty<span style="color: #333333;">[</span>row <span style="color: #333333;">+</span> col<span style="color: #333333;">]</span> <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">true</span><span style="color: #333333;">;</span>
 downDiagEmpty<span style="color: #333333;">[</span>boardSize <span style="color: #333333;">-</span> <span style="color: #0000dd; font-weight: bold;">1</span> <span style="color: #333333;">+</span> row <span style="color: #333333;">-</span> col<span style="color: #333333;">]</span> <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">true</span><span style="color: #333333;">;</span>
<span style="color: #333333;">}</span>
</pre>
</td></tr>
</tbody></table>
</div>
<br />
<div style="background: #ffffff; border-width: .1em .1em .1em .8em; border: none; overflow: auto; padding: .2em .6em; width: auto;">
<table><tbody>
<tr><td><pre style="line-height: 125%; margin: 0;">1
2
3
4
5
6</pre>
</td><td><pre style="line-height: 125%; margin: 0;"><span style="color: #008800; font-weight: bold;">private</span> <span style="color: #008800; font-weight: bold;">static</span> <span style="color: #333399; font-weight: bold;">void</span> <span style="color: #0066bb; font-weight: bold;">placeQueen</span><span style="color: #333333;">(</span><span style="color: #333399; font-weight: bold;">int</span> row<span style="color: #333333;">,</span> <span style="color: #333399; font-weight: bold;">int</span> col<span style="color: #333333;">)</span> <span style="color: #333333;">{</span>
 board<span style="color: #333333;">[</span>row<span style="color: #333333;">][</span>col<span style="color: #333333;">]</span> <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">true</span><span style="color: #333333;">;</span>
 colEmpty<span style="color: #333333;">[</span>col<span style="color: #333333;">]</span> <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">false</span><span style="color: #333333;">;</span>
 upDiagEmpty<span style="color: #333333;">[</span>row <span style="color: #333333;">+</span> col<span style="color: #333333;">]</span> <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">false</span><span style="color: #333333;">;</span>
 downDiagEmpty<span style="color: #333333;">[</span>boardSize <span style="color: #333333;">-</span> <span style="color: #0000dd; font-weight: bold;">1</span> <span style="color: #333333;">+</span> row <span style="color: #333333;">-</span> col<span style="color: #333333;">]</span> <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">false</span><span style="color: #333333;">;</span>
<span style="color: #333333;">}</span>
</pre>
</td></tr>
</tbody></table>
</div>
<div style="background: #ffffff; border-width: .1em .1em .1em .8em; border: none; overflow: auto; padding: .2em .6em; width: auto;">
<table><tbody>
<tr><td><pre style="line-height: 125%; margin: 0;">1
2
3
4
5
6
7
8
9</pre>
</td><td><pre style="line-height: 125%; margin: 0;"><span style="color: #008800; font-weight: bold;">private</span> <span style="color: #008800; font-weight: bold;">static</span> <span style="color: #333399; font-weight: bold;">boolean</span> <span style="color: #0066bb; font-weight: bold;">isSafe</span><span style="color: #333333;">(</span><span style="color: #333399; font-weight: bold;">int</span> row<span style="color: #333333;">,</span> <span style="color: #333399; font-weight: bold;">int</span> col<span style="color: #333333;">)</span> <span style="color: #333333;">{</span>
 <span style="color: #888888;">// if col &amp; up diag &amp; down diag is empty, then the given position is</span>
 <span style="color: #888888;">// safe</span>
 <span style="color: #008800; font-weight: bold;">if</span> <span style="color: #333333;">(</span>colEmpty<span style="color: #333333;">[</span>col<span style="color: #333333;">]</span> <span style="color: #333333;">&amp;&amp;</span> upDiagEmpty<span style="color: #333333;">[</span>row <span style="color: #333333;">+</span> col<span style="color: #333333;">]</span>
   <span style="color: #333333;">&amp;&amp;</span> downDiagEmpty<span style="color: #333333;">[</span>boardSize <span style="color: #333333;">-</span> <span style="color: #0000dd; font-weight: bold;">1</span> <span style="color: #333333;">+</span> row <span style="color: #333333;">-</span> col<span style="color: #333333;">])</span> <span style="color: #333333;">{</span>
  <span style="color: #008800; font-weight: bold;">return</span> <span style="color: #008800; font-weight: bold;">true</span><span style="color: #333333;">;</span>
 <span style="color: #333333;">}</span>
 <span style="color: #008800; font-weight: bold;">return</span> <span style="color: #008800; font-weight: bold;">false</span><span style="color: #333333;">;</span>
<span style="color: #333333;">}</span>
</pre>
</td></tr>
</tbody></table>
</div>
<br />
To save all the solutions of N-Queens problem, we can have an arraylist named <code> solutions </code> as follows:<br />
static ArrayList&lt;ArrayList&lt;String&gt;&gt; solutions;<br />
<br />
Method that initializes all the data structures used and calls the recursive <code> findSafeColumn() </code> method:<br />
<div style="background: #ffffff; border-width: .1em .1em .1em .8em; border: none; overflow: auto; padding: .2em .6em; width: auto;">
<table><tbody>
<tr><td><pre style="line-height: 125%; margin: 0;">&nbsp;</pre>
<pre style="line-height: 125%; margin: 0;"></pre>
<pre style="line-height: 125%; margin: 0;"> 1
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
18</pre>
</td><td><pre style="line-height: 125%; margin: 0;"><span style="color: #008800; font-weight: bold;">
</span></pre>
<pre style="line-height: 125%; margin: 0;"><span style="color: #008800; font-weight: bold; line-height: 125%;">public</span><span style="line-height: 125%;"> </span><span style="color: #008800; font-weight: bold; line-height: 125%;">static</span><span style="line-height: 125%;"> </span><span style="color: #333399; font-weight: bold; line-height: 125%;">void</span><span style="line-height: 125%;"> </span><span style="color: #0066bb; font-weight: bold; line-height: 125%;">solveNQueens</span><span style="color: #333333; line-height: 125%;">(</span><span style="color: #333399; font-weight: bold; line-height: 125%;">int</span><span style="line-height: 125%;"> n</span><span style="color: #333333; line-height: 125%;">)</span><span style="line-height: 125%;"> </span><span style="color: #333333; line-height: 125%;">{</span></pre>
<pre style="line-height: 125%; margin: 0;"> <span style="color: #888888;">// take the board as a boolean array. A true value indicates the</span>
 <span style="color: #888888;">// presence of queen.</span>
 board <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">new</span> <span style="color: #333399; font-weight: bold;">boolean</span><span style="color: #333333;">[</span>n<span style="color: #333333;">][</span>n<span style="color: #333333;">];</span>
 boardSize <span style="color: #333333;">=</span> n<span style="color: #333333;">;</span>
 solutions <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">new</span> ArrayList<span style="color: #333333;">&lt;</span>ArrayList<span style="color: #333333;">&lt;</span>String<span style="color: #333333;">&gt;&gt;();</span>
 colEmpty <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">new</span> <span style="color: #333399; font-weight: bold;">boolean</span><span style="color: #333333;">[</span>n<span style="color: #333333;">];</span>
 upDiagEmpty <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">new</span> <span style="color: #333399; font-weight: bold;">boolean</span><span style="color: #333333;">[</span><span style="color: #0000dd; font-weight: bold;">2</span> <span style="color: #333333;">*</span> n <span style="color: #333333;">-</span> <span style="color: #0000dd; font-weight: bold;">1</span><span style="color: #333333;">];</span>
 downDiagEmpty <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">new</span> <span style="color: #333399; font-weight: bold;">boolean</span><span style="color: #333333;">[</span><span style="color: #0000dd; font-weight: bold;">2</span> <span style="color: #333333;">*</span> n <span style="color: #333333;">-</span> <span style="color: #0000dd; font-weight: bold;">1</span><span style="color: #333333;">];</span>
 Arrays<span style="color: #333333;">.</span><span style="color: #0000cc;">fill</span><span style="color: #333333;">(</span>colEmpty<span style="color: #333333;">,</span><span style="color: #008800; font-weight: bold;">true</span><span style="color: #333333;">);</span>
 Arrays<span style="color: #333333;">.</span><span style="color: #0000cc;">fill</span><span style="color: #333333;">(</span>upDiagEmpty<span style="color: #333333;">,</span> <span style="color: #008800; font-weight: bold;">true</span><span style="color: #333333;">);</span>
 Arrays<span style="color: #333333;">.</span><span style="color: #0000cc;">fill</span><span style="color: #333333;">(</span>downDiagEmpty<span style="color: #333333;">,</span> <span style="color: #008800; font-weight: bold;">true</span><span style="color: #333333;">);</span>

 <span style="color: #888888;">// try the first row</span>
 findSafeColumn<span style="color: #333333;">(</span><span style="color: #0000dd; font-weight: bold;">0</span><span style="color: #333333;">);</span>
  
 <span style="color: #888888;">//return solutions;</span>
<span style="color: #333333;">}</span>
</pre>
</td></tr>
</tbody></table>
</div>
<br />
The method <code> addBoard() </code> is used to fill up the solutions arrayList:<br />
<div>
<br /></div>
<div style="background: #ffffff; border-width: .1em .1em .1em .8em; border: none; overflow: auto; padding: .2em .6em; width: auto;">
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
14</pre>
</td><td><pre style="line-height: 125%; margin: 0;"><span style="color: #008800; font-weight: bold;">private</span> <span style="color: #008800; font-weight: bold;">static</span> <span style="color: #333399; font-weight: bold;">void</span> <span style="color: #0066bb; font-weight: bold;">addBoard</span><span style="color: #333333;">()</span> <span style="color: #333333;">{</span>
 ArrayList<span style="color: #333333;">&lt;</span>String<span style="color: #333333;">&gt;</span> boardList <span style="color: #333333;">=</span> <span style="color: #008800; font-weight: bold;">new</span> ArrayList<span style="color: #333333;">&lt;&gt;();</span>
 <span style="color: #008800; font-weight: bold;">for</span><span style="color: #333333;">(</span><span style="color: #333399; font-weight: bold;">int</span> i<span style="color: #333333;">=</span><span style="color: #0000dd; font-weight: bold;">0</span><span style="color: #333333;">;</span> i<span style="color: #333333;">&lt;</span>boardSize<span style="color: #333333;">;</span>i<span style="color: #333333;">++){</span>
  String row <span style="color: #333333;">=</span> <span style="background-color: #fff0f0;">""</span><span style="color: #333333;">;</span>
  <span style="color: #008800; font-weight: bold;">for</span><span style="color: #333333;">(</span><span style="color: #333399; font-weight: bold;">int</span> j<span style="color: #333333;">=</span><span style="color: #0000dd; font-weight: bold;">0</span><span style="color: #333333;">;</span>j<span style="color: #333333;">&lt;</span>boardSize<span style="color: #333333;">;</span>j<span style="color: #333333;">++){</span>
   <span style="color: #008800; font-weight: bold;">if</span><span style="color: #333333;">(</span>board<span style="color: #333333;">[</span>i<span style="color: #333333;">][</span>j<span style="color: #333333;">])</span>
    row <span style="color: #333333;">=</span> row<span style="color: #333333;">.</span><span style="color: #0000cc;">concat</span><span style="color: #333333;">(</span><span style="background-color: #fff0f0;">"Q"</span><span style="color: #333333;">);</span>
   <span style="color: #008800; font-weight: bold;">else</span>
    row <span style="color: #333333;">=</span> row<span style="color: #333333;">.</span><span style="color: #0000cc;">concat</span><span style="color: #333333;">(</span><span style="background-color: #fff0f0;">"."</span><span style="color: #333333;">);</span>
  <span style="color: #333333;">}</span>
  boardList<span style="color: #333333;">.</span><span style="color: #0000cc;">add</span><span style="color: #333333;">(</span>row<span style="color: #333333;">);</span>
 <span style="color: #333333;">}</span>
 solutions<span style="color: #333333;">.</span><span style="color: #0000cc;">add</span><span style="color: #333333;">(</span>boardList<span style="color: #333333;">);</span>
<span style="color: #333333;">}</span>
</pre>
</td></tr>
</tbody></table>
</div>
<br />
We're done!<br />
Call the main method as:<br />
<div>
<br /></div>
<div style="background: #ffffff; border-width: .1em .1em .1em .8em; border: none; overflow: auto; padding: .2em .6em; width: auto;">
<table><tbody>
<tr><td><pre style="line-height: 125%; margin: 0;">1
2
3
4
5
6</pre>
</td><td><pre style="line-height: 125%; margin: 0;"><span style="color: #008800; font-weight: bold;">public</span> <span style="color: #008800; font-weight: bold;">static</span> <span style="color: #333399; font-weight: bold;">void</span> <span style="color: #0066bb; font-weight: bold;">main</span><span style="color: #333333;">(</span>String<span style="color: #333333;">[]</span> args<span style="color: #333333;">)</span> <span style="color: #333333;">{</span>
  
 solveNQueens<span style="color: #333333;">(</span><span style="color: #0000dd; font-weight: bold;">8</span><span style="color: #333333;">);</span>
 System<span style="color: #333333;">.</span><span style="color: #0000cc;">out</span><span style="color: #333333;">.</span><span style="color: #0000cc;">println</span><span style="color: #333333;">(</span>solutions<span style="color: #333333;">.</span><span style="color: #0000cc;">toString</span><span style="color: #333333;">());</span>

<span style="color: #333333;">}</span>
</pre>
</td></tr>
</tbody></table>
</div>
<div class="separator" style="clear: both; text-align: left;">
<br /></div>
<div class="separator" style="clear: both;">
The output shown for 4 Queens is:</div>
<div class="separator" style="clear: both;">
[[.Q.., ...Q, Q..., ..Q.], [..Q., Q..., ...Q, .Q..]]</div>
<div>
<br /></div>
<div>
Click <a href="https://github.com/amita-shukla/programs/blob/master/NQueens.java" target="_blank">here</a>&nbsp;to get the complete code.</div>
<div>
<br /></div>
</div>
