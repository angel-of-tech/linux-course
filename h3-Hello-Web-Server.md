### a)	Apachen asennus

Asensin Apachen komennolla `sudo apt install apache2 -y`. Seuraavaksi tarkistin toimiiko Apache, komennolla `sudo systemctl enable apache2`

![Add file: Upload](Picture1.png) 

Ja curl-komennon avulla tarkistin, vastaako webpalvelin localhostiin. Eli komento `curl -I http://localhost`. Vastaukseksi tuli 200 OK eli toimii!

![Add file: Upload](Picture2.png) 

b)	Lokien rivit ja niiden analysointi
Seuraavaksi latasin palvelimeltani yhden sivun, ja tarkastelin syntyneen lokin rivejä. 

![Add file: Upload](Picture3.png) 

Analyysi

![Add file: Upload](Picture4.png) 

![Add file: Upload](Picture5.png) 

![Add file: Upload](Picture6.png) 

![Add file: Upload](Picture7.png) 

![Add file: Upload](Picture8.png) 

![Add file: Upload](Picture9.png) 


