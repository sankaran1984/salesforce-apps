Welcome Salesforce User/Developer !

In Salesforce, extending the functionalities through 'Buttons' is an excellent feature. 
So many of my clients using Salesforce for more than 5 years on avergage & one biggest problem they have is, 
'Too many buttons' in the detail page (or) list page for important objects like Account, Opportunity, Cases, etc.

![image](https://cloud.githubusercontent.com/assets/4547493/18390337/b5168b12-76a1-11e6-8964-cbb6acb49cf2.png)

This prevents them from,
   1. Adding more features though Buttons  
   2. Confusing users as they have to figure out the right button to click, from pools of buttons.
   3. In worst case, it gives bad usability on Salesforce product itself.
   
I have a solution for this !!

Steps for the Solution:
-----------------------
1. create a new Visualforce Page & paste the contents of the file 'ButtonsMenu.page'
    (or)
   In Force IDE, you can drop 'ButtonsMenu.page' file under 'Pages' directory & click 'Refresh' under the project's
   right click menu.

Usage Examples:
---------------
Let's assume we have three buttons(which all logically related) that does the following,
	Button1 -> 'Visualforce Page' Redirection
	Button2 -> 'Onclick Javascript' Execution
	Button3 -> 'Webservice' Execution
	
Now, Follow these steps to convert these buttons to Menu,
1) Go to the 'Button, Links, Actions' Page for the Object on which you have these buttons.
2) Create a button with name, say '= My Menu'
3) choose 'OnClick Javascript'
4) The code would be like this,
	
	<code>
	
Happy Coding !
	
