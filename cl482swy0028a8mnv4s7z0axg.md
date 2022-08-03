## How to hide the source code of an HTML web page?

Here are some techniques if you want to restrict your visitor to view or scrap your HTML code in inspect element:

> You can disable Ctrl and F12 keys using javascript

F12. Opens **Chrome’s Developer Tools**. F12 tools provide a set of tools that you can use **to view webpage source code and behavior**.

Ctrl key is mostly used in the combination with other keys to view the source code of the web.

for example:

> Ctrl + S: It is used to save a whole web page.

> Ctrl + U: It is used to open source code of web in new tab.

You can use this code in the **script tag** to apply this change.


```
document.addEventListener("keydown", function (event){

    if (event.ctrlKey){

       event.preventDefault();

    }

    if(event.keyCode == 123){

       event.preventDefault();

    }

});
``` 


> You can disable mouse right click using javascript

By clicking right-click on the webpage, it will give you the option to view and inspect the source code of the web.

You can use this code in the **script tag** to apply this change.


```
document.addEventListener('contextmenu',   
     event => event.preventDefault()  
);
``` 


> Is it enough?

These two techniques are good for non-technical visitors or for some people who have just joined the Computer science field.

![coding meme](https://cdn.hashnode.com/res/hashnode/image/upload/v1654843006631/Hk_bufSdt.jpeg)


What about Web developers (technical experts)?

They can still view the source code of the web using chrome extension, HTML interceptor (BURP), or postman.

![postman](https://cdn.hashnode.com/res/hashnode/image/upload/v1654843007987/xBw4_vGP4.png)

View source code in postman

> THEN HOW TO HIDE?

> You can't hide your HTML source code in browser anyway because your browser needs HTML code to run and view the web page.

However, here are some other techniques to minimize web scraping or code copy-pasting :

*   Use REACT JS to minimum encapsulate your source code.
*   Use server-side rendering to change code structure from time to time.
*   Apply copyright act for legal actions.
*   enable SSL certification to encrypt data between client and server-side.

> Conclusion

If you hide some website code, the Google crawler can still read it, but certain parts, such as No-Follow and No-Index, will tell the crawler whether or not to index the site.

> **“Hiding text or links in your content to manipulate Google’s search rankings can be seen as deceptive and is a violation of Google’s Webmaster Guidelines.”**

You can hide data from users but not from crawlers, but now bots can read all of your website’s source code.

I think the hiding of source code is not a good idea. You might be facing some SEO issues in the future.