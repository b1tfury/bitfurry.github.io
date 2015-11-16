---
layout: post
title: Understanding Layered architecture scrupulously
date: 2015-11-16
---
<p class="p1">Layered architecture is also called as n-tier architecture pattern.</p>
<p class="p1">Most Java EE Applications use this pattern only , so most of the architects are aware of this type of pattern.</p>
<p class="p1">What exactly layered architecture is :-</p>
<p class="p1">Different application components are placed in horizontal layers , each layer has its own purpose and significance.(For example :- presentation logic or business logic)</p>
<p class="p1">There are no specific rule for how many type and number of layers , but most layered architecture applications have standard four layers :</p>
<ul class="ul1">
<li class="li1">Presentation</li>
<li class="li1">Business</li>
<li class="li1">Persistence</li>
<li class="li1">Database</li>
</ul>
<p><a href="https://bitfurry.files.wordpress.com/2015/10/1.jpg"><img  class="wp-image-14 size-medium" title="layered architecture" src="https://bitfurry.files.wordpress.com/2015/10/1.jpg?w=300" alt="1" width="300" height="225" /></a> 
<br>Layered architecture</p>
<p class="p1">Sometimes when two layers have deeper connections they are merged into single one for example persistence layer embedded in to<span class="Apple-converted-space">  </span>business layer.When application is complex numbers of layers may increase to five to six.</p>
<p class="p1">Each layer in the architecture forms an abstraction around its responsibilities needs to be done for the application. For example<span class="Apple-converted-space"> </span>: the<span class="Apple-converted-space">  </span>presentation layer need not to worry about how to get customer data, its only needs is to display the data in a particular format.</p>
<p class="p1">Separation of concerns among the components is one of the powerful feature. Due to this it would be easy to build effective roles and responsibility models.</p>
<p class="p1">Due well-defined component interfaces and limited scoping of components it is easy to develop,test, govern and maintain applications using n-tier architecture plans.</p>
<p class="p4"><b>Key Concepts:-</b></p>
<p class="p1">Notice <b>CLOSED </b>has been marked at the end of each architectural layer , this concept is called <b>layers of isolation.</b></p>
<p><a href="https://bitfurry.files.wordpress.com/2015/10/2.jpg"><img class="wp-image-15 size-medium aligncenter" src="https://bitfurry.files.wordpress.com/2015/10/2.jpg?w=300" alt="2" width="300" height="205" /></a></p>
<p class="p1">In the above diagram we can see that if we want to go to database layer from presentation layer then it’s mandatory to pass through Business and Persistence layer which sounds a bit weird. But it has more benefits than drawback:</p>
<ul class="ul1">
<li class="li1">All layers are independent so changes in one layer won't affect another</li>
<li class="li1">Less coupling</li>
<li class="li1">Easy maintenance i.e. in order to work on presentation layer one need not to know the in working of all other layers</li>
</ul>
<p class="p1">But there are times depending on project need some layers needs to be open i.e. we can bypass them to move to next layer.<span class="Apple-converted-space">  </span>In such scenarios instead of making one of<span class="Apple-converted-space">  </span>these layers open it suggested to add a service layer which could be open.</p>
<p><a href="https://bitfurry.files.wordpress.com/2015/10/3.jpg"><img class="wp-image-16 size-medium" src="https://bitfurry.files.wordpress.com/2015/10/3.jpg?w=300" alt="3" width="300" height="249" /></a> <strong> </strong></p>
<p class="p1">So , if we want to have some common services which can be used from service layer but independent of presentation layer then placing an open service layer below business layer solves our problem.</p>
<p class="p1">Using this concept of open and closed layers one can define relationships between different layers and also provides designers and developers the necessary information about access restrictions within the architecture.</p>
<p class="p4"><b>Example </b></p>
<p><a href="https://bitfurry.files.wordpress.com/2015/10/4.jpg"><img class="wp-image-17 size-medium aligncenter" src="https://bitfurry.files.wordpress.com/2015/10/4.jpg?w=300" alt="4" width="300" height="290" /></a></p>
<p class="p1">The above diagram is an example of layered architecture which shows the flow in which a request from a business user to retrieve customer information for a particular individual.</p>
<p class="p4"><b>Considerations</b></p>
<p class="p1">Although this architecture pattern is solid and generally used for most of the applications in their starting phase when it is not sure that which architecture will suite the most.</p>
<p class="p1">But there are some things which one should keep in mind while choosing this pattern for their application.</p>
<ol class="ol1">
<li class="li1"><strong>Architecture sinkhole anti-pattern</strong> - Since all requests needs to traverse through all all layers in order to go form top to bottom , so this pattern may sometime become overhead to your requests. For this scenario one should follow <strong>80:20 rule</strong> i.e if less than 20 percent of requests are just passing through all layers without any logic implemented on them then this pattern is suitable but , if this ratio is reverse which means that most of the request are travelling back and forth with any additional logic being implemented on them in between then my friend this pattern is a sinkhole for your application.</li>
<li class="li1">Also this pattern will lead to monolithic applications even if layers are independent and also deployed separately, which is not considered good for general robustness and reliability, <span class="Apple-converted-space"> </span>performance and scalability</li>
</ol>
<p class="p4"><b>Analysis:</b></p>
<table style="border-collapse:collapse;border-spacing:0;table-layout:fixed;width:686px;">
<colgroup>
<col style="width:103px;" />
<col style="width:143px;" />
<col style="width:100px;" />
<col style="width:101px;" />
<col style="width:84px;" />
<col style="width:155px;" /></colgroup>
<tbody>
<tr>
<th style="font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;vertical-align:top;">Overall agility</th>
<th style="font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;vertical-align:top;">Ease of deployment</th>
<th style="font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;vertical-align:top;">Testability</th>
<th style="font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;vertical-align:top;">Performance</th>
<th style="font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;vertical-align:top;">Scalability</th>
<th style="font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;vertical-align:top;">Ease of development</th>
</tr>
<tr>
<td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;vertical-align:top;">Low</td>
<td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;vertical-align:top;">Low</td>
<td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;vertical-align:top;">High</td>
<td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;vertical-align:top;">Low</td>
<td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;vertical-align:top;">Low</td>
<td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;vertical-align:top;">High</td>
</tr>
</tbody>
</table>
<p class="p2"><span class="Apple-converted-space">     </span></p>
