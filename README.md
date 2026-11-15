# 🎮 LAN-Lostrommel

Unsere Seite für die LAN-Party: Spiele eintragen, Stimmen vergeben und am LAN-Tag auslosen, was als Nächstes gezockt wird.

**Passwort:** `lan`

## Was die Seite kann
- Eingang nur mit Passwort, dazu Spitzname
- Spiele eintragen (Genre, min./max. Spieler), doppelte Einträge werden abgefangen
- ♥ Stimmen: Wer ein Spiel zocken will, klickt drauf
- **Auslosung** mit Lostrommel: nur Spiele, die zur Spielerzahl passen; Stimmen erhöhen die Chance (abschaltbar); schon Gespieltes wird übersprungen
- „Heute gespielt“-Liste, mit „Neuer LAN-Tag“ wieder leeren

## Gemeinsame Liste für alle (Firebase, kostenlos, ca. 5 Minuten)
Ohne diesen Schritt speichert jeder Browser nur für sich.

1. Auf <https://console.firebase.google.com> mit einem Google-Konto ein neues Projekt anlegen (z. B. `lan-spiele`, Analytics kann aus).
2. Links **Build → Realtime Database → Datenbank erstellen**, Standort *europe-west1*, „Im Testmodus starten“.
3. Unter **Regeln** das hier einfügen und veröffentlichen:
   ```json
   { "rules": { "lan": { ".read": true, ".write": true } } }
   ```
4. **Projekteinstellungen (Zahnrad) → Meine Apps → Web-App (`</>`)** hinzufügen. Firebase zeigt dann ein `firebaseConfig`-Objekt.
5. Diese Werte in `config.js` statt `null` eintragen (Beispiel steht in der Datei) und committen.

Fertig – ab dann sehen alle dieselbe Liste, live.

## Hinweis
Das Passwort ist ein Türsteher für Freunde, kein echter Schutz: Wer den Quelltext liest, kommt auch so rein.
