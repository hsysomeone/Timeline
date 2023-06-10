# Table of Contents 
[*generated with markdown-toc*](http://ecotrust-canada.github.io/markdown-toc/)

- [7-13-2022](#7-13-2022)
- [7-20-2022](#7-20-2022)
- [8-24-2022](#8-24-2022)
- [8-31-2022](#8-31-2022)
- [9-7-2022](#9-7-2022)
- [9-14-2022](#9-14-2022)
- [9-21-2022](#9-21-2022)
- [9-28-2022](#9-28-2022)
- [10-5-2022](#10-5-2022)
- [10-12-2022](#10-12-2022)
- [10-19-2022](#10-19-2022)
- [10-26-2022](#10-26-2022)
- [11-2-2022](#11-2-2022)
- [11-9-2022](#11-9-2022)
- [11-16-2022](#11-16-2022)
- [11-22-2022](#11-22-2022)
- [11-30-2022](#11-30-2022)
- [12-7-2022](#12-7-2022)
- [Winter Break Todos](#Todos)
- [1-12-2023](#1-12-2023)
- [1-18-2023](#1-18-2023)
- [1-25-2023](#1-25-2023)
- [2-1-2023](#2-1-2023)
- [2-8-2023](#2-8-2023)
- [2-16-2023](#2-16-2023)
- [2-23-2023](#2-23-2023)
- [3-2-2023](#3-2-2023)

---
### 7-13-2022
Wrote the code [**Generate_article_list.R**](Generate_article_list.R) to generate the list of ids of our targeted articles, which is a re-work based on the illustration in the unfinished paper:  
*"... We developed an extensible markup language (XML) crawler to retrieve targeted articles from Medline. It was guided by a rule-based configuration that identified articles by both their mesh term and the desired crawling depth. These rules performed an initial screening of the articles in order to best identify the appropriate documents for the final corpus. The crawler started the navigation by retrieving the MESH term “Crowdsourcing” using rentrez() from the XML library in R. This program harnesses NCBI's EUtils API for parsing databases such as GenBank and PubMed. Based on the matching mesh term, the crawler extracted the data based on the nested XML metadata from PubMed and Pubmed Central of PMID, Journal, Publication Date, Article Year, Article Title, and Author Name (First, Last). The extracted data were subsequently processed by plyr() from the R library and automatically compiled into a csv file. ..."*
