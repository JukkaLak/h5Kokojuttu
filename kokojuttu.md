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
  


