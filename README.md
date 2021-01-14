# LDAP security

Used the following sites as reference to develop the ldap auth package

[flask-ldapconn](https://github.com/rroemhild/flask-ldapconn)
[some github repo](https://github.com/haouach/smsgateway/blob/master/wis/wis.py)

## Testing

Using a preconfigured docker version of openldap [OpenLDAP Docker Image for testing](https://github.com/rroemhild/docker-test-openldap)

```
docker pull rroemhild/test-openldap
docker run --rm -p 10389:10389 -p 10636:10636 rroemhild/test-openldap
```

Logon example from site:
Username: `Philip J. Fry`
Password: `fry`

command line testing can be done with ldap-utils
```sudo apt install ldap-utils```

```bash
ldapsearch -x -h localhost -p 10389 -D "cn=Hubert J. Farnsworth,ou=people,dc=planetexpress,dc=com" -w "professor" -b "dc=planetexpress,dc=com" -s sub 'uid=professor'
```

