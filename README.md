1) Create maven project
2) Add maven dependency
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
7) Create structure
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