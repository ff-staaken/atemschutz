# Atemschutz-Logbuch

Web-App der FF Staaken für Inventur und Tausch von Pressluftatmern, Atemschutzmasken und Atemluftflaschen.
Läuft im Browser am Handy, auch offline.

**App:** https://ff-staaken.github.io/Atemschutz/

## Aufs Handy bringen
1. Die Adresse oben am Handy öffnen.
2. iPhone (Safari): Teilen → „Zum Home-Bildschirm“ · Android (Chrome): Menü → „App installieren“.

## Gemeinsame Daten einrichten (einmalig)
Die Daten aller Gerätewarte liegen im **privaten** Repository `ff-staaken/atemschutz-daten`.
Diese App-Seite hier ist öffentlich, die Daten nicht.

### Für die Organisation (einmal)
1. Privates Repository `atemschutz-daten` in der Organisation `ff-staaken` anlegen (darf leer sein).
2. Unter *Organisation → Settings → Personal access tokens* erlauben, dass Fine-grained Tokens auf Repositories der Organisation zugreifen dürfen
   (je nach Einstellung muss ein Owner jeden neuen Token freigeben).
3. Jeden Gerätewart als Mitglied mit Schreibrecht auf `atemschutz-daten` eintragen.

### Für jede Person (einmal pro Handy)
1. Auf GitHub: *Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token*.
   - **Resource owner:** `ff-staaken`
   - **Expiration:** z. B. 1 Jahr
   - **Repository access:** *Only select repositories* → `atemschutz-daten`
   - **Permissions → Repository permissions → Contents:** *Read and write*
2. Token kopieren (beginnt mit `github_pat_`).
3. In der App: **Mehr → Gemeinsame Daten** → Namen, Token eintragen → **Verbinden**.

Der Token bleibt nur auf diesem Handy gespeichert und erlaubt ausschließlich Zugriff auf das Daten-Repository.
Geht ein Handy verloren: Token auf GitHub löschen.

## So funktioniert der Abgleich
- Jede Änderung wird sofort auf dem Handy gespeichert und nach wenigen Sekunden mit GitHub abgeglichen.
- Ohne Netz werden Änderungen gesammelt und automatisch hochgeladen, sobald wieder Verbindung besteht.
- Ändern zwei Personen dasselbe Gerät, gilt die neuere Änderung. Der Verlauf beider Änderungen bleibt erhalten.
- Jede Änderung ist im Daten-Repository mit Name und Zeitpunkt nachvollziehbar (Commit-Verlauf).
- Unterschriften liegen als Bilder im Ordner `unterschriften/`.

## Export
- **CSV** (Excel, Semikolon-getrennt): Geräteliste, Tauschvorgänge, Inventuren
- **PDF**: Tauschprotokoll, Inventurprotokoll, Bestandsliste, Prüffristen (Druckdialog → „Als PDF sichern“)
