# Web安全研究员是怎样炼成的？ <译><转>

![Category](https://img.shields.io/badge/category-methodology-blue.svg)
![Research](https://img.shields.io/badge/research-web_security-blue.svg)
![Timestamp](https://img.shields.io/badge/timestamp-1527560495-lightgrey.svg)
![Progress](https://img.shields.io/badge/progress-100%25-brightgreen.svg)

<sub>* 偶然看到[@猪猪侠](http://weibo.com/ringzero)朋友圈推荐了先知的这篇文章。从攻击技术研究的角度来说，作者的观点比较符合自己胃口，所以在得到许可后转载到自己博客中留存。</sub>

> 译文出处：[先知社区](https://xz.aliyun.com/t/2358)
> 原文出处：[PortSwigger Web Security Blog](https://portswigger.net/blog/so-you-want-to-be-a-web-security-researcher)

## 前言

您是否有志于推动Web安全技术的发展，并与信息安全社区分享相关知识呢？在这篇文章中，我将为读者分享与Web安全研究有关的各种建议，当然，这些建议一方面是来自某些成功经验，而另一些则是来自于曾经踩过的坑，希望对大家有所帮助。

## 以『黑』为生

大部分研究都是在现有的技术的基础之上，百尺竿头更进一步的，所以，研究工作的第一步就是熟悉当前的技术水平。为了实现这一目标，最快的方法是找一份相关的工作，这样就可以有大量时间来接触网络黑客技术了。另外，因为已经有很多大牛分享过『入坑』安全行业的[详细建议](https://medium.com/@niruragu/so-you-want-to-be-a-security-engineer-d8775976afb7)，所以，这里只是简要提一下。

我建议有兴趣的读者采用以实践为中心的研究方法，首先从[OWASP Broken Web应用程序](https://www.owasp.org/index.php/OWASP_Broken_Web_Applications_Project)开始下手，继而转向更具实战性的安全挑战活动，比如[hackxor.net](https://hackxor.net/)，这样的话，就可以通过[HackerOne](https://hackerone.com/)和[BugCrowd](https://bugcrowd.com/)上难度和回报相对较低的挑战来练手，待学有所长之后，最终参加各种高赏金的计划。一旦你发现并公开披露的几个有影响的漏洞之后，加入安全咨询公司将不成问题，这样就可以整天跟黑客技术打交道了。

当然，网络上面也有大量免费的在线资源，包括我们站点提供的[The Burp Methodology](https://support.portswigger.net/customer/portal/articles/2326039-the-burp-methodology)系列文章，HackerOne站点的[Hacker101](https://www.hackerone.com/hacker101)系列文章，以及[OWASP测试指南](https://www.owasp.org/index.php/OWASP_Testing_Guide_v4_Table_of_Contents)。至于书籍，我推荐读者阅读[《WebApp Hacker's Handbook》](https://www.amazon.com/Web-Application-Hackers-Handbook-Exploiting-ebook/dp/B005LVQA9S)和[《The Tangled Web》](https://nostarch.com/tangledweb) *（注：中文《Web之困》，我的第一本安全入门书籍）* 。

## 不要止步不前

一旦开始全职黑客工作，自然能学到很多东西，但一段时间之后，您的专业技能就会停滞不前，除非努力的劲头一直保持不减。

### 要知新，更要温故

为了不被小伙伴甩在后面，所有业内人士都会密切关注[行业专家](https://twitter.com/albinowax/following)、[新闻聚合](https://www.reddit.com/r/netsec/)和安全会议来跟踪行业的最新动向。然而，如果一门心思追逐最新技术的话，往往会遗忘和忽视大量的研究宝藏。

每当读到优质博客文章时，请细心通读整篇文章。这样做的话，往往能够找到一些宝贵的、被遗忘的信息花絮。例如，[这里](https://web.archive.org/web/20110403015721/http://ha.ckers.org:80/blog/20091201/dns-rebinding-video/)有一篇关于DNS重绑定的文章，是RSnake于2009年撰写的。DNS重绑定能够绕过基于IP/防火墙的网站访问控制，唯一有效的缓解方法就是采用相关的白名单技术。之后不久，人们就认为浏览器已经解决了这个问题，遗憾的是，9年以后，这个被遗忘的[漏洞](https://bugs.chromium.org/p/project-zero/issues/detail?id=1524)又重出江湖了。

此外，仔细阅读文档还可以帮助您避免浪费时间来重复其他人已经完成的工作，例如十年后[重新发明](https://twitter.com/LiveOverflow/status/967122565058715648)CSS攻击。换句话说，一些研究文献真的很难找到，所以偶尔的『重蹈覆辙』是不可避免的。我曾与一位研究人员在某技术上面发生过『撞车』现象，戏剧性的是，后来我们两人都发现，早在5年之前，kuza55就发表过该技术了。所以，我们一方面要尽最大努力避免重复研究，但是，即使出现这种情况，也不必太惊讶——这是在所难免的。

### 力求多样性

要想把各种线索串起来并找出别人错过的机会的话，收集不同来源的信息是至关重要的。首先，不要只阅读安全方面的内容——您很快就会发现，[文档手册](http://blog.portswigger.net/2015/08/server-side-template-injection.html#FreeMarker)也可以作为漏洞利用的指南。其次，我们还可以利用谷歌搜索来解决问题，还可以通过Twitter/Reddit/StackOverflow与同行和同事交流。最后，还有大量的知识是在社区内部传播的，换句话说，这些尚未公开发表。

除此之外，还要努力使自己的经历多样化。

在进行安全咨询黑盒测试的过程中，可以接触到各种各样的外部和内部Web应用程序，而这些应用程序则是在漏洞奖励计划中很难遇到的。但是，由于时间限制的缘故，你很难有机会深入理解一个应用程序，而对于漏洞赏金猎人来说，要想捕获特定目标中的漏洞，通常需要花费几个月的时间来熟悉它。尽管通常速度缓慢且受到各种限制，但白盒源代码审计却可以提供不可替代的视角，便于发现黑盒测试人员永远都想不到的攻击方法。为了培养研究能力，最好将三种经历合理组合一下。此外，诸如参加CTF比赛和编写Web应用程序等经验，对于拓宽视野也是非常有帮助的。

### 没有任何想法是愚蠢的

最糟糕的陷阱之一，就是仅仅认为某想法行不通就不去尝试，例如，觉得某些想法『别人肯定早就想到了』或『这想法太蠢了，肯定不行』。实际上，我就曾经为此付出过沉重的代价——拜它所赐，一项研究成果在两年后才姗姗来迟。无论是通过重复尝试使用相同密码登录来[绕过身份验证](https://blog.rapid7.com/2012/06/11/cve-2012-2122-a-tragically-comedic-security-flaw-in-mysql/)，还是通过从笔记本电脑切换到手机[攻入](https://medium.com/bugbountywriteup/bypassing-googles-fix-to-access-their-internal-admin-panels-12acd3d821e3)Google管理页面，踏上下一个重大漏洞的发现之路之前，可能首先需要一个非常愚蠢的想法。

## 迭代，发现，分享

### 迭代

最简单的入门方法是找一些有前途的研究成果，通过混合其他技术构建新方法，然后将其用于某些实际目标，看看是否有什么有趣的事情发生。

例如，这篇关于CORS配置错误的[文章](https://ejj.io/misconfigured-cors/index.html)指出了一种有趣的行为，并且表示这种行为很普遍，但并没有探讨它对个人网站的影响情况。

于是，我把这个概念应用到了漏洞赏金网站，因为我可以在这些网站上合法地探索它的影响，并且设法绕过各种可能的缓解措施。在此过程中，我以常见的开放重定向漏洞技术为助攻，随后在阅读CORS规范时发现了『空源』技术 *（the ‘null’ origin technique）* ，并探索了缓存中毒的可能性。

在这个过程中，根本无需借助于遥不可及的顿悟或卓尔不凡的技术知识，然而，由此产生的演示文稿和[博客文章](https://portswigger.net/blog/exploiting-cors-misconfigurations-for-bitcoins-and-bounties)仍然很容易被大家所接受——毕竟，我付出的努力是大家有目共睹的。

### 发现

虽然对他人的工作进行迭代不失为一个好方法，但现实是，好像任何一个角落都可能发掘出相应的研究宝藏，无论是[相对路径覆盖](http://www.thespanner.co.uk/2014/03/21/rpo/)还是[Web缓存欺骗](https://omergil.blogspot.co.uk/2017/02/web-cache-deception-attack.html)。我的观点是，个人经验在这些发现过程中提供了重要的线索。我将这些经验称为导向器或『面包屑』，因为它们的作用机制往往是非常神秘的，而且，许多重大的发现，都是在一系列的经验的指引下找到的。

例如，2011年，我试图破解addons.mozilla.org使用的CSRF保护机制。尽管我可以绕过令牌检查，但这显然是不够的——他们采用的安全机制还会验证`Referer`头中的主机与当前站点的匹配情况。于是，我在sla.ckers论坛上发帖求助，后来@barbarianbob指出，Django是通过查看`Host`头来确定当前网站的主机的，而这个头恰好可以通过`X-Forwarded-Host`头来覆盖掉。换句话说，将其与`Flash`头注入漏洞相结合的话，就有可能绕过CSRF检查，但更重要的是，这是我们的第一个『面包屑』——它暗示着应用程序可能是通过`Host`头来了解其当前位置的。

之后，通过阅读Piwik的密码重置函数的源代码，发现了如下所示的一行代码：

```php
$passwordResetLink = getCurrentUrlWithoutQueryString() + $secretToken
```

我们可以看出，Piwik使用的是PHP语言，众所周知，该语言的路径处理方式是非常搞笑的：如果通过[http://piwik.com/reset.php/foo;http://evil.com](http://piwik.com/reset.php/foo;http://evil.com)请求重置密码，就会生成一个包含两个链接的电子邮件，并且秘密令牌将被发送到evil.com。这个想法果然是有效的，为此，我不仅获得了一笔赏金，并且还为后来的发现奠定了基础。

第三个也是最后一个『面包屑』就是Piwik修补这个漏洞的方式——他们用`getCurrentUrlWithoutFileName()`替换了`getCurrentUrlWithoutQueryString()`函数。这意味着，我无法再使用该路径进行攻击。由于之前就跟Django打过交道，所以我决定深入研究相关代码，以了解Piwik是如何确定当前的主机名的，经研究后发现，像Django一样，Piwik也是使用的`Host`头，也就是说，我可以轻松生成恶意的密码重置电子邮件。事实证明，这项技术同样适用于addons.mozilla.org、Gallery、Symfony、Drupal以及其他一些网站，即可以通过`Host`头发动[有效的攻击](https://www.skeletonscribe.net/2013/05/practical-http-host-header-attacks.html)。

我之所以啰里啰嗦地阐述上面的发现过程，是希望能够帮助读者揭开安全研究的神秘面纱：许多研究成果，并非从天而降，凭空产生的。从这个角度来看，核心技能 *（超越了既有的知识和经验的广度）* 似乎在于如何识别这些面包屑并坚持不懈地追逐它们上面。我还不太清楚如何做到这一点，但我知道，帮助人们发现重大研究成果的线索，恰恰正是那些原以为『毫无意义』的事物。

## 分享

最后，与社区分享您的研究也是至关重要的。这将有助于提高您的知名度，并可能说服雇主为自己分配更多的研究时间。除此之外，它还能帮助您避免浪费时间，并促进进一步的研究——评论者非常善于指出您之前不知道的工作，而且没有什么比看到其他研究人员在您的想法基础上再接再厉更有成就感了。

请不要仅仅因为没有突破性的发现、两个徽标和一个演示文稿就认为一个技术或想法不值得分享——不要太过苛求，有啥就发布啥好了 *（当然，理想情况下是发表到博客上，而不仅仅是发表到类似Twitter这样不便于搜索引擎收录索引的平台上面）* 。

在共享研究时，至少应展示一个应用于实际应用程序的技术示例。否则的话，一方面不利于人们的理解，另一方面，容易让人怀疑它是否具有实际价值。

最后，演讲对于吸引更多观众来说非常有用，不过需要注意的是，不要把太多的时间花在重复过去的演讲上面。

## 结束语

关于安全研究，我自己还有很多东西要学，所以，我希望能在几年后重新回顾这个话题，并提供更多的线索。另外，我希望其他研究人员提供不同的观点，并期待从他们的分享中学习新的见解。

最后，对于正在寻找安全研究的入门读物的读者，我已经准备好了一份[博客](https://skeletonscribe.net/#inspiration)清单——多年来，我一直从中汲取营养。祝您好运，玩得开心！