# proyJSFMavenSalatti

Para arrrancar nuestro proyecto con jetty necesitaremos tener estas lineas en nuestro pom.xml

<project
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd"
    xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
 
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.huerta</groupId>
    <artifactId>JSFMavenSalatti</artifactId>
    <packaging>war</packaging>
    <version>1.0.0</version>
    <name>JSFMavenSalatti</name>
 
    <dependencies>
        <dependency>
     <groupId>junit</groupId>
     <artifactId>junit</artifactId>
            <version>4.8.1</version>
         <scope>test</scope>
        </dependency>
        <dependency>
         <groupId>org.apache.maven.plugins</groupId>
         <artifactId>maven-compiler-plugin</artifactId>
         <version>3.3</version>
         <type>maven-plugin</type>
        </dependency>
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>javax.servlet-api</artifactId>
            <version>3.1.0</version>
            <scope>provided</scope>
        </dependency>
        <dependency>
     <groupId>org.glassfish</groupId>
     <artifactId>javax.faces</artifactId>
     <version>2.2.9</version>
        </dependency>
        <!--<dependency>
         <groupId>redis.clients</groupId>
         <artifactId>jedis</artifactId>
         <version>2.7.2</version>
        </dependency>
        <dependency>
     <groupId>org.primefaces</groupId>
     <artifactId>primefaces</artifactId>
     <version>5.3</version>
        </dependency>-->
    </dependencies>
    <build>
      <plugins>
      <!--<plugin>
        <groupId>org.eclipse.jetty</groupId>
        <artifactId>jetty-maven-plugin</artifactId>
        <version>9.0.5.v20130815</version>
        <configuration>
          <httpConnector>
           <port>9999</port>
          </httpConnector>
          
           <webAppConfig>
             <contextPath>/s4c</contextPath>
           </webAppConfig>
           <connectors>
            <connector
         implementation="org.eclipse.jetty.server.nio.SelectChannelConnector">
              <port>9096</port>
            </connector>
           </connectors>  
        </configuration>
      </plugin>-->
      <plugin>
         <groupId>org.apache.maven.plugins</groupId>
         <artifactId>maven-compiler-plugin</artifactId>
         <version>3.3</version>
         <configuration>
           <source>1.8</source>
           <target>1.8</target>
         </configuration>
      </plugin>
      <plugin>            
       <groupId>org.apache.maven.plugins</groupId>
       <artifactId>maven-war-plugin</artifactId>
       <version>2.6</version>
       <configuration>
        <webXml>src/main/webapp/WEB-INF/web.xml</webXml>        
       </configuration>
      </plugin>            
     </plugins>
     <finalName>JSFMavenSalatti</finalName>
    </build>
</project>

Primero utilizaremos mvn package despues de modificar el pom.xml desde la raiz del proyecto 
seguidamente el war sera arrancado con mvn jetty:run desde la raiz del proyecto y nos funcionara perfectamente con el servidor jetty y podremos verlo desde nuestro navegador poniendo en la url: localhost:9999(utiliza el 9999 curioso).
