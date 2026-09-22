# Projekt-Plan – bot-source-template

## Kurzbeschreibung
Dies ist kein fertiges Repo, sondern der **Entwurf einer Vorlage**: die Grundstruktur, die jede
zukünftige `bot-core`-Source haben soll. Aus diesem Entwurf wird pro Anwendung ein eigenes
privates Repo erzeugt, das dann `main.go`, `config/source.yaml` etc. mit echtem Inhalt füllt –
das Template selbst bleibt Platzhalter/Doku.

## Ziele & Anforderungen
- Entwurf für eine gleiche Grundstruktur, an der sich jede neue Source orientiert
- Kein eigener Code im Entwurf – nur Doku, die beschreibt was in der jeweiligen Source reinkommt
- Klare Trennung möglicher Feature-Bereiche als Entwurf vorgeben (versionsmanagement, security, console)
- Secrets-Konvention als Entwurf festlegen: ausschließlich lokal in `.env`, nie im Repo

## Tech-Stack
Kein eigener Techstack im Entwurf selbst. Konkrete Source-Repos, die daraus entstehen: Go,
importieren `bot-core` als Dependency (`go get github.com/AgentGG00/bot-core@latest`).

## Grobe Projektstruktur (Entwurf)
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
