# AJAX-Load-Learn
What is Synchronous & Asynchronous

Actually, Synchronous means at a time we can send single request and we need to wait for the response before send the second request, and Asynchronous means we can send the second request before we get the response of first request, Ajax is the example of this Asynchronous type.

What is DOM
Every web page resides inside a browser window which can be considered as an object.
 The Document object has various properties that refer to other objects which allow access to and modification of document content.

The way a document content is accessed and modified is called the Document Object Model, or DOM. The Objects are organized in a hierarchy. This hierarchical structure applies to the organization of objects in a Web document.
1) Window object - Top of the hierarchy
2) Document object 
3) Form object 
4) Form control elements

Reference: http://www.tutorialspoint.com/javascript/javascript_html_dom.htm

When a web page is loaded, the browser creates a Document Object Model of the page. The Document Object Model (DOM) is a cross-platform and language-independent convention for representing and interacting with objects in HTML, XHTML, and XML documents.
The DOM Programming Interface

The HTML DOM can be accessed with JavaScript (and with other programming languages).
In the DOM, all HTML elements are defined as objects.

The programming interface is the properties and methods of each object.
A property is a value that you can get or set (like changing the content of an HTML element).
A method is an action you can do (like add or deleting an HTML element).
Example

The following example changes the content (the innerHTML) of the <p> element with id="demo":
Example

<html>
<body>
<p id="demo"></p>
<script>
document.getElementById("demo").innerHTML = "Hello World!";
</script>
</body>
</html>

What is AJAX
AJAX stands for Asynchronous JavaScript and XML. AJAX is about updating parts of a web page, without reloading the whole page. AJAX is a new technique for creating better, faster, and more interactive web applications with the help of XML, HTML, CSS, and Java Script.

With AJAX, when you hit submit, JavaScript will make a request to the server, interpret the results, and update the current screen. In the purest sense, the user would never know that anything was even transmitted to the server.

How AJAX works:
AJAX communicates with the server using XMLHttpRequest object:

    User sends a request from the UI and a javascript call goes to XMLHttpRequest object.
    XMLHttpRequest object send HTTP Request to the server (using open() and send() methods)
    Server interacts with the database using JSP, PHP, Servlet, ASP.net etc.
    Data is retrieved.
    Server sends XML data or JSON data to the XMLHttpRequest callback function.
    HTML and CSS data is displayed on the browser.
Reference: http://www.javatpoint.com/how-ajax-works

Take this perfect ajax example: http://www.w3schools.com/ajax/tryit.asp?filename=tryajax_first
with this tutorial explanation: http://www.w3schools.com/ajax/ajax_example.asp

Ajax states:
http://www.w3schools.com/ajax/ajax_xmlhttprequest_onreadystatechange.asp


Important Link:
1) http://www.tutorialspoint.com/ajax/what_is_ajax.htm
2) http://www.w3schools.com/ajax/ajax_intro.asp


============== jQuery Ajax ================
jQuery provides several methods for AJAX functionality.

With the jQuery AJAX methods, you can request text, HTML, XML, or JSON from a remote server using both HTTP Get and HTTP Post - And you can load the external data directly into the selected HTML elements of your web page!
The jQuery’s $.ajax() function is used to perform an asynchronous HTTP request.

Important point:
1) Async: True/False
  Setting async to false means that the statement you are calling has to complete before the next statement in your function can be called. If you set async: true then that statement will begin it's execution and the next statement will be called regardless of whether the async statement has completed yet.
2) $.support.cors = true;  // To add ajax/json support for IE

The following example loads the content of the file "demo_test.txt" into a specific <div> element:
Example
$("#div1").load("demo_test.txt");

Another example:
$.ajax({
   url: 'http://api.joind.in/v2.1/talks/10889',
   data: {
      format: 'json'
   },
   error: function() {
      $('#info').html('<p>An error has occurred</p>');
   },
   dataType: 'jsonp',
   success: function(data) {
      var $title = $('<h1>').text(data.talks[0].talk_title);
      var $description = $('<p>').text(data.talks[0].talk_description);
      $('#info')
         .append($title)
         .append($description);
   },
   type: 'GET'
});

Reference: http://www.sitepoint.com/use-jquerys-ajax-function/
