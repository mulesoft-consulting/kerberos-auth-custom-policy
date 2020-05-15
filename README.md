# kerberos-auth-custom-policy

This custom policy is applied to Mule4 APIs protect the APIs with Kerberos V5 SPNEGO authentication protocol. 
This policy used a custom plugin- https://github.com/mulesoft-consulting/Mule4-kerberos-Extension.git


## Deploying to exchange
Clone this project to your local, change the groupId to point your orgId. 
Issue `mvn deploy` (Ensure there is an entry in your maven settings.xml file for your exchange2)

## Local Install
For local install, give any groupId and issue `mvn clean install`

## Usage of the Policy:

1) Publish the policy to Exchange. 
2) In API Manager, locate the API to which you want to apply the custom policy and apply the policy. 
3) Provide the connection parameters at the time of applying the policy. 
4) Refer below sample configuration. 



```
### Sample Values

#### ldapUrl
`ldap://ldapservedev.mulesoft.com`
#### ldapUser
`mulesoft\svc_User_Mule_LDAP`
#### spn
`HTTP/dev.mulesoft.com@MULESOFT.COM`
#### keytabLocation
`E:\mule\mule-enterprise-standalone-4.2.1-hf1\lib\user\http-dev-mulesoft.keytab`
#### ldapFilter
`(&(userPrincipalName={0})(objectClass=user))`
#### ldapSearchBase
`DC=mulesoft`
#### ldapBase
`DC=com`

## Contributors

Roghini Krishnan
