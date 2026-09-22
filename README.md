# bot-source-template

Privates GitHub-Template für Sources von `bot-core`. Alle Dateien hier sind Platzhalter/Doku –
kein lauffähiger Code. Aus diesem Template wird pro Anwendung ein eigenes privates Repo erzeugt
(z. B. `bot-source-ha-compose`), das dann `main.go`, `config/source.yaml` etc. tatsächlich mit
Inhalt füllt.

## Aufbau
- `src/main.md` – Anleitung + Beispiel für das eigene `main.go`, das `bot-core` importiert
- `src/features/versionsmanagement/`, `src/features/security/`, `src/features/console/` – je ein
  Bereich für ein eigenes Feature-Paket; nur der tatsächlich genutzte Bereich wird mit Code gefüllt
- `config/source.md` – erklärt, wie das feature-spezifische Config-Schema aussehen muss
- `config/prompt.md` – Platzhalter für den LLM-Prompt (nur relevant fürs versionsmanagement-Feature)
- `config/context.md` – Platzhalter für laufenden Kontext (Integrationen, Besonderheiten)
- `.env.example` – Secrets, die `bot-core` selbst braucht (Telegram, TOTP); feature-spezifische
  Variablen kommen bei Bedarf dazu
- `go.mod` – noch ohne `require`, wird beim Schreiben des echten `main.go` ergänzt

## Nutzung
1. Template auf GitHub nutzen → neues **privates** Repo erzeugen
2. `go get -u github.com/AgentGG00/bot-core@latest` – zieht immer die aktuell getestete Core-Version
3. `src/main.md` lesen und daraus ein echtes `src/main.go` schreiben
4. Passenden Bereich unter `src/features/` mit echtem Code füllen, die anderen beiden Ordner löschen
5. `config/source.md` in ein echtes `config/source.yaml` nach dem dort beschriebenen Schema umsetzen
6. `.env.example` zu `.env` kopieren und mit echten Werten füllen

## License
MIT, siehe [LICENSE](./LICENSE) – nur relevant, falls eine aus diesem Template erzeugte Source
später doch veröffentlicht wird.
