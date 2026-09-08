In this lab, I utilized hydra to bruteforce a web user's login credentials, as well as their ssh credentials.

1. Assuming that we know what the ip of our target machine is, we can run an nmap scan on it to see what ports and
   services its running on.

2. I found that tcp port 22 is open which is using the service ssh. As well as tcp port 80 which is running on http. Now
   with these information, we can try using hydra to brute force these 2 services using the provided username molly.

3. For ssh bruteforce, I used the command hydra -l molly -P /usr/share/wordlists/rockyou.txt 10.64.154.167 -t 4 ssh
   -l means username, -P means the file containing passwords, then the target IP, then -t 4 allows hydra to do 4 password
   attempts at a time to prevent the machine from suspecting multiple login attempts.
   I then tested the credentials by connecting to the target machine via ssh using the credentials and I was able to login and
   capture the flag.

5. Next is web bruteforce. Lets first check what http method the server is using either by going into developer mode or checking
   the source code. We now know that the method its using is POST so we can use this command.
   hydra -l molly -P /usr/share/wordlists/rockyou.txt 10.64.154.167 http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect"
   /login is the page or path that we want to test this on.

CONCLUSION: hydra is a brute forcing program like john the ripper. The difference is, hydra is online while john is offline.
