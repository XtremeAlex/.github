# Flussi di lavoro Git — standard XtremeAlex

Dettaglio operativo dei flussi citati in `core.md`. Vale per tutti i repo dell'account.

## 1. Feature flow (lavoro quotidiano)

```bash
git checkout develop && git pull
git checkout -b feature/<slug>          # solo per lavori grandi; fix piccoli diretti su develop
# commit convenzionali: feat(scope): ..., fix: ..., docs: ...
git push -u origin feature/<slug>
gh pr create --base develop --title "feat(scope): titolo convenzionale"
# gate: CI verde + template PR compilato -> merge (squash per storie pulite)
```

## 2. Release flow

```bash
gh pr create --base main --head develop --title "release: vX.Y.Z"
# gate completi + review -> merge -> tag
git checkout main && git pull && git tag -a vX.Y.Z -m "vX.Y.Z" && git push origin vX.Y.Z
```

SemVer: MAJOR breaking, MINOR feature, PATCH fix. Le pre-release usano `-rc.N`.

## 3. Gate CI (workflow riusabili centrali)

Caller in un repo qualsiasi — `.github/workflows/ci.yml`:

```yaml
name: CI
on:
  pull_request:
  push: { branches: [develop, main] }
jobs:
  secrets:
    uses: XtremeAlex/.github/.github/workflows/reuse-secret-scan.yml@main
  commits:
    uses: XtremeAlex/.github/.github/workflows/reuse-commit-lint.yml@main
    secrets: inherit
```

- `reuse-secret-scan.yml` — gitleaks su tutta la storia: un segreto in qualsiasi commit blocca la PR.
- `reuse-commit-lint.yml` — titolo PR convenzionale (diventa il messaggio di squash-merge).

## 4. Protection rules (una tantum per repo, da interfaccia)

Repo con CI attiva (partendo dai pubblici più visibili):

1. Settings → Branches → Add rule su `main`: require PR, require status checks (secret-scan, commit-lint), no force push.
2. Regola analoga su `develop` solo per i repo con collaboratori esterni.
3. Settings → General → Pull Requests: disabilita merge commit, tieni **squash** (e rebase).

## 5. Archive flow (storici)

Vecchie copie/funzionanti: branch `archive/AAAA-MM-GG-<slug>` (data = ultimo lavoro), locali.
Push solo se serve backup remoto: `git push origin archive/<nome>`.

## 6. Nuovo progetto (checklist enterprise)

1. Scaffold: `~/_DEV/Personale/_templates/project-template/init-project.sh <path>`.
2. `git config --local` identità personale (vedi `core.md` §1).
3. `LICENSE` secondo la famiglia (registro-repo.md) + riga nel registro.
4. `AGENTS.md` sottile: puntatore a questo repo (lo scrive `sync-standards.sh`).
5. Caller CI (§3) appena il repo ha test o è pubblico.
6. Description + topics su GitHub (il portfolio li raccoglie da solo).
7. `gh repo create` **privato**; pubblico solo dopo scansione storia (core.md §1).

## 7. Info flow (chi sa cosa, dove)

| Informazione | Sede |
|---|---|
| Regole comuni (queste) | `XtremeAlex/.github` → `.ai/` |
| Regole di un progetto | `.ai/` + `AGENTS.md` di quel repo |
| Stato e famiglie dei repo | `.ai/registro-repo.md` (aggiornato a ogni cambio) |
| Decisioni storiche | `_GITHUB_INDICAZIONI.md` (locale, mai sensibile) |
| Vetrina pubblica | `xtremealex.github.io` (automatica) + `XtremeAlex/XtremeAlex` (profilo) |
