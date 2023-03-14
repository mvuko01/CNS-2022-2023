# Sigurnost

1. What is the *Address Resolution Protocol (ARP),* and what is its role in a network?
    1. ARP je komunikacijski protokol koji služi za povezivanje IP adrese MAC adresi u LAN-mreži.
2. What is a *Man-in-the-Middle (MitM)* attack, and how does ARP spoofing enable it?
    1. Man in the middle napad je vrsta napada gdje se napadač ubacuje u razgovor između dvaju korisnika (tj. između dvije krajnje točke u nekakvi kanal) te se pretvara da je on bilo koji od ta dva korisnika. On omogućava ARP spoofing na način kada korisnik A šalje ARP request od nekog računala B. Umjesto ARP odgovora računala B on će dobiti odgovor od računala C tj napadača.
3. How does an attacker use ARP spoofing to intercept network traffic?
    1. Napadač sazna MAC adresu žrtve, drugim računalima šalje svoju MAC adresu kao žrtivnu te mu onda oni šalju svoje zahtjeve
4. How is the cookie used to derive the encryption/decryption key?
    1. Cookie se šalje derive_key funkciji koja generira ključ.
5. What REST API request do you need to send to the crypto oracle the secret cookie?
    1. GET /arp/cookie
6. How do you obtain the authentication token?
    1. Autentikacijski token dobijemo na način da iskoristimo ranjivost ARP protokola i izvršimo man  in the middle napad između crypto oracle servera i računala arp_client. Računalo arp_client periodično traži taj token, a crypto oracle mu ga šalje. Pratimo promet mreže i taj promet filtriramo na način da pronađemo token.
7. How do you use the authentication token to obtain the cookie?
    1. napadac se predstavi kao zrtva pomocu autentifikacijskog tokena i od servera trazi cookie
8. What encryption mode is used to encrypt the challenge in this lab?
    1. AES-CBC
9. What tool can you use to capture network traffic on a local network interface?
    1. tcpdump