javahelper
==========

This would be simple Java code snippets that helped me fix various issues during development.


A. InstallCert.java
   Description: 
        Used to add trusted keystore when using self signed certificates over SSL.
        This was particularly helpful when I had a CAS server deployed on a machine
        It had a self signed certificate in its keystore. 
        In order to connect to it from a HTTP client this keystore was required on the client side.
   
   Usage: java InstallCert localhost:8443

B. HTTPCasClient.java 
   Description: 
               Test a CAS RESTful API 

   Pre-Requisite: 
               Create a RESTful secured API using CAS,
               Make sure You have a working CAS setup at "https://XX.4.YY.63:8443/cas/";
               I used JDBC based Authentication here, https://wiki.jasig.org/display/CASUM/Using+JDBC+for+Authentication

   Notes:
   1. Configure: https://wiki.jasig.org/display/CASUM/RESTful+API
   2. This service can be exposed as in the below sample
            GIT: git://git.springsource.org/spring-security/spring-security.git
            Sample: ~\SampleSpring\spring-security-3.1.x\spring-security-3.1.x\samples\cas\cas-sample
   3. Test : Using commons http client
   4. Workflow,
   	>Get the TicketGrantingTicket from server "https://XX.4.YY.63:8443/cas/v1/tickets" in pre-requisite;
   	>Get the ServiceTicket from CAS based on service "https://XX.4.YY.77:8443/XXYYWeb/secure";
   	>Based on the service ticket GET access to the REST API service created in step 2. 


    This Test code has been implemented using the following Commons HTTP Client, 
		<dependency>
			<groupId>commons-httpclient</groupId>
			<artifactId>commons-httpclient</artifactId>
			<version>3.1</version>
		</dependency>
