## x) Tiivistelmät

Pikainen tiivistys Let's Encryptin [How It Works](https://letsencrypt.org/how-it-works/)-artikkelista:
- Let's Encrypt enables automatic issuance and management of HTTPS server certificates.
- The agent must prove they have control over the domain using either DNS records or an HTTP resource.
- Requesting, renewing, and revoking certificates is done using an authorized key pair.


Pikainen tiivistys Lange 2024: Lego: Obtain a Certificate:[Using an existing, running web server]https://go-acme.github.io/lego/usage/cli/obtain-a-certificate/index.html#using-an-existing-running-web-server) -artikkelista:
- If a web server is already running on port 80, the `--http` option requires `--http.webroot`
- The `--http.webroot` option specifies the directory where Lego writes the http-01 challenge token to the `.well-known/acme-challenge` folder.
- Ensure the specified webroot directory is publicly accessible as the root directory (`/`) for validation purposes.
- Execute the Lego command with `--accept-tos`, `--email`, `--http`, `--http.webroot`, and `--domains` options to obtain certificates.

Pikainen tiivistys The Apache Software Foundationin artikkelista Apache HTTP Server Version 2.4 Official Documentation: SSL/TLS Strong Encryption: How-To: [Basic Configuration Example](https://httpd.apache.org/docs/2.4/ssl/ssl_howto.html#configexample):
- Load the SSL module
- Enable listening on port 443
- Define a virtual host for HTTPS

## a) Let's

Ensin suoritin komennon sudo apt update && sudo apt install certbot python3-certbot-apache, jolla siis asensin certbotin. Certbot on Let’s Encryptin virallinen asiakasohjelma. 

![Add file: Upload](Sala1.png)

Sitten hankin ja asensin sertifikaatin komennolla sudo certbot --apache. Seurasin ruudulle ilmestyviä ohjeita. Syötin oman sähköpostiosoitteeni (tässä kohtaa kannattaa olla kärsivällinen, luulin ensin että komentorivi jumittui, mutta sillä kestikin vain aikansa kunnes vastasi) ja valitsin sen domainin, jolle halusin sertifikaatin, eli angeloftech.com.

![Add file: Upload](Sala2.png)

No sittenpä tulikin vastaan ongelma, nimittäin sen minkä taakseen jättää, sen edestään eittämättä löytää. En siis ollut viime viikolla saanut domainia toimintaan, joten eihän sertifikaatin asennus tietenkään onnistunut. Huoh! No pakkohan tämä on hoitaa kuntoon. Sitä ennen kuitenkin teen vapaaehtoisen web-lomaketehtävän, jotta saan nyt edes jotain palautettua kotitehtäväksi:

## c) Vapaaehtoinen web-lomake

![Add file: Upload](Sala3.png)

Loin ensin hyvin yksinkertaisen HTML-lomakkeen komennolla `sudo nano /var/www/html/login.html` ja kirjoittamalla tarpeellisen koodin tiedostoon. 

![Add file: Upload](Sala4.png)

Jotta lomake pystytään käsittelemään, tarvitaan PHP-koodi. Katsoin koodeihin apuja [freeCodeCampista](https://www.freecodecamp.org/news/creating-html-forms/).

![Add file: Upload](Sala5.png)

Lomake löytyy testisivulta ja näyttää hyvältä.

Liikenteen nappaamiseksi asensin ngrepin komennolla `sudo apt install ngrep`. Sitten lähdin nappaamaan liikennettä komennolla `sudo ngrep -d any -W byline 'GET|POST' tcp and port 80`. Katsoin ohjeita komennon käyttöön [Geeks for Geeks](https://www.geeksforgeeks.org/ngrep-network-packet-analyzer-for-linux/) -sivulta.

![Add file: Upload](Sala6.png)

Komennon vastauksessa näkyy käyttäjätunnus ja salasana selväkielisenä. Tämä ei tietenkään ole hyvä. HTTP-yhteys ei ole salattu, joten salasanat ja muut lomaketiedot voivat helposti joutua verkkohyökkäyksen kohteeksi. Salasanat tulisi aina lähettää suojatun yhteyden yli. Lomakedatassa ei myöskään tulisi lähettää arkaluontoisia tietoja, kuten salasanoja, selväkielisinä, vaan ne pitäisi tiivistää ja suolata kirjautumisen yhteydessä. 

## b) A-rating

Sitten testasin satunnaisen nettisivun TLS:n [SSLLabsilla](https://www.ssllabs.com/ssltest/). 

![Add file: Upload](Sala7.png)

Valitsemani sivu terokarvinen.com sai arvosanakseen B:n, eli melkoisen hyvän. Protocol support näyttäisi tuovan arvosanaa alaspäin. Palvelin ilmeisesti tukee vanhoja TLS 1.0 ja TLS 1.1 -protokollia. TLS 1.2, TLS 1.1 ja TLS 1.0 -versioille on listattu useita WEAK merkittyjä salauskokonaisuuksia (CBC-SHA), jotka heikentävät turvallisuutta. Sivuston turvallisuutta ja siten SSL Labs -arvosanaa saisi siis nostettua poistamalla tuki vanhentuneilta protokollilta.

## Lähteet: 

freeCodeCamp, How to Create a Simple HTML and PHP Form 2023: https://www.freecodecamp.org/news/creating-html-forms/
Geeks for Geeks, Ngrep – Network Packet Analyzer for Linux 2021: https://www.geeksforgeeks.org/ngrep-network-packet-analyzer-for-linux/




