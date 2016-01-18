Handleidingen receiver
=============

1. [Opstarten laptop en inloggen](#opstarten-laptop-en-inloggen)
1. [Een encrypted persistent volume aanmaken](#een-encrypted-persistent-volume-aanmaken)
1. [Het aanmaken van een PGP sleutelpaar](#pgp-versleuteling-van-bestanden)
1. [Het publieke deel van de PGP key in Publeaks zetten](#het-publieke-deel-van-de-pgp-key-in-publeaks-zetten)
1. [Ophalen van een tip](#ophalen-van-een-tip)
1. [Decrypten van een toegezonden bestand](#decrypten-van-een-toegezonden-bestand)
1. [Metadata verwijderen van bestanden](#metadata-verwijderen-van-bestanden)

[Terug naar de inhoudsopgave](README.md#inhoudsopgave)

***

## Opstarten laptop en inloggen

Steek eerst de USB-stick met de Linux versie 'Tails' in de laptop en zet daarna pas de laptop aan.

De eerste keer dat de laptop wordt opgestart ziet het login scherm eruit zoals hieronder. Er is dan nog geen persistent volume.

Klik dan op _Login_ om in te loggen.

Als er wel een persistent volume is aangemaakt ziet het login scherm eruit zoals hieronder. Je kunt dan een wachtwoord invoeren om toegang te krijgen tot de persistent volume. (Hoe je een persistent volume aanmaakt staat beschreven in de volgende stap.) ￼￼￼￼￼￼￼￼

￼￼￼￼￼￼￼￼￼Klik onder _Use persistence?_ op Yes en voer daarna het wachtwoord van de persistent volume in.

Klik daarna op _Login_ om in te loggen.

## Een encrypted persistent volume aanmaken

Standaard bewaard Tails geen gegevens, alles wat er op de laptop wordt gedaan, wordt vergeten en verwijderd als deze wordt afgesloten. Voor het gebruik met Publeaks willen we ook bestanden kunnen bewaren en in elk geval moet de PGP sleutel ergens worden opgeslagen.

Daarom wordt er allereerst een encrypted persistent volume op de USB-stick aangemaakt. Dit is een versleutelde plek op de USB-stick waar veilig data kan worden opgeslagen.

Start de laptop en log in.

Start _Configure persistent volume_

Voer tweemaal een goede wachtzin in en klik op _Create_

Selecteer de volgende onderdelen:
* Personal Data
* GnuPG
* GNOME Keyring
* Network Connections
* Browser bookmarks

Klik daarna op _Save_.

Sluit vervolgens dit programma af door op het kruisje te klikken **en start de laptop opnieuw op**.

Na opnieuw opstarten krijgt u het eerder getoonde inlogscherm waarin u kunt kiezen voor de persistent volume.

## Het aanmaken van een PGP sleutelpaar

Om bestanden veilig op de server op te slaan worden deze voordat ze worden opgeslagen eerst met behulp van PGP versleuteld. Om dat te kunnen doen moeten de gebruikers van Publeaks natuurlijk wel een PGP sleutel hebben. Daarom wordt hier uitgelegd hoe een PGP sleutelpaar kan worden aangemaakt.

**N.B. Zorg dat je bent ingelogd met _Use persistence?_ op _Yes_!**

Start _Passwords and Keys_

Klik op _File_ en dan _New_

Klik _PGP Key_ en dan _Continue_

Klik op _Advanced key options_

Vul de volgende gegevens in en klik _Create_:
* **Full Name** Je volledige naam of naam van het medium
* **Email Address** Het e-mail adres dat je voor Publeaks gebruikt
* Zet de **Key Strength** op 4096
* Zet de **Expiration Date** op één jaar in de toekomst

Vul een goede passphrase in en klik _OK_

Het genereren van de keys kan soms lang duren.

De aangemaakte keys zijn te vinden onder _GnuPG keys_

## Het publieke deel van de PGP key in Publeaks zetten

Om op de server bestanden te versleutelen, moeten de publieke sleutels beschikbaar zijn. Hieronder wordt uitgelegd hoe het publieke deel van het PGP sleutelpaar kan worden geüpload.

Start _Passwords and Keys_ (als deze niet meer actief is) en selecteer jouw _Personal PGP key_

Klik _File_ en dan _Export_

Selecteer de map _amnesia_

Verander rechtsonder de setting naar _Armored PGP keys_

Klik daarna op _Export_

Dubbelklik _home_ op de desktop

Rechtermuisklik op de eerder geëxporteerde key en open het bestand met _gedit Text Editor_

Kopieer **alle** tekst in gedit inclusief -----BEGIN PGP PUBLIC KEY BLOCK----- en -----END PGP PUBLIC KEY BLOCK-----
Start op de laptop de browser en ga naar https://secure.publeaks.nl

Log in door te klikken op _Login pagina_ en je gebruikersnaam en wachtwoord in te voeren.

**N.B. De inlog-link is in voorbereiding op de herziening van de website komen te vervallen. Gebruik https://secure.publeaks.nl/#/login om in te loggen.**

Klik op _Voorkeuren_

Klik op het tabblad _Encryptie instellingen_ en klik op CONFIGUREER EEN PGP SLEUTEL

Plak de eerder gekopieerde public PGP key in het veld.

N.B. Als het veld reeds een PGP key bevat, verwijder deze dan eerst voor de eigen key te plakken.

Klik daarna op _UPDATE NOTIFICATIE EN ENCRYPTIE INSTELLINGEN_

## Ophalen van een tip

Start op de laptop de browser en ga naar https://secure.publeaks.nl

Log in door te klikken op _Login pagina_ en je gebruikersnaam en wachtwoord in te voeren.

**N.B. De inlog-link is in voorbereiding op de herziening van de website komen te vervallen. Gebruik https://secure.publeaks.nl/#/login om in te loggen.**

Nadat je bent ingelogd toont de website de verschillende tips die je hebt ontvangen.

Klik op het getal dat onder _Toegang_ staat om de desbetreffende tip te bekijken.

Uitleg van de verschillende kolommen:

* **Aantal bezoekers** Het aantal maal dat deze tip door die media organisatie is bekeken.
* **Werk** De datum waarop de tip is ingediend.
* **Laatste bezoek** De datum waarop je de tip voor het laatst hebt bekeken.
* **Voorbeeld** Korte informatie over de inhoud van de tip.
* **Bestanden** Het aantal bestanden dat in de tip is geüpload.

Op de statusoverzicht pagina staat alle relevant informatie over de ingezonden tip:

* **Categorie** details Op dit moment is er slechts één categorie.
* **Korte titel** De titel die de tipgever aan upload heeft gegeven.
* **Omschrijving bestanden** Omschrijving van de bestanden door de tipgever.
* **Volledige omschrijving** Omschrijving van de tip door de tipgever.
* **Bestanden** De bestanden die de tipgever heeft gestuurd en hoe vaak ze zijn gedownload.  
N.B. Bestanden kunnen maximaal 3 keer worden gedownload.
* **Reacties** Een lijst van reacties van zowel de journalisten als van de tipgever.  
Een reactie geven kan door in het lege veld te schrijven en te klikken op Voeg een commentaar toe.  
N.B. De tipgever krijgt geen meldingen, hij moet zelf kijken of er (nieuwe) berichten zijn.  
N.B. Niet alleen de tipgever, maar ook de andere ontvangers kunnen deze reacties lezen.
* **Lijst ontvangers** Een overzicht van welke media deze tip hebben ontvangen en hoe vaak die desbetreffende media de tip hebben bekeken.

## Decrypten van een toegezonden bestand

Download het bestand dat je wilt decrypten en sla dit op je laptop op in de map _Persistant_.

N.B. Bestanden die niet in de map _Persistant_ worden opgeslagen verdwijnen als de laptop wordt herstart.

Open de filebrowser, bijvoorbeeld door op de map _Home_ op de desktop te klikken.

N.B. De bestanden die encrypt zijn met PGP hebben meestal de extensie .pgp, maar dat hoeft niet het geval te zijn.

Rechtermuisklik op het bestand dat je wilt decrypten.

Voer het wachtzin van je PGP-key in en klik op _OK_.

Kies eventueel de locatie waar je het gedecrypte bestand op wilt slaan.

## Metadata verwijderen van bestanden

In bestanden staat vaak metadata over de gebruiker die het bestand heeft gemaakt of bewerkt. Deze gegevens zouden mogelijkheid de identiteit van de tipgever kunnen verraden. Daarom is het verstandig om de metadata en andere herkenbare informatie van bestanden eerst te verwijderen voordat ze elders, buiten deze versleutelde laptops, worden gebruikt.

N.B. Dat een bestand geen metadata meer bevat, betekent natuurlijk niet dat de inhoud van het bestand niet alsnog de identiteit van de tipgever kan verraden.

Let daarom ook op mogelijke (onzichtbare) watermerken in de documenten. Het gaat hier te ver om uitgebreid op watermerken in te gaan, maar wees bewust van het bestaan en wees voorzichtig.
