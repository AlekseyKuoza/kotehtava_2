### Kotitehtävä 2 

## Alkutilanne  

lähde...http://terokarvinen.com/2017/aikataulu-%e2%80%93-palvelinten-hallinta-ict4tn022-2-%e2%80%93-5-op-uusi-ops-loppukevat-2017-p2  
työympäristö...  
toimeksianto...  

Käynnistin kannettavan USBlivetikulla.  

## Github weppisivuston toimenpiteet

Firefoxilla kirjauduin github.com sivustolleni.  
Loin siihen uuden tietölähden arkiston (repository) nimeltaan kotitehtava_2.  
HUOM. Otetaan vastaan PUBLIC vaihtoehto, joten kuka tahansa voi nähdä 
arkiston. Samalla saa määritä, kuka saa kirjoutua sisään. Myös otetaan 
käyttöön GNU GPL lisenssi.   
Menin sisään arkostoon ja kopioin sen URLin, pystyäkseeni laitamaan sen 
myöhemmin terminaaliin.  

## Linux terminaalin toimenpiteet ja git asentaminen

Terminali-paneelissa ajasin seuraavat komennot:  
$ sudo apt-get update - päivitin systeemin.  
$ setxkbmap fi - muutin näppäimistön asetukset suomen kieleseksi.  
$ sudo apt-get install git - asensin git moduuli.  
$ git config --global user.email "e-mail osoite"  
$ git config --global user.name Aleksey Kuoza - laitoin gitin alkuasetukset.  
$ get clone https://github.com/AlekseyKuoza/kotitehtava_2.git - kirjauduin arkistoon.  
$ cd kotitehtava_2/ - menin kansioon.  
$ nano readme.md - loin markdownin tyyppisen tiedoston nimeltaan readme.md.  
$ git add .  
$ git commit  
$ git pull  
$ git push - suiritin komennot ja sitten tarkistin, että tiedosto näkyy github.com:n weppisivustolla.  

## Puupet asentaminen

$ sudo apt-get -y install puppet - asensin puppet-moduulin.  
$ ...  






