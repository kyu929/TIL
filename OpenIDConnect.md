- ### OAuth vs OpenIDConnect vs SAML
  https://www.okta.com/identity-101/whats-the-difference-between-oauth-openid-connect-and-saml/   
  https://www.ubisecure.com/education/differences-between-saml-oauth-openid-connect/
  
- ### OIDC vs OAuth
  
  
  
  - #### OpenID and OAuth typical scenario.
  
    OpenID scenario
  
    - User wants to access his account on example.com
    - example.com(the "Relying Party" in OpenID lingo) asks the user for his OpenID
    - User enters his OpenID
    - example.com redirects the user to his OpenID provider
    - User authenticates himself to the OpenID provdier
    - OpenID provider redirects the user back to example.com
    - example.com allows the user to access his account
  
    OAuth
  
    - User is on example.com and wants to import his contacts from mycontacts.com
    - example.com(the "Consumer" in Oauth lingo)redirects the user to mycontacts.com (the "Service Provider")
    - User authenticates himself to mycontacts.com(which can happen by using OpenID)
    - mycontacts.com asks the user whether he wants to authorize example.com to access his contacts
    - User make his choice
    - mycontacts.com redirects the user back to example.com
    - example.com retrieves the contacts from mycontacts.com
    - example.com informs the user that the import was successful
    
    reference : http://cakebaker.42dh.com/2008/04/01/openid-versus-oauth-from-the-users-perspective/
