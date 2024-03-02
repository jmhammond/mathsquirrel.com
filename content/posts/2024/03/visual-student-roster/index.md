---
title: "Building a Chrome extension: Visual Student Roster"
author: ["John Hammond"]
date: 2024-03-02
thumbnailAlt: "goofy screenshot I used on Google's Chrome store."
summary: "Getting to know our students thanks to a little help from Github Copilot"
---

My institution used to have a feature built into our LMS called "Visual Student Roster." It was a nice way to see the photos of each student in your classes. You could use it to help you learn students names or (I was told the original reason it was created) verify the person taking tests in your class are actually in your class. 

However, it was cludgey code that was written by a well-meaning person and it took advantage of the fact that our student photographs were *publicly accessible* via API calls. A few semesters back, the University encountered a major hack and closed all these little holes. 

The faculty, however, hated the loss of the Visual Student Roster. I myself went an entire semester unaware of who almost all of my students were.  Our Office of Instructional Resources helpfully did provide that our administrative platform, Banner, provides student pictures:

{{< figure src="./bannerview.png" width="25%" default="true" alt="screenshot showing banner view" caption="That's as big as the pictures get...">}} 

... this was met with scepticism. The biggest issue that I heard from faculty was: 
1. Those pictures are far too small to be usable.
2. There is no way to print the roster.

A friend of mine pointed out, though, that those images are actually downscaled from 300x300 and that surely we could leverage that to recreate the roster.  I proposed this with tech people, but it never went anywhere.  If you want something done, better do it yourself!

I'd never developed a Chrome extension, but I know my way around javascript and I have access to Github Copilot through my [educator account](https://education.github.com/teachers). I decided that any time I'd normally search online for an answer, I would instead ask the copilot. After a lot of hours on one afternoon of tinkering, I was able to [publish my extension](https://chromewebstore.google.com/detail/visual-student-roster/fckdbhcgcinndiicpcnnefjcmbfopjma)! 

### Folder structure and manifest

> create the structure for a chrome extension

<details>
  <summary>Copilot output giving basic outline for the manifest and files needed in the folder structure.</summary>
Sure, here's a basic structure for a Chrome extension.
The structure of a Chrome extension is defined by a manifest file (manifest.json), which specifies metadata about the extension such as its name, version, permissions it requires, and the files it uses.
Here's a simple example of a Chrome extension structure:

```javascript
{
  "manifest_version": 2,
  "name": "My Chrome Extension",
  "version": "1.0",
  "description": "A simple Chrome extension",
  "permissions": ["tabs", "http://*/*", "https://*/*"],
  "browser_action": {
    "default_icon": "icon.png",
    "default_popup": "popup.html"
  },
  "background": {
    "scripts": ["background.js"]
  }
}
```
In this structure:

`manifest_version`: The version of the manifest file format. This should be 2.

`name`: The name of your extension.

`version`: The version of your extension.

`description`: A description of your extension.

`permissions`: An array of permissions that your extension needs to work. In this case, the extension can access and manipulate tabs and it can make requests to any URL.

`browser_action`: Defines how the extension will appear in the toolbar. This includes the icon that will be displayed and the HTML file that will be shown when the icon is clicked.

`background`: Specifies scripts that run in the background.

In addition to the manifest.json file, you would typically have other files such as:

`background.js`: This is a JavaScript file that contains background scripts for the extension. Background scripts are able to listen for events and interact with various Chrome APIs.

`popup.html`: This is an HTML file that defines the structure of the popup that appears when the user clicks on the extension's icon in the toolbar.

`icon.png`: This is an image file that is used as the extension's icon.

Please note that this is a very basic structure and real-world Chrome extensions can be much more complex.
</details>

So this was easy enough. I updated the relevant parts and got started. 

### GUI Components

After fighting to inject a button into the Banner UI, I gave up and decided to use the extension toolbar button as the UI mechanism (e.g. like Bitwarden).

> how can I tell if my extension icon has been clicked?

<details>
  <summary>Copilot giving guidance on the onClicked event, but noting that I can't actually use it!</summary>
In a Chrome extension, you can listen for clicks on your extension's icon by using the chrome.browserAction.onClicked event. This event is fired when a browser action icon is clicked. This event is not fired if the browser action has a popup.

Here's a basic example:
```javascript
chrome.browserAction.onClicked.addListener(function(tab) {
   // Your code here, e.g.:
   console.log('Browser action clicked!');
});
```

However, as your manifest file indicates that you're using Manifest V3 and a popup, you won't be able to use `chrome.browserAction.onClicked`. Instead, you can detect a click on your extension's icon by adding an event listener in the script of your popup page (popup.html).

Here's how you can do it:
```javascript
// In your popup.js linked to popup.html
document.addEventListener('DOMContentLoaded', function() {
    console.log('Browser action clicked!');
});
```

This code will run when the popup is opened, which happens when the user clicks on the extension's icon.
</details>

So that's neat, and the next thing I needed was that I wanted to be able to send messages between my `popup.js` file and the extension's `background.js`. So copilot helped here:

> how can I send a message with information

<details>
<summary> Copilot output explaining `sendMessage`.</summary>
In a Chrome extension, you can use the `chrome.runtime.sendMessage method` to send a message from the background script to other parts of your extension, such as a content script or a popup script.

Here's an example of how you can send a message:
```
chrome.runtime.sendMessage({greeting: "hello"}, function(response) {
  console.log(response.farewell);
});
```

In this example, an object with a greeting property is being sent. The second argument is a callback function that will be called when a response is received.

To receive this message in a content script or a popup script, you would use the chrome.runtime.onMessage event, like this:
```javascript
chrome.runtime.onMessage.addListener(
  function(request, sender, sendResponse) {
    if (request.greeting == "hello")
      sendResponse({farewell: "goodbye"});
  });
```

In this example, the `request` parameter contains the data sent in the message. The `sendResponse` function can be used to send a response back to the sender.
</details>

... and then I wrote the basic gui in html, played with getting the extension to open the required Banner page (so we can authenticate) and so now it was time to open a new tab... but Chrome wouldn't let me do that programmatically. I was a bit confused about it...

> how can i load a new tab from an extension popup?

<details>
<summary> Copilot explains I need the `tabs` permission</summary>
To open a new tab from a Chrome extension popup, you can use the chrome.tabs.create method. This method creates a new tab with the specified URL.

First, you need to add the "tabs" permission to your manifest file:
```javascript
"permissions": ["tabs"]
```

Then, in your popup script (popup.js), you can add an event listener to the link that should open the new tab. Here's an example:
```javascript
document.addEventListener('DOMContentLoaded', function () {
    var link = document.getElementById('click here');
    link.addEventListener('click', function () {
        chrome.tabs.create({url: 'https://ssbprod.wichita.edu/StudentSelfService/ssb/classListApp/classListPage'});
    });
});
```

In this example, when the element with the ID "click here" is clicked, a new tab will open with the specified URL. Note that the ID of your element contains a space, which is not recommended. Consider changing it to something without spaces, like "clickHere".

</details>

---

I also am always poor at remembering regex's to extract what I want. Copilot did a great job: 

> convert this string: "CRN 22309 Press enter key to view additional class details for Calculus I subject MATH, course 242 for term 202320 and course reference number 22309"   to  "CRN 22309 - Calculus 1"   

<details>
<summary>using the `match()` function</summary>
You can use JavaScript's `String.prototype.match()` method with a regular expression to extract the desired parts from the string, and then concatenate them into the format you want. Here's how you can do it:

```javascript
var str = "CRN 22309 Press enter key to view additional class details for Calculus I subject MATH, course 242 for term 202320 and course reference number 22309";
var crn = str.match(/CRN \d+/)[0]; // Matches "CRN " followed by one or more digits
var course = str.match(/for (.*?) subject/)[1]; // Matches any characters between "for " and " subject"

var result = `${crn} - ${course}`;
```

In this example, `match()` is used to find the parts of the string that match the provided regular expressions. The `[0]` and `[1]` after `match()` are used to get the matched string and the first capturing group, respectively. The `${}` syntax is used to insert the matched parts into the result string.
</details>


### Accessing the images

I now went into my `background.js` and started querying the all the `img` objects in the DOM.  Since a lot of the images on the page are unnecessary noise, I filtered the array to include only those whose source included `"classListPicture"`. 

I created a blank tab that populated with a table of student pictures, and I was pretty excited that it all worked! 

... except I noticed that it only worked in my small classes. In the classes with more than 25 students, I was only getting about 25 pictures... Uh oh!  I finally realized that Banner is dynamically loading the images as I scrolled. They didn't exist in the DOM until manually scrolling.  I was about to google it, but I turned to copilot:

> can I cause the page to scroll using javascript

(yes, but it didn't work for Banner, because it's an SPA).

> how can I force an spa to scroll down?

(better, but still didn't work because Banner wasn't fooled)

> how can I simulate a scroll event on an spa?

(much closer to what I want, but I can't guarantee the pixel height for someone else's monitor)

> send a scroll event to a an element we query

(still not quite there... but I realized the Banner has a "how many records per page"), so after trying all the scrolling, I ended up with: 

```javascript
        // By default, Banner class list only shows a few images; we have to 
        var selectElement = document.querySelector('.per-page-select');
        selectElement.value = 'number:100';
        selectElement.dispatchEvent(new Event("change"));
```
so we're now pulling 100 records each time.  I added a prompt to let users know if they have a class with more than 100, they need to manually "next page" and use the extension to print in blocks of 100. 

### More Assistance

After I completed my working prototype, I needed to submit it to the Chrome store so that others could test it for me. Copilot again was helpful in giving me advice about how to package it (simply a zip file), whether my code had any remote execution, and other security questions from Google.

I also spend hours with Copilot trying to port it to Firefox, but after 3 hours, I gave up. 

### If you're interested in the whole chat history:

You can actually see all of the [github copilot chat history in a json file](./chat.json), if you'd like to see the whole journey. I've yada-yada'd over a lot of details. 

