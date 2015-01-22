#Spring MVC Step-by-step Tutorial

Spring MVC Tutorial
http://docs.spring.io/docs/Spring-MVC-step-by-step/

##Updates
###Completed the project!
I successfully restarted the tutorial and have used version control from start to finish.

See the git repository for the finished project. Feel free to clone this repo at your leisure.
https://github.com/chamoji/springapp

### Troubleshooting Errors
There are a few errors in the tutorial that might take quite a bit of time to debug. Please take a look at the following list to see if you are running into similar problems:

1.  In Chapter 4, there is an extraneous "<beans>" tag in the "springapp-servlet.xml" snippet.
2.  In Chapter 5, add these import statements in "JdbcProductTests.java" to resolve compilation errors:

      import org.springframework.test.AbstractTransactionalDataSourceSpringContextTests;
      import springapp.domain.Product;

3.  [Ant] InstallTask is a deprecated method. Use DeployTask instead to fix Ant build problems.
4.  [Tomcat] Modify the Tomcat classpath in build.xml to fix class definition errors:
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
    
5.  [Java]Verify that you have the correct version of the Java JDK.
6.   Check your Environment Variables and make sure your PATH variable contains the correct path to your Java JDK installation.
7.  Ensure all dependencies are taken care of.
    Your build path should include all .jar files the tutorial depends on:
      * commons-logging.jar
			* spring-webmvc.jar
			* spring.jar
			* servlet-api.jar
			* jsp-api.jar (use the jar from the spring-framework!)




