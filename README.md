# Reisekostenabrechnung

Webbasierte Anwendung zur Abrechnung dienstlicher Reisekosten – komplett im Browser, ohne Server und ohne Installation.

**➡️ Live-Version: https://liebemichael1972-cell.github.io/reisekostenabrechnung/**

## Funktionen

- **Reisedaten erfassen**: Name, Kostenstelle, Reiseziel, Zweck und Reisezeitraum
- **Belege abfotografieren / hochladen**: direkt mit der Handykamera oder aus der Galerie, mehrere Bilder pro Position; Fotos werden automatisch verkleinert
- **Kostenpositionen**: Kategorien (Fahrtkosten, Übernachtung, Verpflegung, Bewirtung, Parken/Maut, Sonstiges), inkl. Kilometerpauschale mit automatischer Berechnung (km × Satz)
- **Verpflegungspauschalen** als eigene Kategorie (Betrag frei wählbar)
- **PDF-Export**: Deckblatt mit Kostenaufstellung, Summen und Unterschriftsfeldern sowie alle Beleg-Fotos als Anlagen (ein Beleg pro Seite)
- **Automatische Speicherung**: alle Daten bleiben lokal im Browser (IndexedDB) erhalten – nichts verlässt das Gerät

## Nutzung

Einfach `index.html` im Browser öffnen – z. B. per Doppelklick oder über einen beliebigen Webserver:

```bash
python3 -m http.server 8000
# dann http://localhost:8000 öffnen
```

Auf dem Smartphone: Seite öffnen, bei „Beleg fotografieren“ tippen – die Kamera öffnet sich automatisch.

## Ablauf

1. Reisedaten eintragen
2. Für jede Ausgabe eine Position anlegen und den Beleg fotografieren
3. Positionen prüfen (bearbeiten/löschen möglich)
4. „PDF erstellen“ – die fertige Abrechnung wird heruntergeladen
5. „Neue Abrechnung starten“ löscht die Reisedaten für die nächste Reise (Name und Kostenstelle bleiben erhalten)

## Technik

- Reines HTML/CSS/JavaScript, keine Build-Tools
- [jsPDF](https://github.com/parallax/jsPDF) (lokal in `vendor/` eingebunden) für die PDF-Erzeugung
- IndexedDB (mit localStorage-Fallback) für die lokale Datenhaltung

## Weitere Anwendung: Fachliche Anforderungen erfassen

Im selben Repository liegt eine eigenständige Web-App zur Erfassung fachlicher
Anforderungen: [`anforderungen.html`](anforderungen.html)
(Live: https://liebemichael1972-cell.github.io/reisekostenabrechnung/anforderungen.html).

- Projektkopf (Name, Autor, Version, Datum, Ziel) erfassen
- Anforderungen mit Titel, Beschreibung, Kategorie, MoSCoW-Priorität
  (Muss/Soll/Kann/Abgrenzung), Stakeholder und Akzeptanzkriterien anlegen,
  bearbeiten und löschen
- Live-Vorschau des erzeugten **Markdown-Dokuments**
- Export als `.md`-Datei zum Download oder Kopieren in die Zwischenablage
- Automatische lokale Speicherung im Browser (localStorage) – nichts verlässt das Gerät

Ebenfalls reines HTML/CSS/JavaScript, ohne Build-Tools und ohne Server.
