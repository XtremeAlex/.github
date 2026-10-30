# `.ai/` — governance centrale GitHub (XtremeAlex)

Questo repo speciale (`XtremeAlex/.github`) è il **cervello** di tutti i repository dell'account.

- `core.md` — costituzione: identità, sanitizzazione, convenzioni (commit/branch/naming/licenze), gate, agenti
- `flussi.md` — feature/release flow, caller CI, protection rules, checklist nuovo progetto, info flow
- `registro-repo.md` — inventario dei 42 repo: famiglie, licenze, stato, debolezze aperte

## Come un repo consuma questa governance

1. **Health file di default** (CONTRIBUTING, SECURITY, CODE_OF_CONDUCT, SUPPORT, template PR/issue):
   GitHub li mostra automaticamente nei repo pubblici dell'account che non ne hanno di propri.
2. **AGENTS.md sottile** in ogni repo: punta a `.ai/core.md` e `.ai/flussi.md`
   (lo scrive `~/_DEV/Personale/github/scripts/sync-standards.sh`).
3. **Workflow riusabili** (`.github/workflows/reuse-*.yml`): i repo li chiamano con 5 righe
   (esempio in `flussi.md` §3) e ottengono secret scan + commit lint senza copiare YAML.
4. **Regole progetto-specifiche**: stanno nel `.ai/` del singolo repo (modelli: `rack_19`, `sitoweb`).
   Qui solo le regole comuni.

## Aggiornare il sistema

Si modifica solo qui; i puntatori nei repo non cambiano mai. Il registro va riallineato a ogni
nuovo repo o cambio di stato (`gh repo list XtremeAlex`).
