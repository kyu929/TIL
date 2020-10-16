Spring MVC
============
Naming a Package  
1. Package names are written in all lower case to avoid conflict with the names of classes or interfaces.  
2. Companies use their reversed Internet domain name to begin their package names-- for example, com.example.mypackage
 for a package named mypackage created by a programmer at example.com  
3. Name collisions that occur within a single company need to be handled by convertion within that company, perhaps by including the region or the project name after the company
 name (com.example.region.mypackage)  
4. Packages in the Java language itself begin with java. or javax.  
5. In some cases, the internet domain name may not be a valid package name. This can occur if the domain name contains a hyphen or other special character, if the package name
 begins with a digit or other character that is illegal to use as the beginning of a Java name, or if the package name contains a reserved Java keyword, such as "int". In this
 event, the suggested convention is to add an underscore.  

For example:
Legalizing Package Names
-------------------------------

|Domain Name|Package Name Prefix|
|---------------|--------------------------------|
|hyphenated-name.example.org  |     org.example.hyphenated_name  |
|example.int              | int_.example|
|123name.example.com       |    com.example._123name|  

reference : https://docs.oracle.com/javase/tutorial/java/package/namingpkgs.html
