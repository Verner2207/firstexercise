Viidentenä harjoituksena piti tehdä moduuli git-varastoon sekä kirjoittaa
sinne raportti MarkDownin avulla.Ajattelin, että tallentaisin repositorioon
moduulin, joka asentaa apachen live-ubuntu tilassa(eli vaaditaan attribuutti
allowcdrom => true).Käytin harjoituksessa linux-tietokonettani, jossa on 
Ubuntu 16.04.1 LTS i386(32-bit) – käyttöjärjestelmä.
Aloitin tehtävän 17:40 7.11.2016.

##Git

Latasin gitin terminaalissa komennolla sudo apt-get install git.
Sen jälkeen loin repositorion sivustolla www.github.com.
Teminaalissa loin kotihakemistoon kansion gitille komennolla mkdir villesgits.
Tämän jälkeen muutin paikallisia git tiedostoja seuraavilla komennoilla
git config --global user.email "sähköpostiosoitteeni"
git config --global user.name "Ville Salama"
Sitten latasin luomani repositorion omalle linux tietokoneelleni
käyttämällä HTTPS-kloonausmenetelmää.
Menin aikaisemmin luomaani hakemistoon nimeltä villesgits ja kirjoitin
komennon, jolla kloonasin repositorion villesgits hakemistoon:
git clone https://github.com/Verner2207/firstexercise.git

Sain tulosteeksi seuraavaa:

Cloning into 'firstexercise'...
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
Checking connectivity... done.
salama@ville:~/villesgits$ 

Kirjoitin komennon ls, jonka jälkeen näin, että repositorio oli siirtynyt 
linux-koneelleni. 

##Moduulin luonti

Menin firstexercise-hakemistoon(kloonattu repositorio) ja tein sinne
uuden kansion komennolla mkdir modules. Modules-hakemistoon taas loin
manifests-kansion(nämä kansiot sisältävät moduulin.) Manifests-kansion
sisälle loin init.pp tiedoston komennolla nano init.pp, ja sen sisällöksi
tuli seuraavaa:

class firstexercise{
 package {"apache2":
 ensure => "installed", 
 allowcdrom => "true",
 }
}

##Repositorion tallentaminen

Moduulin luonnin jälkeen käytin komentoa:
git add . && git commit; git pull && git push, jonka avulla tallensin
muokkaukset repositorioon sekä koneelleni että githubiin. Avautui ikkuna,
johon laitetaan commit message-tiedostoon muokkauksen tiedot(tässä tapauksessa
kirjoitin mitä muokkasin repositoriossa):

First exercise module
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch master
# Your branch is up-to-date with 'origin/master'.
#
# Changes to be committed:
# new file: init.pp
#

Sen jälkeen minulta kysyttiin terminaalissa käyttäjätunnus ja salasana
github-tililleni:

Username for 'https://github.com': Verner2207
Password for 'https://Verner2207@github.com': 
Counting objects: 5, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (5/5), 472 bytes | 0 bytes/s, done.
Total 5 (delta 0), reused 0 (delta 0)
To https://github.com/Verner2207/firstexercise.git
 88ce33a..da874a8 master -> master
salama@ville:~/villesgits/firstexercise/modules/manifests$ 

Menin githubiin ja päivitin nettisivun. Tiedostot olivat päivittyneet
repositoriooni.

