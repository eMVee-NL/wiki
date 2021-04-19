Check hashes online
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

There are several public websites were it is possible to check compromised hashes of passwords. Those websites are often faster with returning a plain text password rather then cracking it with one of the tools.   

Warning: Only use those websites for compromised hashes during a CTF event or a vulnerable machine in a lab environment.

Crackstation
---------
[Crackstation](https://crackstation.net/) uses massive pre-computed lookup tables to crack password hashes. These tables store a mapping between the hash of a password, and the correct password for that hash. The hash values are indexed so that it is possible to quickly search the database for a given hash. If the hash is present in the database, the password can be recovered in a fraction of a second. This only works for "unsalted" hashes. 

Online hash crack
---------
[Online hash crack](https://www.onlinehashcrack.com/hash-identification.php) supports over 250 hash types.

MD5 decrypt
---------
[MD5 decrypt](https://md5decrypt.net/en/)

MD5online
---------
[MD5online](https://www.md5online.org/md5-decrypt.html) uses a huge database in order to have the best chance of cracking the original word.
Just enter the hash in the MD5 decoder in the form and to try to decrypt it! 

Hashes.com
---------
[Hashes](https://hashes.com/en/decrypt/hash) is a hash lookup service. This allows you to input an MD5, SHA-1, Vbulletin, Invision Power Board, MyBB, Bcrypt, Wordpress, SHA-256, SHA-512, MYSQL5 etc hash and search for its corresponding plaintext ("found") in their database of already-cracked hashes.
It's like having your own massive hash-cracking cluster - but with immediate results!

CMD5
---------
[CMD5](https://cmd5.org/) provides online MD5 / sha1/ mysql / sha256 encryption and decryption services. They have a super huge database with more than 90T data records. Most are free, and a small amount is charged. This site can also decrypt types with salt in real time.