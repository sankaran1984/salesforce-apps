Welcome Salesforce User/Developer !

I use Developer Console/ Force IDE most of the time. But, i tend to use Web UI Editor quite few times everyday, mainly for 2 purposes,
 1. 'Quick Save' Feature
 2. Very quick to edit few files. 
    Force IDE & Developer Console gets painfully slow, if there's any async process goes on in the background.
	
Have you ever wondered why Editor in Salesforce Web UI is so small ?
![smalleditor](https://cloud.githubusercontent.com/assets/4547493/18382688/0093fd86-767a-11e6-86c1-a290ae043b0e.JPG)
	
I have a solution for that !

Steps for the solution
----------------------
1. This will work with Stylebot, which is a Google Chrome Extension in Google Chrome.
   Install Stylebot from <url>
2. Right Click 'Stylebot' icon in the toolbar & click 'Options'
3. In Options Page, Click 'Styles' under 'Stylebot Options' in the Lefthand side navigation menu
4. Click 'Add a new style' button under 'Styles',
    * In new dialog box, in URL field, paste this,
	       **salesforce.com**viewApexClass**,**salesforce.com**editApexClass**
    * In the content box(that follows the url field), copy/paste the content from 'Apex.css'
5. Click 'Add a new style' button under 'Styles',
    * In new dialog box, in URL field, paste this,
	       **salesforce.com/*/e?retURL=**ApexComponent.apexp**,**salesforce.com/*/e?retURL=**ApexPage.apexp**,**salesforce.com/**editVFEmailTemplate.apexp**
    * In the content box(that follows the url field), copy/paste the content from 'Visualforce.css'	

Now, try to edit any apex/trigger/visualforce page/visualforce component in web UI.
you get the maximum size of the source code editor, i.e covering the whole window size.

Happy Coding !!
