# SSH

generate a new ssh key pair and sync the public key

``` console
$ ssh-keygen -t rsa
$ ssh-copy-id user@host
```

if you generate a non-default key pair, the key filename can be specified thus:

``` console
$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (~/.ssh/id_rsa): mykey
...
...

$ ssh-copy-id -i ~/.ssh/mykey user@host
```
