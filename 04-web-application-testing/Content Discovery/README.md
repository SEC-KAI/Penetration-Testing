This lab is about different methods of content discovery.
Here are the things that I learned:

1. Robots.txt contains directories that search engine crawlers arent supposed to index but that doesnt mean or stop someone from manually typing it in their own browser. So a pentester can use robots.txt to view disallowed directories for engine crawlers and type it themselves to view if it is accessible or not. Basically, engine crawlers are bots that goes through every websites indexes and directories and reports back to google databse.

2. Sitemap.xml contains urls that the owner wants the engine crawlers to see. Examples are google/login, google/contact. Unlike robots.txt that tells crawlers which is not allowed this one is the opposite.

3. using curl (website) will display the headers instead of just showing the server response in visual form in the browser. This can show details like the server version the website is using which can be searched for vulnerabilities and some hidden directories and urls.

4. Github can be used to search the target and look for the repositories. check the commit changes since they couldve removed sensitive data but was kept in the history.

5. Gobuster can also be used to find hidden directories by using wordlists. VHOST can be used to also find subdomains of the domain.
