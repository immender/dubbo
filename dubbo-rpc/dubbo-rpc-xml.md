# dubbo-rpc-xmlrpc

A RPC Extension for XML-RPC\([http://ws.apache.org/xmlrpc](http://ws.apache.org/xmlrpc)\)

## Maven dependency：

```markup
<dependency>
    <groupId>org.apache.dubbo</groupId>
    <artifactId>dubbo-rpc</artifactId>
    <version>2.7.3-SNAPSHOT</version>
</dependency>
```

## Configure：

Define xmlrpc protocol:

```markup
 <dubbo:protocol name="xmlrpc" port="8080" server="jetty" />
```

Set default protocol:

```markup
<dubbo:provider protocol="xmlrpc" />
```

Set service protocol:

```markup
<dubbo:service protocol="xmlrpc" />
```

Multi port:

```markup
<dubbo:protocol id="xmlrpc1" name="xmlrpc" port="8080" />
<dubbo:protocol id="xmlrpc2" name="xmlrpc" port="8081" />
```

Multi protocol:

```markup
<dubbo:protocol name="dubbo" port="20880" />
<dubbo:protocol name="xmlrpc" port="8080" />
```

```markup
<dubbo:service id="helloService" interface="org.apache.hello.api.HelloService" version="1.0.0" protocol="dubbo,xmlrpc" />
```

Jetty Server: \(default\)

```markup
<dubbo:protocol ... server="jetty" />

Or Jetty9：
<dubbo:protocol ... server="jetty9" />
```

Maven:

```markup
<dependency>
  <groupId>org.mortbay.jetty</groupId>
  <artifactId>jetty</artifactId>
  <version>6.1.26</version>
</dependency>
```

Servlet Bridge Server: \(recommend\)

```markup
<dubbo:protocol ... server="servlet" />
```

web.xml：

```markup
<servlet>
         <servlet-name>dubbo</servlet-name>
         <servlet-class>com.alibaba.dubbo.remoting.http.servlet.DispatcherServlet</servlet-class>
         <load-on-startup>1</load-on-startup>
</servlet>
<servlet-mapping>
         <servlet-name>dubbo</servlet-name>
         <url-pattern>/*</url-pattern>
</servlet-mapping>
```

Cors support:

```markup
<dubbo:protocol name="xmlrpc" ...  />
    <dubbo:parameter key="cors" value="true" />
</dubbo:protocol>
```

