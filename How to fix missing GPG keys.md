### Update Problem through terminal (Missing keys):

sudo apt-get update  giving problem as follows:
```
rohit@iita:~$ sudo apt-get update
Get:1 http://archive.ubuntu.com/ubuntu focal InRelease [265 kB]
Err:1 http://archive.ubuntu.com/ubuntu focal InRelease
  The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 3B4FE6ACC0B21F32 NO_PUBKEY 871920D1991BC93C
Get:2 http://archive.ubuntu.com/ubuntu focal-security InRelease [114 kB]
Err:2 http://archive.ubuntu.com/ubuntu focal-security InRelease
  The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 3B4FE6ACC0B21F32 NO_PUBKEY 871920D1991BC93C
Get:3 http://archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]
Err:3 http://archive.ubuntu.com/ubuntu focal-updates InRelease
  The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 3B4FE6ACC0B21F32 NO_PUBKEY 871920D1991BC93C
Reading package lists... Done
W: GPG error: http://archive.ubuntu.com/ubuntu focal InRelease: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 3B4FE6ACC0B21F32 NO_PUBKEY 871920D1991BC93C
E: The repository 'http://archive.ubuntu.com/ubuntu focal InRelease' is not signed.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
W: GPG error: http://archive.ubuntu.com/ubuntu focal-security InRelease: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 3B4FE6ACC0B21F32 NO_PUBKEY 871920D1991BC93C
E: The repository 'http://archive.ubuntu.com/ubuntu focal-security InRelease' is not signed.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
W: GPG error: http://archive.ubuntu.com/ubuntu focal-updates InRelease: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 3B4FE6ACC0B21F32 NO_PUBKEY 871920D1991BC93C
E: The repository 'http://archive.ubuntu.com/ubuntu focal-updates InRelease' is not signed.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
```

Try the below link to resolve the issue: 
1) [Solution1](https://chrisjean.com/fix-apt-get-update-the-following-signatures-couldnt-be-verified-because-the-public-key-is-not-available/)
2) [Solution2](https://unix.stackexchange.com/questions/75892/keyserver-timed-out-when-trying-to-add-a-gpg-public-key)


If both didnot work then try this method mentioned in the Link: https://askubuntu.com/questions/127326/how-to-fix-missing-gpg-keys .

Probable reason that the above methods not work because of firewall. Resolution steps are as follows:

  **Step-1:** Open the webpage of [Ubuntu Key Server](http://keyserver.ubuntu.com/) in your web browser and search for the string 0x\<hexadecimal code of your missing key\>.
        
   >For Example: If key is 3B4FE6ACC0B21F32 then search 0x3B4FE6ACC0B21F32

  **Step-2:** The sample result of the search given such as-
```  
-----BEGIN PGP PUBLIC KEY BLOCK-----
Comment: Hostname: 
Version: Hockeypuck ~unreleased

xsFNBE+tgXgBEADfiL1KNFHT4H4Dw0OR9LemR8ebsFl+b9E44IpGhgWYDufj0gaM
/UJ1Ti3bHfRT39VVZ6cv1P4mQy0bnAKFbYz/wo+GhzjBWtn6dThYv7n+KL8bptSC
Xgg1a6en8dCCIA/pwtS2Ut/g4Eu6Z467dvYNlMgCqvg+prKIrXf5ibio48j3AFvd
Js1UJeZGet48oaaCjKQFAc4VsPHCwdWxP7TadD4thBBQxoYAX0L+57Yduitt6QfJ
WpY5zRErp1MWCYRXGnEZq+M4kgiR+g3ruOtXR/NkZqXBMQoFGtL8566yzouVq81J
ApzeYHYT6cmxbfTunjdiWFIIdTal/Rad62zgOXO8QCO6dn1q+BTljlnzTfVPewGK
7//UfRnXbmGzy7Je27s1EbzaYh0bzWhjh9LR7nfAHlbnTrUaGZXEgAR32SuWSTZ4
OUjl1uHdp8lsDZQjkYx+zpQ/bFUL73xyxn0eelk5Uj32dpv5qDDwxrlUuX3IKDua
0Sb83NvR3oplVPmd8xblRjBabkpTc44agXXPMk7Lu4Dcne8/BhRiPJu8XA4DssFA
6gzd9+4mj48m1OSx+sfWfMPlLNUnwZ1eEqgueMMMGkCQpoykv3PfHsraoxvTt/RL
4kUSYA4gGsYHDz2icHaIeYR8Z7HHg0bFEnlLTq5qmkp2qynClQQQEwkAHRYhBBGo
qHTf3iziQI5kEMJN9MPone8CBQJeY4fLAAoJEMJN9MPone8CfLoBgMvo45xXEy17
8p2ihlsHUxB8iAcahrE2N7QmO9kQjYIygpMjl3NDzzn087fJcKt12QF+PBhhrLQu
I++g+zWd/URh4fX6ZoG7RAPheJapkP/ELNfmIWhfDc4/UZW8L0XNqvQc
=L47D
-----END PGP PUBLIC KEY BLOCK-----
```
   **Step-3:** Ctrl+a , Ctrl-c and save all the content (i.e from ---BEGIN ... KEY BLOCK---) in a file.
  
   **Step-4:** Now run
  ```
  $ sudo apt-key add <file-with-saved-key>
  ```   
  
  Thanks
