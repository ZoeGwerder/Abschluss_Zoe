#### Abschlussarbeit Zoe Gwerder
# Zug und seine Briefkastenfirmen

Das Endresultat: [**Zug und die Briefkastenfirmen: die Schattenseiten des Erfolgs**](https://www.luzernerzeitung.ch/zentralschweiz/zug/zug-und-die-briefkastenfirmen-die-schattenseiten-des-erfolgs-ld.1210007)

## DIE AUSGANGSLAGE 
**(Stand 1. Januar 2020)**:

#### These:
Der Kanton Zug ist für seine Briefkastenfirmen bekannt. Nur ist nicht klar – und von Amtsstellen auch nicht zu erfahren – wo diese stecken könnten und wie viele es in etwa sind. Es ist davon auszugehen, dass es Ansammlungen, also mehrere an einer Adresse, gibt. Das Ausmass und mögliche Standorte sind unbekannt. 

#### Geschichte:
Wo gibt es im Kanton Zug auffällige Ansammlungen von korrekt registrierten Briefkastenfirmen mit einer c/o-Adresse? Wo sind mögliche Hotspots von nicht mit c/o-Adressen versehenen Briefkastenfirmen? Die Datenanalyse wird durch eine klassische Recherche vor Ort ergänzt und soll zusätzlich Licht ins Dunkle bringen.  
#### Ausbaumöglichkeiten – Folgegeschichte:  
Durch eine eventuelle Abfrage des ersten Eintrages sowie der Löschung des Unternehmens könnte man auch noch die Entwicklung der Briefkastenfirmen über die Jahre hinweg eruieren. Gibt es inzwischen wirklich weniger solche Konstrukte, wie in Zug nach dem Auffliegen der Panama-Papers von offizieller Stelle gesagt wurde? (Damals hiess es 700)

#### Aufwand/Ertrag:
Zwei Datenbanken mit Selenium auslesen ist eher aufwändig. Als Ertrag habe ich dann jedoch zwei Scraper, mit denen ich an alle Daten des Handelsregisters kommen kann und diese neu auswerten kann – mit Potential zu Folgegeschichten und als Recherchenhilfe.

#### Quellen: 
- Handelsregister (HR) des Kantons Zug: https://zg.chregister.ch/cr-portal/suche/suche.xhtml
- Verzeichnis aller Adressen BUND:   https://data.geo.admin.ch/ch.bfs.gebaeude_wohnungs_register/CSV/meta.txt
- evtl. Ergänzung durch Telefonbuch oder wenn auffindbar Register der Anzahl Wohn- und Gewerberäume pro Gebäude. 
#### Möglicher Knackpunkt:
-	Abfrageschranke auf dem Onlineportal (Handelsregister sagt nein, es könnte aber trotzdem der Fall sein) 
-	Falls die Ansammlungen nicht gross sind pro Adresse wird’s schwierig zu erkennen, wo Briefkastenfirmen sein könnten – Entsprechend schwierig würde die Umsetzung der Idee der Verifizierung vor Ort.  
#### Ausschnitt aus Gespräch mit einer Briefingperson (Andreas Hess, Amtsleiter Handelsregister- und Konkursamt Zug)
"Es gibt Adressen, wo man annimmt, dass es Briefkastenfirmen gibt. Jene die ihre Domiziladresse korrekt mit c/o angeben, sind weniger das Problem. Die machen alles Korrekt. Problematischer ist es, wenn sie sich nicht als solche zu erkennen geben und vorgeben, ein Büro mit Mitarbeitern vor Ort zu haben.
Diese befinden sich wohl am ehesten in der Stadt Zug - vielleicht auch noch an der Stadtgrenze zu Baar und Cham. Denn in Berggemeinden gibt es relativ wenig, weil es dort wohl an der Anonymität fehlt. Dort würde uns sicher zugetragen werden, wenn es in einem Gebäude angeblich viel mehr Firmen gibt, als real möglich ist.
Ob eine Firma eine Briefkastenfirma ist oder wirklich Mitarbeiter hat, ist von Seiten Handelsregister schwierig zu beurteilen. Wir sehen es den Gesellschaften nicht an. Wir haben nur entsprechende Papiere auf dem Tisch und auf Grund dieser Papiere haben wir keine Ahnung, ob dort was dahintersteckt oder nicht." 
#### Relevanz:
Erste Telefonate mit dem Handelsregisteramt, der Zuger Kantonalbank sowie dem Amt für Wirtschaft zeigen, dass das Thema Briefkastenfirmen im Kanton Zug quasi ein Tabu-Thema ist. Es wirkt, als wolle man nicht hinschauen und genauer eruieren, welche Firmen nur vorgeben, Büroräume hier zu haben und welche wirklich solche hier betreiben. Entsprechend gross ist die Relevanz der These in Bezug auf den Newsgehalt – mit dem Potential, auch politisch Wellen zu werfen. 


## DIE ARBEIT

#### Zu den Files:
Der erste Anlauf übers Handelsregister mit unvollständigen Daten (wie sich am Schluss herausstellte)
- ![01 Endcode Briefkastenfirmen](https://github.com/ZoeGwerder/Abschluss_Zoe/blob/master/01%20Endcode%20Briefkastenfirmen.ipynb)
- ![1.1 Adresslisten Aufbereitung](https://github.com/ZoeGwerder/Abschluss_Zoe/blob/master/01.1%20Adressenliste%20Aufbereitung.ipynb)
- ![1.2 Auswertung Geopandas Kanton und Stadt](https://github.com/ZoeGwerder/Abschluss_Zoe/blob/master/01.2%20Auswertung%20Geopandas%20Kanton%20und%20Stadt.ipynb)
- ![1.3 Endprodukt Auswertung](https://github.com/ZoeGwerder/Abschluss_Zoe/blob/master/01.3%20Endprodukt%20Auswertung.ipynb)

Der zweite Anlauf via Zefix der zum Endresultat führte
- ![300 ZEFIX Hauptfile](https://github.com/ZoeGwerder/Abschluss_Zoe/blob/master/300%20ZEFIX%20Hauptfile.ipynb)
- ![300.3 ALLE Endprodukt Auswertung ohne Geodaten](https://github.com/ZoeGwerder/Abschluss_Zoe/blob/master/300.3%20ALLE%20Endprodukt%20Auswertung%20ohne%20Geodaten.ipynb)
- Auswertung/Darstellung mit Geopandas und Basemap (leider zu gross für Github-Upload)
- ![302 ZEFIX fehlende Adresse durch Telsearch API](https://github.com/ZoeGwerder/Abschluss_Zoe/blob/master/302%20ZEFIX%20fehlende%20Adresse%20durch%20Telsearch%20API.ipynb)
- ![301 ZEFIX Auslesen der Firmen-Files](https://github.com/ZoeGwerder/Abschluss_Zoe/blob/master/301%20ZEFIX%20Auslesen%20der%20Firmen-Files.ipynb)
#### Arbeitsprotokoll
1.	Adressen aufbereiten, so dass das Format für die Abfrage beim Zuger Handelsregister funktioniert. Zudem mussten jene Adressen, welche keine Hausnummer haben, noch separat noch behandelt werden.   
2.	
- Mit Selenium einen Scraper fürs Handelsregister bauen, um alle vorhandenen Adressen abzufragen und jeweils die erste Seite abzuspeichern. Dort gibt es glücklicherweise einen Eintrag, wie viele Firmen unter dieser Adresse zu finden sind. So müssen nicht alle Unterseiten angesteuert werden – bez. ich könnte diese bei Bedarf in einer zweiten Runde ansteuern, sobald ich weiss, an welchen Adressen es mehr als eine Seite gibt (es sind immer 20 Firmen pro Seite).

- Die ersten 5000 Abfragen gingen gut. Danach ging immer weniger. Ich fing an das zu verarbeitende Dataframe in 1000-er Stücke aufzuteilen und nach jedem Stück den Browser zu schliessen. Dies ging ebenfalls immer schlechter, bis ich nur noch 20 Abfragen ohne Error machen konnte. Dann der Versuch try-except-Schlaufen um die Problemstellen zu bauen. Es wurden jedoch immer wieder neue Errors ausgelöst. 

- Danach der Versuch mit Tor. Anfangs hatte ich versehentlich nur den Firefox (und noch nicht Tor). Dies ging besser. Verschlechterte sich jedoch auch wieder auf wenige 100 Abfragen pro Lauf. Danach wirklich mit Tor. Diese IPs schien der Rechner zu kennen. Ich konnte kaum 50 Abfragen machen ohne Error. 

- Versuch mit einem Proxi-Surfer. Dies verstand ich jedoch zu wenig. Die Lösung war am Ende das Löschen der Cookies. Ich baute eine try-except-Schlaufe um das Ganze – so dass bei jedem Error der Browser geschlossen wird und mit der entsprechenden Browsereinstellung die Cookies gelöscht werden. Mit diesem Kniff konnte ich auch noch die verbliebenen rund 10000 Adressen abfragen. 
- Auf Grund der Probleme mit dem Scraper konzentrierte ich mich parallel zum fixen dieses Problems auf das extrahieren und Auswerten der Zahlen der Stadt Zug. Denn gemäss dem Leiter des Handelsregisteramtes (Briefingperson) sind solche Briefkastenadressen vor allem in der Stadt zu erwarten. Auf Grund der Ordnerstruktur die sich daraus ergab (gleiche Filenamen mit unterschiedlichem Inhalt) entschied ich mich, die Stadt sowie die restlichen Gemeinden separat durch den Code zu lassen und die Files am Ende wieder zusammenzufügen.  
3.	Die Seiten grob auslesen. Sie sind schön strukturiert. 
4.	Anzahl Firmen sowie Adresse extrahieren. Und codierte Umlaute bereinigen.
5.	Das File mit den Firmen anhand der Adressen mit dem Adressfile zusammenbringen und schauen, was noch fehlt. Fehlende nochmals durch den Scraper lassen.
6.	Die Recherchen ergaben, dass es keine Daten zur Anzahl Büroeinheiten pro Gebäude gibt und auch das vorhandene Register nur Gebäude ausweist, welche mindestens eine Wohnung beinhalten. Erste Datenauswertungen sowie die zwischenzeitliche Berichterstattung zu den Luanda-Leaks zeigten mir, dass ich dringend einen Referenzwert benötige. Denn die 41 Firmen, welche an der Adresse der Zuger Luanda-Leak-Firma domiziliert sind, fallen ohne Referenzwert nicht auf. Weiss man jedoch, dass die Altstadt nur kleine Gebäude hat, mit meistens höchstens 3-4 Parteien darin, fällt diese Zahl definitiv auf.
Mangens Alternative entscheide ich mich für das Telefonbuch. Wohl sind darin bei weitem nicht mehr alle Telefonanschlüsse eingetragen – einige Stichproben zeigen jedoch, dass es als Referenzwert wohl ausreicht.
7.	Scraper für Telefonbuch bauen und all jene Adressen durchgehen, an welchen mindestens eine Firma zuhause ist. (Eigentlich reichen auch jene, an denen mindestens 10 domiziliert sind, da 10 Firmen wohl auch von einer Person noch gut zu durchschauen sind und ich später nur jene mit mehr als 15 Firmen anschaue). 
8.	Wie mit den Handelsregistereinträgen nun wieder extrahieren, Umlaute bereinigen und kontrollieren, ob alle erwischt wurden. Fehlende Adressen nochmals durch den Scraper lassen.
9.	Frame mit Anzahl Firmen sowie Frame mit Anzahl Telefonbucheinträgen zusammenbringen.
10.	Um die Relation von Anzahl Firmen und Anzahl Telefonbucheinträge zu erfassen, kreiere ich durch die Division der Firmen durch die Telefonbucheinträge einen Vergleichswert.
11.	Auswerten mit Geopandas und klassisch. Bei der weiteren Textrecherche zeigen Zahlen einer Publikation des Kantons, dass mir rund ein Drittel aller Firmen fehlen.
->	 Offenbar habe ich falsche Grundlagen beim Adressregister gewählt. Die Publikation wird verschoben. Die Dokumentation für die Abgabe der Arbeit als Version 2 (ohne publizierten Artikel) erstellt.

##### Zurück auf Feld 1 (Nach dem 7. Februar)
12. Die Nachforschungen zeigen, dass das Adressregister im Kanton Zug bisher nur aus Adressen besteht, bei welcher es mindestens eine Wohnung gibt. Abklärungen haben ergeben: Ein vollständiges Adressregister aller von der Post belieferten Adressen gäbe es bei der Post – kostet alleine für den Kanton Zug aber 1900 Franken. Gemäss Post gibt es zwar irgendeine Person im Vertrieb von chmedia, die diese Daten hätte. Die Suche nach dieser Person scheint mir jedoch etwas aufwändig. Und wenn mir die Post die Daten zusammenstellt (ohne Geodaten) kostet es trotzdem noch 350 Franken. Ich suche eine Alternative.
13. Über Zefix lade ich halbmanuell – dank dem Umstand, dass Kanton Zug nur 11 Gemeinden hat – alle Firmen des Kantons Zug und deren UID runter. Ich gebe die einzelnen Gemeinden von Hand ein und gehe die Unterseiten mit Selenium durch und speichere diese ab. Glücklicherweise kann man auf der Seite die Gemeinde eingeben und alle Firmen werden aufgelistet.
14. Eigentlich will ich nun mit der UID die Firmendaten abfragen. Beim Handelsregister Zug gelingt dies nicht (ich ging der Sache noch nicht weiter nach). Bei der Zefix-Seite ging es auch nicht. Dort erschien eine Nachricht, meine IP sei gesperrt worden, da es sich um eine Massenabfrage handle.
15. Die Nachfrage bei der UID-Stelle ergab, dass sie keine Massenabfragen zulassen wollen. Der Herr am Telefon gab mir jedoch den Wink, dass der Rechner bei mehr als 10 Abfragen pro Minute die IP während einer Minute sperre. 
16. Ich baue in die Abfrage ein Random-Time-Sleep ein, welcher höchstens 10 Abfragen pro Minute machen kann. Es funktioniert. Während fast 80 Stunden werden die rund 34000 UID-Einzelseiten, welche die Adress-Angaben enthalten runtergezogen.
17. Die Seiten sind gut strukturiert. Ich kann leicht die Adressen rausholen.
18. Nun benötige ich die Geodaten zu jeder Adresse. Die Abfragen sind bei allen Diensten beschränkt. Um nicht zu viele machen zu müssen filtere ich jene Adressen raus, die noch keine Geodaten haben. Der Versuch mit dem gratis-Angebot OSM misslingt. Ich versuche es mit der API von Google-Maps. Mit zwei kleinen Except-Schlaufen gelingt dies. Nun habe ich bei fast allen Adressen die Geodaten. Aus den Json-Resultaten hole ich mir die Geodaten indem ich die verschachtelten Dicts in einen Satz konvertiere und sie dort mit Regex extrahiere.
19. Jetzt noch alle neu dazugekommenen Adressen durch das Telefonbuch lassen. Dort habe ich inzwischen ebenfalls eine API. Auf Nachfrage stellen sie mir diese kostenlos zur Verfügung. 
20. Nun wieder mit den ursprünglichen Daten zu einem Frame machen: Daten anpassen (z.b. Strassennamen extrahieren und Vergleichswert erstellen) und die Geodaten ins Schweizer Format umwandeln. 
21. Das neue, vollständige Dataframe durch den Geopandas- und Auswertungscode lassen. Neu anschauen.

#### Wie weiter:
Die Interviews mit Expertinnen, dem Handelsregisteramt und dem Zuger Finanzdirektor sind gemacht. Zur Visualisierung fürs Online werden die Firmen auf der Karte mit dem Programm Datawrapper aufbereitet. Der Grafiker ist informiert. Er kann mit Hilfe des Punkte-Bildes diese auf die bei unserer Zeitung gängigen Grafik-Landkarten bringen. Im Print wird es ein Pano mit drei Grafiken geben.
	

## DIE GESCHICHTE 
**(Anhand der am 7. Februar vorliegenden Fakten)**

#### Titel: 
Zug und seine Briefkastenfirmen

#### Lead:
Die Luanda-Leaks haben einmal mehr die Schattenseiten eines florierenden Wirtschaftsstandortes wie Zug gezeigt. Experten und Kanton sind sich jedoch einige: Will man wirtschaftlich attraktiv bleiben, gehören solche substanzlose Firmen dazu - und diese sind wohl nicht nur in der Stadt Zug zu finden.

#### Storyline:
- **Texteinstieg** mit Überblick über die Firmenzahlen zur Bevölkerungszahl des Kantons Zug: Jeder vierte Zuger – Kinder und Greise eingeschlossen – hätte demnach eine Firma. Bei 34000 Firmen werden nur mal gerade rund 18000 als "Betriebe" aufgeführt.

- **Erklärung zur Attraktivität von Stadt und Kanton Zug**. Mit Infos von Claudia Brunner und Susanne Grau, Studienleiterinnen HSLU Wirtschaftskriminalität und WirtschaftStatement. Zudem erklärt der Zuger Finanzdirektors Heinz Tännler die Haltung des Kantons zum Thema Briefkastenfirmen sowie zur aktuellen Strategie.

- **Grafik "Übersicht über den Kanton"** mit Information, wo wie viele Firmen ansässig sind und dass es vor allem in der Stadt Zug auffällige Anhäufungen gibt. Inklusiver Erklärung des "Verhältnis-Werts" und dessen Bedeutung/Interpretation. Mit Hinweis auf auffällige Punkte auch ausserhalb der Stadt.

- **Grafik "Nähere Betrachtung der Stadt Zug"** mit Hinweis zu den Luanda-Leaks, welche zu einem Altstadthaus führen, an welchem 41 Firmen registriert sind. Was heisst, dass der Vergleichswert wohl eher zu Auffälligkeiten führt. So ist prompt unter der auffälligsten Adresse ein Unternehmen, welches sich "Trust" nennt im Telefonbuch eingetragen.

- **Grafik "Die beliebtesten Briefkastenstrassen"** mit den Fakten, wie viele Einwohner die Stadt hat und wie viele Firmen. So hätte dort jede zweite Person eine eigene Firma.

- **Abschluss** mit Blick auf die Luanda-Leaks, nach deren Publikation der Kanton von linker Seite aufgefordert wurde zu handeln. Infos von Claudia Brunner und Susanne Grau, mit der Erklärung, weshalb dies schwierig ist, und wo man trotzdem noch ansetzten könnte: mehr und schnellerer Austausch zwischen den Ämtern zulassen. Statement dazu von Heinz Tännler.

- **KONTEXTUELLER ZUSATZTEXT (Box)** Erklärung zum Thema Briefkastenfirmen mit Claudia Brunner und Susanne Grau. Was sind Indizien für Briefkastenfirmen, wieso sind diese so schwer zu erkennen und weshalb ist es noch schwieriger, kriminelle Machenschaften zu verfolgen.

- **INFOBOX (box)** Zum Vorgehen der Datenrecherche.



## DIE GRAFIKEN:

#### **Übersicht über den Kanton Zug**
Hier sieht man alle (im Datensatz vorhandenen) Adressen mit Firmen (rot, je mehr Firmen desto grösser) sowie alle Adressen mit mehr als 15 Firmen und einem Vergleichswert von mindestens 5 (blau, je höher der Vergleichswert desto grösser). Die Grafik zeigt, dass verdächtige Adressen – mit hohem Vergleichswert – vorderhand an Adressen vorkommen, an denen es per se schon viele Firmen hat. Ausnahmen inbegriffen, wie beispielsweise in Oberägeri. Ebenfalls ersichtlich sind die Ballungszentren. Adressen mit auffällig vielen Firmen gibt es hauptsächlich in der Stadt Zug. Doch entgegen den Vermutungen des Leiters des Handelsregisteramtes gibt es solche auch in den Gemeinden – wenn auch deutlich seltener.

![Grafik 1: Anzahl Firmen und verdächtige Vergleichswerte Kanton](https://github.com/ZoeGwerder/Abschluss_Zoe/blob/master/Vergleichswert%20und%20Firmen%20Kanton%20%C3%BCbereinander.png)

#### **Nähere Betrachtung der Stadt Zug**
In der Grafik sind alle Adressen mit mehr als 15 Firmen (rot) sowie alle Adressen mit mindestens 15 Firmen und einem Vergleichswert von 5 und mehr zu sehen. Bei näherer Betrachtung wird ersichtlich, dass der Vergleichswert nötig ist. Denn hier sieht man nun, dass es auch in der Altstadt und beim wohlhabenderen Teil der Stadt (am Hang), wo deutlich weniger Firmen ihren Sitz an derselben Adresse haben (rot), verdächtige Verhältnisse von Telefonbucheinträgen zur Anzahl Firmen gibt (blau). Wobei dieses Verhältnis mit Vorsicht betrachtet werden muss. Ein Telefonbucheintrag ist nur einer der Indizien für eine existente Firma.

![Grafik 2: Nähere Betrachtung der Stadt](https://github.com/ZoeGwerder/Abschluss_Zoe/blob/master/Vergleichswert%20und%20Anzahl%20Firmen%20Stadt%20Zug.png)


#### **Die beliebtesten Briefkastenstrassen**
Hier wird deutlich, dass die These, dass die Baarerstrasse wohl am meisten Adressen mit Briefkastenfirmen hat, bestätigt wird. Die Chamerstrasse scheint hingegen eine Strasse zu sein, an welcher Firmen in Gebäuden mit vielen privaten Einträgen domiziliert sind, einige wenige jedoch einen besonders hohen Vergleichswert aufweisen. Denn bezüglich Vergleichswert steht die Chamerstrasse an zweiter Stelle, obwohl es über das ganze gerechnet an Adressen mit mindestens einer Firma deutlich mehr Telefonbucheinträge gibt, als Firmeneinträge. Zudem zeigt die Rangliste, was nach den Luanda-Leaks zu vermuten war: Tatsächlich können auch Adressen, wie die Untere Altstadt in Zug, zu den Top-Ten-Hotspots des Kantons gehören. 

![Grafik3: Die Top-Strassen der verdächtigen Adresse](https://github.com/ZoeGwerder/Abschluss_Zoe/blob/master/Strassen%20mit%20h%C3%B6chstem%20Vergleichswert.png)




