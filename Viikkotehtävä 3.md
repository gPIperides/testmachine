# Palvelinten Hallinta Viikkotehtävä 3 

Alotin tehtävän seuraamalla Tero Karvisen ohjeita 

Tässä postauksessa raportoin Tero Karvinen Palvelinten Hallinta Kurssia Viikkotehtävä 3 

Käyttämäni tietokone on ASUS R571GD-BQ132T läppäri. Tein tehtävät Virtuaalikoneella, Virtualboxissa oli Xubuntu 18.04 LTS käyttöjärjestelmänä. 

Alotin tehtävän ottamalla suomi-näppäimistön käyttöön komennolla 

##### –setxkbmap fi 

Seuraavakasi päivitin käyttöjärjestelmän komennolla 

##### -sudo apt-get update 

sekä 

##### -sudo apt-get upgrade 

##### -sudo ufw enable 

 

## h3 Versionhallinta 

a) MarkDown. Tee tämän tehtävän raportti MarkDownina. Helpointa on tehdä raportti GitHub-varastoon, jolloin md-päätteiset tiedostot muotoillaan automaattisesti. Tyhjä rivi tekee kappalejaon, risuaita ‘#’ tekee otsikon, sisennys merkitsee koodinpätkän. 

 

d) Näytä omalla git-varastollasi esimerkit komennoista ‘git log’, ‘git diff’ ja ‘git blame’. Selitä tulokset. 

 

e) Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset –hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia. 

 

f) Tee uusi salt-moduli. Voit asentaa ja konfiguroida minkä vain uuden ohjelman: demonin, työpöytäohjelman tai komentokehotteesta toimivan ohjelman. Käytä tarvittaessa ‘find -printf “%T+ %p\n”|sort’ löytääksesi uudet asetustiedostot. (Tietysti eri ohjelma kuin aiemmissa tehtävissä, tarkoitushan on harjoitella Salttia) 

 

## a)

 Alotin tehtävän seuraamalla Tero Karvisen ohjeita. (http://terokarvinen.com/2020/configuration-managment-systems-palvelinten-hallinta-ict4tn022-spring-2020/#h3-versionhallinta). Kirjauduin Githubin omilla tunnuksilla ja menin luomaan uuden Repositoryn.

![alt text](https://github.com/gPIperides/testmachine/blob/master/repesotiry%20creation.PNG)

![alt text](https://github.com/gPIperides/testmachine/blob/master/git%20usage.PNG)

![alt text](https://github.com/gPIperides/testmachine/blob/master/started%20a%20readme.PNG)

Kloonasin tämän xubuntuun komennolla "git clone https://github.com/gPIperides/testmachine"

Määrittelen tässä vaiheessa käyttäjätiedot jotta kaikki toimisi hyvin.

$ git config --global user.email xxxx

$ git config --global user.name "gpiperides"

$ git config --global credential.helper "cache --timeout=3600"

Nyt siirretään tämä .md tiedosto miejän repoon ja käytetään komentoa :

-git add . && git commit; git pull && git push

Näin tiedostot siirtyvät minun kotikoneeni kotikansiosta suoraan GitHubiin.

## b)

#### Git Log :

Tämä komento näyttää kaikki repoon ajetut muutokset ja commitit. Jokaisesta commitista näkyy commitin token, commitin ajaja, commitin aika ja commitin ajajan kommentti, tässä esimerkkinä kun aloitin kirjoittamaan raporttia koneen kansiosta.

#### Git Diff:

Tämä komentoo kertoo mitä muutoksia on tehty ja mikä on paikallisen hakemiston ja repon ero. Tässä tapauksessa loin muutaman muutoksen readme tiedostoon,

#### Git Blame:

Tämä komento on juuri sitä mitä se on. Tällä voi katsoa kuka on kirjoittanut minkäkin rivin tiedostoon. Tässä esimerkkinä minun muutokseni readme tiedostoon.

#### c) Git Reset --hard:

Muutoksen peruminen hakemistosta ennen committia.



#### d) Moduuli

Loin uuden kansion komennolla 

#####  -sudo mkdir /srv/salt/cmatrix/

Loin kansion sisälle tekstitiedoston cmatrix.init mihin annoin määrityksen asentaa tämän ohjelman.

##### cmatrix:

#####    pkg.installed  

Sitten ajoin tämän moduulin minioneille komennolla 

##### sudo salt '*'  state.apply cmatrix

 ja asennus onnistui. 



## Lähteet

http://terokarvinen.com/2016/publish-your-project-with-github

https://github.com/terokarvinen/sirotin

http://terokarvinen.com/2012/git-from-offline-to-network

https://guides.github.com/features/mastering-markdown/

https://github.com/KakoMirai/palvhallintaharj3/



