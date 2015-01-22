#Spring MVC Step-by-step Tutorial

Spring MVC Tutorial
http://docs.spring.io/docs/Spring-MVC-step-by-step/

##Updates
###Completed the project!
I successfully restarted the tutorial and have used version control from start to finish.

See the git repository for the finished project. Feel free to clone this repo at your leisure.
https://github.com/chamoji/springapp

##Running springapp
1. `ant build deploy`
2. Start your tomcat webserver (`<tomcat.path>/bin/startup.bat`)
3. Execute `ant list` to confirm your application was picked-up by tomcat.
4. Start the database server by executing `/db/server.bat`
5. Point your web browser to `http://localhost:8080/springapp`
6. Done. The web application is now live! 

### Notes about the step-by-step Tutorial
*In Chapter 4, there is an extraneous `<beans>` tag in the `springapp-servlet.xml` snippet.
*In Chapter 5, add these import statements in `JdbcProductTests.java` to resolve compilation errors:
```
      import org.springframework.test.AbstractTransactionalDataSourceSpringContextTests;
      import springapp.domain.Product;
```


### Other Errors
There are a few errors in the tutorial that might take quite a bit of time to debug. Please take a look at the following list to see if you are running into similar problems:

1. `InstallTask` is a deprecated method. Use `DeployTask` instead to fix `ant` build problems.
2. Your build path should include all `.jar` files the tutorial depends on:
      *`commons-logging.jar`
      *`spring-webmvc.jar`
      *`spring.jar`
      *`servlet-api.jar`
      *`jsp-api.jar` (from the spring framework directory)
3. Modify the `tomcat` classpath in `build.xml` to fix class definition errors:
```
    <path id="catalina-ant-classpath">
        <!-- We need the Catalina jars for Tomcat -->
        <!--  * for other app servers - check the docs --> 
        <fileset dir="${appserver.lib}">
            <include name="catalina-ant.jar"/>
            <include name="tomcat-coyote.jar"/>
            <include name="tomcat-util.jar"/>
        </fileset>
        <fileset dir="${appserver.home}/bin">
                    <include name="tomcat-juli.jar"/>
        </fileset>
    </path>
```
