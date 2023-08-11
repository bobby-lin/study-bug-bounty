# Guide to Bug Bounty Hunting
## Mindset
If you are beginning bug bounty hunting, you will need to know that it will take time to learn the bug hunting skills. You need to have the patience and determination to continue hunting even though you might not see successful results quickly. The bug bounty field is crowded and competitive, hence you will require hardwork, dedication, lateral thinking to persist on. Hunting is about learning and acting noob all the time. Everyone starts from somewhere.

> From Tommy (dawgyg) DeVoss: If you have the ability to look at a web application and think of ways to break the application, then you can give it a shot. For some people it can be a very slow start to the process, and others will start finding bugs right after they begin. A very important thing to remember when doing bug bounties is to not get depressed / upset if it takes you longer to find valid bugs etc. Not everyone is going to find bugs every time they sit down to hack. And its very common to go days, weeks or even months with out finding bugs. Don't compare your own success or failures to others. Because as with anything else, there will always be someone better than you, and others worse than you. So setting your own goals and working to acheive them can be very important.

> From Shubs (https://shubs.io/so-you-want-to-get-into-bug-bounties/): If someone came up to you and asked you if you could find a security vulnerability in Facebook or Google, your knee-jerk reaction may be to explain how hard that would be because of how much money these companies spend on security and how many staff they have securing their applications. As a bug bounty hunter, you cannot have this mentality. It is extremely prohibitive, and as you find yourself finding security issues in the largest corporations in the world, you will soon realise that it is possible to find vulnerabilities in anything (given enough time and resources). What you may find is that some companies are harder to find vulnerabilities in (how long it takes to find security issues), and you may give up before you find anything, but you need to understand that there are still vulnerabilities yet to be found for any attack surface.

<b>Rewards.</b> The lessons and knowledge learned are the only rewards that are within your control. So if you are a beginner, you should set the goal of learning about the vulnerabilities and techniques to exploit them rather than how much money you should make.

<b>Responsiblity.</b> Do not disclose an issue if the counterparty have not agreed to do so.

## Learning
<b>Web Application basics</b>. Learn how a request works, HTTP headers, JSON requests, how a browser works, how they communicate and send data to the servers, DNS etc. https://developer.mozilla.org/en-US/docs/Web

<b>Common scope vulnerabilities.</b> You will need to know common scope vulnerabilities such as Remote Code Execution (RCE), Cross Site Request Forgery (CSRF), Cross Site Scripting (XSS), Injections (SQL, Command etc.), Clickjacking, Open Redirects, etc.

<b>Read blogs.</b> Learn new techniques from other bug bounty hunters so that you can test it out during your testing.

>If you are new to Bug Bounty program, you might not feel confident that you can find something a public program. This is something that a lot of hackers are struggling with. If you haven’t found a lot of security vulnerabilities yet, it might payoff to practice on Capture The Flag (CTF). Exploiting something for the first time is difficult and eye-opening. Apply the same structure if you would apply when looking in real targets as this help you a build a solid foundation and will help you to become an amazing hacker. Use bug bounty as a way to expand your knowledge and not as a race. Write simple scripts and use available tools to expand the process of expanding attack surface [...] Understand the web application and figure out what assets the web application are trying to protect. Think like an engineer of the web application. (Jobert Abma, Hackerone Cofounder)

<b>Learn how to make and then break.</b> You need to know how a web or mobile application is developed first so that you can understand how the thing works and hence how it can be broken down. This is beneficial for your long-term development rather than being a hunter that only knows how to send payloads (obtained from internet). Build a few web applications to understand how the web architecture works.

> From <a href="https://twitter.com/spaceraccoonsec/status/1250403032971407360?s=20"> Spaceraccoon's tweet</a>: To be blunt, I don't automate. I tried building a pipeline and failed. You can succeed just by learning the fundamentals. Check out @PortSwigger's web academy, watch @NahamSec's stream, read @Hacker0x01 disclosures. And learn how to build what you're hacking.

### Training Platforms
- [BugBountyHunter](https://www.bugbountyhunter.com/): 
  - Simulates Opacity: The platform simulates a more realistic bug hunting experience where you need to explore and understand each features to find bugs. You do not know beforehand on whether the features have bugs or not (and what kind of vulnerabilities).
  - Community: Members share resources and help each other.
  - Zseano Methodology: Download from https://www.bugbountyhunter.com/methodology/

## Testing Strategies
<b>Scope your Testing.</b> You do not want to test the applications for different vulnerabilities in an unstructured manner because this often results in shallow testing or makes you feel that you have already search for everything. If you are stuck with your testing, ask yourself what you are testing on. Set a SMART goal - specify what the vulnerability you are targeting, the hard deadline for completing the testing, etc. This strategy will help you to know which resources to look for and specific questions to ask your peers. You can also prioritize on what to look for based on the goal.

````Example of a goal: For the next 4 hours, I will test on feature X for SQL Injection.````

<b>Choosing programs with Larger Scope.</b> You want to choose a program that uses something that you are familiar with. If not, then you must ask yourself whether this is something you will like to learn. Larger scope is better because the researchers will not concentrate on the same targets and some things might be overlooked.

> From Tommy (dawgyg) DeVoss: When it comes to picking a program to start there are several things to consider. The first, and most important, is picking a program that employs the kind of stack / architecture you may be familiar with, or have a desire to learn and attack [...] Next you are going to want to consider the scope. When I look at a program to decide if I want to spend any time on it, I look for programs with either large scopes (such as wild card domains, and the more domains the better) or with web apps that are very complex. I personally love huge scopes, since it kind of helps to spread out the researchers a bit. 

<b>Test the uncommon attack vectors.</b> This requires you to do more in depth work in understanding how the application works (in terms of technologies and business functions). Ask yourself whether the bug that you are looking for are already tested automatically by a conventional scanner. For example, if you test a normal XSS payload on the common attack vectors such as input boxes etc., the chances are that many hunters have done it. Ask yourself whether there are other ways to trigger the XSS payload in an unexpected attack vector.

> From Inti: Edge-cases like that is what I love. If I have a secret, that is the one. Do not look where everyone is looking, because you will get a duplicate [...] My advice: if you are a researcher and want to secure your payout for the next 5-10 years, start looking for custom bugs, logical flaws, and other things scanners or other researchers do not look into. That can lead to more impact, you will find new types of vulnerabilities, you can get speaker events, write blog posts about it, opportunities are plenty. It is more about your mindset and being open-minded to try stupid stuff or something unknown and not follow a checklist.

<b>Look for impactful bugs.</b> Try to submit bugs which are impactful and easy to understand. Choose quality over quantity. Many successful hunters read the programme policies first before they start looking for vulnerabilities.

<b>Do the unexpected action</b> Don't submit what the application is expecting. Instead, start thinking about the things that the developers did not consider.

>From Peter Yaworski: <ul><li>For a text editor, if you can insert html, try doubling up on html attributes, like two hrefs in an anchor tag, or extra quotes like the markdown example.</li><li>When submitting forms, use a tool or proxy to remove parameters (for Firefox, tamperdata is a great one). On the same note, if a site is using JavaScript to validate input before it is submitted to the server, use the proxy to change the values after they are validated in the event the developer just relied on the JavaScript.</li><li>Combining steps to create vulnerability. Again, with the Hackerone markdown example, having the hanging single quote combined with additional html later in the page with a single quote would create vulnerability. With Google's program, they include a multiplier whereby if you need multiple steps and you can actually demonstrate that all the steps are achievable, they'll increase your reward.</li><li>Consider where the vulnerability might actually show up. For example, Shopify's disclosure program states that it excludes vulnerabilities on your own store or cart (I learned the hard way from over excitement...). BUT, some of the fields that are used to create your store are used externally as well. There is an disclosure report indicating that the currency formatting field allowed for XSS injection. At first glance, you would think this shows up on the store page so who cares. BUT, Shopify provides integration with Facebook and Twitter using that same field and actually rendered the XSS resulting in a $500 bounty</li></ul>

## Finding evasive bugs
My notes from [Hunting Evasive Vulnerabilities: Finding Flaws That Others Miss by James Kettle](https://www.youtube.com/watch?v=skbKjO8ahCI&feature=emb_title&ab_channel=nullcon)
- Don’t look for defences; Start with the attacks first.
- Look for unfashionable flaws.
- Your understanding of a vulnerability concept may be corrupted. Dig deeper to the original sources rather than accepting the secondary sources that appear in on internet searches to learn.
- Recognise the fear from the new or unknown (Technique sounds cool but…)
- Recognise that you might think that something is an implausible idea. Don’t just try something and then give out if it does not work. Instead do this: Explain why the idea will not work unless condition X exists. Try the obvious to make sure that it is obviously secured.
- Look to gain advantages by having a better understanding of a particular application context, application specific knowledge or something that is inconvenient to others (such that they can't test the feature).

## Resources
### Books
<ul>
  <li>The Web Application Hacker’s Handbook</li>
  <li><a href="https://www.owasp.org/index.php/OWASP_Testing_Project">OWASP Testing Guide</a></li>
  <li>The Tangled Web: A Guide to Securing Modern Web Applications</li>
  <li>Web Hacking 101</li>
  <li>Breaking into Information Security</li>
  <li>Mastering Modern Web Penetration Testing</li>
  <li>The Mobile Application Hacker's Handbook</li>
  <li><a href="https://www.owasp.org/index.php/OWASP_Mobile_Security_Testing_Guide">OWASP Mobile Security Testing Guide (MSTG)</a></li>
</ul>

### Platform / Companies
<ul>
  <li><a href="https://www.hackerone.com/">Hackerone</a></li>
  <li><a href="https://www.bugcrowd.com/">Bug Crowd</a></li>
  <li><a href="https://www.cobalt.io/">Cobalt</a></li>
  <li><a href="https://www.synack.com/">Synack</a></li>
  <li><a href="https://immunefi.com/">ImmuneFi</a></li>
  <li><a href="https://hackenproof.com/">HackenProof</a></li>
  <li><a href="https://huntr.dev/">Huntr (OSS Bounty)</a></li>
  <li><a href="https://www.facebook.com/whitehat">Facebook</a></li>
  <li><a href="https://www.google.com/about/appsecurity/">Google</a></li>
</ul>

### Writeups
<ul>
  <li><a href="https://github.com/xdavidhu/awesome-google-vrp-writeups">Google VRP Writeups</a></li>
</ul>

### Online Readings
<ul>
  <li><a href="https://portswigger.net/research/how-i-choose-a-security-research-topic">James Kettle on how he choose a security research topic</a></li>
  <li><a href="https://bugbountytuts.files.wordpress.com/2018/02/dirty-recon.pdf">Recon Like A Boss</a></li>
  <li>https://whitton.io/articles/bug-bounties-101-getting-started/</li>
  <li><a href="https://github.com/jhaddix/tbhm">The Bug Hunters Methodology</a></li>
  <li><a href="https://github.com/EdOverflow/bugbounty-cheatsheet">Bug Bounty Cheatsheet</a></li>
  <li><a href="https://github.com/ngalongc/bug-bounty-reference/">Bug Bounty Reference</a></li>
  <li><a href="https://github.com/bugcrowd/vulnerability-rating-taxonomy">Bugcrowd Vulnerability Rating Taxonomy (VRT)</a></li>
  <li><a href="https://hackerone.com/hacktivity">Hackerone Hacktivity</a></li>
  <li>https://www.hackerone.com/blog/What-To-Do-When-You-Are-Stuck-Hacking</li>
  <li>https://www.quora.com/How-does-one-become-a-bug-bounty-hunter/answer/Jobert-Abma</li>
  <li>https://www.quora.com/How-much-time-did-you-take-from-completely-beginning-hacking-to-your-first-success-or-bug-bounty/answer/Jobert-Abma</li>
  <li>https://www.quora.com/How-do-bug-bounty-hunters-find-bugs/answer/Jobert-Abma</li>
  <li>https://www.quora.com/How-much-can-I-make-in-my-first-year-as-a-bug-bounty-hunter</li>
  <li>https://blog.detectify.com/2019/05/03/meet-the-hacker-inti-de-ceukelaire-while-everyone-is-looking-for-xss-i-am-just-reading-the-docs</li>
  <li>http://blog.oath.ninja/basic-bug-bounty-faq</li>
  <li>https://twitter.com/spaceraccoonsec</li>
  <li>https://rhynorater.github.io/Beginners-Resources</li>
  <li>https://securityflow.io/roadmap/</li>
</ul>
 
 ### Online Videos
 <ul>
  <li><a href="https://sites.google.com/site/bughunteruniversity/">Google Bughunter University</a></li>
  <li>https://www.hacksplaining.com/lessons</li>
  <li>https://www.udemy.com/android-application-penetration-testing-ethical-hacking/</li>
  <li>https://www.youtube.com/user/Hak5Darren/playlists</li>
  <li>https://www.youtube.com/user/DEFCONConference/videos</li>
  <li>https://www.youtube.com/user/JackkTutorials/videos</li>
  <li>https://www.youtube.com/watch?v=mQjTgDuLsp4</li>
  <li>https://www.youtube.com/watch?v=KDo68Laayh8</li>
  <li>https://www.youtube.com/watch?v=XoYF-euS-zs</li>
  <li><a href="https://www.youtube.com/watch?v=Q2WK5LpDbxw">Finding Bugs with Burp Plugins & Bug Bounty 101</a></li>
 </ul>

### Forums / Blogs
<ul>
  <li>https://www.bugcrowd.com/about/blog/</li>
  <li>https://www.reddit.com/r/netsec</li>
  <li>https://www.reddit.com/r/websecurity/</li>
</ul>

### Other Aggregated Resources
<ul>
  <li>https://www.hackerone.com/blog/resources-for-new-hackers</li>
  <li>https://www.peerlyst.com/posts/the-everything-bug-bounty-wiki-peerlyst?trk=company_page_posts_panel</li>
  <li>https://github.com/onlurking/awesome-infosec</li>
  <li>https://forum.bugcrowd.com/t/researcher-resources-tutorials/370</li>
  <li>https://forum.bugcrowd.com/t/researcher-resources-tools/167</li>
  <li>https://forum.bugcrowd.com/t/how-do-you-approach-a-target/293</li>
  <li>http://www.amanhardikar.com/mindmaps/Practice.html</li>
  <li>https://github.com/djadmin/awesome-bug-bounty</li>
</ul>
