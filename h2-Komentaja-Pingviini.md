x) Pikainen tiivistys Tero Karvisen artikkelista [Command Line Basics Revisited](https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited)

Tärkeimpiä komentorivikehotteita:
- `pwd`: näyttää nykyisen työhakemiston.  
- `ls`: listaa hakemiston tiedostot ja kansiot.  
- `cd`: vaihtaa hakemistoa.  
- `less`: näyttää tiedoston sisällön.  
- `mkdir`: luo uuden hakemiston.  
- `mv`: siirtää tai nimeää tiedostoja ja kansioita.  
- `cp`: kopioi tiedostoja tai kansioita.  
- `rm`: poistaa tiedoston tai hakemiston.  
- `ssh`: yhdistää etäpalvelimeen Secure Shellin avulla, eli turvallisesti.    
- `man`: näyttää komennon manuaalisivun, eli selityksen komennon käytöstä.  
- `--help`: näyttää lyhyen version komennon käytön ohjeista.  
- `history`: näyttää aiemmin käytetyt komennot.  
- `apt-get update`: päivittää pakettien luettelon.  
- `apt-cache search`: hakee ohjelmia avainsanoilla.  
- `apt-get install`: asentaa ohjelmia.  
- `apt-get purge`: poistaa ohjelman ja sen asetukset.  

a) Ihan ensi töikseni asensin Micro-tekstinkäsittelyohjelman Ubuntu-virtuaalikoneeseeni. Seurasin ohjeita ja katsoin muutenkin apuja ohjelman käyttöön Googlesta löytämältäni nettisivulta https://itsfoss.com/micro-editor-linux/. 
Syötin komentokehotteeseen komennon  `sudo apt install micro`. 
Asennussyöte rullasi ruudulla eteenpäin mallikkaasti, mutta tarkistin vielä onnistuiko asennus todella, käyttämällä komentoa `micro --version`.

![Add file: Upload](ping-(8).png)

Ja siellähän se on! Testasin vielä ohjelman toimintaa luomalla tekstitiedoston komennolla `micro testitiedosto.txt`

![Add file: Upload](ping-(9).png)

Ja taas toimi, ja pääsin kirjoittamaan tiedostoon onnistuneesti.

b) Veikkasin, että asentaakseni kaikki kolme ohjelmaa, voin käyttää samaa komentoa kuin yksittäisen ohjelman asennukseen, ja laittaa kaikkien ohjelmien nimet komennon perään. Eli tässä tapauksessa `sude apt-get install cowsay nmap fortune-mod `. 
Fortunen on tarkoitus antaa satunnainen lainaus tai hauska fakta. Luulin ohjelman olevan automaattisesti englanniksi, mutta käyttäessäni fortune-komentoa, kaikki teksti tulikin italiaksi, enkä osannut vaihtaa kieltä. Ongelman googlettaminenkaan ei tuottanut tulosta. Osaan kuitenkin jonkin verran italiaa, joten tämäkin tulos oli ihan hyväksyttävissä. 

![Add file: Upload](ping-(10).png)

Seuraavaksi käytin Cowsayta ja laitoin ASCII-lehmän sanomaan jotain tärkeää.

![Add file: Upload](ping-(11).png)

Kolmas ohjelma oli Nmap, jolla skannasin satunnaisen verkkosivun. Selvitin kyseisen palvelimen avoimet portit ja muita verkkoon liittyviä tietoja. Nmapia käytetään kyberturvallisuuspuolella paljon. 

![Add file: Upload](ping-(12).png)

c) Kävin läpi Linux-järjestelmäni tärkeimmät kansiot noudattaen Tero Karvisen [Command Line Basics Revisited -artikkelia](https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited). 

Aloitin juuresta, eli /, komennolla `ls /`.

![Add file: Upload](ping-(3).png)

Sitten siirryin /home/, komennolla `ls /home`. Ja kotikansioni nimi on oma nimeni, eli veera. 

![Add file: Upload](ping-(4).png)

Komennolla `ls /home/veera` pääsen näkemään mitä kansioita hakemistossa on.

![Add file: Upload](ping-(5).png)

Komento `ls /etc` näyttää valtavan listan järjestelmän asetustiedostoja.

![Add file: Upload](ping-(6).png)

Komento `ls /var/log/` puolestaan näyttää järjestelmän lokitiedostot.

![Add file: Upload](ping-(7).png)


d) & e) Grep-komentoa käyttämällä voi etsiä tekstiä ja sanoja tiedostoista. Se on helppo tapa löytää tärkeä tieto isosta määrästä dataa, esimerkeiksi logeissa. (https://www.gnu.org/software/grep/manual/grep.html) 
Loin nopeasti tekstitiedoston kopiomalla Dracula-kirjan ensimmäisen kappaleen [Gutenbergista](https://www.gutenberg.org/cache/epub/345/pg345-images.html), käyttäen komentoa `echo "teksti" > dracula.txt`. Sitten greppasin "you"-sanan esiintymismäärän tekstissä komennolla `grep -o "you" dracula.txt | wc -l`. Kommennosta näkee, että käytin myös putkimerkkiä. Putkimerkki ohjaa grep-komennon tulosteen seuraavalle komennolle. Tässä tapauksessa grep siis ensin tulostaa jokaisen "you"-sanan omalle rivilleen, ja putkimerkki siirtää tämän tulosteen wc-komennolle (word count), joka laskee rivien määrän.

![Add file: Upload](ping-(13).png)

Koska luomani tekstitiedosto oli vain nopeasti netistä kopioitu, eivät "you"-sanat ole mitenkään siististi omilla riveillään. Käyttäessäni pelkkää grepiä, tulos oli siis tämä: 

![Add file: Upload](ping-(14).png)

Ensimmäinen rivi, jolla "you" esiintyy, on siis hyvin pitkältä näyttävä seinä tekstiä. Komento kuitenkin toimi kuten piti.

f) Asensin ensin lshw:n komennolla `sudo apt-get install lshw`

![Add file: Upload](ping-(1).png)

Seuraavaksi ajoin komennon `sudo lshw -short -sanitize`. Tässä komennossa "sanitize" pitää huolen siitä, ettei näkyviin tule henkilökohtaisia tunnistetietoja, kuten IP-osoitteita.

![Add file: Upload](ping-(2).png)

Komento näyttää virtuaalikoneen raudan osat. Käydään läpi mitä tärkeimmät kohdat tuloksessa tarkoittavat. Käytin oman ymmärtämisen apuna Googlea, erityisesti tätä [sivua](https://linuxhandbook.com/lshw-command/)

System: kertoo järjestelmän, tässä tapauksessa virtualisoidun järjestelmän eli VirtualBoxin.

Bus: virtuaalikoneessa väylä on myös virtuaalinen, eli VirtualBox

Memory: muisti, sekä system memory (4GB) että BIOS (128KB). BIOSin on pakko käyttää pieni osa muistista järjestelmän käynnistykseen.

Processor: eli prosessori, virtuaalikone käyttää isäntäjärjestelmän fyysistä prosessoria

/dev/sda: 64G VBOX HARDDISK eli virtuaalikoneen tallennustila

Display: SVGA II ADAPTER eli virtuaalikoneen käyttämä näytönohjain/adapteri.

Network: Gigabit Ethernet Controller, virtuaalikoneen verkkoyhteys verkkosovittimen kautta

