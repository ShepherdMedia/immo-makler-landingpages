# WordPress · Integrationsvorbereitung

Ziel sind zwei Divi-4-Seiten mit eigener redaktioneller Struktur. Das vorhandene Maklerprofil, die Formularlogik, CRM, Tracking und Consent des Makler-Marketing-Systems liefern die produktiven Daten und Abläufe. Diese Spezifikation beschreibt Zielanforderungen. Konkrete Post-Typen, Feldschlüssel, Shortcodes, Hooks und Registrierungsmechanismen des Produktrepositories wurden im Rahmen der auf den Fork begrenzten Analyse nicht verifiziert.

## Seiten und Zuständigkeiten

| Bestandteil | Ziel und erwartete Übergabe |
| --- | --- |
| Verkäuferseite | WordPress-Seite mit Divi-4-Layout, Profilbindung und einem primären Einstieg in vorhandenes Verkäuferformular oder Bewertungs-Funnel. „Bewertung anfragen“ muss zum gewählten Einstieg passen. |
| Käuferseite | WordPress-Seite mit eigenem Layouttext und Einstieg in die vorhandene Anfrage- und Suchauftragslogik. Der CTA benennt die tatsächlich ausgelöste Aktion. |
| Registrierung | Später unter „Makler Tools → Landingpages“ die vorhandene Registrierung verwenden. Benötigt werden überprüfbare Bezüge zu Seitentyp und WordPress-Seite. Slugs, Profilzuordnung, Status und Verhalten bei erneuter Registrierung gegen den tatsächlichen Produktmechanismus prüfen. |
| Seiten-URLs | Bestehende produktive URLs und Marketing-Links prüfen. Als Ausgangspunkt `/verkauf` und `/akquise`. Falls Produkt oder Suchintention einen anderen Käufer-Slug erfordern, Weiterleitungen, Canonical, interne Links und Kampagnenziele zusammen umstellen. |
| Rendering | Divi für Sektionen und Stil. Der vorhandene WordPress-Mechanismus liefert Form, Einwilligungsoberfläche und Rechtstexte. Einbettung über einen unterstützten Block bzw. Shortcode oder vorhandener Formularlink. Funktionsfähige Einbettung im echten Kontext der Zielversion testen. |
| Bestand aus dem Fork | Kein Transfer von Next.js-Landingpages, `/api/contact`, Nodemailer/SMTP-Konfiguration, CAPI, Tracking-Skripten, Cookie-Banner, Uploads, Authentifizierung und Admin-Dashboard. Die vorhandenen Zielsysteme bestimmen Verarbeitung und Berechtigungen. |

## Profilbindung und Freigabe

| Logische Daten | Erwarteter Datentyp und Verwendung | Verhalten bei fehlenden Daten |
| --- | --- | --- |
| Firmenname und Logo | Freigegebener Text und Mediathek-Referenz je aktivem Profil, mit geeignetem Logo-Alternativtext. | Unternehmensname als Text, wenn Logo fehlt. Fehlender Firmenname blockiert die redaktionelle Freigabe. |
| Region und Angebot | Klarer Regionsname, bediente Gebiete, Objektarten, Bewertungsumfang, Kosten und verfügbare Vermarktungsleistungen. Einsatz in H1, Meta und FAQ. | Platzhalter vor Freigabe auflösen. Unbestätigte Zusatzleistungen sowie Kosten- und Fristversprechen auslassen. |
| Markenfarben | Validierte Primär- und ggf. Akzentfarbe, Presets mit geprüften Normal-, Hover- und Fokuszuständen. | Standard-Tokens aus dem [Layoutkonzept](LANDINGPAGES-DIVI4-KONZEPT.md). Kontrast auch bei Profiländerungen prüfen. |
| Kontakt | Profilname, Rolle, Mediathek-Porträt, zulässige Telefonnummer und ggf. E-Mail. | Freigegebener allgemeiner Unternehmenskontakt. Leere Kontaktaktionen und Bildmodule auslassen. |
| Nachweise | Liste optionaler Bewertungen, Verkaufsfälle, Zertifikate oder Kennzahlen. Quelle, Zeitraum/Datum, Freigabestatus und verwendbare Darstellung pro Eintrag. | Sektion samt Überschrift und Menüanker bei fehlenden oder abgelaufenen Daten auslassen. |
| Rechtstexte | URLs oder bestehende Integrationspunkte aus derselben WordPress-Site und dem richtigen Profil. | Veröffentlichung erst nach Zuordnung und Prüfung. |

Die Namen oben sind konzeptionelle Felder. Beim Pilot zuerst prüfen, welche Werte das Profil bereits liefert und welche Divi-Felder darauf zugreifen können. Für skalare Werte sind vorhandene WordPress-Kontextfelder und Divi Dynamic Content Kandidaten. Verwendet das Profil eigene Optionen oder komplexe Listen, eine vorhandene Darstellungsschnittstelle nutzen oder die wenigen Inhalte im Pilot redaktionell pflegen. HTML, URL und Medienauflösung müssen zur jeweiligen Ausgabe passen. Die Profilauflösung erfolgt aus dem verlässlichen Seiten- oder Site-Kontext. Öffentliche URL-Parameter dürfen den Lead-Empfänger nicht bestimmen. Cache-Schlüssel und Template-Zuweisung so prüfen, dass Daten eines anderen Maklers nicht erscheinen. [Divi Dynamic Content](https://help.elegantthemes.com/en/articles/8661798-using-divi-dynamic-content-options)

## Formulare und CRM

| Prozess | Vorgeschlagener Vertrag und zu prüfende Details |
| --- | --- |
| Bewertung | Primären CTA auf den tatsächlichen ersten Schritt führen. Beim eingebetteten Formular auf `#bewertung` verlinken. Bei getrennter Funnel-Seite deren produktiven Einstieg verwenden. Objektart und Lage früh abfragen, weitere Details und Kontaktangaben entsprechend dem bestehenden Flow. Vollständige Adresse oder Unterlagen erst erfragen, wenn sie für den nächsten Schritt gebraucht werden. |
| Suchprofil | Bestehendes Suchauftragsformular auf `#suchprofil` oder den getrennten Zielpfad anbinden. Gebiet, Objektart, Budget und verarbeitete Zusatzkriterien als Werte übergeben, die die bestehende Logik akzeptiert. Bei reiner Kontaktanfrage die alternative CTA- und Bestätigungssprache aus [Texte V1](LANDINGPAGES-INHALTE-V1.md) verwenden. |
| Routing und CRM | Empfänger aus zugeordneter Site bzw. Maklerprofil im Bestand ermitteln. Verkäufer und Käufer im bestehenden Lead-Typ bzw. Kampagnenfeld auseinanderhalten. Verfügbarkeit, Pflichtfeldregeln, eventuelle CRM-Erstellung und unterstützte Herkunftsparameter prüfen. Formulare und CRM sind für Validierung, Spam-Schutz und Dublettenverhalten zuständig. |
| Ergebnis | Erfolg nach der vom bestehenden Workflow definierten, verlässlichen Annahme. Falls die Verarbeitung asynchron ist, nur die Entgegennahme bestätigen. Fehler verständlich darstellen, Angaben bei korrigierbaren Fehlern erhalten und Mehrfachübermittlung im vorhandenen Ablauf prüfen. |
| Bedienung | Richtige Feldtypen und Autocomplete, optionale Felder sichtbar kennzeichnen, Fehler mit Feldern verknüpfen. Im Mehrschritt-Funnel Fortschritt und Rücknavigation prüfen. Fokus nach Wechsel, Fehler und Abschluss im tatsächlichen Formular testen. Alternativer Kontaktweg mit echter Telefonnummer. |

WordPress-Site, Formular und CRM gemeinsam mit synthetischen Datensätzen abnehmen. Die beiden Seitentypen, ungültige und ausgelassene Angaben, unterbrochene Verbindung, Doppelklick, Browser-Zurück und Zuordnung zu zwei Testprofilen prüfen. Die Erfolgsmeldung wird mit dem Empfang beziehungsweise dem gespeicherten Test-Lead abgeglichen. Eventuelle Benachrichtigungen in der Testumgebung an freigegebene Testziele umleiten.

## Consent, Datenschutz und Messung

- Die bestehende CMP-Konfiguration steuert Statistik- und Marketinginstrumente einschließlich serverseitig ausgelöster Weitergabe. Anfrageverarbeitung und optionale Marketingzustimmung bleiben eigenständige Vorgänge. Passende Rechtsgrundlage, benötigte Hinweise, Verantwortlicher, Aufbewahrung und Löschweg im Produktprozess klären.
- Vorhandene Ereignisnamen und Datenverträge übernehmen. Für die Entscheidung im MVP sind Haupt-CTA und bestätigter Bewertungslead sinnvoll, bei Bedarf zusätzlich ein tatsächlicher Formularstart. Käuferprofil als eigener vorhandener Typ oder Parameter. Den Einstiegskanal über die bestehende Attribution behandeln. Formwerte, Namen, E-Mail, Telefon und Freitext gehören weder in Analyseparameter noch in URL-Abfragen.
- Ablehnung, Zustimmung und Widerruf durchspielen. Anfrage muss gemäß Zielprozess auch ohne optionale Messfreigabe möglich sein. Einwilligungsabhängige Events dürfen bei Ablehnung oder Widerruf nicht weiter ausgelöst werden. Wo Browser und Server dasselbe Ereignis liefern, den vorhandenen Deduplizierungsmechanismus und Ereigniszeitpunkt prüfen.
- Medien und Schriften möglichst über die WordPress-Site ausliefern. Keine Tracking-Codes, externen Widget-Skripte oder Next.js-Konfiguration über Divi-Layoutdateien einschleusen. Rechtliche Links im jeweiligen Profil prüfen und Consent-Einstellungen im vorhandenen Mechanismus verlinken.

## Offene Fragen vor dem Pilot

| Klärung | Abnahmekriterium |
| --- | --- |
| Installierte Divi-4-, WordPress- und PHP-Version, Theme Builder und aktive Plugins | Konkreten Versionsstand dokumentieren. Ein Testlayout exportiert und in passendem Ziel erneut geprüft. Keine versehentliche globale Header-/Footer-Zuweisung. |
| Bestehendes Profilmodell und Registrierungsweg | Verantwortliche Umsetzung bestätigt Quelle für Text, Medien, Farben, Kontakt und Rechte-Links sowie Seitenauswahl unter „Makler Tools → Landingpages“. Zwei Profile werden korrekt aufgelöst. |
| Verkäuferformular/Funnel und Suchauftrag | Unterstützter Einbettungs- oder Linkweg, Feldregeln, Erfolgssignal und CRM-Zuordnung identifiziert. Kurze synthetische End-to-End-Probe je Prozess. |
| CMP und Tracking | Eigentümer der Events, Semantik, erlaubte Common-Parameter und Einwilligungssignale dokumentiert. Abnahme nach Zustimmung, Ablehnung und Widerruf. |
| Veröffentlichung und SEO | Pilot zunächst auf später vereinbartem, nicht öffentlich indexierbarem Staging. Auf Produktivseiten tatsächliche Canonicals, Metadaten, rechtliche Angaben und Indexierungsregeln vor Freigabe prüfen. |
| Performance und Barrierefreiheit | Bei 375, 390, 768 und 1280 px sowie zwei realen Mobilbrowsern prüfen. Tastatur, Screenreader, 200 % Zoom, Fokus, FAQ, Formfehler, Formularschritte und Consent-Overlay abnehmen. Produktionsnah LCP/CLS im Labortest und INP über Felddaten beurteilen, sobald verfügbar. |
