# Divi 4 · Layoutkonzept

Die Verkäuferseite ist das erste Seitenlayout. Sie beantwortet Preis- und Ablauffragen in der Reihenfolge, in der private Eigentümer typischerweise eine Entscheidung treffen. Die Käuferseite verwendet dieselben Modulvorgaben mit einem klar benannten Suchprofil als eigenem Ziel.

## Design-Tokens

| Eigenschaft | Standardvorschlag |
| --- | --- |
| Farben | Primär Waldgrün `#1B4D3E`, Hover `#153D31`, Text `#182320`, Sekundärtext `#495B54`, Fläche `#FFFFFF`, Alternativfläche `#F5F7F4`, Trennlinie `#DCE4DC`. Weißer Buttontext auf dem Standardprimärton. Dunkelgrün kann in einer einzelnen Abschlussfläche eingesetzt werden. |
| Typografie | Lokal verfügbare systemnahe Sans oder lokal lizenzierte Work Sans. H1 48–56 / 40 / 32–36 px (Desktop/Tablet/Mobil), Zeilenhöhe 1,1–1,2. H2 34–40 / 32 / 26–30 px. H3 20–23 px. Fließtext 17–18 px, Zeilenhöhe 1,55–1,65, ca. 58–68 Zeichen je Zeile. Labels und Hinweise 15–16 px. |
| Breite | Zeile bis 1160 px. Textspalten bis ca. 620 px, FAQ bis 760 px. Innenabstand 16–20 px auf Mobil, 24 px auf Tablet, 32 px auf Desktop. |
| Rhythmus | Sektionen Desktop ca. 72–88 px, Tablet 56–64 px, Mobil 40–48 px vertikal. Zeilen-/Spaltengap 32 / 24 / 16–20 px. 12–16 px zwischen Titel und Text, 20–24 px vor Buttons. |
| Formen und Fokus | Radius 10–12 px für Bilder und Karten. Schlichte Linien, wenig Schatten, Flächenwechsel sparsam. Bedienelemente mindestens 44 px hoch, klar sichtbarer Fokus und Linkunterstreichung im Fließtext. Bei Profilfarben Kontrast prüfen (WCAG AA 4,5:1 bei normalem Text und 3:1 bei großen Schriften sowie für relevante UI-Grenzen und Fokusindikatoren). |
| Bilder | Freigegebene eigene Motive in der WordPress-Mediathek, beispielsweise 1200 × 900 px für Hero und 800 × 1000 px für Porträts. WebP, nach WordPress-Unterstützung AVIF, mit geeigneten Zwischenformaten und reserviertem Seitenverhältnis. Lokale Motive als solche beschreiben, beispielhafte Häuser ohne Referenzanspruch verwenden. |

Die Gerätevorgaben beziehen sich auf Divis Desktop-, Tablet- und Telefon-Einstellungen. Den tatsächlichen Stapelpunkt auf der Zielversion prüfen, insbesondere 768, 980 und 981 px. Im Zweifel die Tablet-Zeile einspaltig halten, damit Texte und CTA bei 768 px ausreichend Raum haben. Die Lesereihenfolge folgt der Modulreihenfolge. Ein Hero hat eine H1, Abschnittstitel verwenden H2 und Karten H3.

## Verkäuferseite

Die Positionen entsprechen den Texten in [Inhalte V1](LANDINGPAGES-INHALTE-V1.md).

| Pos. und Abschnitt | Inhalt und Module in Divi 4 | Desktop → Tablet/Mobil | Bild, Akzent, CTA und Grenze |
| --- | --- | --- | --- |
| 0 · Kopf | Vorhandener Site-Header oder seitenbezogener Theme-Builder-Header. Logo per Bild, Menü mit Ablauf und FAQ, optional Button. | Eine Zeile. Bei wenig Breite Logo und Telefon beziehungsweise vorhandenes kompaktes Menü. | Weiß, ca. 64–76 px hoch. Button „Bewertung anfragen“ auf breiten Ansichten. Auf Mobil trägt der Hero den Haupt-CTA. Profilquelle und mobile Menüsemantik prüfen. |
| 1 · Hero | Textmodul für H1 und Nutzen, Button, Textlink, Bildmodul. | 55/45, linksbündig, Text zuerst. Unterhalb des Stapelpunkts Text, CTA und dann Bild. Keine Bildschirm-Mindesthöhe. | Helle Alternativfläche, freigegebene regionale Wohnimmobilie im 4:3-Format. Button zum tatsächlichen Bewertungsstart. Textlink zum Ablauf. Bei fehlendem Bild einspaltiges Layout ohne Leerraum. |
| 2 · Vorbereitung | H2 im Textmodul, drei Blurbs oder Textmodule zu Preis, Aufwand und Interessenten. | Drei Spalten oben ausgerichtet, auf Tablet und Mobil untereinander. | Weiß, kurze Texte und zurückhaltende optionale Icons. Kompakte Textmodule funktionieren auch bei größerer Schrift. |
| 3 · Ablauf | Textmodul und drei nummerierte Blurbs. | Drei gleich breite Spalten, auf Tablet und Mobil gestapelt. | Alternativfläche und klar lesbare Schrittnummern. „Bewertung anfragen“ kann am Ende dieses Abschnitts wiederholt werden, wenn die folgende Strecke lang ist. Keine verbindende Grafik nötig. |
| 4 · Ansprechpartner | Bild, Text und Linkmodul bzw. Textlink. | 1/3 Porträt, 2/3 Text. Mobil H2 und Kontaktinformationen vor dem Bild oder kompakte einspaltige Folge, ohne visuelle Umordnung gegen den Fokus. | Freigegebenes 4:5-Porträt, weiß. Telefon als `tel:`-Link. Bei fehlendem Porträt Kontaktblock als eine Spalte. |
| 5 · Nachweise, optional | Ein bis zwei freigegebene Fälle oder Zitate, Text- oder Testimonial-Modul. | Ein Fall als breite oder zwei als gleich breite Spalten, dann einspaltig. | Neutrale Fläche, keine automatisch vorbefüllten Sterne. Echte Objektbilder nur mit geklärten Rechten. Ohne Daten den kompletten Abschnitt ausblenden oder bei Seitenerstellung weglassen. |
| 6 · FAQ | H2 und einzelne Toggle-Module. Bei unzureichender Semantik Fragen und Antworten als offene Textmodule. | Eine schmale Spalte in allen Ansichten. | Heller Hintergrund, 16–20 px Innenabstand pro Frage. Interaktion, Fokus und Zustandsausgabe auf Zielversion testen. |
| 7 · Bewertung und Abschluss | H2, Text und vorhandenes Formular bzw. Link zum vorhandenen Funnel. Formular per unterstütztem Embed in der vorgesehenen Zeile. | Mittig, textlich linksbündig, kurze Einleitung und eine Formspalte für alle Geräte. | `#bewertung` bei Einbettung oder vorhandenes Funnel-Ziel für alle primären Buttons. Alternativfläche, kein zusätzliches CTA-Foto. Bei externem Funnel den Wechsel vor dem Klick erläutern. |
| 8 · Fuß | Vorhandener Site-Footer oder seitenbezogener Theme-Builder-Footer. | Unternehmenseintrag plus Links, auf Mobil mit Umbruch und ausreichender Trefferfläche. | Impressum, Datenschutz und ggf. Consent-Einstellungen aus dem Zielsystem. Keine lokalen Mock-Links. |

## Käuferseite

| Pos. und Abschnitt | Inhalt und Module in Divi 4 | Desktop → Tablet/Mobil | Bild, Akzent, CTA und Grenze |
| --- | --- | --- | --- |
| 0 · Kopf | Bild bzw. vorhandenes Logo, Menü, Button „Suchprofil anlegen“. | Einzeilig, bei wenig Platz kompaktes Menü oder Logo und Telefon. | Weiß. Menü auf Fragen und Ablauf begrenzen. |
| 1 · Hero | Text, Button, optional Bild. Eigenständige H1 zur Suche in der Region. | 55/45 bzw. einspaltig, CTA vor dem Bild. | 4:3-Foto aus der Region, keine Illustration eines aktuell verfügbaren Angebots ohne Bezug und Freigabe. Button zum Suchprofil. |
| 2 · Suchkriterien | Text und drei Blurbs für Lage, Immobilie und Budget. | Drei Spalten, einspaltig auf Tablet/Mobil. | Weiß. Beispiele in knappen Sätzen, ohne wiederholten CTA. |
| 3 · Ablauf | Text und drei nummerierte Blurbs. | Drei Spalten, einspaltig auf Tablet/Mobil. | Alternativfläche. Falls CTA wiederholt wird, gleiches Ziel wie im Hero. |
| 4 · Kontakt und optionale Stimmen | Bild und Text für den Ansprechpartner. Text/Testimonial für freigegebene Käuferstimme als separate Zeile. | 1/3 und 2/3, mobil gestapelt. Stimme in schmaler Einzelzeile. | 4:5-Porträt und direkter Telefonlink. Stimme nur bei Freigabe, keine Stockporträts als Käuferidentität. |
| 5 · FAQ | H2 und Toggle- oder offene Textmodule. | Eine Spalte. | Fragen zu Verfügbarkeit, Änderungen und Kosten. Gleiche Bedienanforderungen wie auf der Verkäuferseite. |
| 6 · Suchprofil | H2, Text, bestehender Suchauftrag bzw. Link dazu. | Zentrierte Zeile, Eingaben in natürlicher Reihenfolge, auf Mobil durchgehend einspaltig. | `#suchprofil` bei Einbettung oder bestehendes Ziel. Strukturierte Kriterien kommen aus der vorhandenen Logik. |
| 7 · Fuß | Vorhandener Site-Footer oder seitenbezogener Theme-Builder-Footer. | Layout wie Verkäuferseite. | Unternehmensname und rechtliche Links des aktiven Profils bzw. der Site. |

## Wiederverwendung und Portabilität

- Layout und Sektionen in der Divi-Bibliothek als lokale Vorlagen anlegen. Text, Button und Blurb über Presets im Ziel gestalten. Globale Bibliothekselemente nur einsetzen, wenn Änderungen auf allen betroffenen Seiten derselben Site erwünscht sind.
- Einzelne Profilwerte als Dynamic Content nur dort binden, wo Divi 4 und das vorhandene Datenmodell die Quelle für das konkrete Modul unterstützen. Wiederholbare Nachweise und Formularzustände über eine vorhandene Schnittstelle abbilden oder für den Pilot manuell pflegen. Siehe [Integration](LANDINGPAGES-INTEGRATION.md). [Divi Dynamic Content](https://help.elegantthemes.com/en/articles/8661798-using-divi-dynamic-content-options)
- Als Katalogbausteine eignen sich Hero mit einem Hauptziel, Nutzenliste, Drei-Schritte-Ablauf, Ansprechpartner, Nachweisblock, FAQ und Formular-Einstieg. Erbschaft kann Unterlagen und beteiligte Personen erklären, Scheidung Terminabstimmung und vertraulichen Kontakt, Privatverkauf die Wahl des Unterstützungsumfangs und Verkleinerung die zeitliche Planung. Themen, Bilder und FAQ bleiben später je Seite redaktionell eigenständig.
- Zuerst einen nativen Seiten-Export aus der installierten Divi-4-Version erzeugen. In einer zweiten Seite beziehungsweise Instanz mit passendem Versionsstand importieren, bevor er als Vorlage gilt. Seitenlayout, Bibliothek und Theme-Builder-Zuweisungen haben jeweils eigene Importkontexte. Presets, Farben, Medienverweise, Anker und Profilbindungen nach dem Import kontrollieren. [Divi Portability](https://help.elegantthemes.com/en/articles/8626073-importing-exporting-divi-builder-layouts-library-collections) · [Divi Library](https://help.elegantthemes.com/en/articles/8625678-the-divi-library) · [Theme Builder](https://help.elegantthemes.com/en/articles/8624263-using-the-divi-theme-builder)
- Primär die nativen Layout- und Responsivoptionen nutzen. Kleines seitenbezogenes CSS ist für Header-Ankerversatz (`scroll-margin-top`) oder einen fehlenden Fokusstil denkbar. Eigene JavaScript-Logik ist für das Layout nicht vorgesehen. Ist ein Toggle nicht zugänglich oder ein Sticky-Header unzuverlässig, ist die statische Variante der einfachste Weg zur Abnahme.
