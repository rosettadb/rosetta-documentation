When it comes to security Rosetta is divided in two sections:

- Secure store - for storing credentials and other secrutiy related info used during operations like accessing data source.
- Authentication (LDAP) - for allowing/restricting acces to the platform.

# Secure Store

To secure credentials platform utilizes Java KeyStore in JKS format to create a secure store file. Location of this file and the password used for it's encryption can be configured in `application.properties` file. Note: these values need to be modified before any data source is added - otherwise all data source passwords for existing data sources need to be re-entered through <strong>UI->Data Source->Edit</strong> form.

| Property                  | Value        | Required | Description                                               |
| ------------------------- | ------------ | -------- | --------------------------------------------------------- |
| proedms.secure.store.file | keystore.jks | Yes      | Location of the file where to store keys                  |
| proedms.secure.store.type | JCEKS        | Yes      | Type of the keystore. Currently only `JCEKS` is supported |

# Authentication (LDAP)

Authentication in Rosetta is optional and can be enabled/disabled from `application.properties` file. Rosetta uses LDAP for authentication and it also provides the ability to bring up local server based on provided LDIFF file. Once the user credentials are verified JWT token is created which is valid for 24 hours and all subsequent interactions have this token provided in `Authorization` header property.

There are few properties that are required to be set in `application.properties` in order to enable authentication.

| Property                                | Value                                               | Required | Description                                                                                                                                                                                                                                                                                                                                                       |
| --------------------------------------- | --------------------------------------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| proedms.security.authentication.enabled | true                                                | Y        | This property enables the authenticaiton mechanism in general. Default: false                                                                                                                                                                                                                                                                                     |
| proedms.jwt.auth.type                   | SECRET                                              | Y        | Indicates the type of secret JWT will use to has/ecnrypt tokens. Can be set to `SECRET` for using string type of key. Can be set to `KEY` for using private key file.                                                                                                                                                                                             |
| proedms.jwt.secret                      | [String/Path]                                       | Y        | Depending on how the property `proedms.jwt.auth.type` this can be either a string type of secret or location to private key file.                                                                                                                                                                                                                                 |
| ldap.user.dn.patterns                   | ex:uid={0},ou=people                                | Y        | User DN Pattern - A DN pattern that can used to directly login users to the LDAP database. This pattern is used for creating a DN string for "direct" user authentication, where the pattern is relative to the base DN in the ldapUrl. <br /><strong>Note</strong>: uid needs to have {0} as value as it will be matched against username provided during login. |
| ldap.group.search.base                  | ex: `ou=groups`                                     | Y        | Subtree to search for username                                                                                                                                                                                                                                                                                                                                    |
| ldap.url                                | ex: `ldap://localhost:8389/dc=AdaptiveScale,dc=com` | Y        | LDAP url to connect to - can be set as localhost if Rosetta embeded LDAP is to be used.                                                                                                                                                                                                                                                                     |
| ldap.password.attribute                 | userPassword                                        | Y        | Name of the attribute for password in LDAP. Default:`userPassword`.                                                                                                                                                                                                                                                                                               |

Rosetta also provided embeded LDAP server that can be activated by providing additional properties to properties file. This is useful for the cases where users don't have their own LDAP server or don't want to connect the platform with existing LDAP server. Keeping the configuration sa examples from abvoe and additionally setting the following configurations will allows users to start Rosetta embedded LDAP server based on provided LDIFF file which will contains LDAP data.

| Property                     | Value                     | Required | Description                                                                                                                             |
| ---------------------------- | ------------------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| spring.ldap.embedded.ldif    | file:///opt/apt/auth.ldif | Y        | Absolute path to LDIFF file                                                                                                             |
| spring.ldap.embedded.base-dn | dc=AdaptiveScale,dc=com   | Y        | A base dn from where the server will search for users. This is dependent with LDIFF contents and is also needed in `ldap.url` property. |
| spring.ldap.embedded.port    | 8389                      | Y        | Port on which embedded LDAP server will run.                                                                                            |

Using embedded server requires LDIFF file which is a copy of LDAP data structure dumped to single file. The following example ldiff matches the example configurations given above and creates user with username `admin` and password `admin`. Create a file with `.ldif` extension and add the follwing as it's content.

```
# LDAP Auth data
dn: dc=AdaptiveScale,dc=com
objectclass: top
objectclass: domain
objectclass: extensibleObject
dc: AdaptiveScale

# Organizational Units
dn: ou=groups,dc=AdaptiveScale,dc=com
objectclass: top
objectclass: organizationalUnit
ou: groups

dn: ou=people,dc=AdaptiveScale,dc=com
objectclass: top
objectclass: organizationalUnit
ou: people

# Accounts
dn: uid=admin,ou=people,dc=AdaptiveScale,dc=com
objectclass: top
objectclass: person
objectclass: organizationalPerson
objectclass: inetOrgPerson
cn: AdaptiveScale
sn: AdaptiveScale
uid: admin
userPassword: admin

# Create Group Admin
dn: cn=admins,ou=groups,dc=AdaptiveScale,dc=com
objectclass: top
objectclass: groupOfUniqueNames
cn: admins
ou: admin
uniqueMember: uid=admin,ou=people,dc=AdaptiveScale,dc=com
```

Starting Rosetta with the configration set as above will land user in Login screen where user `admin` and password `admin` can be used to authenticate.

# Authorization (LDAP)

Rosetta utilizes groups/roles for ACL, both authentication and authorization is based on LDAP, this can be configured either from the `auth.ldif` file or from a LDAP server. Access is divided into the following categories:

| Category name | Category description |
|---------------|----------------------|
| DS | Stands for data-source - handles access for resources under data-source |
| CAT | Stands for catalog - handles access for resources under catalog |
| DEP | Stands for deployment - handles access for resources under deployment |
| COL | Stands for collection - handles access for resources under collection |
| DT | Stands for data-transfer - handles access for resources under data-transfer |
| TAG | Stands for tag - handles access for resources under tag |
| SCHED | Stands for schedule - handles access for resources under schedule |
| SEARCH | Stands for search - handles access for resources under search |
| EV | Stands for schema-evolution - handles access for resources under schema-evolution |
| ALERT | Stands for alert - handles access for resources under alert |
| SQLEXPL | Stands for sql-explorer - handles access for resources under sql-explorer |
| GIT | Stands for git-configuration - handles access for resources under git-configuration |

Besides the categories there is also operational level permissions:

| Permission name | Permission description |
|-----------------|------------------------|
| READ | This permission allows the user to view/list resource(s) |
| WRITE | This permission allows the user to modify resource(s) |
| EXECUTE | This permission allows the user to execute operations on resource(s) |

ACL in Rosetta is achieved by creating a group name that combines the category name as a prefix and permission name as a suffix.

Like the following example defines a group which has permission to view/list data-sources and assigns the user `test` as a member of the group which will allow user to have access to the data-sources:
```
# GROUP DS-READ
dn: cn=adaptive-ds-readers,ou=groups,dc=adaptivescale,dc=com
objectClass: top
objectClass: groupOfNames
cn: adaptive-ds-read
member: uid=test,ou=people,dc=adaptivescale,dc=com
```

Besides the combinations that can be achieved above there is also an `adaptive-admin` group, members of which have full access to all resources, including the capability to delete resources.

Example given below shows how an `adaptive-admin` group looks like:
```
# GROUP ADMIN
dn: cn=adaptive-admins,ou=groups,dc=adaptivescale,dc=com
objectClass: top
objectClass: groupOfNames
cn: adaptive-admin
member: uid=admin,ou=people,dc=adaptivescale,dc=com
```

Note: Enabling and disabling permissions reflects on the UI components visibility as well.