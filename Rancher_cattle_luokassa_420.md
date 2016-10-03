### Virtuaalikoiden liittäminen osaksi Rancher cattleä.



Työn tarkoituksena oli selvittää voidaanko luokan koneilla liittyä Rancher ympäristöön ja toimivatko ne moitteettomasti.



### Toteutus

Aluksi rakennettiin virtuaalikoneen image Ubuntu 14.04:sta, johon lisättiin tarvittavat scriptit Rancher cattleen liittymistä varten.

Työ toteutettiin luokassa 420, jossa sijaitsee 13kpl Windows-konetta. Labranetin koneissa on oletuksena asennettu Oraclen Virtualbox.

Koneisiin kirjauduttiin Vierailija tunnuksilla.

Koneilla ladattiin aikaisemmin tehty image ja käynnistettiin se.

Virtualboxin network asetuksista on valittava bridged network.

Virtuaalikoneet liittyivät moitteettomasti osaksi Rancher pilveä ja saivat yhteyden myös toisiinsa.

Hostien välisiä yhteyksiä testattiin käyttämällä toimivaksi todettua WordPress konttia.

Virtuaalikoneet liittyivät osaksi cattleä ilman ongelmia ja kommunikoivat keskenään ongelmitta.



### Havaitut ongelmat

Koneet menevät lepotilaan 30min kuluessa viimeisestä komennosta, jolloin yhteys virtuualikoneen ja Rancher masterin välillä katkeaa ja hostit näkyvät reconnecting tilassa. Kun koneille kirjautuu uudestaan sisään niin virtuaalikone saa jälleen yhteyden masteriin. 

Hostit kannattaa poistaa  Rancher cattlesta käyttäen masterin selaimella toimivaa interfacea eikä vaan sammuttaa virtuaalikonetta. Rancherin UI menee aivan jumiin kun se yrittää reconnectaa useampaa virtuaalikonetta, joita ei ole enään olemassa.



### Yhteenveto

Virtuaalikoneet toimivat moitteemmasti Labranetissä sijaitsevassa Rancher cattlessä. Labranet ei rajoita niiden portteja eikä yhteyksiä toisiinsa. 

Virtuaalikoneet ovat aika heikkotehoisia, mutta soveltuvat mainiosti pieneen demoon ja testaamiseen.



### Kuvia

![] (http://i.imgur.com/ZRxbeRN.jpg)

![] (http://i.imgur.com/W2SWiaR.jpg)
