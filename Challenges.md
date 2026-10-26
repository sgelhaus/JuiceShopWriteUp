## Scoreboard  
### Goal  
The scoreboard has been hidden from links on the Juice Shop web app. Find the URL to the scoreboard.
### Approach  
To view resource that compose a web application, use the developer tools. Press F12 to open developer tools in this browser.
In the debugger tab, choose the main.js script as a starting point. Search within this script with Ctrl + F to find instances of 'score'.
Many results are found for 'score'. Also try 'routerLink' to locate URLs. Still there is many matches.
With these search methods, you will stumble upon the 'score-board' routerLink. This URL has been located.  

http://127.0.0.1:3000/#/score-board  

### Lesson Learned  
All scripts and resources which compose a web app can be downloaded and accessed by clients. Be careful what is included in these files. 
