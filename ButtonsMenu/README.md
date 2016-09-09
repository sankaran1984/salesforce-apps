Welcome Salesforce User/Developer !

In Salesforce, extending the functionalities through 'Buttons' is an excellent feature. 
So many of my clients using Salesforce for more than 5 years on avergage & one biggest problem they have is, 
'Too many buttons' in the detail page (or) list page for important objects like Account, Opportunity, Cases, etc.

![image](https://cloud.githubusercontent.com/assets/4547493/18390403/fbf4a46a-76a1-11e6-9aa6-4e72cd145ccf.png)


These are the consequences,
   1. Prevents adding more features though Buttons  
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
* Button1 -> 'Visualforce Page' Redirection
* Button2 -> 'Onclick Javascript' Execution
* Button3 -> 'Webservice' Execution
	
Now, Follow these steps to convert these buttons to Menu,
 1. Go to the 'Button, Links, Actions' Page for the Object on which you have these buttons.
 2. Create a button with name, say '☰ My Menu' (Note I have added a unicode character before the name 'My Menu', just to differentiate from normal button)
 3. choose 'Detail page button'
 4. choose behaviour 'Executing javascript' & content source 'OnClick Javascript'
 5. The code would be like this,
	
```javascript
{!REQUIRESCRIPT("/soap/ajax/9.0/connection.js")}
{!REQUIRESCRIPT("/soap/ajax/9.0/apex.js")}
{!REQUIRESCRIPT("/apex/ButtonsMenu")}

var m = ButtonsMenu(element,
	[
		{
			Label : 'Button1',
			onClick : onButton1Clicked
		},
		{
			Label : 'Button2',
			onClick : onButton2Clicked
		},
		{
			Label : 'Button3',
			onClick : onButton3Clicked
		}		
	]
);

function onButton1Clicked(){
	/*Page redirection to page1*/
	windows.location.href = '/apex/page1';
}

function onButton2Clicked(){
	/*Onclick javascript execution*/
	alert('Any custom logic in Javascript, goes here');
	
	//By default, once you click the button, label changes to 'Please Wait' while the 
	//webservice returns. So, in order to put back the original label, one need to call resetButtonBack()
	m.resetButtonBack();
}

function onButton3Clicked(){
	/*calling webservice called testservice*/
	var ret = sforce.apex.execute('WebServiceCls', 'testservice', 
		{'param1' : 'test'});
	
	//By default, once you click the button, label changes to 'Please Wait' while the 
	//webservice returns. So, in order to put back the original label, one need to call resetButtonBack()
	m.resetButtonBack();
}
```
 6. Add the new '☰ My Menu' button to the layout. Now, you have neat logical menu collating all those buttons.

 ![image](https://cloud.githubusercontent.com/assets/4547493/18401254/89dd868c-76d1-11e6-8b0b-b5a80d886117.png)


Happy Coding !
	
