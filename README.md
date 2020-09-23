<div align="center">

## Scaling problem warning about the browser sniffer control


</div>

### Description

ASP comes with a control named MSWC.BrowserType that can be used to detect the user's browser. In another article I posted, it detailed how to use it. However, if you have a heavy use web site, you need to read this warning.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Ian Ippolito \(vWorker\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/ian-ippolito-vworker.md)
**Level**          |Beginner
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |ASP \(Active Server Pages\)
**Category**       |[Server Side](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/server-side__4-31.md)
**World**          |[ASP / VbScript](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/asp-vbscript.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/ian-ippolito-vworker-scaling-problem-warning-about-the-browser-sniffer-control__4-7180/archive/master.zip)





### Source Code

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Planet Source Code receives a pretty decent volume of traffic about 6-7 hits/second. When I implemented some code to detect the user's browser using MSWC.BrowserType and copied it to production and interesting thing happened. For about an hour, the site functioned normally. But after an hour or so, the CPU would max out at 100% and the site would accept new connections but wouldn't post back any return content to the users.<BR>
<BR>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;When I unplugged the T1s, the CPU still wouldn't go down...telling me that IIS was hosed. This repeated itself for about 2-3 days (site crashing many times...having to reboot to fix) until I put two and two together and removed the MSWC.BrowserType code.<BR>
<BR>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Instantly the site went back to normal. So the lesson I learned is...use this component with care!<BR>
<BR>
For those who are interested, this was done on 2 machines running WLBS and Windows 2000 SP2.

