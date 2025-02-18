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

- **`"my exact search term"`** – Exact match search.  
- **`intitle:"keyword"`** – Find pages with keyword in the title.  
- **`inurl:"keyword"`** – Find pages with keyword in the URL.  
- **`intext:"keyword"`** – Find pages containing the keyword in their content.  
- **`OR` / `|`** – Logical OR between search terms.  
- **`-keyword`** – Exclude results containing the keyword.  

---

## **Filetype Searches**  

Find specific file types indexed by Google.  

- **`filetype:pdf "keyword"`** – Search for PDFs containing the keyword.  
- **`filetype:xls site:example.com`** – Find Excel files on a specific site.  
- **`filetype:docx confidential`** – Search for Word documents related to "confidential."  

---

## **Site and Domain Searches**  

Refine searches to specific sites or domains.  

- **`site:example.com "search term"`** – Find pages on a specific domain.  
- **`site:.gov "report"`** – Find reports on government websites.  
- **`site:example.com -inurl:www`** – Find subdomains of a website.  

---

## **Index and Directory Listings**  

Find exposed directories and file indexes.  

- **`intitle:"index of /"`** – Find open directories.  
- **`intitle:"index of" "parent directory" ext:mp3`** – Find MP3 files in open directories.  
- **`intitle:"index of" passwords`** – Look for exposed password files.  

---

## **Sensitive Information Discovery**  

Find exposed login pages, credentials, and configurations.  

- **`inurl:admin intitle:login`** – Find admin login portals.  
- **`ext:sql "password"`** – Look for SQL files with password mentions.  
- **`ext:env "DB_PASSWORD"`** – Look for exposed `.env` files containing database credentials.  
- **`"Confidential" OR "Internal Use Only" filetype:pdf`** – Search for restricted documents.  

---

## **Common Dorks**  

- **`"powered by phpbb" inurl:register`** – Find forums running PHPBB.  
- **`"Warning: mysql_connect()" filetype:php`** – Identify sites with database connection errors.  
- **`"index of" "wp-config.php"`** – Search for exposed WordPress config files.  
- **`intitle:"login" "Welcome to Webmin"`** – Find exposed Webmin login pages.
- 
*Created by M Harrell*
