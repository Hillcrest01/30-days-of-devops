Apache Tomcat is an open-source web server and Servlet Container developed by the Apache Software Foundation. While often called an "Application Server," it is technically a web server designed specifically to execute Java Servlets and render JavaServer Pages (JSP).

  Key Components
1. Catalina (The Servlet Container)
Catalina is the engine that actually implements the Java Servlet specification. It manages the lifecycle of your servlets (init, service, destroy). When you deploy a .war file, Catalina unpacks it and loads the classes.

2. Coyote (The Connector)
Coyote handles the network communication. It supports HTTP/1.1, HTTP/2, and AJP protocols. It manages the thread pool, creating threads to handle incoming requests efficiently.

3. Jasper (The JSP Engine)
If your application uses .jsp files (JavaServer Pages), Jasper is responsible for parsing them. It compiles the JSP file into a standard Java Servlet (.class file) so that Catalina can execute it. This is why the first load of a JSP page is slow (compilation) but subsequent loads are fast.

  The Request Lifecycle: From Browser to Servlet
What happens when a user types http://localhost:8080/my-app/hello?

Accept: The Coyote Connector listening on port 8080 accepts the TCP connection.
Parse: It parses the HTTP headers and creates HttpServletRequest and HttpServletResponse objects.
Route (Engine): The Connector passes these objects to the Engine, which looks at the hostname (localhost).
Route (Host): The Engine passes the request to the matching Host.
Route (Context): The Host looks at the URL path (/my-app) and passes the request to the correct Context (your application).
Execute (Servlet): The Context looks at the specific mapping (/hello) and invokes the corresponding Java Servlet code.
Response: The Servlet writes data to the response object, which travels back up the chain (Context -> Host -> Engine -> Connector) and is sent back to the user's browser.

Downloading and extracting in Linux:
  wget https://downloads.apache.org/tomcat/tomcat-9/v9.0.x/bin/apache-tomcat-9.0.x.tar.gz tar xzvf apache-tomcat-9.0.x.tar.gz sudo mv apache-tomcat-9.0.x /opt/tomcat
Create a service user and fix permissions
  sudo useradd -r -m -U -d /opt/tomcat -s /bin/false tomcat sudo chown -R tomcat: /opt/tomcat sudo chmod +x /opt/tomcat/bin/*.sh


  Practical was done in the ubuntu server where maven was previously installed.

  NEXT UP - Jenkins
