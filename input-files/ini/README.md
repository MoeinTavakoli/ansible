# ini file 

An INI file is a configuration file used by Windows programs to initialize program settings. It contains sections for settings and preferences (delimited by a string in square brackets) with each section containing one or more name and value parameters.

this file is `key=value` type.

At the top of this key value  we define `section` it means define a group of data 

for example 

auth.ini

```
[auth]
username=moeen.tavakoli
password=12345
```

in this case we define a section with name auth for authentication information.

In Ansible we can access to the data in ini file with `lookup`

syntax :

`lookup('ansible.builtin.ini', 'KEY', section='Section_name', file='PATH+file_name.ini')`

for example : 


`{{ lookup('ansible.builtin.ini', 'username', section='auth', file='password.ini') }}`

we this line we can access username in section auth at the password.ini file.