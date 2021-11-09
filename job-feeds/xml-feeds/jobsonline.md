---
description: Linkedin XML Feed
---

# Jobsonline

## Documentatie aanlevering vacatures - met koppeling aan werkgever

**Website: https://www.jobsonline.nl/**

### Voorbeeld XML-bestand

_Onderaan dit document vindt u een voorbeeld XML-bestand zonder commentaar_

\<?xml version="1.0" encoding="UTF-8"?>

\<jobs>

&#x20;   \<job>                                                                                                                                                                                            start vacature

&#x20;       \<employerkey>4c6ccf26-xxx\</employerkey>\
&#x20;                                                                                                                                                               feedkey werkgever, zie 'Werkgevers' \*

&#x20;       \<id>24823749\</id>                                                                                                                                                       unieke referentie

&#x20;       \<producttype>top\</producttype>                                                                                          type vacature, zie 'Vacaturetypes' \*

&#x20;       \<title>Media Adviseur Sales - New business\</title>                                                                                 titel van de vacature \*

&#x20;       \<careerlevels>                                                                                                                                                                 carriereniveau(s)

&#x20;           \<careerlevel>2\</careerlevel>                                                                                                                                              id uit lijst

&#x20;           \<careerlevel>5\</careerlevel>                                                                                                                                              id uit lijst

&#x20;       \</careerlevels>

&#x20;       \<educations>                                                                                                                                                               opleidingsniveau(s)

&#x20;           \<education>2\</education>                                                                                                                                                  id uit lijst

&#x20;           \<education>5\</education>                                                                                                                                                  id uit lijst

&#x20;       \</educations>

&#x20;       \<functiongroups>                                                                                                                                                           functiegroep(en)

&#x20;           \<functiongroup>2\</functiongroup>                                                                                                                                 id uit lijst

&#x20;           \<functiongroup>5\</functiongroup>                                                                                                                                 id uit lijst

&#x20;       \</functiongroups>

&#x20;       \<industries>                                                                                                                                                                                 branche(s)

&#x20;           \<industry>2\</industry>                                                                                                                                                         id uit lijst

&#x20;           \<industry>5\</industry>                                                                                                                                                         id uit lijst

&#x20;       \</industries>

&#x20;       \<employmentcontracts>                                                                                                                                           dienstverband(en)

&#x20;           \<employmentcontract>2\</employmentcontract>                                                                                                      id uit lijst

&#x20;           \<employmentcontract>5\</employmentcontract>                                                                                                      id uit lijst

&#x20;       \</employmentcontracts>

&#x20;       \<workinghours>                                                                                                                                                                   uren per week

&#x20;           \<workinghours>2\</workinghours>                                                                                                                                   id uit lijst

&#x20;           \<workinghours>5\</workinghours>                                                                                                                                   id uit lijst

&#x20;       \</workinghours>

&#x20;       \<salarylevel>2\</salarylevel>                                                                                                                        salarisindicatie, id uit lijst

&#x20;       \<visibility>

&#x20;           \<visibilitytype>city\</visibilitytype>\
&#x20;                                                                                                                                                                      zichtbaarheid, zie "Verspreiding" \*

&#x20;           \<country>1\</country>                                                                                                                                              land, id uit lijst \*

&#x20;           \<city>661\</city>                                                                                                                                                      plaats, id uit lijst \*

&#x20;       \</visibility>

&#x20;       \<keywords>                                                                                                                                                                              trefwoorden

&#x20;           \<keyword>\<!\[CDATA\[media]]>\</keyword>

&#x20;           \<keyword>\<!\[CDATA\[adviseur]]>\</keyword>

&#x20;       \</keywords>

&#x20;       \<startdatetext>date\</startdatetext>                                                                                   tekst startdatum, zie "Startdatum" \*

&#x20;       \<startdate>2018-01-12\</startdate>                                                                                              startdatum, zie "Startdatum" \*

&#x20;       \<introtext>\<!\[CDATA\[                                                                                                                            introtekst (max 170 karakters)

&#x20;           Als Media-adviseur.....]]>

&#x20;       \</introtext>

&#x20;       \<description>\<!\[CDATA\[                                                                                                                                                     vacaturetekst

&#x20;           \<p>\<strong>In deze uitdagende functie...........\</strong>\</p>]]>

&#x20;       \</description>

&#x20;       \<applylink>http://www.company.com/job1.html>\</applylink>\
&#x20;                                                                                                                                                                                     sollicitatielink (URL/e-mail)

&#x20;       \<trackingpixelurl>http://www.company.com/track/234o2i4ji/\</trackingpixelurl>\
&#x20;                                                                                                                                                                                                    URL tracking pixel

&#x20;   \</job>                                                                                                                                                                                         einde vacature

&#x20;   \<job>                                                                                                                                                                                            start vacature

&#x20;       .....

&#x20;   \</job>                                                                                                                                                                                         einde vacature

\</jobs>

&#x20;

\* verplicht veld

### Werkgevers

U koppelt de vacature aan een **bestaand Jobsonline werkgeversaccount** door in het veld "employerkey" de feedkey van de werkgever mee te sturen. De feedkey is op te vragen bij Jobsonline.

### Vacaturetypes

Mogelijke types:

* basic: basis vacature
* top: top vacature
* premium: premium vacature
* professional: professional vacature

### Zichtbaarheid

U kunt kiezen in welk verspreidingsgebied de vacature wordt getoond:

* city: in een plaats (vul veld 'city' in)
* regio: in een regio (vul een 'region' id in)
* province: in een of meer provincies (vul één of meer 'province' id's in)
* countrywide: landelijk

In alle gevallen moet 'country' worden ingevuld invullen.

_Let op: de volgorde waarin vacatures worden getoond in de zoekresultaten wordt bepaald door de nauwkeurigheid van de locatie. Hoe specifieker u de locatie opgeeft, hoe hoger de vacature in de zoekresultaten verschijnt en hoe meer views uw vacature krijgt._

### Startdatum

Voor het weergeven van de startdatum van de functie heeft u de keuze uit de volgende opties (voor 'startdatetext'):

* direct: weergegeven als 'Per direct'
* asap: weergegeven als 'Zo spoedig mogelijk'
* inconsultation: weergegeven als 'In overleg'
* date: toont de datum die ingevuld is in het 'startdate' veld

Het veld 'startdate' dient alleen te worden ingevuld wanneer bij 'startdatetext' de waarde 'date' ingevuld is.

&#x20;

#### Voorbeeld zichtbaarheid op plaats

&#x20;       \<visibility>

&#x20;           \<visibilitytype>city\</visibilitytype>

&#x20;           \<country>1\</country>                                                                                                                                                           id uit lijst

&#x20;           \<city>661\</city>                                                                                                                                                                      id uit lijst

&#x20;       \</visibility>

&#x20;

#### Voorbeeld zichtbaarheid op regio

&#x20;       \<visibility>

&#x20;           \<visibilitytype>region\</visibilitytype>

&#x20;           \<country>1\</country>                                                                                                                                                           id uit lijst

&#x20;           \<regions>

&#x20;               \<region>3\</region>                                                                                                                                                            id uit lijst

&#x20;           \</regions>

&#x20;       \</visibility>

&#x20;

#### Voorbeeld zichtbaarheid op provincie

&#x20;       \<visibility>

&#x20;           \<visibilitytype>province\</visibilitytype>

&#x20;           \<country>1\</country>                                  Documentatie aanlevering vacatures - met koppeling aan werkgever

**Website: https://www.jobsonline.nl/**

### Voorbeeld XML-bestand

_Onderaan dit document vindt u een voorbeeld XML-bestand zonder commentaar_

\<?xml version="1.0" encoding="UTF-8"?>

\<jobs>

&#x20;   \<job>                                                                                                                                                                                            start vacature

&#x20;       \<employerkey>4c6ccf26-xxx\</employerkey>\
&#x20;                                                                                                                                                               feedkey werkgever, zie 'Werkgevers' \*

&#x20;       \<id>24823749\</id>                                                                                                                                                       unieke referentie

&#x20;       \<producttype>top\</producttype>                                                                                          type vacature, zie 'Vacaturetypes' \*

&#x20;       \<title>Media Adviseur Sales - New business\</title>                                                                                 titel van de vacature \*

&#x20;       \<careerlevels>                                                                                                                                                                 carriereniveau(s)

&#x20;           \<careerlevel>2\</careerlevel>                                                                                                                                              id uit lijst

&#x20;           \<careerlevel>5\</careerlevel>                                                                                                                                              id uit lijst

&#x20;       \</careerlevels>

&#x20;       \<educations>                                                                                                                                                               opleidingsniveau(s)

&#x20;           \<education>2\</education>                                                                                                                                                  id uit lijst

&#x20;           \<education>5\</education>                                                                                                                                                  id uit lijst

&#x20;       \</educations>

&#x20;       \<functiongroups>                                                                                                                                                           functiegroep(en)

&#x20;           \<functiongroup>2\</functiongroup>                                                                                                                                 id uit lijst

&#x20;           \<functiongroup>5\</functiongroup>                                                                                                                                 id uit lijst

&#x20;       \</functiongroups>

&#x20;       \<industries>                                                                                                                                                                                 branche(s)

&#x20;           \<industry>2\</industry>                                                                                                                                                         id uit lijst

&#x20;           \<industry>5\</industry>                                                                                                                                                         id uit lijst

&#x20;       \</industries>

&#x20;       \<employmentcontracts>                                                                                                                                           dienstverband(en)

&#x20;           \<employmentcontract>2\</employmentcontract>                                                                                                      id uit lijst

&#x20;           \<employmentcontract>5\</employmentcontract>                                                                                                      id uit lijst

&#x20;       \</employmentcontracts>

&#x20;       \<workinghours>                                                                                                                                                                   uren per week

&#x20;           \<workinghours>2\</workinghours>                                                                                                                                   id uit lijst

&#x20;           \<workinghours>5\</workinghours>                                                                                                                                   id uit lijst

&#x20;       \</workinghours>

&#x20;       \<salarylevel>2\</salarylevel>                                                                                                                        salarisindicatie, id uit lijst

&#x20;       \<visibility>

&#x20;           \<visibilitytype>city\</visibilitytype>\
&#x20;                                                                                                                                                                      zichtbaarheid, zie "Verspreiding" \*

&#x20;           \<country>1\</country>                                                                                                                                              land, id uit lijst \*

&#x20;           \<city>661\</city>                                                                                                                                                      plaats, id uit lijst \*

&#x20;       \</visibility>

&#x20;       \<keywords>                                                                                                                                                                              trefwoorden

&#x20;           \<keyword>\<!\[CDATA\[media]]>\</keyword>

&#x20;           \<keyword>\<!\[CDATA\[adviseur]]>\</keyword>

&#x20;       \</keywords>

&#x20;       \<startdatetext>date\</startdatetext>                                                                                   tekst startdatum, zie "Startdatum" \*

&#x20;       \<startdate>2018-01-12\</startdate>                                                                                              startdatum, zie "Startdatum" \*

&#x20;       \<introtext>\<!\[CDATA\[                                                                                                                            introtekst (max 170 karakters)

&#x20;           Als Media-adviseur.....]]>

&#x20;       \</introtext>

&#x20;       \<description>\<!\[CDATA\[                                                                                                                                                     vacaturetekst

&#x20;           \<p>\<strong>In deze uitdagende functie...........\</strong>\</p>]]>

&#x20;       \</description>

&#x20;       \<applylink>http://www.company.com/job1.html>\</applylink>\
&#x20;                                                                                                                                                                                     sollicitatielink (URL/e-mail)

&#x20;       \<trackingpixelurl>http://www.company.com/track/234o2i4ji/\</trackingpixelurl>\
&#x20;                                                                                                                                                                                                    URL tracking pixel

&#x20;   \</job>                                                                                                                                                                                         einde vacature

&#x20;   \<job>                                                                                                                                                                                            start vacature

&#x20;       .....

&#x20;   \</job>                                                                                                                                                                                         einde vacature

\</jobs>

&#x20;

\* verplicht veld

### Werkgevers

U koppelt de vacature aan een **bestaand Jobsonline werkgeversaccount** door in het veld "employerkey" de feedkey van de werkgever mee te sturen. De feedkey is op te vragen bij Jobsonline.

### Vacaturetypes

Mogelijke types:

* basic: basis vacature
* top: top vacature
* premium: premium vacature
* professional: professional vacature

### Zichtbaarheid

U kunt kiezen in welk verspreidingsgebied de vacature wordt getoond:

* city: in een plaats (vul veld 'city' in)
* regio: in een regio (vul een 'region' id in)
* province: in een of meer provincies (vul één of meer 'province' id's in)
* countrywide: landelijk

In alle gevallen moet 'country' worden ingevuld invullen.

_Let op: de volgorde waarin vacatures worden getoond in de zoekresultaten wordt bepaald door de nauwkeurigheid van de locatie. Hoe specifieker u de locatie opgeeft, hoe hoger de vacature in de zoekresultaten verschijnt en hoe meer views uw vacature krijgt._

### Startdatum

Voor het weergeven van de startdatum van de functie heeft u de keuze uit de volgende opties (voor 'startdatetext'):

* direct: weergegeven als 'Per direct'
* asap: weergegeven als 'Zo spoedig mogelijk'
* inconsultation: weergegeven als 'In overleg'
* date: toont de datum die ingevuld is in het 'startdate' veld

Het veld 'startdate' dient alleen te worden ingevuld wanneer bij 'startdatetext' de waarde 'date' ingevuld is.

&#x20;

#### Voorbeeld zichtbaarheid op plaats

&#x20;       \<visibility>

&#x20;           \<visibilitytype>city\</visibilitytype>

&#x20;           \<country>1\</country>                                                                                                                                                           id uit lijst

&#x20;           \<city>661\</city>                                                                                                                                                                      id uit lijst

&#x20;       \</visibility>

&#x20;

#### Voorbeeld zichtbaarheid op regio

&#x20;       \<visibility>

&#x20;           \<visibilitytype>region\</visibilitytype>

&#x20;           \<country>1\</country>                                                                                                                                                           id uit lijst

&#x20;           \<regions>

&#x20;               \<region>3\</region>                                                                                                                                                            id uit lijst

&#x20;           \</regions>

&#x20;       \</visibility>

&#x20;

#### Voorbeeld zichtbaarheid op provincie

&#x20;       \<visibility>

&#x20;           \<visibilitytype>province\</visibilitytype>

&#x20;           \<country>1\</country>                              id uit lijst                                                                                                                            &#x20;

&#x20;           \<provinces>

&#x20;               \<province>3\</province>                      id uit lijst                                                                                                                          &#x20;

&#x20;           \</provinces>

&#x20;       \</visibility>

&#x20;

#### Voorbeeld zichtbaarheid landelijk

&#x20;       \<visibility>

&#x20;           \<visibilitytype>countrywide\</visibilitytype>

&#x20;           \<country>1\</country>

&#x20;       \</visibility>

### Lijsten

#### Carriereniveau

Veldnaam in XML:  careerlevel

&#x20;

\


&#x20;     1           Geen ervaring

&#x20;     2           Starter

&#x20;     3           Ervaren

&#x20;     4           Leidinggevend

&#x20;     5           Senior management

&#x20;     6           Directie

\


&#x20;

#### Opleiding

Veldnaam in XML:  education

&#x20;

\


&#x20;     1           Postdoctoraal

&#x20;     2           WO

&#x20;     3           HBO

&#x20;     4           MBO

&#x20;     5           VWO

&#x20;     6           HAVO

&#x20;     7           VMBO/Mavo

&#x20;     8           LBO

&#x20;     9           Lagere school

\


&#x20;

#### Functiegroep

Veldnaam in XML:  functiongroup

&#x20;

\


&#x20;     3           Administratief/Secretarieel

&#x20;     4           Automatisering/Internet

&#x20;     5           Beleid/Bestuur/Staf

&#x20;     6           Beveiliging/Defensie/Politie

&#x20;   17           Callcenter/Receptie

&#x20;     7           Commercieel/Verkoop

&#x20;     8           Consultancy/Advies

&#x20;     9           Design/Creatie/Journalistiek

&#x20;   10           Directie/Management

&#x20;   11           Financieel/Accounting

&#x20;   12           Financiële dienstverlening

&#x20;   13           Horeca/Detailhandel

&#x20;   14           HR/Training/Opleiding

&#x20;   15           Inkoop/Logistiek/Transport

&#x20;   16           Juridisch

&#x20;   18           Marketing/Communicatie

&#x20;   19           Medisch/Verzorging

&#x20;   20           Onderwijs/Wetenschap

&#x20;   21           Overig

&#x20;   22           Productie/Uitvoerend

&#x20;   23           Techniek

\


&#x20;

#### Branche

Veldnaam in XML:  industry

&#x20;

\


&#x20;     1           Accountancy

&#x20;     2           Advies/Consultancy

&#x20;     3           Afval en milieu

&#x20;     4           Automotive

&#x20;     5           Banken/Financiële dienstverlening

&#x20;     6           Beveiliging/Bewaking

&#x20;     7           Bouw/Installatie

&#x20;     8           Chemie/Petrochemie

&#x20;     9           Detailhandel

&#x20;   10           Elektronica

&#x20;   11           Energie/Gas/Water

&#x20;   12           Facilitaire dienstverlening

&#x20;   13           Farmacie

&#x20;   14           FMCG

&#x20;   15           Gezondheidszorg/Welzijn

&#x20;   16           Handel/Groothandel

&#x20;   17           Horeca

&#x20;   18           ICT

&#x20;   19           Industrie/Metaal

&#x20;   20           Internet

&#x20;   21           Juridische dienstverlening

&#x20;   22           Kunst/Cultuur

&#x20;   23           Agri/Landbouw/Visserij

&#x20;   24           Makelaardij/Vastgoed

&#x20;   25           Maritiem

&#x20;   26           Media/Uitgeverijen/TV

&#x20;   27           Mode/Textiel/Cosmetica

&#x20;   28           Onderwijs/Opleiding

&#x20;   29           Overheid/Non-profit

&#x20;   30           Overig

&#x20;   31           Personen vervoer

&#x20;   32           Reclame/PR/Communicatie

&#x20;   33           Sport/Recreatie/Toerisme

&#x20;   34           Techniek

&#x20;   35           Telecom

&#x20;   36           Transport/Distributie

&#x20;   37           Uitzend/Detachering/W\&S

&#x20;   38           Verzekeringen/Assurantiën

&#x20;   39           Zakelijke Dienstverlening

\


&#x20;

#### Dienstverband

Veldnaam in XML:  employmentcontract

&#x20;

\


&#x20;     1           Vast

&#x20;     2           Tijdelijk

&#x20;     3           Freelance/ZZP

&#x20;     4           Interim

&#x20;     5           Leer-werk overeenkomst

&#x20;     6           Thuiswerk

&#x20;     7           Vakantiewerk

&#x20;     8           Vrijwilliger

&#x20;     9           Bijbaan

&#x20;   10           Stage

\


&#x20;

#### Uren per week

Veldnaam in XML:  workinghours

&#x20;

\


&#x20;     1           0 tot 8 uur

&#x20;     2           8 tot 16 uur

&#x20;     3           16 tot 24 uur

&#x20;     4           24 tot 32 uur

&#x20;     5           32 tot 40 uur

&#x20;     8           In overleg

&#x20;     6           Parttime

&#x20;     7           Fulltime

\


&#x20;

#### Salarisindicatie

Veldnaam in XML:  salarylevel

&#x20;

\


&#x20;     1           0 - 1750 euro

&#x20;     2           1750 - 2500 euro

&#x20;     3           2500 - 3500 euro

&#x20;     4           3500 - 5000 euro

&#x20;     5           5000+ euro

&#x20;     6           In overleg

&#x20;     7           Marktconform

\


&#x20;

#### Land

Veldnaam in XML:  country

&#x20;

\


&#x20;     1           Nederland

&#x20;     2           België

&#x20;     3           Duitsland

&#x20;     4           Frankrijk

&#x20;     5           Oostenrijk

&#x20;     6           Luxemburg

&#x20;     7           Zwitserland

\


&#x20;Documentatie aanlevering vacatures - met koppeling aan werkgever

**Website: https://www.jobsonline.nl/**

### Voorbeeld XML-bestand

_Onderaan dit document vindt u een voorbeeld XML-bestand zonder commentaar_

\<?xml version="1.0" encoding="UTF-8"?>

\<jobs>

&#x20;   \<job>                                                                                                                                                                                            start vacature

&#x20;       \<employerkey>4c6ccf26-xxx\</employerkey>\
&#x20;                                                                                                                                                               feedkey werkgever, zie 'Werkgevers' \*

&#x20;       \<id>24823749\</id>                                                                                                                                                       unieke referentie

&#x20;       \<producttype>top\</producttype>                                                                                          type vacature, zie 'Vacaturetypes' \*

&#x20;       \<title>Media Adviseur Sales - New business\</title>                                                                                 titel van de vacature \*

&#x20;       \<careerlevels>                                                                                                                                                                 carriereniveau(s)

&#x20;           \<careerlevel>2\</careerlevel>                                                                                                                                              id uit lijst

&#x20;           \<careerlevel>5\</careerlevel>                                                                                                                                              id uit lijst

&#x20;       \</careerlevels>

&#x20;       \<educations>                                                                                                                                                               opleidingsniveau(s)

&#x20;           \<education>2\</education>                                                                                                                                                  id uit lijst

&#x20;           \<education>5\</education>                                                                                                                                                  id uit lijst

&#x20;       \</educations>

&#x20;       \<functiongroups>                                                                                                                                                           functiegroep(en)

&#x20;           \<functiongroup>2\</functiongroup>                                                                                                                                 id uit lijst

&#x20;           \<functiongroup>5\</functiongroup>                                                                                                                                 id uit lijst

&#x20;       \</functiongroups>

&#x20;       \<industries>                                                                                                                                                                                 branche(s)

&#x20;           \<industry>2\</industry>                                                                                                                                                         id uit lijst

&#x20;           \<industry>5\</industry>                                                                                                                                                         id uit lijst

&#x20;       \</industries>

&#x20;       \<employmentcontracts>                                                                                                                                           dienstverband(en)

&#x20;           \<employmentcontract>2\</employmentcontract>                                                                                                      id uit lijst

&#x20;           \<employmentcontract>5\</employmentcontract>                                                                                                      id uit lijst

&#x20;       \</employmentcontracts>

&#x20;       \<workinghours>                                                                                                                                                                   uren per week

&#x20;           \<workinghours>2\</workinghours>                                                                                                                                   id uit lijst

&#x20;           \<workinghours>5\</workinghours>                                                                                                                                   id uit lijst

&#x20;       \</workinghours>

&#x20;       \<salarylevel>2\</salarylevel>                                                                                                                        salarisindicatie, id uit lijst

&#x20;       \<visibility>

&#x20;           \<visibilitytype>city\</visibilitytype>\
&#x20;                                                                                                                                                                      zichtbaarheid, zie "Verspreiding" \*

&#x20;           \<country>1\</country>                                                                                                                                              land, id uit lijst \*

&#x20;           \<city>661\</city>                                                                                                                                                      plaats, id uit lijst \*

&#x20;       \</visibility>

&#x20;       \<keywords>                                                                                                                                                                              trefwoorden

&#x20;           \<keyword>\<!\[CDATA\[media]]>\</keyword>

&#x20;           \<keyword>\<!\[CDATA\[adviseur]]>\</keyword>

&#x20;       \</keywords>

&#x20;       \<startdatetext>date\</startdatetext>                                                                                   tekst startdatum, zie "Startdatum" \*

&#x20;       \<startdate>2018-01-12\</startdate>                                                                                              startdatum, zie "Startdatum" \*

&#x20;       \<introtext>\<!\[CDATA\[                                                                                                                            introtekst (max 170 karakters)

&#x20;           Als Media-adviseur.....]]>

&#x20;       \</introtext>

&#x20;       \<description>\<!\[CDATA\[                                                                                                                                                     vacaturetekst

&#x20;           \<p>\<strong>In deze uitdagende functie...........\</strong>\</p>]]>

&#x20;       \</description>

&#x20;       \<applylink>http://www.company.com/job1.html>\</applylink>\
&#x20;                                                                                                                                                                                     sollicitatielink (URL/e-mail)

&#x20;       \<trackingpixelurl>http://www.company.com/track/234o2i4ji/\</trackingpixelurl>\
&#x20;                                                                                                                                                                                                    URL tracking pixel

&#x20;   \</job>                                                                                                                                                                                         einde vacature

&#x20;   \<job>                                                                                                                                                                                            start vacature

&#x20;       .....

&#x20;   \</job>                                                                                                                                                                                         einde vacature

\</jobs>

&#x20;

\* verplicht veld

### Werkgevers

U koppelt de vacature aan een **bestaand Jobsonline werkgeversaccount** door in het veld "employerkey" de feedkey van de werkgever mee te sturen. De feedkey is op te vragen bij Jobsonline.

### Vacaturetypes

Mogelijke types:

* basic: basis vacature
* top: top vacature
* premium: premium vacature
* professional: professional vacature

### Zichtbaarheid

U kunt kiezen in welk verspreidingsgebied de vacature wordt getoond:

* city: in een plaats (vul veld 'city' in)
* regio: in een regio (vul een 'region' id in)
* province: in een of meer provincies (vul één of meer 'province' id's in)
* countrywide: landelijk

In alle gevallen moet 'country' worden ingevuld invullen.

_Let op: de volgorde waarin vacatures worden getoond in de zoekresultaten wordt bepaald door de nauwkeurigheid van de locatie. Hoe specifieker u de locatie opgeeft, hoe hoger de vacature in de zoekresultaten verschijnt en hoe meer views uw vacature krijgt._

### Startdatum

Voor het weergeven van de startdatum van de functie heeft u de keuze uit de volgende opties (voor 'startdatetext'):

* direct: weergegeven als 'Per direct'
* asap: weergegeven als 'Zo spoedig mogelijk'
* inconsultation: weergegeven als 'In overleg'
* date: toont de datum die ingevuld is in het 'startdate' veld

Het veld 'startdate' dient alleen te worden ingevuld wanneer bij 'startdatetext' de waarde 'date' ingevuld is.

&#x20;

#### Voorbeeld zichtbaarheid op plaats

&#x20;       \<visibility>

&#x20;           \<visibilitytype>city\</visibilitytype>

&#x20;           \<country>1\</country>                                                                                                                                                           id uit lijst

&#x20;           \<city>661\</city>                                                                                                                                                                      id uit lijst

&#x20;       \</visibility>

&#x20;

#### Voorbeeld zichtbaarheid op regio

&#x20;       \<visibility>

&#x20;           \<visibilitytype>region\</visibilitytype>

&#x20;           \<country>1\</country>                                                                                                                                                           id uit lijst

&#x20;           \<regions>

&#x20;               \<region>3\</region>                                                                                                                                                            id uit lijst

&#x20;           \</regions>

&#x20;       \</visibility>

&#x20;

#### Voorbeeld zichtbaarheid op provincie

&#x20;       \<visibility>

&#x20;           \<visibilitytype>province\</visibilitytype>

&#x20;           \<country>1\</country>                                                                                                                                                           id uit lijst

&#x20;           \<provinces>

&#x20;               \<province>3\</province>                                                                                                                                                   id uit lijst

&#x20;           \</provinces>

&#x20;       \</visibility>

&#x20;

#### Voorbeeld zichtbaarheid landelijk

&#x20;       \<visibility>

&#x20;           \<visibilitytype>countrywide\</visibilitytype>

&#x20;           \<country>1\</country>

&#x20;       \</visibility>

### Lijsten

#### Carriereniveau

Veldnaam in XML:  careerlevel

&#x20;

\


&#x20;     1           Geen ervaring

&#x20;     2           Starter

&#x20;     3           Ervaren

&#x20;     4           Leidinggevend

&#x20;     5           Senior management

&#x20;     6           Directie

\


&#x20;

#### Opleiding

Veldnaam in XML:  education

&#x20;

\


&#x20;     1           Postdoctoraal

&#x20;     2           WO

&#x20;     3           HBO

&#x20;     4           MBO

&#x20;     5           VWO

&#x20;     6           HAVO

&#x20;     7           VMBO/Mavo

&#x20;     8           LBO

&#x20;     9           Lagere school

\


&#x20;

#### Functiegroep

Veldnaam in XML:  functiongroup

&#x20;

\


&#x20;     3           Administratief/Secretarieel

&#x20;     4           Automatisering/Internet

&#x20;     5           Beleid/Bestuur/Staf

&#x20;     6           Beveiliging/Defensie/Politie

&#x20;   17           Callcenter/Receptie

&#x20;     7           Commercieel/Verkoop

&#x20;     8           Consultancy/Advies

&#x20;     9           Design/Creatie/Journalistiek

&#x20;   10           Directie/Management

&#x20;   11           Financieel/Accounting

&#x20;   12           Financiële dienstverlening

&#x20;   13           Horeca/Detailhandel

&#x20;   14           HR/Training/Opleiding

&#x20;   15           Inkoop/Logistiek/Transport

&#x20;   16           Juridisch

&#x20;   18           Marketing/Communicatie

&#x20;   19           Medisch/Verzorging

&#x20;   20           Onderwijs/Wetenschap

&#x20;   21           Overig

&#x20;   22           Productie/Uitvoerend

&#x20;   23           Techniek

\


&#x20;

#### Branche

Veldnaam in XML:  industry

&#x20;

\


&#x20;     1           Accountancy

&#x20;     2           Advies/Consultancy

&#x20;     3           Afval en milieu

&#x20;     4           Automotive

&#x20;     5           Banken/Financiële dienstverlening

&#x20;     6           Beveiliging/Bewaking

&#x20;     7           Bouw/Installatie

&#x20;     8           Chemie/Petrochemie

&#x20;     9           Detailhandel

&#x20;   10           Elektronica

&#x20;   11           Energie/Gas/Water

&#x20;   12           Facilitaire dienstverlening

&#x20;   13           Farmacie

&#x20;   14           FMCG

&#x20;   15           Gezondheidszorg/Welzijn

&#x20;   16           Handel/Groothandel

&#x20;   17           Horeca

&#x20;   18           ICT

&#x20;   19           Industrie/Metaal

&#x20;   20           Internet

&#x20;   21           Juridische dienstverlening

&#x20;   22           Kunst/Cultuur

&#x20;   23           Agri/Landbouw/Visserij

&#x20;   24           Makelaardij/Vastgoed

&#x20;   25           Maritiem

&#x20;   26           Media/Uitgeverijen/TV

&#x20;   27           Mode/Textiel/Cosmetica

&#x20;   28           Onderwijs/Opleiding

&#x20;   29           Overheid/Non-profit

&#x20;   30           Overig

&#x20;   31           Personen vervoer

&#x20;   32           Reclame/PR/Communicatie

&#x20;   33           Sport/Recreatie/Toerisme

&#x20;   34           Techniek

&#x20;   35           Telecom

&#x20;   36           Transport/Distributie

&#x20;   37           Uitzend/Detachering/W\&S

&#x20;   38           Verzekeringen/Assurantiën

&#x20;   39           Zakelijke Dienstverlening

\


&#x20;

#### Dienstverband

Veldnaam in XML:  employmentcontract

&#x20;

\


&#x20;     1           Vast

&#x20;     2           Tijdelijk

&#x20;     3           Freelance/ZZP

&#x20;     4           Interim

&#x20;     5           Leer-werk overeenkomst

&#x20;     6           Thuiswerk

&#x20;     7           Vakantiewerk

&#x20;     8           Vrijwilliger

&#x20;     9           Bijbaan

&#x20;   10           Stage

\


&#x20;

#### Uren per week

Veldnaam in XML:  workinghours

&#x20;

\


&#x20;     1           0 tot 8 uur

&#x20;     2           8 tot 16 uur

&#x20;     3           16 tot 24 uur

&#x20;     4           24 tot 32 uur

&#x20;     5           32 tot 40 uur

&#x20;     8           In overleg

&#x20;     6           Parttime

&#x20;     7           Fulltime

\


&#x20;

#### Salarisindicatie

Veldnaam in XML:  salarylevel

&#x20;

\


&#x20;     1           0 - 1750 euro

&#x20;     2           1750 - 2500 euro

&#x20;     3           2500 - 3500 euro

&#x20;     4           3500 - 5000 euro

&#x20;     5           5000+ euro

&#x20;     6           In overleg

&#x20;     7           Marktconform

\


&#x20;

#### Land

Veldnaam in XML:  country

&#x20;

\


&#x20;     1           Nederland

&#x20;     2           België

&#x20;     3           Duitsland

&#x20;     4           Frankrijk

&#x20;     5           Oostenrijk

&#x20;     6           Luxemburg

&#x20;     7           Zwitserland

\


&#x20;                                                                                                                      &#x20;

&#x20;           \<provinces>

&#x20;               \<province>3\</province>                                                                                                                                                   id uit lijst

&#x20;           \</provinces>

&#x20;       \</visibility>

&#x20;

#### Voorbeeld zichtbaarheid landelijk

&#x20;       \<visibility>

&#x20;           \<visibilitytype>countrywide\</visibilitytype>

&#x20;           \<country>1\</country>

&#x20;       \</visibility>

### Lijsten

#### Carriereniveau

Veldnaam in XML:  careerlevel

&#x20;      1           Geen ervaring

&#x20;     2           Starter

&#x20;     3           Ervaren

&#x20;     4           Leidinggevend

&#x20;     5           Senior management

&#x20;     6           Directie



&#x20;

#### Opleiding

Veldnaam in XML:  education

&#x20;      1           Postdoctoraal

&#x20;     2           WO

&#x20;     3           HBO

&#x20;     4           MBO

&#x20;     5           VWO

&#x20;     6           HAVO

&#x20;     7           VMBO/Mavo

&#x20;     8           LBO

&#x20;     9           Lagere school

\
&#x20;

#### Functiegroep

Veldnaam in XML:  functiongroup

&#x20;      3           Administratief/Secretarieel

&#x20;     4           Automatisering/Internet

&#x20;     5           Beleid/Bestuur/Staf

&#x20;     6           Beveiliging/Defensie/Politie

&#x20;   17           Callcenter/Receptie

&#x20;     7           Commercieel/Verkoop

&#x20;     8           Consultancy/Advies

&#x20;     9           Design/Creatie/Journalistiek

&#x20;   10           Directie/Management

&#x20;   11           Financieel/Accounting

&#x20;   12           Financiële dienstverlening

&#x20;   13           Horeca/Detailhandel

&#x20;   14           HR/Training/Opleiding

&#x20;   15           Inkoop/Logistiek/Transport

&#x20;   16           Juridisch

&#x20;   18           Marketing/Communicatie

&#x20;   19           Medisch/Verzorging

&#x20;   20           Onderwijs/Wetenschap

&#x20;   21           Overig

&#x20;   22           Productie/Uitvoerend

&#x20;   23           Techniek



#### Branche

Veldnaam in XML:  industry

&#x20;      1           Accountancy

&#x20;     2           Advies/Consultancy

&#x20;     3           Afval en milieu

&#x20;     4           Automotive

&#x20;     5           Banken/Financiële dienstverlening

&#x20;     6           Beveiliging/Bewaking

&#x20;     7           Bouw/Installatie

&#x20;     8           Chemie/Petrochemie

&#x20;     9           Detailhandel

&#x20;   10           Elektronica

&#x20;   11           Energie/Gas/Water

&#x20;   12           Facilitaire dienstverlening

&#x20;   13           Farmacie

&#x20;   14           FMCG

&#x20;   15           Gezondheidszorg/Welzijn

&#x20;   16           Handel/Groothandel

&#x20;   17           Horeca

&#x20;   18           ICT

&#x20;   19           Industrie/Metaal

&#x20;   20           Internet

&#x20;   21           Juridische dienstverlening

&#x20;   22           Kunst/Cultuur

&#x20;   23           Agri/Landbouw/Visserij

&#x20;   24           Makelaardij/Vastgoed

&#x20;   25           Maritiem

&#x20;   26           Media/Uitgeverijen/TV

&#x20;   27           Mode/Textiel/Cosmetica

&#x20;   28           Onderwijs/Opleiding

&#x20;   29           Overheid/Non-profit

&#x20;   30           Overig

&#x20;   31           Personen vervoer

&#x20;   32           Reclame/PR/Communicatie

&#x20;   33           Sport/Recreatie/Toerisme

&#x20;   34           Techniek

&#x20;   35           Telecom

&#x20;   36           Transport/Distributie

&#x20;   37           Uitzend/Detachering/W\&S

&#x20;   38           Verzekeringen/Assurantiën

&#x20;   39           Zakelijke Dienstverlening

\


&#x20;

#### Dienstverband

Veldnaam in XML:  employmentcontract

&#x20;      1           Vast

&#x20;     2           Tijdelijk

&#x20;     3           Freelance/ZZP

&#x20;     4           Interim

&#x20;     5           Leer-werk overeenkomst

&#x20;     6           Thuiswerk

&#x20;     7           Vakantiewerk

&#x20;     8           Vrijwilliger

&#x20;     9           Bijbaan

&#x20;   10           Stage

&#x20;

#### Uren per week

Veldnaam in XML:  workinghours

&#x20;      1           0 tot 8 uur

&#x20;     2           8 tot 16 uur

&#x20;     3           16 tot 24 uur

&#x20;     4           24 tot 32 uur

&#x20;     5           32 tot 40 uur

&#x20;     8           In overleg

&#x20;     6           Parttime

&#x20;     7           Fulltime

&#x20;

#### Salarisindicatie

Veldnaam in XML:  salarylevel

&#x20;      1           0 - 1750 euro

&#x20;     2           1750 - 2500 euro

&#x20;     3           2500 - 3500 euro

&#x20;     4           3500 - 5000 euro

&#x20;     5           5000+ euro

&#x20;     6           In overleg

&#x20;     7           Marktconform



#### Land

Veldnaam in XML:  country

&#x20;      1           Nederland

&#x20;     2           België

&#x20;     3           Duitsland

&#x20;     4           Frankrijk

&#x20;     5           Oostenrijk

&#x20;     6           Luxemburg

&#x20;     7           Zwitserland

\


&#x20;
