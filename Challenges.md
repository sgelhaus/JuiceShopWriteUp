## Scoreboard  
### Goal  
The scoreboard has been hidden from links on the Juice Shop web app. Find the URL to the scoreboard.
### Approach  
1. Open the web browser developer tools with F12 for this browser.
2. Go to the debugger / sources tab.
3. Open the Javascript resources and begin with main.js.
4. Search within this script with Ctrl + F to find instances of 'score' or 'routerLink' to locate URLs.
   
You will locate the 'score-board' routerLink defined within the web application. 

http://127.0.0.1:3000/#/score-board  

### Lesson Learned  
Any resource that is part of the front end can be examined by dowloaded and viewed by clients. Be careful what is included in these files. This could be viewed as code, comments, or assets.
