# double-crypt

template for linux users to easily encrypt files automatically

as well as for automating double AES256 file 

encryption with multiple technologies.

This way if one key leaks, the other key

has to have been leaked as well for the

file to be decrypted, if the double option is used.


The first layer is required, and that is a gpg asymmetric aes256 encryption.

The second layer is option, which is a symmetric openssl aes256 encryption.


The core program is called ddc

Then there is a wrapper template called encryptor_template that is to be copied

and then edited to fit the situation. The tne edited template is what is

executed directly, whic calls ddc, or whatever else you need.


Running the installer in pwd with the template, will make a copy of the template

and drop you into a vim session to edit the copy, as well as set up ~/Desktop

files for GUI usage.


Example generation of the additional option symmetric keyfile:

```
cat /dev/urandom | fold -w9999 | head -n42 > ~/Desktop/keyfile.bin
```

Then when using ddc in double mode, using that file generated in the example above:

```
ddc ~/Desktop/encrypt/ mygpgkey@localhost ~/Desktop/keyfile.bin
```


Also see https://github.com/jpegleg/crypt-baller
