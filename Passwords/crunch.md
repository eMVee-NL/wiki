Crunch - Wordlist generator
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__


Crunch is a wordlist generator where you can specify a standard character set or a character set you specify. crunch can generate all possible combinations and permutations.


The Syntax
---------

The basic syntax for crunch looks like this in the CLI:

```bash
crunch min<min> max<max> <characterset> -t <pattern> -o <output filename>
```

Now, let's go over what's included in the syntax above.

min = The minimum password length.
max = The maximum password length.
characterset = The character set to be used in generating the passwords.
-t <pattern> = The specified pattern of the generated passwords. For instance, if you knew that the target's birthday was 0728 (July 28th) and you suspected they used their birthday in their password (people often do), you could generate a password list that ended with 0728 by giving crunch the pattern @@@@@@@0728. This word generate passwords up to 11 characters (7 variable and 4 fixed) long that all ended with 0728.
-o <outputfile> = This is the file you want your wordlist written to.


Example
---------
```bash
crunch 3 9 <characterset> -t <pattern> -o wordlist.txt
```