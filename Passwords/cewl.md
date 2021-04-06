CeWL - Custom Word List generator
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

CeWL is a ruby app which spiders a given url to a specified depth, optionally following external links, and returns a list of words which can then be used for password crackers such as John the Ripper.

CeWL also has an associated command line app, FAB (Files Already Bagged) which uses the same meta data extraction techniques to create author/creator lists from already downloaded.

Usage
---------
Scan to a depth of 2 (-d 2) and use a minimum word length of 5 (-m 5), save the words to a file (-w ords.txt), targeting the given URL (https://example.com):

```bash
cewl --with-numbers -d 2 -m 5 -w words.txt http://$ip/
```
Parameters explained
---------
| Switch            | Example                       | Description                                           |
| ----------------- |-------------------------------| ------------------------------------------------------|
| -d <x>            | -d 4                          | Depth to spider to, default 2                         |
| -m <x>            | -m 7                          | Minimum word length, default 3                        |
| -w                | -w words.txt                  | Write the output to the file                          |
| -u                | -u $agent                     | User agent to send                                    |
| --with-numbers    | --with-numbers                | Accept words with numbers in as well as just letters  |
| --lowercase       | --lowercase                   | Lowercase all parsed words                            |
| -h                | -h                            | Show help                                             |

