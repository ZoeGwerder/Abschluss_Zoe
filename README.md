## Abschlussarbeit Zoe Gwerder
# «Wo gibt es im Kanton Zug am meisten Briefkastenfirmen»

AUSGANGSLAGE:
**These:** 
Zug ist für seine Briefkastenfirmen bekannt. Nur ist nicht klar – und von Amtsstellen auch nicht zu erfahren – wo diese stecken könnten und in etwa wie viele es sind. Es ist davon auszugehen, dass es solche Ansammlungen gibt. Ort und Ausmass sind unbekannt. 
Geschichte:
Wo gibt es im Kanton Zug auffällige Ansammlungen von registrierten c/o-Firmen? Wo sind mögliche Hotspots von nicht mit c/o-Adressen deklarierten Briefkastenfirmen? Die Datenanalyse wird durch eine klassische Recherche vor Ort ergänzt und soll zusätzlich Licht ins Dunkle bringen.  
Ausbaumöglichkeiten – Folgegeschichte:  
Durch eine eventuelle Abfrage des ersten Eintrages sowie der Löschung des Unternehmens könnte man auch noch die Entwicklung der Briefkastenfirmen über die Jahre hinweg eruieren. Gibt es wirklich weniger solche Konstrukte, wie in Zug nach dem Auffliegen der Panama-Papers von offizieller Stelle her gesagt wurde.
Quellen: 
Handelsregister (HR) des Kantons Zug: https://zg.chregister.ch/cr-portal/suche/suche.xhtml
Verzeichnis aller Adressen BUND:   https://data.geo.admin.ch/ch.bfs.gebaeude_wohnungs_register/CSV/meta.txt
evtl. Ergänzung durch Telefonbuch oder wenn auffindbar Register der Anzahl Wohn- und Gewerberäume pro Gebäude. Hier könnte die Gebäudeversicherung Zahlen haben – sie war jedoch noch nicht erreichbar. 
Möglicher Knackpunkt:
-	Abfrageschranke auf dem Onlineportal (HR sagt nein, könnte trotzdem sein) 
-	Falls die Ansammlungen nicht gross sind pro Adresse wird’s schwierig zu erkennen, wo Briefkastenfirmen sein könnten – Entsprechend schwierig würde die Umsetzung der Idee der Verifizierung vor Ort.  
Ausschnitt aus Gespräch mit einer Breafingperson (Andreas Hess, Amtsleiter Handelsregister- und Konkursamt Zug)
Es gibt Adressen, wo man annimmt, dass es Briefkastenfirmen gibt. Jene die ihre Domiziladresse korrekt mit c/o angeben, sind weniger das Problem. Die machen alles Korrekt. Problematischer ist es, wenn sie sich nicht als solche Outen und vorgeben, ein Büro mit Mitarbeitern vor Ort zu haben. 
Diese befinden sich wohl am ehesten in der Stadt Zug. Vielleicht noch Stadtgrenze zu Baar. Denn in Berggemeinden gibt es relativ wenig, weil es dort wohl an der Anonymität fehlt. Dort würde uns sicher zugetragen werden, wenn es in einem Gebäude angeblich viel mehr Firmen gibt, als real möglich ist.
Ob eine Firma eine Briefkastenfirma ist oder wirklich Mitarbeiter hat, ist von Seiten Handelsregister schwierig zu beurteilen. Wir sehen es den Gesellschaften nicht an. Wir haben nur entsprechende Papiere auf dem Tisch und nur auf Grund dieser Papiere haben wir keine Ahnung, ob dort was dahinter steckt oder nicht. 
Relevanz:
Erste Telefonate mit dem Handelsregister, der Zuger Kantonalbank sowie dem Amt für Wirtschaft zeigen, dass das Thema Briefkastenfirmen im Kanton Zug quasi ein Tabu-Thema ist. Man will nicht hinschauen und genauer eruieren, welche Firmen nur vorgeben, Büroräume hier zu haben und welche wirklich solche hier betreiben. Entsprechend gross ist die Relevanz in Bezug auf den Newsgehalt – mit dem Potential, auch politisch Wellen zu werfen. 
Arbeitsprotokoll:
Zu den Files:
01 Endcode Briefkastenfirmen
1.1 Adresslisten Aufbereitung
1.2 Auswertung Geopandas Kanton und Stadt
1.3 Endprodukt Auswertung
1.	Adressen aufbereiten, so dass das Format für die Abfrage beim Zuger Handelsregister funktioniert. Zudem mussten jene Adressen, welche keine Hausnummer haben separat noch behandelt werden.   
2.	Mit Selenium Scraper fürs Handelsregister bauen, um alle vorhandenen Adressen abzufragen und jeweils die erste Seite abzuspeichern. Dort gibt es glücklicherweise einen Eintrag, wie viele Firmen unter dieser Adresse zu finden sind. So müssen nicht alle Unterseiten angesteuert werden – bez. ich kann diese in einer zweiten Runde ansteuern, sobald ich weiss, an welchen Adressen es mehr als eine Seite gibt (es sind immer 20 Firmen pro Seite).
Die ersten 5000 Abfragen gingen gut. Danach ging immer weniger. Ich fing an das zu verarbeitende Dataframe in 1000-er Stücke aufzuteilen und nach jedem Stück den Browser zu schliessen. Dies ging ebenfalls immer schlechter bis ich nur noch 20 Abfragen ohne Error machen konnte. Dann Versuch mit try-except um die Problemstellen zu bauen. Es wurden jedoch immer wieder neue Errors geschmissen. Danach Versuch mit Tor. Anfangs hatte ich versehentlich nur den Firefox (und noch nicht Tor). Dies ging besser. Verschlechterte sich jedoch auch wieder auf wenige 100 Abfragen pro Lauf. Danach mit Tor. Diese IPs schien der Rechner zu kennen. Ich konnte kaum 50 Abfragen machen ohne Error. Versuch mit einem Proxi-Surfer. Dies verstand ich jedoch zu wenig. Die Lösung war am Ende das Löschen der Cookies. Ich baute eine try-except-Schlaufe um das Ganze – so dass bei jedem Error der Browser geschlossen wird und mit der entsprechenden Browsereinstellungen die Cookies gelöscht werden. Mit diesem Kniff konnte ich auch noch die verbliebenen rund 10000 Adressen abfragen. 
2.1  Auf Grund der Probleme mit dem Scraper konzentrierte ich mich paralell zum fixen dieses Problems auf das extrahieren und Auswerten der Zahlen der Stadt Zug. Denn gemäss dem Leiter des Handelsregisteramtes (Briefingperson) sind solche Briefkastenadressen vor allem in der Stadt zu erwarten. Auf Grund der Ordnerstruktur die sich daraus ergab (gleiche Filenamen mit unterschiedlichem Inhalt) entschied ich mich, die Stadt sowie die restlichen Gemeinden separat durch den Code zu lassen und die Files am Ende wieder zusammenzufügen.  
3.	Die Seiten grob auslesen. Sie sind schön strukturiert. 
4.	Anzahl Firmen sowie Adresse extrahieren. Und codierte Umlaute bereinigen.
5.	Das File mit den Firmen anhand der Adressen mit dem Adressfile zusammenbringen und schauen, was noch fehlt. Fehlende nochmals durch Scraper hindurch lassen.
6.	Da die Recherchen ergaben, dass es keine Daten zur Anzahl Büroeinheiten pro Gebäude gibt und auch das vorhandene Register nur Gebäude ausweist, welche mindestens eine Wohnung beinhalten. Erste Datenauswertungen sowie die zwischenzeitliche Berichterstattung zu den Luanda-Leaks, zeigten mir, dass ich dringend einen Referenzwert benötige. Denn die 41 Firmen, welche an der Adresse der Zuger Luanda-Leak-Firma domiziliert sind, fallen ohne Referenzwert nicht auf. Weiss man jedoch, dass die Altstadt nur kleine Gebäude hat, mit meistens höchstens 3-4 Parteien darin, fällt diese Zahl definitiv auf.
Mangens Alternative entscheide ich mich für das Telefonbuch. Wohl sind darin bei weitem nicht mehr alle Telefonanschlüsse eingetragen – einige Stichproben zeigen jedoch, dass es als Referenzwert wohl ausreicht.
7.	Scraper für Telefonbuch bauen und all jene Adressen durchgehen, an welchen mindestens eine Firma zuhause ist. (Eigentlich reichen auch jene, an denen mindestens 10 domiziliert sind, da 10 Firmen wohl auch von einer Person wohl noch gut zu durchschauen sind). 
8.	Wie mit den Handelsregistereinträgen nun wieder extrahieren, Umlaute bereinigen und kontrollieren, ob alle erwischt wurden. Fehlende Adressen nochmals durch den Scraper lassen.
9.	Frame mit Anzahl Firmen sowie Frame mit Anzahl Telefonbucheinträgen zusammenbringen.
10.	Um die Relation von Anzahl Firmen und Anzahl Telefonbucheinträge zu erfassen, kreiere ich durch die Division der Firmen durch die Telefonbucheinträge einen Vergleichswert.
11.	Auswerten mit Geopandas und klassisch.
	Erkenntnis: Mir fehlen auf Grund falsch gewählten Grundlagen rund ein Drittel aller Firmeneinträge. Die Publikation wird verschoben.

Wie weiter:
Die Anschliessenden Recherchen für den zu publizierenden Text haben ergeben, dass mir rund ein Drittel der Firmen fehlen. Die Nachforschungen zeigen, dass das Adressregister offenbar nur aus Adressen besteht, bei welcher es mindestens eine Wohnung gibt. 
Abklärungen haben ergeben: Ein vollständiges Adressregister aller von der Post belieferten Adressen gäbe es – kostet alleine für den Kanton Zug aber 1900 Franken. Anfrage betreffend Erlass der Gebühr zur Verwendung der Daten zur Recherche läuft.
Über Zefix kann ich zwar alle Firmen des Kantons Zug runterladen – und deren UID. Die Abfrage dieser stiess aber bei beiden Portalen auf Widerstände (Bei Zefix IP Sperrung, da es als Massenabfrage erkannt wurde). Die Nachfrage bei der UID-Stelle ergab, dass sie keine Massenabfragen zulassen wollen. Mit dem Wink, dass der Rechner bei mehr als 10 Abfragen pro Minute die IP während einer Minute sperre. Nun versuche ich, mit ausreichend Zeit diese UIDs abzufragen. Stand nach den ersten 24h und 10‘000 Abfragen: es scheint zu funktionieren. 
Aus den UID-Pages des Bundes werde ich die Adresse rausholen können. Leider hat es dort keine weiteren relevanten Infos. 
Inzwischen habe ich auch erreicht, dass Telsearch mir ihre kostenpflichtige API für Recherchen kostenlos zur Verfügung stellt (hier dauerten die Abklärungen einfach länger, weshalb ich davor mit dem Scraper mir die Daten holte.)
Dann werde ich die Daten wieder zu einem Frame machen und muss dann noch neu rausfinden, wie ich die Koordinaten der Adressen rausfinde.







Die Geschichte: 
Der Kanton Zug und die Briefkastenfirmen

Storyline:


Die Grafik:
[Grafik 1: Anzahl Firmen und verdächtige Vergleichswerte Kanton](Vergleichswert und Firmen Kanton übereinander.png)
Hier sieht man anhand der roten und blauen Punkte, dass verdächtige Adressen – mit hohem Vergleichswert – vorderhand an Adressen vorkommen, an denen es per se schon viele Firmen hat. Ausnahmen inbegriffen, wie beispielsweise in Oberägeri. 
Stadt Grafik:
Bei näherer Betrachtung wird ersichtlich, dass der Vergleichswert nötig ist. Denn hier sieht man nun, dass es auch in der Altstadt und beim wohlhabenderen Teil der Stadt (am Hang), wo deutlich weniger Firmen ihren Sitz an derselben Adresse haben, verdächtige Verhältnisse von Telefonbucheinträgen zur Anzahl Firmen gibt. 
Balken zu den Strassen:
Hier wird deutlich, dass die These, dass die Baarerstrasse wohl am meisten Adressen mit Briefkastenfirmen hat bestätigt. Die Chamerstrasse scheint hingegen eine Strasse zu sein, an welcher Firmen in Gebäuden mit vielen privaten Einträgen domiziliert sind. Einige wenige wohl jedoch einen besonders hohen Vergleichswert aufweisen. Denn bezüglich Vergleichswert steht die Chamerstrasse an zweiter Stelle, obwohl es über das ganze gerechnet an Adressen mit mindestens einer Firma deutlich mehr Telefonbucheinträge gibt, als Firmeneinträge.


