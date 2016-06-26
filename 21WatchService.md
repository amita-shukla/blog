#JAVA API for recording changes in a directory

http://shuklaamita.blogspot.in/2016/06/java-watch-service-api-file-change-notification.html

<div dir="ltr" style="text-align: left;" trbidi="on">
While I was making my <a href="https://github.com/amita-shukla/file-scanner" target="_blank">File Scanner Project</a>, the most initial task was to set a watch over given property files. If any change occurred in any of the properties files, it had to be reported.<br />
<br />
<div class="separator" style="clear: both; text-align: center;">
<a href="https://1.bp.blogspot.com/-N5Lm08r-JlE/V2_r17fYbtI/AAAAAAAABNU/j_RBqo0FrUcmwsKKgRsuz65Eqg6QdytXQCLcB/s1600/JAVA_%2Bwatch_service_api.jpg" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img alt="Java+Watch+Service+api" border="0" src="https://1.bp.blogspot.com/-N5Lm08r-JlE/V2_r17fYbtI/AAAAAAAABNU/j_RBqo0FrUcmwsKKgRsuz65Eqg6QdytXQCLcB/s1600/JAVA_%2Bwatch_service_api.jpg" title="" /></a></div>
<br />
<br />
You may have seen this functionality in the form of 'file change notification'. Suppose you are writing a program, and the file is modified by some other program. You then see a notification saying to load the changes.<br />
Another time it may happen that you are working on a project with several files and any change in a file in the same project prompts a notification that a file is changed.<br />
<br />
To make this functionality, we need to keep a regular watch over the directory. One way we can think of is that we can poll the directory (file system) from time to time to record any changes.<br />
<br />
But the API that comes to our rescue is Watch Service API, in java.nio.file package.<br />
<br />
<h3 style="text-align: left;">
<span style="font-weight: normal;">How does Watch Service API work?</span></h3>
<div>
<span style="font-weight: normal;">When a watch service is initiated, a separate thread is launched that keeps track of the changes in the specified directory.</span></div>
<div>
From the main(), I call a method called runWatch(). This initiates the whole process.</div>
<div>
<br /></div>
<div>
</div>
<div>
As you can see I call a method of the WatchDir class.<br />
The WatchDir class contains the functionalities needed for watching over the directory.<br />
In the constructor, we can initiate the 'watcher'. The watcher is nothing but an instance of WatchService API, that will do the job for us.<br />
<br />
<br />
</div>
<div>
<br />
The register() assigns the watcher. Other events can also be specified, such as<br />
<br />
<ul style="text-align: left;">
<li>ENTRY_CREATE</li>
<li>ENTRY_DELETE</li>
<li>OVERFLOW</li>
</ul>
<div>
Next is the processEvents(). This method creates an infinite loop which polls for events and as and when they happen, it reports them.</div>
<div>
<br />
</div>
<div>
<br /></div>
<div>
<br /></div>
<div>
The processing events are described aptly in the Oracle WatchService API tutorial :&nbsp;</div>
<br />
<div style="font-family: Arial, Helvetica, sans-serif; font-size: 12.8px; line-height: 19.2px;">
The order of events in an event processing loop follow:</div>
<blockquote class="tr_bq">
<ol style="font-family: Arial, Helvetica, sans-serif; font-size: 12.8px; line-height: 19.2px;">
<li>Get a watch key. Three methods are provided:<ul>
<li><a class="APILink" href="https://docs.oracle.com/javase/8/docs/api/java/nio/file/WatchService.html#poll--" style="color: #3a87cf; cursor: pointer; text-decoration: none;" target="_blank"><code style="font-family: Monaco, Courier, 'Courier New';">poll</code></a>&nbsp;– Returns a queued key, if available. Returns immediately with a&nbsp;<code style="font-family: Monaco, Courier, 'Courier New';">null</code>&nbsp;value, if unavailable.</li>
<li><a class="APILink" href="https://docs.oracle.com/javase/8/docs/api/java/nio/file/WatchService.html#poll-long-java.util.concurrent.TimeUnit-" style="color: #3a87cf; cursor: pointer; text-decoration: none;" target="_blank"><code style="font-family: Monaco, Courier, 'Courier New';">poll(long, TimeUnit)</code></a>&nbsp;– Returns a queued key, if one is available. If a queued key is not immediately available, the program waits until the specified time. The<code style="font-family: Monaco, Courier, 'Courier New';">TimeUnit</code>&nbsp;argument determines whether the specified time is nanoseconds, milliseconds, or some other unit of time.</li>
<li><a class="APILink" href="https://docs.oracle.com/javase/8/docs/api/java/nio/file/WatchService.html#take--" style="color: #3a87cf; cursor: pointer; text-decoration: none;" target="_blank"><code style="font-family: Monaco, Courier, 'Courier New';">take</code></a>&nbsp;– Returns a queued key. If no queued key is available, this method waits.</li>
</ul>
</li>
<li>Process the pending events for the key. You fetch the&nbsp;<code style="font-family: Monaco, Courier, 'Courier New';">List</code>&nbsp;of&nbsp;<a class="APILink" href="https://docs.oracle.com/javase/8/docs/api/java/nio/file/WatchEvent.html" style="color: #3a87cf; cursor: pointer; text-decoration: none;" target="_blank"><code style="font-family: Monaco, Courier, 'Courier New';">WatchEvents</code></a>from the&nbsp;<a class="APILink" href="https://docs.oracle.com/javase/8/docs/api/java/nio/file/WatchKey.html#pollEvents--" style="color: #3a87cf; cursor: pointer; text-decoration: none;" target="_blank"><code style="font-family: Monaco, Courier, 'Courier New';">pollEvents</code></a>&nbsp;method.</li>
<li>Retrieve the type of event by using the&nbsp;<a class="APILink" href="https://docs.oracle.com/javase/8/docs/api/java/nio/file/WatchEvent.html#kind--" style="color: #3a87cf; cursor: pointer; text-decoration: none;" target="_blank"><code style="font-family: Monaco, Courier, 'Courier New';">kind</code></a>&nbsp;method. No matter what events the key has registered for, it is possible to receive an&nbsp;<code style="font-family: Monaco, Courier, 'Courier New';">OVERFLOW</code>&nbsp;event. You can choose to handle the overflow or ignore it, but you should test for it.</li>
<li>Retrieve the file name associated with the event. The file name is stored as the context of the event, so the&nbsp;<a class="APILink" href="https://docs.oracle.com/javase/8/docs/api/java/nio/file/WatchEvent.html#context--" style="color: #3a87cf; cursor: pointer; text-decoration: none;" target="_blank"><code style="font-family: Monaco, Courier, 'Courier New';">context</code></a>&nbsp;method is used to retrieve it.</li>
<li>After the events for the key have been processed, you need to put the key back into a&nbsp;<code style="font-family: Monaco, Courier, 'Courier New';">ready</code>&nbsp;state by invoking&nbsp;<a class="APILink" href="https://docs.oracle.com/javase/8/docs/api/java/nio/file/WatchEvent.html#reset--" style="color: #3a87cf; cursor: pointer; text-decoration: none;" target="_blank"><code style="font-family: Monaco, Courier, 'Courier New';">reset</code></a>. If this method returns&nbsp;<code style="font-family: Monaco, Courier, 'Courier New';">false</code>, the key is no longer valid and the loop can exit. This step is very&nbsp;<strong>important</strong>. If you fail to invoke&nbsp;<code style="font-family: Monaco, Courier, 'Courier New';">reset</code>, this key will not receive any further events.</li>
</ol>
</blockquote>
<br />
&nbsp;When an event occurs, we can either print the result using System.out.println , or call another function that takes these values further and does whatever else we may want.<br />
For example, in this project, I have transferred the file name and the event type, which passes these values to another object to further work on it.<br />
<br />
So, we are done! You might get overwhelmed thinking about the complexity of the task, but it's quite simple as we dig into it.<br />
<br />
Here is the complete code of WatchDir class that handles Watch Service API.<br />
<br />
<br /></div>
<div>
You can get the code and project <a href="https://github.com/amita-shukla/file-scanner/blob/master/src/WatchDir.java">here</a> at GitHub.<br />
<br />
<span style="font-family: Courier New, Courier, monospace;">Want to view how I tackled other problems in other projects? Check Out : <a href="http://shuklaamita.blogspot.in/2016/02/implement-own-session-mechanism-java.html" target="_blank">&nbsp;http://shuklaamita.blogspot.in/2016/02/implement-own-session-mechanism-java.html</a></span><br />
<br />
Want to suggest edits? Get this post on Github :<br />
<br />
<br />
<br />
<span style="font-family: Courier New, Courier, monospace;">EDIT (26/06/2016) : Image added</span></div>
</div>

