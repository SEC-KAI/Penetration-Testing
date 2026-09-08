In this lab, i used gobuster to find out hidden directories, vhosts, and subdomains.

1. ENUMERATING DIRECTORIES:
   I used the command gobuster dir -u http://10.64.176.233 -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt
   dir means using directory enumeration
   -u means the target url
   -w is the wordlist path we want to use
   This command would show hidden directories of the http://10.64.176.233 like /development.log

2. ENUMERATING SUBDOMAINS:
   We first need the parent domain in order to find its subdomain. In this case, our parent domain is example.thm so we did
   gobuster dns -d example.thm -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt --wildcard
   additionally, you can use -i to resolve its dns and show its ip aswell.
   what this does is that gobuster is going to add these wordlists on the given domain example.thm for example,
   wordlist has "admin" -> admin gets added -> admin.example.thm -> asks to resolve for admin.example.thm and if it gets
   resolved then success and add to found subdomains.
   
4. ENUMERATING VHOSTS:
   gobuster vhost -u http://10.64.176.233 --domain example.thm -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-       top1million-5000.txt --append-domain --exclude-length 250-320
   What this does is that gobuster appends the domain with the wordlist like admin -> admin.example.thm, then it makes an
   http request to 10.64.176.233 with the host:admin.example.thm, then if the server replies okay, then that means the
   website exists on that domain.

IN CONCLUSION:
   multiple hostnames/websites can resolve to the same IP address. When your browser connects to that IP, the web server        needs to know which website you requested, so it looks at the HTTP Host: header.
