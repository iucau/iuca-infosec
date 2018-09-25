Lab Tasks
=========

You can use the AUCA server for this work through SSH at 'auca.space'. The login
has the format `<last name>_<first letter of the first name>`.

## Lab #1, Find the Password

Proove that security by obscurity does not always work by finding passwords in the executables `1`, `2`, and `3` located
at `iuca-infosec` of your home directory on the `auca.space` server. Try analyzing the binary with the `strings` command and the `gdb` debugger. Try using the raibow tables to find the value of the hash in the last executable.

## Lab #2, Break the Cipher

Given the following [text](https://drive.google.com/file/d/19Q60HCDDswcSA_BvWlVV-Q641Vs2i1KA/view?usp=sharing), try break it by using at least two different approaches discussed during the class. Select one
approach and write a decryption function in Python for any text that uses the same symmetric encryption scheme.

Try using a Jupyter notebook. You can get one online for free at <https://notebooks.azure.com>.

One possible solution can be found [here](https://notebooks.azure.com/toksaitov-gatech/libraries/iuca-infosec-lab02).

## Lab #3, Encryption System

Create two Java applications, one that can encrypt any given text with a symmetric AES cipher, and another that can decrypt the
given text. Allow the key to be bundled and transmited together with the encrypted data through untrusted channels.

### Documentation for Helpfull Unix Tools

    man strings
    man gdb

### Links

* [Beej's Guide to C Programming](http://beej.us/guide/bgc)

### Books

* _C Programming: A Modern Approach, 2nd Edition by K. N. King_
