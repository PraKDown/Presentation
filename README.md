# Browser extension api  
## 1 Slide  
Extensions are zipped bundles of HTML, CSS, JavaScript, images, and other files used in the web platform, that customize the Google Chrome browsing experience. Extensions are built using web technology and can use the same APIs the browser provides to the open web.
Extensions have a wide range of functional possibilities. They can modify web content users see and interact with or extend and change the behavior of the browser itself.  
## 2 Slide  
Architecture  
Here's a diagram of the architecture for a Chrome extension:
And now let's take a closer look at each element within the architecture.
#### 2.2  
The entry point of your extension is the manifest.json file. It should contain a valid JSON object. 
The required properties are name, version, and manifest_version. The version can be anywhere from one to four, dot-separated integers. It's something which is used by Google's autoupdate system. That's how it knows when to update your extension. The value of the manifest_version should be the integer 2.
The manifest could contain other properties depending on what kind of extension you need.
#### 2.3
Every extension has an invisible background page which is run by the browser. There are two types - persistent background pages and event pages. The first one is active, all of the time. The second is active only when it is needed.
if the persistent property is false then you are using event pages. Otherwise, you are working with a persistent background page.
#### 2.4	
If you need access to the current page's DOM, then you have to use a content script. The code is run within the context of the current web page, which means that it will be executed with every refresh.
that the value of matches determines for which pages your script will be used.
#### 2.5
There are several ways to build the UI of your extension. Here are the four most popular: Browser Action, Page Action, DeveloperTools, Omnibox
#### 2.6
Most developers use the browser_action property to build their plugins. Once you set it, an icon representing your extension will be placed on the right side of the address bar. Users can then click the icon and open a pop-up which is actually HTML content controlled by you.
#### 2.7
The page_action property is similar to the browser action, but the icon is shown inside the address bar.
The RSS icon will be shown only if the current page contains a link to the RSS feed. If you need to see your icon all the time, it is good to use browser_action directly.
#### 2.8
The first thing you should do is add an HTML page which will be loaded when the panel is opened.
There's no need to put any HTML inside the page, except for linking in a JavaScript file, which will create the tab.
And then include the code inside the devtools.js file.
Now the above code will add a new tab with a name of TheNameOfYourExtensionand once you click on it the browser will load index.html inside the DeveloperTools.
#### 2.9
The omnibox is the keyword which is shown inside Chrome's address bar.
You should be able to type yeah inside the address bar.
Pressing tab will produce the screen.
## 3 Slide
There are bunch of different things which you can do in your extension. For example, you can get access to the user's bookmarks or history. You can move, create tabs or even resize the main window.
Chrome apis are divided into the following groups :
1.	Stable APIs
2.	Beta APIs
3.	Dev APIs
4.	Experimental APIs
5.	API conventions
#### 3.1
Example
Four color options are provided then generated as buttons on the options page with onclick event listeners. When the user clicks a button, it updates the color value in the extension's global storage. Since all of the extension's files pull the color information from global storage no other values need to be updated.
#### 3.2
Chrome Extensions have access to powerful APIs above and beyond what's available on the open web. You can view the documentation at the following link.
## 4 Slide
There is a way to test your extension without having to upload it to Chrome's web store. In your browser's address bar, just type in:
Make sure that you check Developer mode and click the Load unpacked extension... button. Then simply select the folder from your hard disk which contains the extension's files.
## 5 Slide
Thanks for attention!
