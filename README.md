javahelper
==========

This would be simple Java code snippets that helped me fix various issues during development.


1. InstallCert.java
   Description: 
        Used to add trusted keystore when using self signed certificates over SSL.
        This was particularly helpful when I had a CAS server deployed on a machine
        It had a self signed certificate in its keystore. 
        In order to connect to it from a HTTP client this keystore was required on the client side.
   
   Usage: java InstallCert localhost:8443

