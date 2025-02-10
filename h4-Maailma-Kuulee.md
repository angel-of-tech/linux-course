## h4) Maailma Kuulee

### x) 
Muutama tiivistetty kohta Susanna Lehdon artikkelista [Teoriasta käytäntöön pilvipalvelimen avulla (h4)](https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/):

- Autentikointiin voi valita salasanan, mutta SSH-avaimia suositellaan.

- Palvelin suojataan palomuurilla, ja verkkosivujen toimintaa varten HTTP ja HTTPS-liikenne tulee avata.

- Muut portit kannattaa sulkea tietoturvan takaamiseksi.

- Tietoturvan kannalta myös ohjelmistojen päivitykset tulisi tehdä säännöllisesti.

  
Muutama tiivistetty kohta Tero Karvisen artikkelista [First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS](https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/):

- Luo uusi virtuaalipalvelin DigitalOceanissa ja valitse Ubuntu 16.04 LTS.

- Ota käyttöön palomuuri sallimalla ensin SSH-yhteydet.

- Luo uusi käyttäjä ja anna sille sudo-oikeudet, sitten poista root-kirjautuminen.

- Päivitä järjestelmän ohjelmistot uusimpiin versioihin.
  
- Konfiguroi julkinen DNS-nimi NameCheapissa, jotta se ohjautuu palvelimelle.

### a) 

Vuokrasin pilvipalvelimen [UpCloud](https://upcloud.com/) -sivustolta. Halusin palvelimen Suomesta, ja UpCloud on suomalainen palveluntarjoaja. 

![Add file: Upload](maailma1.png)

![Add file: Upload](maailma2.png)

![Add file: Upload](maailma3.png)

![Add file: Upload](maailma4.png)

![Add file: Upload](maailma5.png)

![Add file: Upload](maailma6.png)


### b) / c)

![Add file: Upload](maailma7.png)

Menin SSH ja rootin kautta serverin IP:lle. 

![Add file: Upload](maailma8.png)
 
Asensin palomuurin käyttämällä komentoa sudo apt update && sudo apt install ufw -y

![Add file: Upload](maailma9.png)
 
Sitten reikä SSH:lle, jonka jälkeen enabloin palomuurin.

![Add file: Upload](maailma10.png)
 
Palomuuri päällä.

![Add file: Upload](maailma11.png)

Olinkin jo jäsen osassa ryhmiä. Lisäsin itseni adm-ryhmään. 

![Add file: Upload](maailma12.png)

Lukitsin rootin.

![Add file: Upload](maailma13.png)
 
Sitten päivitin ohjelmat komennolla sudo apt upgrade.

![Add file: Upload](maailma14.png)
 
Tarkistin vielä mitkä portit olikaan sallittu. 

![Add file: Upload](maailma15.png)

Nyt palvelimen IP johdattaa meidät Apachen testisivulle.

![Add file: Upload](maailma16.png)

Tein vaatimattoman uuden testisivun ja uudelleenkäynnistin Apachen. 

![Add file: Upload](maailma17.png)

Ja sehän toimii!
