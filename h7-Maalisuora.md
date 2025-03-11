# "Hei maailma" -ohjelman toteutus Linuxissa kolmella ohjelmointikielellä

Tehtävänä oli kirjoittaa kolmella kielellä "Hei maailma!". Valitsin Pythonin, Bashin ja C:n.

![image](https://github.com/user-attachments/assets/1df7242e-29a4-4fbd-bf95-110bb1cb20eb)

![image](https://github.com/user-attachments/assets/226198b6-601a-440c-ac1d-4edd3ff4f8a2)

Loin tiedoston `hello.py` ja kirjoitin sinne tarvittavan koodinpätkän. Kun kirjoitin terminaaliin `python3 hello.py`, tulostui juuri se mitä pitikin.

![image](https://github.com/user-attachments/assets/78a9aefe-ac28-4878-a4d5-815bdf9eb982)

Sitten loin `hello.sh`. Tein skriptistä toimivan komennolla `chmod +x hello.sh`.

![image](https://github.com/user-attachments/assets/14fc3fe8-64da-4e2f-954b-aa7ed1c335a1)

Kun skriptin ajoi, tulostui juuri se mitä pitikin.

Ja lopuksi C-koodi eli `nano hello.c`. 

![image](https://github.com/user-attachments/assets/aaa29c0f-db27-4921-9371-73e97c103438)

C on matalan tason ohjelmointikieli, joka vaatii kääntämisen ennen suoritusta. Käännetään se siis! Käytin komentoa `gcc hello.c -o hello`. Komennossa käytin gcc eli GCC (GNU Compiler Collection) joka on avoimen lähdekoodin kääntäjä.

![image](https://github.com/user-attachments/assets/184ec7e8-8ded-46db-86e2-cd902d741afd)

Ja nyt ohjelman voi ajaa onnistuneesti.

# Oman komennon lisääminen Linuxiin kaikkien käyttäjien käytettäväksi

Siirryin ensin /usr/local/bin/ -hakemistoon, joka on yleisesti tarkoitettu käyttäjän lisäämille komennoille. Käytin komentoa `cd /usr/local/bin/`.

![image](https://github.com/user-attachments/assets/37d8a2ff-4adc-474d-996a-20596eab3c15)

Komennolla `sudo nano heipsu` loin uuden komentotiedoston, ja kirjoitin tiedostoon haluamani koodin. 

Sitten tein komennosta kaikille käyttäjille ajettavan komennolla `sudo chmod +x /usr/local/bin/heipsu`. Halusin vielä varmistaa että onnistuin, komennolla `ls -l /usr/local/bin/heipsu`.

![image](https://github.com/user-attachments/assets/c82aa7b8-2fcb-4524-9e0f-01aece833f9b)

Tulos rwxr-xr-x tarkoittaa, että kaikki käyttäjät voivat suorittaa skriptin.

![image](https://github.com/user-attachments/assets/ea1ce916-c799-49ac-a211-990b513f51fa)

Nyt kun komennon `heipsu` suorittaa, terminaaliin tulostuu haluamani viesti.

# Vanha laboratorioharjoitus

### Ei kolmea sekoseiskaa

Tässä alakohdassa tulee suojata raportti siten, etteivät muut voi katsella sitä. Jos raporttitiedosto on nimeltään raportti.txt, sen voi suojata komennolla `chmod 600 raportti.txt`. Nyt minä voin lukea ja kirjoittaa tiedostoon, mutta muut käyttäjät eivät voi katsoa sitä.

### 'howdy'-komento

![image](https://github.com/user-attachments/assets/87447394-ac35-4b76-96c4-96275ec491b8)

Loin uuden komentoskriptin /usr/local/bin/-hakemistoon komennolla `sudo nano /usr/local/bin/howdy` ja kirjoitin tiedostoon haluamani asiat. 

Tallensin tiedoston ja annoin tiedostolle suoritusoikeudet komennolla `sudo chmod +x /usr/local/bin/howdy`. Seuraavaksi testasin toimiiko komento.

![image](https://github.com/user-attachments/assets/c0d72b2e-8cca-45f9-8b4e-817c33e4f214)

Toimii kuten pitääkin.

### Apache-verkkopalvelimen asennus ja AI Kakone -kotisivu

Apachen voi asentaa komennoilla `sudo apt update` ja `sudo apt install apache2 -y`. 

![image](https://github.com/user-attachments/assets/75fdee67-0dd0-4ea2-a7ec-ee493fdd6f0a)

Poistin alkuperäisen Apache-sivun (otettuani siitä ensin varmuuskopion) komennolla `sudo rm /var/www/html/index.html`, jonka jälkeen kirjoitin uuden HTML-sivun.


![image](https://github.com/user-attachments/assets/289f0a55-5531-4f08-b1cd-21cfe8ea7a15)

Näkyy! Jotta normaalikin käyttäjä pääsee ilman sudo-oikeuksia muokkaamaan, ajoin komennot `sudo chown -R $USER:$USER /var/www/html/` ja `sudo chmod -R 755 /var/www/html/`.

Sitten asensin SSH-palvelimen komennoilla `sudo apt update` ja `sudo apt install openssh-server -y`.

![image](https://github.com/user-attachments/assets/090a9a3c-fef9-4aab-ad97-ebdb3eac9783)

Lisäsin uuden käyttäjän omalla nimelläni. Uuden avainparin sain luotua komennolla `ssh-keygen -t rsa -b 4096 -f ~/.ssh/id_rsa`.

![image](https://github.com/user-attachments/assets/8e0456e3-80e5-42a2-9263-0092d3acb524)

Kopioin julkisen avaimen käyttäjälle `ssh-copy-id veerate01@localhost` ja pääsin kirjautumaan sisään. 




# Lähteet:

Tero Karvinen 2024, Vanha laboratorioharjoitus: [https://terokarvinen.com/2024/arvioitava-laboratorioharjoitus-2024-linux-palvelimet/ 
](https://terokarvinen.com/2024/arvioitava-laboratorioharjoitus-2024-linux-palvelimet/)

SDSU, Run a C Program in Linux: [https://ost.sdsu.edu/kb/faq.php?id=152](https://ost.sdsu.edu/kb/faq.php?id=152)








