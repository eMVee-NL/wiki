Dorks
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

Google
---------
| Operator      | Example                   | Description                                                                                                                                   |
| ------------- |---------------------------| ----------------------------------------------------------------------------------------------------------------------------------------------|
| site:         | site:microsoft.com        |Displays results related to the search. The example shows everything from microsoft.com. You can also search on a top level domain such as: eu | 
| filetype:     | filetype:pdf              | Returns results with a specific file format. The example only searches for PDF files.                                                         | 
| intitle:      | intitle:OSINT             | Displays results containing the search query in the title. In the example, OSINT will be searched for in the title.                           | 
| allintitle:   | allintitle:Security OSINT | Google lists all pages where the words “security” and “OSINT” appear in the title of the page.                                                | 
| inurl: 	    | inurl:osint 	            | Returns results with the search topic in the URL. In the example, OSINT will be searched for in the URL.                                      | 
| allinurl: 	| allinurl:Security OSINT 	| Google lists all pages where the words “security” and “OSINT” appear in the URL of the page                                                   | 
| related: 	    | related:google.com 	    | Returns related websites. The example shows related websites to Google.com.                                                                   | 
| inanchor: 	| inanchor:"cyber security" | Displays results where a link contains the relevant search query.                                                                             |
| info: 	    | info:google.com 	        | Provides more information about website. In the example about Google.com.                                                                     | 
| intext: 	    | intext:Microsoft Office 	| Displays results containing the search query. The results will have Microsoft Office in the text.                                             |
| cache: 	    | cache:microsoft.com 	    | Geeft de cache weer die Google bewaard heeft van een bepaalde website. In het voorbeeld de gecachde website van Microsoft.com                 |
| * 	        | “A &ast; has nine &ast;” 	| Google will show results where the sentence is automatically completed. The * will be used as a wildcard while searching.                     |
| .. 	        | google logo’s 2000..2010 	| By using the combination of two dots (..), a series can be searched. The example searches for Google logos from 2000 to 2010.                 | 
| + 	        | security OSINT +Google 	| Displays web pages that deal with “security” and / or “OSINT” but which definitely mention Google.                                            | 
| - 	        | security OSINT -Google    | Displays web pages that deal with “security” and / or “OSINT” but that do __not__ mention Google.                                             | 
| ( ) 	        | (Gun &#124; Rifle) ammo   | Group a series of words / operators individually  (Gun &#124; Rifle) ammo.                                                                    |
| " " 	        | "John Doe" 	            | Returns only results with the exact search query. In the example, each result will show the exact search query for John Doe.                  |

Bing
---------
| Operator  | Example               | Description                                                                                                                                           |
| --------- |-----------------------| ------------------------------------------------------------------------------------------------------------------------------------------------------|
| ( ) 	    |(Gun &#124; Rifle) ammo| Finds or excludes web pages containing a group of words.                                                                                              |
| " " 	    | "John Doe" 	        | Returns only results with the exact search query. In the example, each result will show the exact search query for John Doe.                          |
| - 	    | -security 	        | Exclude web pages containing a term or phrase.                                                                                                        | 
| NOT 	    | NOT security 	        | Same as above.                                                                                                                                        |
| + 	    | +security 	        | Finds web pages containing all terms preceded by the '+' symbol. This allows you to search for terms that are usually ignored.                        |
| OR 	    | OSINT OR security 	| Finds web pages that contain any of the terms or phrases.                                                                                             | 
| / 	    | OSINT / security 	    | Same as above.                                                                                                                                        |
| AND 	    | OSINT AND security 	| Finds web pages that contain any terms or phrases. In the example, it will be checked whether the search terms OSINT and security are present.        |
| & 	    | OSINT & security 	    | Same as above.                                                                                                                                        |
| language: | "security" language:nl| Returns the results of the topic in the specified language. In the example, the subject security is searched in Dutch pages.                          |
| loc: 	    | loc:nl 	            | Only returns results from a specific region / country. In the example only results from the Netherlands are shown.                                    | 
| location: | location:nl 	        | Same as above                                                                                                                                         |
| prefer: 	| security prefer:OSINT | Emphasizes a search term or other operator to focus the search results.                                                                               |
| near: 	| security near:5 OSINT | Words in x proximity to each other security near: 5 OSINT                                                                                             | 
| ip: 	    | ip:8.8.8.8 	        | This will show websites in the results hosted by a specific IP address. This functionality does not work in all countries.                            |
| site: 	| site:microsoft.com 	| Displays results related to the search. The example shows everything from microsoft.com. You can also search on a top level domain such as site: eu   | 
| url: 	    | url:microsoft.com 	| Checks if the URL is in the Bing index. The example checks if microsoft.com is in the Bing index.                                                     | 
| feed: 	| feed:security 	    | Searches RSS feeds about the topic, in the example it will search for RSS feeds about security.                                                       | 
| hasfeed: 	| hasfeed:security 	    | Finds web pages that contain an RSS or Atom feed on a website for the terms you are looking for.                                                      | 
| contains: | contains:pdf 	        | Finds web pages that contain links to a certain type of file (such as pdf, doc, docx, etc.).                                                          | 
| ext: 	    | ext:docx 	            | Returns results with a specific file format. The example only searches for docx files.                                                                | 
| filetype: | filetype:pdf 	        | Returns results with a specific file format. The example only searches for PDF files.                                                                 | 
| inanchor: | inanchor:"security"   | Will show only web pages that contain the specified term in the metadata.                                                                             |
| inbody: 	| inbody:OSINT 	        | Will show only web pages that contain the specified term in the metadata.                                                                             |
| intitle: 	| intitle:security 	    | Will show only web pages that contain the specified term in the metadata.                                                                             |

DuckDuckGo
---------
| Operator  | Example                    | Description                                                                                                                              |
| --------- |----------------------------| -----------------------------------------------------------------------------------------------------------------------------------------|
|           | OSINT security 	         | Returns results with OSINT or security.                                                                                                  | 
| " " 	    | "OSINT en Security" 	     | Returns only results with the exact search query. In the example, each result will show the exact search OSINT and security.             | 
| + 	    | -OSINT +security 	         | Shows more results with security as OSINT.                                                                                               | 
| filtype: 	| OSINT filetype:pdf 	     | Displays files about subject. In the example it will show PDF files about OSINT. Supported files: pdf, doc (x), xls (x), ppt (x), html   | 
| site: 	| Office site:microsoft.com  | Displays results related to the search. The example shows everything from Office on microsoft.com.                                       | 
| -site: 	| Office -site:microsoft.com | Finds web pages that contain any of the terms or phrases.                                                                                | 
| intitle: 	| intitle:security 	         | Displays results related to the search. The example searches everything from Office except microsoft.com.                                | 
| inurl: 	| inurl:security 	         | Finds web pages that have security in the URL.                                                                                           | 

Yandex
---------
| Operator  | Example               | Description                                                                                                                                   |
| --------- |-----------------------| ----------------------------------------------------------------------------------------------------------------------------------------------|
| lang: 	| security lang:EN 	    | Displays results in a specific language for the searched topic.                                                                               |
| mime: 	| mime:docx AVG 	    | Shows types of files in the results which are relevant to the searched topic.                                                                 |
| date: 	| OSINT date:20191121 	| Displays results where the subject has been modified on a specific date.                                                                      |
| url: 	    | url:microsoft.com 	| Displays results related to the search. The example shows everything from microsoft.com. With a * after the URL you can search for documents. |

Baidu
---------
The most common dorks of Google works as well for Baidu.

Qwant
---------
The most common dorks of Google works as well for Qwant.