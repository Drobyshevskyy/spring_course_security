<h2>Overview</h2>
A simple web application that provides access to different web pages depending on the user's role. The application uses only the Spring Security features
<br><br>
A simple employee logging into the system sees one jsp page with information for all employees, HR logging into the system sees a page where in addition to information for all employees there is a button that allows you to view the salaries of all employees<br>
If a user has a manager role, then he will see a page where in addition to information for all employees there is a button that allows to view salaries of all employees and also a button that allows to view performance of all employees
<br><br>
The application stores all user names and passwords in the mySQL database 
<br><br>
Class "MyController.java" is responsible for switching pages depending on user's role:
<br>
<ul>
<li>when a user who is a regular employee logs in, the user goes to view "view_for_all_employees.jsp"</li> 
<li>when a user who is HR logs in, a button appears on the page intended for all employees, which is used to switch to view "view_for_hr.jsp", which is available only to employees with the HR role</li> 
<li>when a person with the role of manager logs in, a button appears on the page for all employees to switch to view "view_for_managers.jsp", intended only for managers; managers also see the button for HR</li>
</ul>
<br>
<h3>Configuration</h3>
Project is created from Maven archetype "maven-archetype-webapp"<br>
Deployment to the server is performed by Tomcat<br>
The configuration of Spring Container and database connection is the responsibility of file "MyConfig.java" of package "configuration"<br>
"MyWebInitializer.java" class is responsible for DispatcherServlet<br>
In order to request an authentication form in our application, we created a class "MySecurityInitializer.java"<br>
"MySecurityConfig" is responsible for Spring Security configuration
