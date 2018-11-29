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

1. You can use the following guide to understand what classes you have to use and how <https://goo.gl/RhLm1b>

The command-line interface should be the following

    java Encryptor <file> <private key file>
    # produces a file named <text file>.enc

    java Decryptor <file>.enc <public key file>
    # produces a file named <file>.dec

2. Swap keys in the code.

### How to Generate a Key Pair

    openssl genrsa -out key.pem 2048
    openssl pkcs8 -topk8 -inform PEM -outform DER -in key.pem -out key -nocrypt
    openssl rsa -in key.pem -pubout -outform DER -out key.pub

## Lab #4, Authentication

1. Deploy a simple web-application locally or remotely from `iuca-infosec/blog` dir on `auca.space` server.

You can use the following `tcpdump` command to catch all the POST HTTP packets.

```bash
tcpdump -s 0 -A 'tcp dst port 80 and (tcp[((tcp[12:1] & 0xf0) >> 2):4] = 0x504f5354)'
```

You may find the following packages usefull

* [Node.js](https://nodejs.org/en/download)
* [MySQL](https://dev.mysql.com/downloads/file/?id=478883)
* [MySQL Portable Database Scripts](https://github.com/toksaitov/portable-mysql.git)

2. Perform a security audit of the software.

3. Make improvements to the software to secure it.

* [Let's Encrypt Certificates](https://letsencrypt.org)
* [Enabling HTTPS in Express](https://timonweb.com/posts/running-expressjs-server-over-https)
* [bcrypt Hash Library for Node.js](https://www.npmjs.com/package/bcrypt)

## Lab #5, Unix Access Control

1. For a collaborative project, create and share a directory with another team member
   on `iuca.space` in your home directory. Allow him to read and create new files.
   
2. Consider that your team got a new member. Use ACL to also allow him to work with the
   project directory.

* [ACL, Ubuntu](https://help.ubuntu.com/community/FilePermissionsACLs)

## Lab #6, Spyware Analyses

Research what should an application do to track global key presses on Windows. Try to find the
specific API calls and build a simple key tracking application in C# around them. In a virtualized
environment analyze the behaviour of popular antivirus software packages to your program.

## Lab #6, RAT Analyses

Select sources of one of the Remote-Access-Trojans in the malware source code, sample database
<https://github.com/malwares>. In brief words, write a report in a markdown format about it.

In your report try to answer the following questions.

* What was the language used to create the RAT?
* What Windows specific APIs were used to allow the RAT to function?
* What Windows specific vulnarabilities were used to allow the RAT to function?
* Were any other software APIs or vulnerabilities exploited by the tool?

Outline the functionality of the RAT and the basic steps the tool was doing
to abuse the system.

Remember to use a virtualized environment to avoid harm to your machine.

### Documentation for Helpfull Unix Tools

    man strings
    man gdb

### Links

* [Beej's Guide to C Programming](http://beej.us/guide/bgc)

### Books

* _C Programming: A Modern Approach, 2nd Edition by K. N. King_
