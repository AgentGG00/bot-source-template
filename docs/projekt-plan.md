# Projekt-Plan – bot-source-template

## Kurzbeschreibung
Privates GitHub-Template für Sources von `bot-core`. Enthält ausschließlich Platzhalter/Doku
(.md-Dateien) und Ordnerstruktur – kein lauffähiger Code. Aus dem Template wird pro Anwendung
ein eigenes privates Repo erzeugt, das `bot-core` als Go-Dependency einbindet und sein eigenes
`main.go` + Feature-Paket schreibt.

## Ziele & Anforderungen
- Gleiche Grundstruktur für jede Source, damit neue Anwendungen schnell starten können
- Kein eigener Code im Template selbst – nur Doku, die beschreibt was reinkommt
- Klare Trennung möglicher Feature-Bereiche (versionsmanagement, security, console)
- Secrets ausschließlich lokal in `.env` auf dem Server, nie im Repo

## Tech-Stack
Kein eigener Techstack im Template. Konkrete Source-Repos: Go, importieren `bot-core` als
Dependency (`go get github.com/AgentGG00/bot-core@latest`).

## Grobe Projektstruktur
bot-source-template/
├── src/
│ ├── main.md
│ └── features/
│ ├── versionsmanagement/README.md
│ ├── security/README.md
│ └── console/README.md
├── config/
│ ├── source.md
│ ├── prompt.md
│ └── context.md
├── docs/
├── go.mod
├── .env.example .gitignore README.md LICENSE

## Rahmenbedingungen
- Repo: privat, GitHub-Template, MIT-Lizenz (nur falls später doch veröffentlicht)
- Branch: nur `main`, kein `dev`
- Kein CI/CD, keine Badges (privates Repo)

## Secrets-Übersicht
Nur als Platzhalter in `.env.example`, echte Werte nie im Repo:

TELEGRAM_BOT_TOKEN=xxxxxxx
TELEGRAM_CHAT_ID=xxxxxxx
TOTP_SECRET=xxxxxxx
