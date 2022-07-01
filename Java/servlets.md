- A server is a piece of hardware or software with high processing capacity than normal computers, which provides functionality to connect to other programms or devices in the internet with http protocol.
- There are two type of servers. 1.web server 2.application server.
Difference between webserver and Application server
- A webserver handles the static content that is of HTML documents or audio, video etc formats, most of the web servers also considered as servlet containers because they provide features of servlet/jsp processing.Even webservers process some dynamic content through servlets/jsp but they can't handle entire suite of enterprise edition of EJB.
Eg. Tomact, IIS

- An application server handles both static and dynamic content, application servers moslty process the requests of enterprise applications, and the application has the inbuilt webservers and applications servers consumes more resources than a webserver. It also supports multithreading.
Eg.Weblogic, Jboss, websphere, glassfish.

- A servlet is nothing but java files which are present in a server which is also known as web container, which takes request from the client and process the request on server and sends the response back in the form of html format.

- Servlet is a java file which runs on servlet container which is nothing but a web or application server, that provides network services for recieving requests and sending responses.

# Servlet context and servlet config
- Servlet context and servlet config are interfaces and the objects of these interfaces will be created by the server(tomcat), we just have to provide the object references, thats it.
- Servlet context and config are the objects that are created when a servlet is initialized and these objects provides initial parameters or information to the servlet. The main difference between these are that information shared by servlet config is for specific servlet and info shared by servlet context is for all the servlets in the web application.

- Servlet config is a object which is created by the servlet container and it has initial parameters and configuration information which are passed to servlet during initialization.The information is shared with only one specific servlet.Every servlet has its own servlet config.
The information is stored in the form of name-value pair in <init-parameter> inside a servlet, and the servlet config object can be obtained by using the getServletConfig() method.

- Servlet Context is a object which is created by the servlet container to share the initial parameters and information to the whole web application.Whole web application has only one servlet context.
The information is stored in the form of name-value pair in <context-param> outside the servlet and inside the web application. Servlet context object can be obtained by using the getServletContext() method.

- getInitParameter is method which will give us the value of an attribute, which is passed as a parameter.

- We can't set attributes in servlet config object, where as we can set attributes in servlet context which can be used by all servlets.

# Service methods
- Get method is used to get data from the server. Get requests can be cached and stored in the browser history and data is exposed in the url and can be bookmarked

- Post method is used to post data to the server/update the server. It can't be cached, not stored in browser history and data is not exposed in the url

- Put method is similar to post method, the only difference is put method is idempotent, which means calling the same put request will always produce same results.

- Head method is similar to Get method, the difference is head method returns only status codes and content type of the data

- Options method is used to know what are the methods that the server will support to communicate

- Delete method deletes the data on specified resource.

- Trace method is used to trace the path of the request sent to the server.

- Request Dispatcher is used to call a servlet from another servlet, and we can pass the parameters from the other servlet using set and get attributes.

# What is Tomcat?
Tomcat is a http server as well as a web container.

- Client and server communicate with the help of http
- Http is a protocol, contains web specific features
- Http is responsible for sending file from source to destination completely
- Client sends a http request, server responds with a http response.
Http request contains url, http methods and some other parameters.GET and POST are the most used ones.
HTTP response contins status code, content type and actual content.


# LIFE CYCLE of Servlet
A servlet is program which runs within a web server. Servlets recieve a request from the client and that request is processed and it will be sent back in the form of a static or a dynamic web page, usually across http protocol.
To implement this interface, we can write a generic servlet that extends a javax.servlet.Generic or a HTTP servlet that extends javax.servlet.HttpServlet.
The servlet is developed and inititalized with the init method.
Then the request from the client side are proccessed with the help of service methods, after successfully completing the init method.
After handling the requests, the servlet is taken out of the service and destroyed with the destroy method, then garbage collected and finalized.
The interface also provides the servletconfig method which provides initial parameters and startup information to the servlet, this method is specific for every method. Similarly we also have servlet context method, which also provides initial parameters and startup information to the servlet, but this method is for whole web application.

1.init() method takes servlet config as parameter and it cannot place the servlet into service method if the init method throws a servlet Exception.
2.service() method takes two objects as parameters they are servlet request and servlet response, it is only called after the successful completion of init method. This method runs in multithreaded web containers that can handle multiple requests concurrently.
3.destroy() method is called by the servlet container to indicate a servlet is taken out of service, this method is only called once all threads are exited, once this method is called, it will not call the service method again.

Difference between Generic and Http servlet
-> One common feature is, both these Classes are Abstract Classes.
-> GenericServlet is a super class of HttpServlet class.
-> The main difference is that, HttpServlet is a protocol dependent whereas GenericServlet is protocol independent. So GenericServlet can handle all types of protocols, but HttpServlet handle only HTTP specific protocols.
-> GenericServlet belongs to javax.servlet package. HttpServlet belongs to javax.servlet.http package
-> GenericServlet is an abstract class which extends Object and implements Servlet, ServletConfig and java.io.Serializable interfaces. HttpServlet is an abstract class which extends GenericServlet and implements java.io.Serializable interface.
-> GenericServlet supports only service() method does not contain doGet() and doPost() methods. HttpServlet support doGet(), doPost(), doHead() methods, plus doPut(), doOptions(), doDelete(), doTrace() methods.

**Difference between cookies and session**
*Cookies*:These are small files that are created when the request is sent to the server, and these files are sent to the client with response that is generated by the server. These cookies are stored in the client machine and won't be lost until the user deletes them, and cookies store only strings.

*Session*: It is similar to cookie, where the session id is generated when the request is sent to the server and server sends the session id to the client with the response, whenever client sends the request again to the server the id which is generated will sent back to server and server verifies the id and remebers the previous interaction. The session will store the user info on the server side and it will get lost when the user closes the browser, it can store all types of objects.

URL rewriting
- URL rewriting is fall back option or kind of backup option, which is enabled when the coolies are disabled. URL rewriting method uses the session id which is previously generated, and appends it to the url, so that the browser knows the user is previously requested or not.

- Hidden form field is a method used to track the session of client, where a hidden form is created which passes the control the servlet which is mentioned in the form action area. Using this method the user information can be stored and transferred to location where we want to store the data. The main advantage of hidden form field is that, it works fine even though the cookies are disabled in the browser.

**Methods of request dispatcher**
- Request Dispatcher is an interface in javax.servlet, this interface is used to transfer the control over to other resource in the application, by creating object or instance to the interface, this will be done by the server itself, in our case it is tomcat. We just needs to provide the object reference and the instance can be get by using request.getReqeustDispatcher();
This interface is having two methods, they are.

*forward() and include()*

- forward() tag takes two parameters they are the reference of the servlet request and servlet response, this tag is used to forward the request over the other servlet which is present in the same application. Consider the application is having two servlets A and B, whenever there is forward tag in A and the request is send to servlet B, the control will still be in servlet A, untill the process encounters another forward tag in servlet B, and the control is shifted to B and after finishing the process the control will not return back to A.

- include() is similar to forward() but the only difference is that the control will be returned back to the servlet A after the process is completed in servlet B

MIME: Multipurpose Internet Mail Extensions it describes what type of data the file contains.

Methods of Servlet request and response
**Servlet Request**
object getAttribute() = return value of request attributes as an object
 int getContentLength()= return the length of request in bytes
String getContentType() = return the format of the data(MIME type)
String getParameter() = return request parameter as a string
String getProtocol() = returns name and version of the request protocol
int getRemotePort() = return IP port of the client
String getServerName() = returns host name of the server to which the request has been sent

**Servlet Response**
void flushBuffer() = forces the content in the buffer to be written to the client
int getBufferSize() = returns actual buffer size
String getContentType() = return the type used to send this response
PrintWriter getWriter() = used to send the character text to the client
void reset() = clears the status code, buffer and header data
void setBufferSize(int size) = sets the specified buffer size
void setContentType(String type) = sets the content type of the response being sent to client

# Http protocol
HTTP protocol is an application layer protocol which is used to transfer information between networked devices, http protocol is used to transfer the data in the form of plain text, audio, video, and process the static contents such as HTML documents.
Http protocol is same as FTP but the only difference is FTP takes multiples connections to transfer the data, where http takes only one connection
Http is also similar to SMTP(Simple Mail Transfer Protocol) but the only difference is that smtp stores and then delivers the message, http sends the message directly.

# *HTTP status codes*
1.Information response(100-199)
2.Successful response(200-299)
3.Redirect(300-399)
4.Client errors(400-499)
5.Server errors(500-599)

**Filters in servlet**
Filter is an interface in javax.servlet, object for this interface is created by the server. Filter is an object that is used to perform filtering tasks such as conversion, compression, loging, authentication etc, which is invoked at preprocessing and postprocessing of the request. It contains three methods init(), doFilter(), and destroy(). Init and destroy methods are only called once in the life cycle of the same as servlet. doFilter() is the one responsible of performing the filtering tasks. Filters are pluggable which means the info about the filters are stored in xml file, if there is no need of using filters in the application we can remove the tags belonging to filter and thats it, there is no need of changing servlet. The order of the filter depends on which order we declared the filter tags in xml file.

Filter chain
It is an object in do filter method which is responsible of sending the request to next filter or the next resource.

Filter config is same as servlet config where the initial parameters for the filter is passed using init param tags.

HTTP process
When ever there is http request from the client the reqeust will be sent in the form of http headers which will be converted by the web browsers, Http headers contains the method, http root directory and version and it also contains the information about the content type of the reqeust. Request to the server is sent using form action field of html. Request form the client machine is sent to the server, server contains a container which is known as deployment descriptor which is also known as web.xml file, which contains tags and these tags map the servlet that needed to be loaded, servlet process the reqeuest, and response will be sent back in the form of html format. Http response message contains the method, status code and status message, and also contains the time, content type of the response.

JSP
Java Server Pages
Jsp is written in html code, where as in servlets we write html in out.println(). Even though we write servlet code in html it will be ultimately converted to servlet, which is done by the servlet container itself. 
Jsp contains tags which helps us to write java code in html or jsp file. they are
Scriptlet tag - <% %> code which is written in these tags will be transfered to service method of servlet after conversion.

Declaration tag- <%! %> this tag is used to write code out side of the service method.

Directive tag <%@ %> this tag is used to import the packages

Expression tag <%= %> this tag is used to print the values without writing out.println statement.

Jsp has implicit objects, which means the objects will be created by the servlet itself, we just have to mention the object references that are already declared.

Jsps are easy to create but the processing speed of jsp is little bit slower compared to servlets, because jsp files are converted to servlets which will take some time.
JSP directive tags
@page
@include
@taglib

Implicit objects in JSP
request: It is an object reference for HttpServletRequest used to get the request from the client
response: It is an object reference for HttpServletResponse used to send response to client
out: is an object reference for PrintWriter class used to print something on the client side
pageContext: is an object of PageContext class which is used to define the scope for an attribute
application: is an object of ServletContext whose purpose is as same as servletContext
config: is an object reference of ServletConfig whose purpose is as same as servletConfig
exception: is an object reference of Throwable class, used to catch the exception and display the error message
session : is an object reference of the HttpSession interface, used to get the session
page: page is an instance of JSP implementation class which is created at the time of translation. Page is synonymous with "this " in java.