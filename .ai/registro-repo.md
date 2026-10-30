# Registro repository — inventario e salute

Aggiornato il 30/10/2026 da `gh repo list` + cloni locali (`~/_DEV/Personale/github/`).
**Da aggiornare** a ogni repo nuovo, rinominato, pubblicato o archiviato.

Legenda stato: `attivo` (lavoro recente) · `pubblicato` (stabile, vetrina) · `in-revisione` (privato, in preparazione alla pubblicazione) · `storico` (fermo, da valutare archiviazione).

## Famiglia EDIFACT (prodotto, monetizzabile → AGPL-3.0 + dual)

| Repo | Visibilità | Stato | Note |
|---|---|---|---|
| xtr-edifact-core | privato | attivo | libreria core; 23 commit locali da creare online |
| xtr-edifact-mcp | pubblico | attivo | MCP EDIFACT |
| xtr-edifact-inspector-ms | pubblico | attivo | |
| xtr-edifact-vscode | pubblico | attivo | estensione VS Code |
| xtr-edifact-desktop | pubblico | attivo | |
| xtr-edifact-android | privato | attivo | |
| xtr-aeroport-edifact-spring-web | pubblico | attivo | 68 commit locali, il più corposo da pubblicare |
| xtr-codecript | pubblico | storico | |

## Famiglia aeroport (microservizi → AGPL-3.0 + dual)

| Repo | Visibilità | Stato | Note |
|---|---|---|---|
| xtr-aeroport-ms | pubblico | pubblicato | rifattorizzato 30/09, test aggiunti |
| xtr-aeroport-batch | pubblico | pubblicato | bonificato IP |
| xtr-aeroport-typology | pubblico | pubblicato | rinominato (era typological) |
| xtr-aeroport-common-lib | pubblico | pubblicato | |
| xtr-aeroport-web-java | pubblico | pubblicato | |
| xtr-aeroport-api-spring | pubblico | attivo | 15 commit locali |
| xtr-aeroport-api-quarkus | pubblico | attivo | |
| PAXLST-Message-Converter | privato | storico | 2019 |

## Famiglia toolkit / openmail / mwo

| Repo | Visibilità | Licenza | Note |
|---|---|---|---|
| xtr-toolkit-hosts | pubblico | MIT/Apache | |
| xtr-toolkit-hosts-macos | pubblico | MIT/Apache | Swift |
| xtr-openmail | pubblico | AGPL-3.0 + dual | da creare online |
| xtr-openmail-macos | pubblico | AGPL-3.0 + dual | |
| api-mwo-profile / app-mwo-profile | pubblico | MIT | MechWarrior Online |
| CertSnatcher | pubblico | Apache-2.0 | Kotlin + estensione Firefox |
| xtr-mcp-mail | privato | da decidere | MCP email multi-provider, nuovo |
| xtr-llm-credits-touchbar | privato | da decidere | in-revisione |
| xtr-simulatorMqtt-ms | privato | da decidere | in-revisione |
| xtr-redline-ha-theme | privato | da decidere | in-revisione (tema HA) |
| xtr-sidebery-conf | privato | da decidere | in-revisione |
| xtr-ai-image | privato | da decidere | in-revisione |
| JavaFx | privato | da decidere | in-revisione |
| xtr-fast-beach-ms / -web | privato | storico | 2024 |

## Guide e documentazione (CC BY 4.0)

| Repo | Stato | Note |
|---|---|---|
| Docker | pubblicato | IP corporate sanitizzato |
| Kubernetes | pubblicato | guida k3s-raspberry aggiunta |
| Linux | pubblicato | |
| Hackintosh | pubblicato | bonificato da 1463 file spazzatura |
| the-scriptorium | pubblicato (Apache) | script utilità |
| nginx_to_docker | pubblicato (MIT) | |

## Siti e vetrina

| Repo | Visibilità | Note |
|---|---|---|
| xtremealex.github.io | pubblico | portfolio automatico (Action giornaliera) |
| XtremeAlex | pubblico | README profilo (branch develop) |
| **.github** | pubblico | **questo repo: governance centrale** |
| sitoweb | privato | 2AD + ComitatoCimina' → *.bubume.it; struttura .ai completa (30/10) |

## Solo locali (mai su GitHub, per scelta)

- `rack_19` (rete di casa + cluster k3s): contiene topologia e indirizzi della rete. Locale per sempre, backup via bundle in `~/_DEV/_backups/`.

## Debolezze aperte (backlog enterprise)

1. 19 repo solo locali o con commit non pushati (elenco in `_STATO_GIT_REPOS.md`): creare/pushare appena utile; i `-manutenzione` da valutare (placeholder?).
2. Nessun repo ha branch protection: checklist in `flussi.md` §4, partire da aeroport-ms e edifact-core.
3. Caller CI assenti: introdurre prima sui repo pubblici più visibili.
4. Description/topics mancanti su molti repo: il portfolio ne risente.
5. Licenze mancanti nei repo "da decidere": scegliere per famiglia (core.md §2) prima della pubblicazione.
