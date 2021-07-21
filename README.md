#double-crypt
template for linux GUI users to encrypt files easily

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
