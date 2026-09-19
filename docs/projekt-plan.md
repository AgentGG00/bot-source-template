# Projekt-Plan – bot-source-template

## Kurzbeschreibung
Privates GitHub-Template für Sources von `bot-core`. Definiert die einheitliche Ordnerstruktur
und Platzhalter, aus denen pro Anwendung ein eigenes privates Repo erzeugt wird.

## Ziele & Anforderungen
- Gleiche Struktur für jede Source, damit der Core sie ohne Anpassung laden kann
- Kein eigener Code, nur Config (YAML/Markdown) und Bash-Skripte
- Secrets ausschließlich lokal in `.env` auf dem Server, nie im Repo

## Tech-Stack
Kein eigener Techstack – Bash-Skripte und YAML/Markdown-Config, ausgeführt vom `bot-core`-Binary.

## Grobe Projektstruktur
bot-source-template/
├── src/scripts/
├── config/
├── docs/
├── .env.example .gitignore README.md LICENSE projekt-plan.md projekt-stand.md

## Rahmenbedingungen
- Repo: privat, GitHub-Template, MIT-Lizenz (nur falls später doch veröffentlicht)
- Branch: nur `main`, kein `dev`
- Kein CI/CD, keine Badges (privates Repo)

## Secrets-Übersicht
Nur als Platzhalter in `.env.example`, echte Werte nie im Repo:

TELEGRAM_BOT_TOKEN=xxxxxxx
TELEGRAM_CHAT_ID=xxxxxxx
TOTP_SECRET=xxxxxxx
OLLAMA_HOST=xxxxxxx
HA_LONG_LIVED_TOKEN=xxxxxxx

