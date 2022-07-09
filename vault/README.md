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

## CreateNew encrypted Files

lets create an encrypted file with ansible-valut.

for create and encrypted file we use option `create` .

for exmaple --> 

`ansible-vault create vault.yml`

you enter a password for vault password and confirm this password then a code editor open that allow you to write something to encrypte it .

