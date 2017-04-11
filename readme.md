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

Tässä vaiheessa menin jumiin, sillä en valitettavasti ymmärtänyt toimeksiantoa... mitä se "moduuli, joka tekee asetukset jollekin komentorivi- tai graafisen käyttöliittymän ohjelmalle" - mahtaisi tarkoittaa..... 

Joten menin katsomaan, kuinka minun ystäväni Ville Kauppinen on onnistunut teekemään tämän tehtävän.... Häneltä (niin kuin melkein aina) löytyi selkeä ja johdonmumkainen ratkaisu. Tässä on linkki hänen kotitehtävään https://github.com/ibiuman/puppetalias/blob/master/README.md   

Niin päätin tehdä perässä saman moduulin... 

$ cd /etc/puppet/modules - menin modules-kanssioon. 
$ sudo mkdir xcolors - loin uuden moduulin. 
$ cd xcolors - 
$ sudo mkdir manifests - 
$ sudo mkdir templates - 
$ cd manifests - laitoin kuntoon perus asetukset. 
$ sudoedit init.pp - loin init.pp-tiedoston. 

ja kirjoitin siihen seuraavan koodin  
class xcolors {
        file { '/etc/X11/app-defaults/XTerm-color':
                content => template('xcolors/XTerm-color.erb')
        }
}

$ sudo cp /etc/X11/app-defaults/XTerm-color /etc/puppet/modules/xcolors/templates/XTerm-color.erb  - elikä, kopioin XTerm-color-tiedoston minun puppetin moduuliini, samalla muutin sen nimen. 

$ sudoedit XTerm-color.erb - muokkasin sen sisältöä, "background and foreground colors" 

$ sudo puppet apply -e 'file {"xtermcolors":}' - ajoin komennon.

mutta ei se kuitenkaan toiminut.... lopputulos näytti seuraavalta:  

Screenshot_2017-04-11_10-14-02





