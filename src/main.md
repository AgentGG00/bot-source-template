# main.go – Anleitung

Diese Datei beschreibt, was ins echte `src/main.go` der konkreten Anwendung kommt. Es gibt hier
absichtlich kein lauffähiges `main.go` – das entsteht erst im konkreten Source-Repo, abhängig
davon welcher Bereich unter `src/features/` genutzt wird.

## Was `bot-core` bereitstellt
- `core/telegram` – Bot-Anbindung, Long Polling, Chat-ID-Whitelist
- `core/auth` – TOTP-Login, Session, Step-up-Verifizierung
- `core/lockdown` – Kill-Switch-Check (`state/lockdown.flag`)
- `core/mask` – Secret-Maskierung für ausgehende Nachrichten
- `core/state` – SQLite-Init für Sessions/Replay-Schutz

## Minimal-Gerüst (Beispiel, kein echter Code)

    package main

    import (
        "github.com/AgentGG00/bot-core/src/core/auth"
        "github.com/AgentGG00/bot-core/src/core/lockdown"
        "github.com/AgentGG00/bot-core/src/core/mask"
        "github.com/AgentGG00/bot-core/src/core/state"
        "github.com/AgentGG00/bot-core/src/core/telegram"

        // TODO: eigenes Feature-Paket importieren, z.B.
        // "github.com/<org>/<source-repo>/src/features/versionsmanagement"
    )

    func main() {
        // TODO: .env laden (Telegram-Token, Chat-ID, TOTP-Secret)
        // TODO: state.Init(...) für Sessions
        // TODO: telegram.New(...)
        // TODO: Polling-Loop mit lockdown.IsLocked(...)-Check
        // TODO: eigenes Feature-Paket verdrahten
    }

## Wichtig
- Lockdown-Check gehört an den Anfang jeder Update-Verarbeitung im Polling-Loop (fail-closed)
- Alle ausgehenden Telegram-Nachrichten laufen automatisch durch `mask.Masker` (in `telegram.Bot`
  bereits eingebaut)
