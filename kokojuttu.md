# h5 Koko juttu
## a) Uuden virtuaalikoneen luonti ja web-palvelimen asennus
- Aloitin uuden tyhjän virtuaalikoneen luomisen antamalla sille nimen, lisäämällä Debian 12 ISO Imagen, jota olen käyttänyt myös aiemmin luomissani virtuaalikoneissani, ja versioksi valitsin
Debianin 64 bittisen käyttöliittymän. Muistin määräksi asetin 4000 MB:ta ja loin koneelle 60 GB:n virtuaalikovalevyn. Kun olin nämä asetukset tehnyt, käynnistin koneen.
- Kun kone oli käynnistynyt, avasin Debian installerin Debianin asentamista varten. Asetin koneen sijainniksi Helsingin, asetin suomenkielisen näppäimistön, valitsin Partitions valikossa
"Erase disk"-vaihtoehdon, lisäsin käyttäjätiedot ja salasanan ja annoin koneelle nimen. Tämän jälkeen tarkistin vielä yhteenveto-osiossa tekemäni asetukset ja aloitin asennuksen. Asennuksessa
meni noin kymmenen minuuttia ja kun se oli valmis, käynnistin virtuaalikoneen uudelleen. Uudelleen käynnistämisessä meni muutama minuutti.
- Uudelleenkäynnistyksen jälkeen avasin terminaalin ja aloin tekemään alkuasetuksia. Ensimmäiseksi hain tiedot saatavilla olevista päivityksistä komennolla
    ```$ sudo apt-get update```.
Sitten asensin kaikki tärkeimmät pävitykset komennolla
    ```$ sudo apt-get -y dist-upgrade```.
Kun päivitykset oli asennettu, asensin vielä palomuurin komennolla
    ```$ sudo apt-get -y install ufw``` ja kytkin sen päälle komennolla
    ```sudo ufw enable```.
- Seuraavaksi asensi Apache-weppipalvelimen komennolla
    ```$ sudo apt-get -y install apache2``` ja sen jälkeen asensin SSH-etähallintapalvelimen komennolla
    ```$ sudo apt-get install openssh-server```.
- Vuokrasin tätä tehtävää varten kokonaan uuden pilvipalvelimen DigitalOceanilta, koska olin unohtanut aiemmin tekemäni palvelimen salasanan enkä päässyt kirjautumaan sinne. Vuokrasin myös itselleni uuden domain-nimen Name.com-palvelusta ja hyödynsin tähän GitHub Education paketin krediittejä ja valitsin domain-nimeksi jukkalakkala.live.
- Uuteen palvelimeeni tein samat asetukset mitä olin aiemmin luomaani palvelimeen asettanut eli palvelimen sijainniksi valitsin Amsterdamin, käyttöliittymäksi 64 bittisen Deabian 12:sta, lisäsin tavallisen 1 GB:n prosessorin ja 25 GB:n SSD-kovalevyn. Sitten asetin juuren salasanan ja asetin hostnamen. Kun palvelin oli luotu asetin Name.comissa luomani domainin osoittamaan uuden palvelimen IP-osoitteeseen.
- Seuraavaksi avasin ssh-yhteyden uuteen virtuaalipalvelimeeni sen IP-osoitteen mukaan komennolla
    ```$ ssh root@161.35.148.7```   ja asensin sen jälkeen palomuurin sekä tein siihen reiän porttia varten komennolla
    ```$ sudo ufw allow 22/tcp``` ja laitoin palomuurin päälle.
- Seuraavaksi loin virtuaalipalvelimelle uuden käyttäjän komennolla
    ```$ sudo adduser jukka```, asetin käyttäjälle salasanan ja nimitiedot ja annoin uudelle käyttäjälle pääkäyttäjäoikeudet komennolla
    ```$ sudo adduser jukka sudo```.
- Sitten kokeilin ottaa uudessa terminaalissa ssh-yhteyden virtuaalipalvelimeen luomillani käyttäjätunnuksilla komennolla
    ```$ ssh jukka@161.35.148.7```, syötin salasanan ja yhteyden muodostus onnistui. Lopuksi lukitsin juuren komennolla
    ```$ sudo usermod --lock root```.
- Seuraavaksi asensin Apachen myös virtuaalipalvelimelleni ja tein palomuuriin uuden reiän komennolla
    ```$ sudo ufw allow 80/tcp``` ja tämän jälkeen testasin selaimessa, vastaako palvelin osoitteessa jukkalakkala.live ja minulle avutui Apachen testisivu eli palvelin toimi.
 



