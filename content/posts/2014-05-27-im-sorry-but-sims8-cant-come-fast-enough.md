---
title: I’m sorry, but SIMS8 can’t come fast enough
author: matt
type: post
date: 2014-05-27T23:39:37+00:00
url: /2014/05/im-sorry-but-sims8-cant-come-fast-enough/
categories:
  - MIS systems
  - SIMS .net
tags:
  - Advise
  - Rant

---
I haven&#8217;t really been on <a href="http://support.capitaes.co.uk/" target="_blank" rel="nofollow" class="broken_link">SupportNet</a>, <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">Capita SIMS</a> support portal, regularly since changing roles about 20 months ago, the only time I pop on nowadays is to find something when I&#8217;m helping out my old team during busyhard times (you never really escape at my work). On this occasion I stopped by the forum and one thing jumped out at me. The lack of progress. Now I appreciate I&#8217;m about to unload both barrels into my foot, but I think it needs to be said.

The same issues exist today that exists when I was dealing with <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">SIMS .net</a> on daily bases over 20 months ago. That&#8217;s nearly 2 years. There are still people who aren&#8217;t using <a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS3</a> &#8211; you know that free tool <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">Capita</a> created to ease the woes of upgrades and deployments. Despite a large number of users already using it and all the major bugs being resolve. More worrying, <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">Capita</a> has even issued <a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS2</a> with it&#8217;s marching orders. It&#8217;s not a question of if, but when. The last release will be Autumn 2014 unless they are forced to push it back. Again.

I don&#8217;t think pushing it back is the answer. Pushing the date back is like putting a plaster over a gunshot wound. OK, it might help stop the bleeding, but it&#8217;s not the answer. Now I accept my approach of nagging my boss until he allowed me get on top of <a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS3</a> whilst <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">Capita</a> was throwing major development time at it so I can make sure it works for our schools might not be possible for everyone. In fact it&#8217;s impossible, there aren&#8217;t enough developers to go around. But something has epically failed. Why, why, why hasn&#8217;t someone gone. Right, this needs to happen. It&#8217;s not going to go away. We have these problems:

  * <a href="http://www.capita-sims.co.uk/our-products/sims-discover-primary-schools-and-academies" target="_blank" rel="nofollow" class="broken_link">SIMS Discover</a> needs <a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS3</a> &#8211; Sorry, you don&#8217;t install SIMS manually why? So why is installing Discover manually an option?
  * <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">SIMS .net</a> needs MORE access rights to installupgrade &#8211; switching UAC off is just plain stupid
  * Upgrades are just a pain

We need to resolve. Lets get <a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS3</a> setup.

Now if your one of the support teams I&#8217;m attacking, before you start defending yourselves. Step back. Being busy isn&#8217;t an valid excuse. If you weren&#8217;t busy, you&#8217;ll be at the job centre. Someone, either yourself or your boss should be reviewing whats happening. Regularly. If your trying to do workarounds, you&#8217;re never going to have time to implement a fix. See what your doing is a putting a plaster on a gunshot wound and stop, get to the hospital. I know smaller support teams this will be a lot harder, especially when schools are doing their own thing, but I think this actually makes it easier.

<a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS3</a> is a bit of a different beast. The way I explain <a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS3</a> to new IT staff is, <a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS3</a> is your tool. It&#8217;s a IT technician&#8217;s tool. This tool will manage <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">SIMS .net</a> across your network &#8211; it also keeps <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">SIMS .net</a> at a safe distance so you don&#8217;t enter the mists of MIS land. At the same time it keeps the MIS manager away from any sort of Windows permissions &#8211; you&#8217;re not giving any non-IT staff administrator access to YOUR network. System Manager is the DataMIS managers tool, it keeps people out of THEIR database, including IT staff. I&#8217;ve found this has been really useful with new IT staff coming from the &#8220;real&#8221; world and they have found the clear what you do and don&#8217;t do has helped keep them out of trouble. You do get the odd, why can&#8217;t I get a <a href="http://technet.microsoft.com/en-gb/systemcenter/" target="_blank" rel="nofollow">SCCM</a> package, but when you point out that would require either <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">Capita</a> forcing schools to buy more <a href="http://www.microsoft.com/en-gb/" target="_blank" rel="nofollow">Microsoft</a> licenses or them reading more <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">Capita</a> documentation, they tend to go quiet.

Now I think the issue is the MIS support people are trying to push <a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS3</a>, when it should be the IT support people. If you look at the problems people are having with <a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS3</a>, they are IT problems, firewall and DNS mainly. Which MIS support staff don&#8217;t resolve. IT support staff do. If you&#8217;re now saying, but we don&#8217;t have any IT support people, it&#8217;s all third parties. What would happen if something, non-MIS related was required to be pushed out? What I&#8217;d do is organise a third party to support it, get the community together and issue training. So, find someone who has deployed <a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS3</a> successfully and get them to do some training sessions for those pesky IT support teams. The cost of even getting even a <a href="http://www.capita-sims.co.uk/support-and-services/site-training-and-consultancy" target="_blank" rel="nofollow">Capita trainer</a> in at £££, booking a venue could be offset by charging fees to delegates and to be honest, it isn&#8217;t that much when you compare it to even 1 day of failed <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">SIMS</a> upgradesdeployments. Costs can be cut by using a central school as the venue, by using a non-Capita trainer, by joining forces with other local support teams or even going completely digital. Support forums like <a href="http://www.edugeek.net/" target="_blank" rel="nofollow">EduGeek</a> are a excellent way for the community to support itself with very little effort. I would also not be fussy by who attends, if they support one of your schools, offer them the training. Don&#8217;t get caught up in the fact their going to resell your knowledge. Think bigger picture.

So, do I think their will be much progress? Do I think <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">Capita</a> will stick with their Autumn 2014 is the last <a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS2</a> release?

Well I also noticed they still had the following documents on the <a href="http://support.capitaes.co.uk/" target="_blank" rel="nofollow" class="broken_link">SupportNet</a> homepage as sticky items:

  * **Technical Guide &#8211; Network Impact of SIMS**
  * **Technical Guide &#8211; Optimising SIMS .net startup speed**
  * **Technical Guide &#8211; Remote Working with SIMS**

Sound pretty useful, till you look at the dates, 06 April 2005, 08 April 2005 and 11th June 2004 respectively.

Take the first one, **Network Impact of SIMS** &#8211; to quote a bit of it:

> Unfortunately, minimum hardware specifications are set to rise as we cease support for Windows 98.
> 
> Realistically Windows 2000 and Windows XP we would recommend a minimum of 256MB.

<div class="page" title="Page 8">
  <div class="layoutArea">
    <div class="column">
      <p>
        I&#8217;m sorry, didn&#8217;t <a href="http://www.microsoft.com/en-gb/" target="_blank" rel="nofollow">Microsoft</a> and even <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">Capita</a> just drop support for Windows XP? Why haven&#8217;t they updated a document that is important enough to warrant being displayed on their support portal? In over <strong>9</strong> years?!?
      </p>
      
      <p>
        Looking at <strong>Optimising SIMS .net startup speed</strong>, why are worrying about turning the antivirus off certain directories? Aren&#8217;t our computers these days powerful enough to handle it? Surely it&#8217;ll be a good idea if we&#8217;re <strong>not</strong> using <a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS3</a> and giving everyone and their dog access to a protected folder location &#8211; Program Files. Why are we worrying about SIMSload, it&#8217;s does nothing once the <a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS3</a> agent gets installed. Why would anyone compress the drive nowadays?
      </p>
      
      <p>
        Remotely accessing <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">SIMS .net</a> is a hot topic &#8211; the general concession is to use RemoteApp (Terminal Services). But the &#8220;official&#8221; <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">Capita</a> response is the <strong>Remote Working with SIMS</strong> document&#8230; which says to use a VPN. I&#8217;m not a fan of this idea. <a href="http://web.archive.org/web/20151114110121/http://www.capita-sims.co.uk:80/our-products/sims-financial-management-system-fms-primary-schools-and-academies" target="_blank" rel="nofollow">FMS</a>, the <a href="http://web.archive.org/web/20151114110121/http://www.capita-sims.co.uk:80/our-products/sims-financial-management-system-fms-primary-schools-and-academies" target="_blank" rel="nofollow">Capita SIMS finance package</a>, for starts doesn&#8217;t work well over a VPN, it&#8217;s not a speed issue, I&#8217;ve got 50MBs and that&#8217;s the lowest package I could get, it&#8217;s a latency issue. SQL doesn&#8217;t like latency. If you think of that 50MBs as the number of lanes and the latency as the speed what the cars are traveling. <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">SIMS .net</a> isn&#8217;t immune either, it just more modern, so it copes better.
      </p>
      
      <p>
        I&#8217;m sorry, but SIMS8, the next generation of <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">SIMS</a> which is rumoured to be in the &#8220;cloud&#8221;, can&#8217;t come fast enough for me to wash away all this silly technical problems. It&#8217;s ridiculous that things aren&#8217;t further along. Take the file sets for the School Census, I can see 4 file sets that came out in May, it&#8217;s still a manual import. <a href="http://www.capita-sims.co.uk/support-and-services/solus" target="_blank" rel="nofollow">SOLUS3</a> should be deploying file sets. Automatically. The biggest strength of SIMS is the community, it&#8217;s also the biggest problem. Viva la revolution!
      </p>
    </div>
  </div>
</div>

<a href="//matt40k.uk/img/2014/05/cloud-rev1.png" target="_blank" rel="nofollow"><img class="size-full wp-image-89 aligncenter" src="//matt40k.uk/img/2014/05/cloud-rev.png" alt="Cloud revolution" width="300" height="177" /></a>
