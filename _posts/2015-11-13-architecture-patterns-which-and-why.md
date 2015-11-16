---
layout: post
title: 'Architecture Patterns : Which and why ?'
date: 2015-11-13
---
<blockquote>
<p class="p1"><span class="s1">Carefully designed structure of something is called architecture.  </span></p>
</blockquote>
<p class="p1"><span class="s1">In software industry this word is often used but rarely followed at first place.</span></p>
<p class="p6"><span class="s1">Often all developers start coding their project without a clear picture of the architecture of their application and the reason for not having it is “this is just beginning , we will formalise it at a later stage.” . Eventually it leads to a standard n-tier architecture in which implicitly multiple layers are created to separate modules into packages.</span></p>
<p class="p6"><span class="s1">This will make source code :-</span></p>
<ul class="ol1">
<li class="li7"><span class="s1">unorganised</span></li>
<li class="li7"><span class="s1">highly coupled (spaghetti code)</span></li>
<li class="li7"><span class="s1">prone to break down</span></li>
<li class="li7"><span class="s1">hard to maintain</span></li>
</ul>
<p class="p6"><span class="s1">This list is never ending. And it would become just another<strong> “big ball of mud”</strong>.</span></p>
<p class="p6"><span class="s1">The bad architecture will lead to “<a href="http://batman.wikia.com/wiki/The_Pit" target="_blank">The Pit</a>”. For such poorly architected apps in order to understand the architectural characteristics one need to know the inner working of each component .</span></p>
<p class="p6"><span class="s1"> The basic questions like </span></p>
<ul>
<li class="li7"><span class="s1">will it scale?</span></li>
<li class="li7"><span class="s1">what are the performance characteristics ?</span></li>
<li class="li7"><span class="s1">what are the deployment characteristics?</span></li>
<li class="li7"><span class="s1">how much responsive is to the change?</span></li>
</ul>
<p class="p6"><span class="s1">All such questions will be very hard to answer if architecture of your app is not planned properly.</span></p>
<p class="p6"><span class="s1">With a planned architecture one can define the basic working and behaviour of the application. And there are numerous architecture patterns which can be adopted depending on your requirements. For example, some architecture pattern will naturally lend themselves toward highly scalable apps while some other lend themselves to highly agile. Thus knowing strengths and weakness of each architecture pattern is necessary in order to choose for your business. I will be writing on following architecture patterns in coming days:-</span></p>
<ol class="ol1">
<li class="li7"><span class="s1">Layered architecture</a></span></li>
<li class="li7"><span class="s1"><a href="https://en.wikipedia.org/wiki/Event-driven_architecture" target="_blank">Event-driven architecture</a></span></li>
<li class="li7"><span class="s1"><a href="http://viralpatel.net/blogs/microkernel-architecture-pattern-apply-software-systems/" target="_blank">Microkernel architecture</a></span></li>
<li class="li7"><span class="s1"><a href="https://en.wikipedia.org/wiki/Space-based_architecture" target="_blank">Space-based architecture</a></span></li>
</ol>
<p class="p6"><span class="s1">Stay tuned.</span></p>
<p class="p6"><span class="s1">Credits :- Software architecture patterns by Mark Richards.</span></p>
