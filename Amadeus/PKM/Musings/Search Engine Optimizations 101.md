---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "SEO"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 18, 2022 2:50 AM"
Sources: "Unknown"
---

# Search Engine Optimizations 101

The term "*SEO*" stands for "*Search Engine Optimization*" and it refers to the process of improving a site to increase its visibility and traffic for people who use search engines such as Google, Bing, DuckDuckGo, Yandex, and many more.

## **Indexing**

Once bots are finished crawling the content of the page, they will upload the information to the servers of the company that owns that search engine. Inside the server, the information lives in an index with all the other visited pages. An "*Index*" is something similar to a dictionary. Search engine users will querying against this index.

As time passes, the information in the index must be changed from time to time, crawlers use algorithms to establish the frequency with which they scan a specific page and how many pages of the website it must scan. These algorithms help crawlers to tell a frequently updated page from one that doesn't change over time: the crawler would scan the first one more regularly.

## **Crawling**

A search engine must provide content relevant to the users. To obtain such content search engines need to have the content stored somewhere in their servers, always available for them to use at any moment. The technique used by search engines to obtains such content is called "*Crawling*".

Search engines use "*crawling*" as a way of accessing and discovering pages around the web. They have bots that will visit our websites, trying to crawl every page they can find. They will search for all the links contained in a page and *Sitemap file* and follow the instructions inside a `robots.txt` file.

The robots.txt is a file created to instruct bots. We can suggest to ignore particular resources within our website. This file is part of the the "[*Robots Exclusion protocol (REP*)](https://moz.com/blog/robots-exclusion-protocol-101)", a group of web standards that regulate how robots crawl the web, access and index content, and serve that content up to users. The instructions written down in the file are specified by “disallowing” or “allowing” the behavior of certain user agents (User Agents = "*Web Crawling Software*"):

```jsx
User-agent: [User agent name]
Disallow: [URL to ignore]
User-agent: *
Disallow: /
User-agent: *
Disallow: /wp-admin/
Allow: /wp-admin/admin-ajax.php
```

[Google has documented](https://developers.google.com/search/reference/robots_txt) regarding how they handle the robots.txt file.

User agents expect to find the robots.txt file of a website in the path /robots.txt. If the user agent does not find any file there, it will assume the site does not have one and proceed with crawling everything on the page (and maybe even on the entire site).

It's a list of all the pages in our website. The idea of a sitemap is to help users and bots to understand the structure of the website. In the case of bots, they usually discover pages from links within the site and from other sites. Sitemaps are just there to supplement this data to allow crawlers to pick up all URLs in the Sitemap and learn about those URLs.

Sitemaps do not improve the search engine results, they are hints for bots to perform a better job when they craw your website.

- **HTML Sitemap**: This kind of sitemap is specifically for humans. Usually a website should have a link to the sitemap somewhere (usually in the footer for example). If a visitor clicks on it, it should take him/her to a new page where all the pages available listed in a hierarchical fashion.
- **XML Sitemap**: This kind of sitemap is specifically for crawlers. It's a list of all the websites listed using a XML file. XML Sitemaps follow a protocol called The "[*Sitemap protocol*](https://www.sitemaps.org/protocol.html)".

Search engine users may be from different countries and languages and they will expect their content to be consumable, results from a page in Australia are expected to be related to Australia and in english, similar with a user in France, expects the results to be in french. When performing the crawling step, bots are locale aware so the content stored is also categorized by the language and the country (locale).

At the end of the crawling step, the crawled content of the website ends up being stored on something called "index".

## **Ranking**

Once the crawled content from your website starts living inside the index of the search. The content is processed to determine where a particular piece of content should appear on a search engine result page, this is called "*Ranking*". Highly visible content (usually the content that ranks highest) may appear right at the top of organic search results or even in a featured snippet, while less-visible content may not appear until searchers click to page two and beyond.

### **Ranking Factors**

Ranking is a complex process, there are a lot of factors search engines take into account to rank crawled page, Google categorize such factors into the following groups:

- **Domain Factors**: such as the domain age, keywords appearing in top level domains, keywords appearing first word in domain, the domain registration length, etc.
- **Page-Level Factors**: Such as having keywords in the title tag, having the title tag starting with the keyword, having keywords in the description tag, having header tags with keywords, the length of the content, having a table of contents, keyword density, etc.
- **Site-Level Factors**: Having high quality content, having a contact page, having a good score in TrustRank, frequency of updates, having a sitemap presence, the site uptime, the server location, having SSL certificate, being mobile optimized, etc.
- **Backlink Factors**: Using aged domains rather than new domains, the number of referring domains, the number of linking pages, the text of the anchors, using alt text for clickable images, being an authority figure in the topic, being linked from competitors, not having links from "*bad-neighbors*", number of comments, etc.
- **User Interaction:** [Google's RankBrain algorithm](https://backlinko.com/google-rankbrain-seo), "*Organic click through rate for a keyword*", bounce rate, direct traffic, repeat traffic, pogosticking, bookmark storage, etc.
- **Special Google Algorithm Rules**: Your browser history, the user search history, geo targeting, safe search, domain diversity, transactional searches, local searches, etc.
- **Brand Signals**: Brand name anchor text, branded searches, having a twitter profile with your brand, having a facebook profile with your brand, brand mentions on top stories, etc.
- **On-Site Web spam Factors**: Sites with low quality content suffer penalties, having distracting ads, sneaky redirects, being linked from bad neighbors, having gibberish content, having doorway pages, having too many ads, etc..
- **Off-Site Web spam Factors**: Being hacked, metatag spamming, having an unnatural number of links, having links from articles and press releases, selling links, etc.

One could summarize such large group and take the most important ones as the followings:

- Referring domains.
- Organic click-through-rate.
- Being considered a domain authority in the topic.
- Mobile usability of your website.
- How long people spend on your website coming form a search engine result page.
- Total number of links pointing back at your website.
- Having high quality content.
- Site optimizations for SEO.

For the extensive list of ranking factors [Google has documented 200 ranking factors they use to rank content](https://www.notion.so/Search-Engine-Optimization-23c319eee75d49c49c20ce2b21f6eace#906c35539cfa401dbb2ceb3bf2b34ab1).

### **On-page SEO**

It's also known as "*On-site*" SEO. It is the technique of optimizing your website content for search engine and visitors. This concept of optimizing your website may appear old but is still relevant because google still crawls your site for keywords. For Google and other search engines the most basic signal that the information is relevant is when your website contains the same keywords the user is querying. If they appear in the headings or body of the text, the information is likely to be relevant.

- **Header tags**: HTML tags used to identify headings and subheadings. They provide organizational structure and go from most relevant (h1) to less relevant (h6). Headers are expected to contain keywords.
- **Keyword frequency**: How often a keyword appears in a page of content. When you keyword frequency is really low, Google cannot determine if your page is relevant.
- **Meta description**: They are tags that should include brief description that summarizes the content o the indexed page. Search engines may use the provided description as snippets for your pages, this is something search engines can't do on their own.
- **Title tag**: It's the most important tag of your page when it comes to on-page SEO. It's what users see read first when they are reading the search engine results page. It summarizes the content and it can affect your click rates.
- **High Quality Content**: Content is essential for SEO ranking. Our website needs to provide content that is unique, relevant and comprehensible. Content creation goes hand in hand with a keyword research. Another way to show your page is a hub of high quality content is pointing out to other pages with related topics. That helps search engines determine your website's topic and it may recognize you as a hub of quality info.
- **Keyword research**: A research on what keywords should be used in the page is certainly important because we are looking for a high volume of traffic with the least possible amount of competition while also having relevancy in our domain topic.
- **Internal linking:** Hyperlinks that point from one page of your website to another one. Having internal links is a must since linked pages are also indexed with the current page.
- **SEO friendly URLs**: Overly complex URLs with multiple parameters can cause problems for crawlers by creating high number of URLs that point to identical or similar content of a website. Bots may consume too much content and may not index everything relevant in it. Usually the shorter and simpler, the better.
- **Sitemaps**: The benefits of using sitemaps are quite obvious, they improve craw-ability of content for bots.

### **Off-page SEO**

It's also known as "*Off-site*" SEO. The term refers to the process of linking or promoting your website using link building.

Crawling algorithms and ranking factors may change overtime, but there are factors like relevance, trustworthiness and authority that are effective and play major roles when ranking a website. "*Off-page*" optimizations are actions taken outside of your own website to impact your rankings within search engine results pages.

This is accomplished by other reputable places on the Internet (pages, sites, people, etc.) linking to or promoting your website, and effectively "*vouching*" for the quality of your content.

If you are linked by a well known page:

- The website may have a traffic increase.
- Website's recognition increases.
- Website's credibility increases.
- Page rank increases.
- Brand awareness increases.

**Types of External Linking**

Search engines use links to determined the linked content's quality. The higher external linking, the higher a domain authority you are considered, and therefore will probably obtain a higher ranking than other websites with fewer external linking.

Search engines categorizes external links in three ways:

- **Natural links**: are the most desired kind of links for SEO. They are links that the website owner obtained without any kind of action. Another entity/person/website decided to link to the content without asking them to do so, that is why it is called *natural*.
- **Outreach links**: **These are links that are acquired after contacting other website and content creators, and asking them to link to your content to increase your ranking.** This includes things like getting customers to link to your website or asking influencers to share your content. **It is really common to do this with websites with related content to yours.**
- **Non-editorial links:** These are a fraudulent type of links aim to fool research engines into thinking some piece of content is relevant and important, that is candidate to be indexed. Content owners usually post links to their websites in online blogs, comments and forums in an attempt to increase traffic. Search engines have evolved sufficiently enough to determine that these kind of links are not valuable anymore and penalize websites who do this.

### **An Strategy**

Usually when you refer to Off-page SEO you need a strategy that involves:

- High quality content creation: Even though it was mentioned in the "*On-page*" SEO section. Content is also essential for "*Off-page*" SEO. It's the way to show your website brings something unique to the table and prompts other website to link to yours.
- Offsite engagement.
- Promoting in Social Media Platforms: Where you could promote and be promoted by users of such social media. Of course, it depends because not all social media platforms are useful for the kind of content one wish to promote.
    - Collaboration with other content creators: A normal strategy that takes place is having guest posts / content, collaborations or being referred by other known content creators in their websites.