# Guide to Bug Bounty Hunting
## Mindset
If you are beginning bug bounty hunting, you will need to know that it will take time to learn the bug hunting skills. You need to have the patient and determination to continue hunting even though you might not see successful results quickly. The bug bounty field is crowded and competitive, hence you will require hardwork, dedication, lateral thinking to persist on. Hunting is about learning and acting noob all the time. Everyone starts from somewhere.

<b>Rewards.</b> The lessons and knowledge learned are the only rewards that are within your control. So if you are a beginner, you should set the goal of learning about the vulnerabilities and techniques to exploit them rather than how much money you should make.

<b>Responsiblity.</b> Do not disclose an issue if the counterparty have not agreed to do so.

## Learning
<b>Web Application basics</b>. Learn how a request works, HTTP headers, JSON requests, how a browser works, how they communicate and send data to the servers, DNS etc.

<b>Common scope vulnerabilities.</b> You will need to know common scope vulnerabilities such as Remote Code Execution (RCE), Cross Site Request Forgery (CSRF), Cross Site Scripting (XSS), Injections (SQL, Command etc.), Clickjacking, Open Redirects, etc.

<b>Read blogs.</b> Learn new techniques from other bug bounty hunters so that you can test it out during your testing.

>If you are new to Bug Bounty program, you might not feel confident that you can find something a public program. This is something that a lot of hackers are struggling with. If you haven’t found a lot of security vulnerabilities yet, it might payoff to practice on Capture The Flag (CTF). Exploiting something for the first time is difficult and eye-opening. Apply the same structure if you would apply when looking in real targets as this help you a build a solid foundation and will help you to become an amazing hacker. Use bug bounty as a way to expand your knowledge and not as a race. Write simple scripts and use available tools to expand the process of expanding attack surface [...] Understand the web application and figure out what assets the web application are trying to protect. Think like an engineer of the web application. (Jobert Abma, Hackerone Cofounder)

<b>Learn how to make and then break.</b> You need to know how a web or mobile application is developed first so that you can understand how the thing works and hence how it can be broken down. This is beneficial for your long-term development rather than being a hunter that only knows how to send payloads (obtained from internet). Build a few web applications to understand how the web architecture works.

## Testing Strategies
<b>Scope your Testing.</b> You do not want to test the applications for different vulnerabilities in an unstructured manner because this often results in shallow testing or makes you feel that you have already search for everything. If you are stuck with your testing, ask yourself what you are testing on. Set a SMART goal - specify what the vulnerability you are targeting, the hard deadline for completing the testing, etc. This strategy will help you to know which resources to look for and specific questions to ask your peers. You can also prioritize on what to look for based on the goal.

````Example of a goal: For the next 4 hours, I will test on feature X for SQL Injection.````

<b>Look for impactful bugs.</b> Try to submit bugs which are impactful and easy to understand. Choose quality over quantity. Many successful hunters read the programme policies first before they start looking for vulnerabilities.

<b>Do the unexpected action</b> Don't submit what the application is expecting. Instead, start thinking about the things that the developers did not consider.

>From Peter Yaworski: <ul><li>For a text editor, if you can insert html, try doubling up on html attributes, like two hrefs in an anchor tag, or extra quotes like the markdown example.</li><li>When submitting forms, use a tool or proxy to remove parameters (for Firefox, tamperdata is a great one). On the same note, if a site is using JavaScript to validate input before it is submitted to the server, use the proxy to change the values after they are validated in the event the developer just relied on the JavaScript.</li><li>Combining steps to create vulnerability. Again, with the Hackerone markdown example, having the hanging single quote combined with additional html later in the page with a single quote would create vulnerability. With Google's program, they include a multiplier whereby if you need multiple steps and you can actually demonstrate that all the steps are achievable, they'll increase your reward.</li><li>Consider where the vulnerability might actually show up. For example, Shopify's disclosure program states that it excludes vulnerabilities on your own store or cart (I learned the hard way from over excitement...). BUT, some of the fields that are used to create your store are used externally as well. There is an disclosure report indicating that the currency formatting field allowed for XSS injection. At first glance, you would think this shows up on the store page so who cares. BUT, Shopify provides integration with Facebook and Twitter using that same field and actually rendered the XSS resulting in a $500 bounty</li></ul>

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
  <li><a href="https://www.facebook.com/whitehat">Facebook</a></li>
  <li><a href="https://www.google.com/about/appsecurity/">Google</a></li>
</ul>

### Online Readings
<ul>
  <li>https://whitton.io/articles/bug-bounties-101-getting-started/</li>
  <li><a href="https://hackerone.com/hacktivity">Hackerone Hackactivity</a></li>
  <li>https://www.hackerone.com/blog/What-To-Do-When-You-Are-Stuck-Hacking</li>
  <li>https://www.quora.com/How-does-one-become-a-bug-bounty-hunter/answer/Jobert-Abma</li>
  <li>https://www.quora.com/How-much-time-did-you-take-from-completely-beginning-hacking-to-your-first-success-or-bug-bounty/answer/Jobert-Abma</li>
  <li>https://www.quora.com/How-do-bug-bounty-hunters-find-bugs/answer/Jobert-Abma</li>
  <li>https://www.quora.com/How-much-can-I-make-in-my-first-year-as-a-bug-bounty-hunter</li>
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
