# ansible vault 

### whats ansible ? 

Ansible Vault is a feature that allows users to encrypt values and data structures within Ansible projects. 

this feature provide this ability to secure sensive data and keep safe  .

we can use this feature when we want to run an ansible playbook .

this ability called `ansible-vault` and has several option to use it 

<ul>
  <li>create</li>
  <li>decrypt</li>
  <li>edit</li>
  <li>view</li>
  <li>encrypt</li>
  <li>encrypt_string</li>
  <li>rekey</li>
</ul>

## Create new encrypted Files

lets create an encrypted file with ansible-valut.

for create and encrypted file we use option `create` .

for exmaple --> 

`ansible-vault create vault.yml`

you enter a password for vault password and confirm this password then a code editor open that allow you to write something to encrypte it .

save this file and exit then you can see a new file created like `vault.yml` with encrypted data .

## Decrypt Files

for example we have an encrypted file and we want to decrypt it .

for decrypt files we use option `decrypt` .

for exmaple --> 

`ansible-vault decrypt vault.yml`

and ask your vault password to decrypt it .

so when you open this file we can see data that decrypted .

## View encrypted Files

for example you want to just see decrypted data and you didnt want to change the file (change encrypted file to decrypt).

In this case you can use option `view` .

for exmaple --> 

`ansible-vault view vault.yml`

and ask your vault password to decrypt it and print it .

**in this case didnt change your encrypted file**.

