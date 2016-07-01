Normalization in Databases
http://shuklaamita.blogspot.com/2016/07/normalization-in-databases.html

<div dir="ltr" style="text-align: left;" trbidi="on">
In my previous <a href="http://shuklaamita.blogspot.in/2016/06/relational-database-functional-dependencies-canonical-cover-keys.html">post</a>, we&nbsp;discussed Relational Database Design. To store data effectively, we must ensure that the data is non-redundant. This reduces conflicts. But how to design such a database that the conflicts are reduced? The answer lies in Normalization.<br />
<br />
<!--more--><br />
A database designed keeping in mind normalization techniques leads to a more robust design and avoid the problems that can crop up later. This design&nbsp;is viewed in terms of Functional Dependencies, that we studied in the previous post.<br />
Remember that a relation containing only 2 attributes is always normalized.<br />
<br />
Let's start now.<br />
<br />
<h3 style="text-align: left;">
<span style="font-weight: normal;">First Normal Form</span></h3>
The first states a simple rule : If all attributes in a relation are atomic, then the relation is in First Normal Form.<br />
<h4 style="text-align: left;">
<span style="font-weight: normal;">What does it mean for an attribute to be atomic?</span></h4>
An atomic attribute means that the values of that attribute can not be further divided.<br />
<br />
Suppose a relation has an attribute called 'Name'. Now, a name can have sub-attributes like First Name, Middle Name, and Last Name. In this case, instead of having one attribute, we should divide it into separate attributes. Therefore, we should delete the attribute 'Name' and place 3 attributes : 'First Name', 'Middle Name' and 'Last Name'.<br />
<br />
<br />
<h3 style="text-align: left;">
<span style="font-weight: normal;">Second Normal Form</span></h3>
<div>
Any relation is said to be in Second Normal Form:</div>
<div>
<ul style="text-align: left;">
<li>if it is in First Normal Form, and</li>
<li>all non-prime attributes are fully, functionally dependent on the candidate key.</li>
</ul>
<div>
To check if a relation is in Second Normal Form,&nbsp;</div>
<div>
<ul style="text-align: left;">
<li>find the Candidate Key. To know how to find candidate key in a relation, check my previous post :<a href="http://shuklaamita.blogspot.in/2016/06/relational-database-functional-dependencies-canonical-cover-keys.html"> Relational Database Design</a></li>
<li>Find <b>Prime attributes</b>. &nbsp;Prime Attributes are those attributes that comprise a candidate key. So, if a Relation(ABC) has AB as its primary key, then A and B are prime attributes.</li>
<li>Find <b>Non-Prime attributes</b>. All those attributes that are not prime are non-prime attributes (that was simple :D) . Hence, as in the above example, C is a non-prime attribute.</li>
</ul>
<div>
Let's elaborate on what is a fully functional dependency before moving further.&nbsp;</div>
</div>
</div>
<h4 style="text-align: left;">
<span style="font-weight: normal;">Fully Functional Dependency</span></h4>
<div>
<span style="font-weight: normal;">For an FD to be fully functional, any subset of the candidate key (i.e. the prime attributes) should not determine any non-prime attribute.If so happens, it is called as </span><b>Partial Dependency</b>.</div>
<div>
<span style="font-weight: normal;"><br /></span></div>
<div>
<span style="font-weight: normal;">Consider the following diagrams for a relation R(ABCD), here the arrows represent dependency.</span></div>
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://1.bp.blogspot.com/-B98Be2W44Mc/V3ZPh8bumSI/AAAAAAAABOs/TlFmJii3KfAzo0tc3VQBA521ZHR1JtoJACLcB/s1600/Fully%252BFunctional%252BDependency.png" style="margin-left: auto; margin-right: auto;"><img border="0" src="https://1.bp.blogspot.com/-B98Be2W44Mc/V3ZPh8bumSI/AAAAAAAABOs/TlFmJii3KfAzo0tc3VQBA521ZHR1JtoJACLcB/s1600/Fully%252BFunctional%252BDependency.png" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Fully Functional Dependency</td></tr>
</tbody></table>
<div>
<span style="font-weight: normal;"><br /></span></div>
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://2.bp.blogspot.com/-0C0A464XgsU/V3ZP-adQklI/AAAAAAAABOw/FTrTT_26-aQo6isUxeJ9ft12_DnZ2XSzACLcB/s1600/Partial%252BDependency.png" style="margin-left: auto; margin-right: auto;"><img border="0" src="https://2.bp.blogspot.com/-0C0A464XgsU/V3ZP-adQklI/AAAAAAAABOw/FTrTT_26-aQo6isUxeJ9ft12_DnZ2XSzACLcB/s1600/Partial%252BDependency.png" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Partial Dependency</td></tr>
</tbody></table>
<div>
<span style="font-weight: normal;"><br /></span></div>
<div>
<span style="font-weight: normal;"><br /></span></div>
<div>
You might think, what if one non-prime attribute determines another non-prime attribute? Wait wait. We will get to that.</div>
<div>
<br /></div>
<div>
But first, we must discuss what should be done if we find a relation&nbsp;that is not in 2 NF.&nbsp;</div>
<h4 style="text-align: left;">
<span style="font-weight: normal;">Decomposing a relation into 2NF</span></h4>
<div>
A relation can be decomposed into multiple relations in 2NF. The partial dependencies with the same attribute on the left are combined together to form a separate relation. Consider the following diagram:</div>
<div class="separator" style="clear: both; text-align: center;">
<a href="https://4.bp.blogspot.com/-0C0A464XgsU/V3ZP-adQklI/AAAAAAAABO4/F7NmOheyNVcuoBMjewiACIDMU2VaoC_4ACKgB/s1600/Partial%252BDependency.png" style="margin-left: 1em; margin-right: 1em;"><img border="0" src="https://4.bp.blogspot.com/-0C0A464XgsU/V3ZP-adQklI/AAAAAAAABO4/F7NmOheyNVcuoBMjewiACIDMU2VaoC_4ACKgB/s1600/Partial%252BDependency.png" /></a></div>
<div>
<br /></div>
<div>
<br /></div>
<div>
Here,&nbsp;</div>
<div>
AB&nbsp;<span style="background-color: white; color: #222222; font-family: Lora; font-size: 15px; line-height: 26.25px;">→&nbsp;</span>C : full</div>
<div>
AB&nbsp;<span style="background-color: white; color: #222222; font-family: Lora; font-size: 15px; line-height: 26.25px;">→&nbsp;</span>D : full</div>
<div>
B&nbsp;<span style="background-color: white; color: #222222; font-family: Lora; font-size: 15px; line-height: 26.25px;">→&nbsp;</span>C &nbsp; &nbsp;: partial</div>
<div>
<br /></div>
<div>
Therefore R(AB, C, D ) can be decomposed into:&nbsp;</div>
<div>
R1(AB, C, D) [Primary Key: AB]</div>
<div>
R2(B, C) [Primary Key : B] &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</div>
<div>
<br /></div>
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://3.bp.blogspot.com/-B98Be2W44Mc/V3ZPh8bumSI/AAAAAAAABO0/XkJIIb8ceRQovPz-IwS8K314RRjJ2JXAgCKgB/s1600/Fully%252BFunctional%252BDependency.png" style="margin-left: auto; margin-right: auto;"><img border="0" src="https://3.bp.blogspot.com/-B98Be2W44Mc/V3ZPh8bumSI/AAAAAAAABO0/XkJIIb8ceRQovPz-IwS8K314RRjJ2JXAgCKgB/s1600/Fully%252BFunctional%252BDependency.png" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">R1 in 2 NF</td></tr>
</tbody></table>
<br />
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://3.bp.blogspot.com/-9WgR-Qd_Bjo/V3acYI8RLtI/AAAAAAAABQA/keQ8eI1g7PASQSzeX2tgb3LQj3HjVKFGwCLcB/s1600/R2%252BIn%252B2%252BNF.png" style="margin-left: auto; margin-right: auto;"><img border="0" src="https://3.bp.blogspot.com/-9WgR-Qd_Bjo/V3acYI8RLtI/AAAAAAAABQA/keQ8eI1g7PASQSzeX2tgb3LQj3HjVKFGwCLcB/s1600/R2%252BIn%252B2%252BNF.png" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">R2 in 2NF</td></tr>
</tbody></table>
<div>
<br /></div>
<div>
Note that when the candidate key contains a single attribute, the need for looking up for full or partial dependencies is eliminated, as no subset of the candidate key is possible.</div>
<div>
Hence, such a relation is automatically in 2NF. You can <b>save</b>&nbsp;yourself from all the above analysis :P</div>
<div>
<br /></div>
<h3 style="text-align: left;">
<span style="font-weight: normal;">Third Normal Form</span></h3>
<div>
<span style="font-weight: normal;">A relation is in 3NF if it is in 2NF and all non-prime attributes are non-transitively dependent on candidate key.</span></div>
<div>
<span style="font-weight: normal;">Consider the following diagram for a relation R(ABCD) with FDs:</span></div>
<div>
<span style="font-weight: normal;">AB&nbsp;</span><span style="background-color: white; color: #222222; font-family: Lora; font-size: 15px; line-height: 26.25px;">→&nbsp;</span>C</div>
<div>
<span style="font-weight: normal;">AB&nbsp;</span><span style="background-color: white; color: #222222; font-family: Lora; font-size: 15px; line-height: 26.25px;">→&nbsp;</span>D</div>
<div>
C&nbsp;<span style="background-color: white; color: #222222; font-family: Lora; font-size: 15px; line-height: 26.25px;">→&nbsp;</span>D</div>
<div class="separator" style="clear: both; text-align: center;">
<a href="https://2.bp.blogspot.com/-qI9BVFFvhew/V3Z6DSi7HAI/AAAAAAAABPM/kb4YvKwHaHcQC_q1NfZ_ZTsBQrPnPi-EACLcB/s1600/Not%252BIn%252B3NF.png" style="margin-left: 1em; margin-right: 1em;"><img border="0" src="https://2.bp.blogspot.com/-qI9BVFFvhew/V3Z6DSi7HAI/AAAAAAAABPM/kb4YvKwHaHcQC_q1NfZ_ZTsBQrPnPi-EACLcB/s1600/Not%252BIn%252B3NF.png" /></a></div>
<div>
<br /></div>
<div>
Here C is said to be transitively dependent on D. You can take it as, D has two owners:&nbsp;C, and AB. This can cause conflict in the schemas, at the time of insertion, deletion or updation.</div>
<div>
<br /></div>
<div>
The wait ends here. The above diagram is very well in 2nd Normal Form but violates the rule of the Third Normal Form.</div>
<div>
<br /></div>
<h4 style="text-align: left;">
<span style="font-weight: normal;">Decomposition of a relation into 3NF</span></h4>
<div>
<span style="font-weight: normal;">The above relation R can be decomposed into two relations:</span></div>
<div>
<span style="font-weight: normal;">R1(ABC) [Primary Key : AB]</span></div>
<div>
<span style="font-weight: normal;">R2(CD) [Primary Key : C]</span></div>
<div>
<span style="font-weight: normal;"><br /></span></div>
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://2.bp.blogspot.com/-KvqlY8he8iA/V3Z60tnXBFI/AAAAAAAABPU/oWcSwgouNdwYob6edEEgVGwU5LpElQpIACLcB/s1600/R1%252BIn%252B3NF.png" style="margin-left: auto; margin-right: auto;"><img border="0" src="https://2.bp.blogspot.com/-KvqlY8he8iA/V3Z60tnXBFI/AAAAAAAABPU/oWcSwgouNdwYob6edEEgVGwU5LpElQpIACLcB/s1600/R1%252BIn%252B3NF.png" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">R1 in 3 NF</td></tr>
</tbody></table>
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://3.bp.blogspot.com/-tkrREusspjI/V3Z7p5Umo5I/AAAAAAAABPg/8fIy1QK1SkciNk45AVpFCpKftFgQ5ZoKQCLcB/s1600/R2%252BIn%252B3NF.png" style="margin-left: auto; margin-right: auto;"><img border="0" src="https://3.bp.blogspot.com/-tkrREusspjI/V3Z7p5Umo5I/AAAAAAAABPg/8fIy1QK1SkciNk45AVpFCpKftFgQ5ZoKQCLcB/s1600/R2%252BIn%252B3NF.png" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">R2 in 3 NF</td></tr>
</tbody></table>
<div>
<span style="font-weight: normal;"><br /></span></div>
<div>
<span style="font-weight: normal;"><br /></span></div>
<div>
<span style="font-weight: normal;">Steps to decompose a relation into 3NF :&nbsp;</span></div>
<div>
<ul style="text-align: left;">
<li>Find Canonical Cover</li>
<li>Find Candidate Key</li>
<li>Consider all the FDs a new relation</li>
<li>Combine those relations where the primary key is same.</li>
<li>If none of the decomposed relations contain candidate key, add a new relation containing candidate key.</li>
</ul>
<h3 style="text-align: left;">
<span style="font-weight: normal;">Boyce-Codd Normal Form</span></h3>
</div>
<div>
<span style="font-weight: normal;">A relation is said to be in BCNF if all determinants are candidate keys.</span></div>
<div>
<ul style="text-align: left;">
<li>Find Non-Redundant Cover.</li>
<li>Determine the candidate key.</li>
<li>Compare with determinants.</li>
</ul>
<div>
Below is an example depicting a relation which is in 3 NF but not in BCNF:</div>
</div>
<div>
<br /></div>
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://3.bp.blogspot.com/-QbabxlUaZlc/V3aduDnAolI/AAAAAAAABQM/DIZz7GxyrIQQKaBZm0S_PXgHZxjzeXClgCLcB/s1600/Not%252BIn%252B3NF.png" style="margin-left: auto; margin-right: auto;"><img border="0" src="https://3.bp.blogspot.com/-QbabxlUaZlc/V3aduDnAolI/AAAAAAAABQM/DIZz7GxyrIQQKaBZm0S_PXgHZxjzeXClgCLcB/s1600/Not%252BIn%252B3NF.png" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">In 3 NF but NOT in BCNF</td></tr>
</tbody></table>
<div>
<br /></div>
<div>
The above are prominent Normal Forms that&nbsp;exist, and implied upon during database modeling.&nbsp;</div>
<div>
However, normalizing 'too' much a database can completely dissolve the purpose of a database. It can give rise to many small relations related to each other in a complex way.&nbsp;</div>
<div>
Therefore, the designers need to maintain a trade-off between normalization and performance. Some designers choose the other way: they deliberately store redundant data to improve search performance.</div>
<div>
<br /></div>
<div>
<br /></div>
<div>
<br /></div>
</div>
