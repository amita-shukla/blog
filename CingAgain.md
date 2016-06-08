<div dir="ltr" style="text-align: left;" trbidi="on">
<div dir="ltr" style="text-align: left;" trbidi="on">
As I was checking out some programming questions on the topic linked list, it was boring to just read the programs without implementing them.<br />
So, I decided to try out linked list again, trying to devise out some more efficient ways to solve a very simple problem.<br />
But before playing with the list, I needed to create a list.<br />
<br />
During the process, I revised an old concept:<br />
Why do we need to use double pointer whenever we need to change the head pointer?<br />
The function that I had to write was <code>insbgn()</code>.<br />
<br />
<b>Insertion at the beginning of the list:</b><br />
<br />
Initial declarations:<br />
<pre style="background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;"> struct node{  
     int data;  
     struct node *next;  
 };  
   
 typedef struct node *nodeptr;  
</code></pre>
<br />
On can think of the following implementation:<br />
<pre style="background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;"> void insbgn(nodeptr head, int data){  
     nodeptr p = getnode();  
     p-&gt;next = head;  
     head = p;      
 }  
</code></pre>
<br />
But you will observe no changes if you make a call to this function:<br />
<pre style="background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;"> print(head); //output: 1 2 3 4 5 6  
 insbgn(head, 0);  
 print(head); //output 1 2 3 4 5 6     
</code></pre>
<br />
This is because the head pointer is changing here.<br />
when <code> insbgn() </code> is called,<br />
the pointer 'head' points to the head of the list.<br />
Changes are made to the list accordingly but as soon as the function returns, the changes to the head are lost.<br />
<br />
To show this, if I call print(head) from inside insbgn():<br />
<pre style="background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;"> void insbgn(nodeptr head, int data){  
     nodeptr p = getnode();  
     p-&gt;next = head;  
     head = p;  
     print(head);      
 }  </code></pre>
</div>
<br />
The output is:<br />
<br />
<pre style="background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;"> print(head); //output: 1 2 3 4 5 6  
 insbgn(head, 0); //output: 0 1 2 3 4 5 6  
 print(head); //output 1 2 3 4 5 6  
</code></pre>
<br />
Hence you need to pass double pointer, i.e. pointer to the head pointer.<br />
<br />
So, the correct way to define <code> insbgn() </code> is as follows:<br />
<br />
<pre style="background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;"> void insbgn(nodeptr *headptr, int data){ //you get a pointer to the head pointer  
     nodeptr p = getnode(data);  
     p-&gt;next = *headptr; // p-&gt;next points to the value at headptr, i.e. the head of the list  
     *headptr = p; // the value at headptr is set to p, i.e., head = p.  
 }   
</code></pre>
<br />
As we have the pointer to the head, we can easily dereference it and manipulate the real head.<br />
If you do not know any other example than the swap problem for pass by value and pass by reference, this is another one you can count on!<br />
But if you really want to use the previous version, you will need to return the new head back:<br />
<br />
<pre style="background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;"> nodeptr insbgn(nodeptr head, int data){  
      nodeptr p = getnode(data);  
      p-&gt;next = head;     head = p;  
     printf("Linked list inside insbgn\n");  
      print(head);  
      printf("\n");  
      return head;  
  }  
</code></pre>
<br />
&nbsp;And call it like:<br />
&nbsp;
<code>head = insbgn(head,data);&nbsp;</code><br />
The problem with this approach is that you can assign the new head, and later go mad figuring where you got wrong.</div>
