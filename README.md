# Atemschutz-Logbuch

Offline-Web-App für Inventur und Tausch von Pressluftatmern, Masken und Atemluftflaschen.

## Aufs Handy bringen
Die App muss einmal über eine https-Adresse geöffnet werden, danach läuft sie offline.

**Am einfachsten (Netlify Drop, kostenlos):**
1. https://app.netlify.com/drop öffnen
2. Den ganzen Ordner `atemschutz-logbuch` hineinziehen
3. Die angezeigte Adresse am Handy öffnen
4. iPhone: Teilen → „Zum Home-Bildschirm“ · Android: Menü → „App installieren“

Alternativ: GitHub Pages oder jeder andere Webspace.

## Wichtig zu den Daten
- Die Daten liegen nur im Browser des Geräts, nicht auf einem Server.
- Regelmäßig unter **Export → Sicherung speichern** sichern (JSON-Datei).
- Mit **Sicherung laden** lassen sich Daten wiederherstellen oder auf ein anderes Gerät übertragen.

## Export
- **CSV** (öffnet in Excel, Semikolon-getrennt): Geräteliste, Tauschvorgänge, Inventuren
- **PDF**: Tauschprotokoll, Inventurprotokoll, Bestandsliste, Prüffristen (über den Druckdialog „Als PDF sichern“)
