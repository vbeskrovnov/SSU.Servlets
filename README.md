Servlets:
---------
1) Create maven project
2) Add maven dependency
```xml
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>servlet-api</artifactId>
            <version>2.5</version>
            <scope>provided</scope>
        </dependency>
```
3) Create HelloServlet extends HttpServlet
4) Override GET method
5) Create 'WEB-INF/web.xml'
```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app version="2.4" xmlns="http://java.sun.com/xml/ns/j2ee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://java.sun.com/xml/ns/j2ee
http://java.sun.com/xml/ns/j2ee/web-app_2_4.xsd">

    <servlet>
        <servlet-name>Hello servlet</servlet-name>
        <servlet-class>com.beskrovnov.HelloServlet</servlet-class>
    </servlet>

    <servlet-mapping>
        <servlet-name>Hello servlet</servlet-name>
        <url-pattern>/hello</url-pattern>
    </servlet-mapping>
</web-app>
```
6) Download tomcat from http://mirror.linux-ia64.org/apache/tomcat/tomcat-9/v9.0.5/bin/apache-tomcat-9.0.5.zip
7) Build project
8) Create structure in tomcat webapps directory
```
\--Tomcat
     \--webapps
          \--<App Name>
               \--WEB-INF
                   \--web.xml 
                    \--classes
                         \--com
                              \--<YourPackage>
                                   \--<YourClass>.class
```

8) Run tomcat `/bin/startup.bin`
5) Open `localhost:8080/<App Name>//hello`


JSP:
----
1) Create JSP in `src/main/webapp/first.jsp`, with:
```xml
<html>
<head><title>First JSP</title></head>
<body>
  <%
    double num = Math.random();
    if (num > 0.95) {
  %>
      <h2>You'll have a luck day!</h2><p>(<%= num %>)</p>
  <%
    } else {
  %>
      <h2>Well, life goes on ... </h2><p>(<%= num %>)</p>
  <%
    }
  %>
  <a href="<%= request.getRequestURI() %>"><h3>Try Again</h3></a>
</body>
</html>
```
2) Build project
3) Create structure in tomcat webapps directory
   ```
   \--Tomcat
        \--webapps
             \--<App Name>
                  \--<YourJspName>.jsp
                  \--WEB-INF
                      \--web.xml 
                       \--classes
                            \--com
                                 \--<YourPackage>
                                      \--<YourClass>.class
   ```
4) Run tomcat `/bin/startup.bin`
5) Open `localhost:8080/<App Name>/<YourJspName>.jsp`
