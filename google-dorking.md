# **Google Dorking Quick Reference**  

Google Dorking (also known as Google Hacking) is a technique for using advanced search operators to find specific information indexed by Google.  

## **Table of Contents**  
- [Basic Operators](#basic-operators)  
- [Filetype Searches](#filetype-searches)  
- [Site and Domain Searches](#site-and-domain-searches)  
- [Index and Directory Listings](#index-and-directory-listings)  
- [Sensitive Information Discovery](#sensitive-information-discovery)  
- [Common Dorks](#common-dorks)  

---

## **Basic Operators**

- **`"my exact search term"`** – Narrow down to the exact phrase of interest.  
  - *ex:* `"confidential client database"`

- **`intitle:"keyword"`** – Hunt for specific keywords in titles, like admin panels.  
  - *ex:* `intitle:"admin login"`

- **`inurl:"keyword"`** – Get URLs that lead to sensitive portals or hidden areas.  
  - *ex:* `inurl:"admin.php"`

- **`intext:"keyword"`** – Look for juicy mentions within page content.  
  - *ex:* `intext:"root password"`

- **`OR` / `|`** – Combine multiple potential targets for bigger results.  
  - *ex:* `"admin panel" OR "server config"`

- **`-keyword`** – exclude irrelevant stuff to narrow your results.  
  - *ex:* `"SQL dump" -testing`

---

## **Filetype Searches**

- **`filetype:pdf "keyword"`** – Find PDF reports or blueprints that expose info.  
  - *ex:* `filetype:pdf "network security blueprint"`

- **`filetype:xls site:excom`** – Zero in on excel files on a specific site—could have financial data.  
  - *ex:* `filetype:xls site:bankexcom`

- **`filetype:docx confidential`** – Search for internal documents using Word files.  
  - *ex:* `filetype:docx confidential`

---

## **Site and Domain Searches**

- **`site:excom "search term"`** – Get specific pages from a site, especially if it’s a vulnerable one.  
  - *ex:* `site:targetsite.com "usernames and passwords"`

- **`site:.gov "report"`** – Sneak around government sites for sensitive data.  
  - *ex:* `site:.gov "classified reports"`

- **`site:excom -inurl:www`** – Look for subdomains that could be poorly secured.  
  - *ex:* `site:excom -inurl:www`

---

## **Index and Directory Listings**

- **`intitle:"index of /"`** – Search for exposed file directories.  
  - *ex:* `intitle:"index of /" "backup"`

- **`intitle:"index of" "parent directory" ext:mp3`** – Access a directory full of unprotected files.  
  - *ex:* `intitle:"index of" "parent directory" ext:mp3`

- **`intitle:"index of" passwords`** – Find unsecured directories with passwords and sensitive data.  
  - *ex:* `intitle:"index of" passwords`

---

## **Sensitive Information Discovery**

- **`inurl:admin intitle:login`** – Find login portals for high-value admin areas.  
  - *ex:* `inurl:admin intitle:login`

- **`ext:sql "password"`** – Hunt for SQL dumps with passwords or credentials.  
  - *ex:* `ext:sql "password" "dump"`

- **`ext:env "DB_PASSWORD"`** – expose hidden `.env` files for database credentials.  
  - *ex:* `ext:env "DB_PASSWORD"`

- **`"Confidential" OR "Internal Use Only" filetype:pdf`** – Target internal files with restrictions.  
  - *ex:* `"Confidential" OR "Internal Use Only" filetype:pdf`

---

## **Common Dorks**

- **`"powered by phpbb" inurl:register`** – Look for vulnerable forums with open registration pages.  
  - *ex:* `"powered by phpbb" inurl:register`

- **`"Warning: mysql_connect()" filetype:php`** – Find exposed PHP files with database errors or vulnerabilities.  
  - *ex:* `"Warning: mysql_connect()" filetype:php`

- **`"index of" "wp-config.php"`** – Look for exposed WordPress configuration files—rich with sensitive info.  
  - *ex:* `"index of" "wp-config.php"`

- **`intitle:"login" "Welcome to Webmin"`** – Search for unsecured Webmin login portals.  
  - *ex:* `intitle:"login" "Welcome to Webmin"`

