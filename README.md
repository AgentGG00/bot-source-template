# bot-source-template

Private Vorlage für eine `bot-core`-Source. Aus diesem Template wird pro Anwendung ein eigenes
privates Repo erzeugt (z. B. `bot-source-ha-compose`).

## Aufbau
src/scripts/ # backup.sh, restore.sh, update.sh, check-*.sh
config/
source.yaml # Buttons, Scheduler-Regeln, Sperrfenster, Update-Ziele
prompt.md # Aufgabe für den LLM-Provider
context.md # laufende Integrationen, Besonderheiten
.env.example

## Nutzung
1. Template auf GitHub nutzen → neues **privates** Repo erzeugen
2. `.env.example` zu `.env` kopieren und mit echten Werten füllen
3. `config/source.yaml`, `config/prompt.md`, `config/context.md` für die Anwendung anpassen
4. Skripte in `src/scripts/` an die konkreten Pfade/Container anpassen
5. `bot --source /pfad/zu/diesem/repo` starten

## License
MIT, siehe [LICENSE](./LICENSE) – nur relevant, falls eine aus diesem Template erzeugte Source
später doch veröffentlicht wird.