# source.yaml – Schema-Konvention

Es gibt hier absichtlich kein fertiges `source.yaml` – das Schema hängt vom gewählten Feature-
Bereich ab (`versionsmanagement`, `security`, `console`) und wird von dessen Go-Paket definiert
und geparst.

## Was in jedem Fall sinnvoll ist
- Eine Datei `config/source.yaml`, die vom jeweiligen Feature-Paket beim Start geladen wird
- Secrets werden **nicht** hier reingeschrieben – nur Namen von Env-Variablen, die aus `.env`
  aufgelöst werden (z. B. `bot_token_env: TELEGRAM_BOT_TOKEN`)

## Beispiel für das versionsmanagement-Feature (zur Orientierung, kein fixes Schema)

    telegram:
      bot_token_env: TELEGRAM_BOT_TOKEN
      chat_id_env: TELEGRAM_CHAT_ID
    totp:
      secret_env: TOTP_SECRET
    targets:
      - name: home-assistant
        github_repo: home-assistant/core
        scripts:
          backup: "..."
          restore: "..."
          update: "..."
          check_version: "..."
    lock_windows:
      - name: hacs-fenster
        day: daily
        start: "9:00 PM"
        end: "11:00 PM"
        buffer_before_minutes: 120
        buffer_after_minutes: 30
