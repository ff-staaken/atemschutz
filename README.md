# Atemschutz-Logbuch

Web-App der FF Staaken für Inventur und Tausch der Atemschutztechnik: Pressluftatmer, Fluchthauben, Masken (M/S), Filter, CO-Warner, Mehrgasmessgeräte und Sonstiges – pro Fahrzeug, wie in der Inventarliste.
Läuft im Browser am Handy, auch offline.

**App:** https://ff-staaken.github.io/atemschutz/

## Aufs Handy bringen
1. Die Adresse oben am Handy öffnen.
2. iPhone (Safari): Teilen → „Zum Home-Bildschirm“ · Android (Chrome): Menü → „App installieren“.

## Einrichtung (wie bei der Kantine)

| Teil | Wo | Inhalt |
|---|---|---|
| Die App | öffentliches Repository `atemschutz` (GitHub Pages) | nur Programmcode, keine Daten |
| Die Daten | **privates** Repository `atemschutz-daten` | Bestand, Tauschvorgänge, Inventuren, Benutzer, Unterschriften – **verschlüsselt** |

**Wer darf was?**

| Rolle | Darf |
|---|---|
| **Admin** | alles, dazu Benutzer verwalten, Einstellungen, Datei laden, Gerät trennen |
| **Gerätewart** | Tausch, Inventur, Bestand und Geräte pflegen, Exporte |

### 1. Zugangsschlüssel (einmal, durch den Admin)
GitHub → *Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token*
- **Resource owner:** `ff-staaken` · **Expiration:** längste Dauer (im Kalender notieren)
- **Repository access:** *Only select repositories* → `atemschutz-daten`
- **Permissions → Contents:** *Read and write*

### 2. Erstes Gerät
1. App öffnen → **Mehr → Gemeinsame Daten** → Zugangsschlüssel und ein **Atemschutz-Passwort** (mindestens 10 Zeichen) → **Verbinden** → Passwort wiederholen → **Gemeinsame Daten anlegen**.
2. **Mehr → Benutzer:** dich selbst als Admin anlegen.
3. Alle Gerätewarte mit Namen und erstem Passwort hinzufügen.
4. Einmalig die Startdatei mit der Inventarliste über **Mehr → Datei laden** einlesen.

> Das **Atemschutz-Passwort gut aufbewahren** (z. B. verschlossen bei der Wehrführung). Ohne es sind die Daten auf neuen Geräten nicht lesbar.

### 3. Weitere Handys
App öffnen → **Mehr → Gemeinsame Daten** → Zugangsschlüssel + Atemschutz-Passwort → **Verbinden**.
Das macht der Admin oder er gibt beides an die Person weiter. Danach meldet sich jede Person mit **Namen und eigenem Passwort** an.
Auf den Homescreen legen: iPhone *Teilen → Zum Home-Bildschirm*, Android *Menü → App installieren*.

- **Passwort vergessen:** Admin → Mehr → Benutzer → „Passwort“.
- **Person ausgeschieden:** Admin → „Deaktivieren“. Ihre Einträge bleiben mit Namen erhalten.
- **Handy verloren:** Zugangsschlüssel auf GitHub löschen, neuen erzeugen, übrige Geräte neu verbinden.

## So funktioniert der Abgleich
- Die Daten liegen verschlüsselt in `inventar.enc.json`, Unterschriften verschlüsselt im Ordner `unterschriften/`.
- Jede Änderung wird sofort auf dem Handy gespeichert und nach wenigen Sekunden mit GitHub abgeglichen.
- Ohne Netz werden Änderungen gesammelt und automatisch hochgeladen, sobald wieder Verbindung besteht.
- Ändern zwei Personen dasselbe Gerät, gilt die neuere Änderung. Der Verlauf beider Änderungen bleibt erhalten.
- Jede Änderung ist im Daten-Repository mit Name und Zeitpunkt nachvollziehbar (Commit-Verlauf).

## Bestand übernehmen
Die bestehende Inventarliste wird einmalig über **Mehr → Datei laden** eingelesen (Startdatei `.json`).
Die Startdatei gehört **nicht** in dieses öffentliche Repository.

## Export
- **Inventarliste als Excel (.xlsx)** im Aufbau der bisherigen Liste, Fälliges gelb, Abgelaufenes rot
- **PDF**: Inventarliste, Fälligkeiten, Tausch- und Inventurprotokolle (Druckdialog → „Als PDF sichern“)
- **CSV**: Tauschvorgänge

## Datumsangaben
Alle Monatsangaben (z. B. `11/26`) bedeuten: gültig bis Ende dieses Monats.

## Tausch
Was vom Fahrzeug runterkommt, geht an die Atemschutzwerkstatt bzw. ist verbraucht und wird ausgebucht (Verlauf bleibt erhalten).
Ersatz kommt aus dem Pool. Neue Geräte von der Werkstatt im **Pool** mit „+ Gerät“, Masken/Hauben/Filter mit „+ Bestand“ anlegen.

## Rechtliches
[Impressum](impressum.html) · [Datenschutz](datenschutz.html)
