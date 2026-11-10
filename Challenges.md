## Scoreboard  
A scoreboard webpage has been hidden from links on the Juice Shop web app.  
### Goal  
Find the URL to the scoreboard.
### Approach  
1. Open the web browser developer tools with F12 for this browser.
2. Go to the debugger / sources tab.
3. Open the Javascript resources and begin with main.js.
4. Search within this script with Ctrl + F to find instances of 'score' or 'routerLink' to locate URLs.
   
You will locate the 'score-board' routerLink defined within the web application. 

http://127.0.0.1:3000/#/score-board  

This scoreboard page now can be used to track your challenge progress.  
### Lesson Learned  
Any resource that is part of the front end can be examined by dowloaded and viewed by clients. Be careful what is included in these files. 
This could be viewed as code, comments, or assets.

## DOM XSS 
Document Object Model (DOM) is a structured representation of web document where HTML elements is represented as a node in a tree diagram.  
Cross-Site Scripting is a type of web security vulnerability where an attacker injects code into a website, causing it to be run client side on another user's browser. 
Web Apps with forms for user inputs can be susceptible to these vulnerabilities.  
### Goal  
Use the Juice Shop web App to run a DOM XSS.

### Approach  
The scoreboard page provides a summary of this challenge which includes the injection payload to use.  
```
http://127.0.0.1:3000/#/search?q=<iframe src%3D"javascript:alert(`xss`)">
```
Enter this payload into the search box on the Juice Box site, then search to run it. The result is a JavaScript alert with the text 'XSS'.  

### Lesson Learned  
This is an example web app that does not contain any real data. In order to prevent this XSS vulnerability use  
- Input validation used to verify the input meets application expected format.
- Output encoding used to confirm input code is treated as text and is not interpreted to run on the browser.
- HTML sanitization used to remove or replace elements that might cause code to be executed.

## Login Jim  
Following the interactive tutorial for guidance.  
### Goal  
Login as the user Jim without knowing the user account or the password.
### Approach  
The interactive tutorial states that the login for Jim was shared in the product reviews page. 
See the product reviews under the menu and Customer Feedback. Jim's review is under the Green Smoothie product. 
His email address is  
*jim@juice-sh.op*    
Return to the interactive tutorial and input the email address. The tutorial instructs to add '-- after the user account along with any password.
This logs in to Jim's account.  
### Lesson Learned  
A web application might be vulnerable to SQL injections for input fields. In this login demonstration, suppose the SQL query is as follows  
```
SELECT * FROM users
WHERE username = 'jim@juice-sh.op'
AND password = 'qwerty';
```
In SQL syntax the '-- means 
- A single quote which matched the username beginning single quote with an ending quote
- Two hyphens used as comments 
Place these symbols back into the SQL query looks like the following  
```
SELECT * FROM users
WHERE username = 'jim@juice-sh.op'--'
AND password = 'qwerty';
```
SQL interprets double hyphen as a comment. The remaining query is commented out. This leaves the SQL to soley the starting query up until the point of the comment
```
SELECT * FROM users
WHERE username = 'jim@juice-sh.op'
```
The interpreted query finds the matching username without matching the password. Role of the database is to return a matching record, 
not to determine user access.


  
