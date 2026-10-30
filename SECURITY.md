# Security Policy

## Segnalare una vulnerabilità

**Non aprire una issue pubblica.** Scrivi in privato tramite GitHub:
[Security Advisories del repo] oppure contatta il proprietario (@XtremeAlex) dal suo profilo.

Tempi attesi: presa in carico entro 7 giorni, piano di fix comunicato entro 14.

## Politica sui segreti

- Credenziali, token, chiavi, URL aziendali, email aziendali e IP privati **non devono mai**
  entrare nel codice, nella storia git, nelle issue o nelle PR.
- Ogni PR passa un secret scan automatico (gitleaks). Se trovi un segreto nella storia,
  segnalalo in privato: la rimozione richiede la riscrittura della storia (filter-repo).
