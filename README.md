# Completionist NG — Traduzione italiana / Italian Localization

**Fork sorgente della localizzazione italiana di Completionist NG per Skyrim Special Edition e Anniversary Edition.**

**English:** This repository contains the source fork for Italian-localized text in the Completionist NG native plugin. The original mod and the separate Italian translation package are available on Nexus Mods. This repository is not a ready-to-install translation package.

**Collegamenti principali**

- [Scarica la traduzione italiana — Nexus Mods](https://www.nexusmods.com/skyrimspecialedition/mods/192318)
- [Completionist NG originale — Nexus Mods](https://www.nexusmods.com/skyrimspecialedition/mods/46358)
- [Codice sorgente originale — Faen668/Completionist-NG](https://github.com/Faen668/Completionist-NG)
- [Sorgenti del fork italiano — falker47/Completionist-NG-Italian](https://github.com/falker47/Completionist-NG-Italian)

## Il progetto

**Completionist NG**, sviluppato da **Faen90 / Faen668** e dai contributori del progetto originale, è una mod per Skyrim che permette di monitorare missioni, oggetti, collezionabili e altre attività di completamento attraverso un'interfaccia integrata nel gioco.

Questo repository è un fork realizzato per rendere disponibili le modifiche al codice C++ relative alla localizzazione italiana della DLL.

La traduzione distribuita separatamente su Nexus Mods è curata da **falker47 (Maurizio Falconi)** e si rivolge ai giocatori che utilizzano Skyrim in italiano.

Il fork non introduce un nuovo sistema di tracciamento e non rivendica lo sviluppo delle funzionalità di Completionist NG. Il codice originale e la relativa evoluzione appartengono al progetto upstream.

### Due risorse con scopi diversi

| Risorsa | Contenuto |
|---|---|
| Completionist NG originale | Mod e funzionalità di tracciamento sviluppate dal progetto upstream |
| Traduzione italiana su Nexus | Pacchetto installabile di localizzazione per la versione supportata |
| Questo repository GitHub | Sorgenti upstream e modifiche C++ del fork italiano, con documentazione di provenienza e licenza |

**Per utilizzare la traduzione in gioco occorre scaricare il pacchetto Nexus.** Il solo checkout di questo repository non costituisce un'installazione della traduzione.

## Installazione

La traduzione italiana pubblicata come versione **1.0** è destinata a **Completionist NG 5.0.0.4**.

1. Installa [Completionist NG originale](https://www.nexusmods.com/skyrimspecialedition/mods/46358) con il tuo mod manager.
2. Se utilizzi [Completionist Addons](https://www.nexusmods.com/skyrimspecialedition/mods/112406), considera che le integrazioni italiane incluse nella traduzione sono basate sulla versione **3.0.0**. Non presumere la compatibilità con versioni successive.
3. Scarica dalla [pagina Nexus della traduzione italiana](https://www.nexusmods.com/skyrimspecialedition/mods/192318) il pacchetto principale **Completionist Skyrim Completion Tracker ITA**.
4. Installa la traduzione dopo la mod originale e, quando presenti, dopo gli Addons compatibili. In caso di conflitti relativi ai file tradotti, lascia prevalere quelli della traduzione italiana.
5. Abilita `Completionist ITA.esp` e assicurati che venga caricato dopo `Completionist.esp`.

Completionist Addons è opzionale: la traduzione principale può essere utilizzata senza installarlo.

Per i requisiti e la configurazione della mod originale, consulta la sua pagina Nexus. Le istruzioni di installazione riportate qui derivano dalla documentazione della distribuzione italiana e non costituiscono una nuova verifica in gioco.

## Compatibilità e requisiti

La mod originale richiede:

- **Skyrim Special Edition / Anniversary Edition**, in una versione supportata dalla release originale.
- **SKSE64**, compatibile con il runtime Skyrim installato.
- **Address Library for SKSE Plugins**.
- **PapyrusUtil SE**.
- **SkyUI**, utilizzato per l'interfaccia MCM.

Questi sono requisiti della mod originale, non nuove dipendenze introdotte dal codice italiano.

La pagina Nexus della traduzione documenta una release candidate testata in **Skyrim Anniversary Edition**, comprendente verifiche di MCM, missioni, notifiche e stati del tracker. La stessa pagina indica che la build finale contiene ulteriori stringhe localizzate nella DLL.

Non è disponibile in questo repository una matrice di test indipendente per le singole versioni del runtime Skyrim, di SKSE o per Skyrim VR.

**Le impostazioni di compilazione per SE, AE e VR presenti nel progetto C++ non dimostrano, da sole, la compatibilità delle relative build con il pacchetto italiano pubblicato.**

## Cosa viene tradotto

La distribuzione Nexus descrive la localizzazione delle seguenti componenti:

- Menu MCM, sezioni e pagine del tracker.
- Stati di completamento e raccolta.
- Tooltip e altri testi dell'interfaccia.
- Notifiche e messaggi visualizzati durante il gioco.
- Stringhe presenti negli script Papyrus.
- Testi generati direttamente dalla DLL.
- Titoli di missioni vanilla e DLC.
- Integrazioni selezionate di Completionist Addons 3.0.0.

Questo elenco descrive **l'ambito dichiarato del pacchetto Nexus**, non l'insieme delle traduzioni presenti nel checkout GitHub.

### Modifiche C++ verificabili

Rispetto al commit upstream utilizzato come base della localizzazione, il fork contiene cinque sostituzioni testuali in due file.

**`src/Internal Utility/Variables.cpp`**

| Testo originale | Testo italiano |
|---|---|
| `Need It!` | `Da ottenere!` |
| `Got It!` | `Ottenuto!` |
| `Displayable!` | `Esponibile!` |
| `Displayed!` | `Esposto!` |

Queste stringhe sono valori predefiniti utilizzati dagli indicatori di stato degli oggetti nell'interfaccia.

**`src/Internal Utility/MCMHandler.cpp`**

Il formato del riepilogo di completamento passa da:

`{}/{} - {}% Completed`

a:

`{}/{}: {}% completato`

Le modifiche riguardano testo visualizzato, senza introdurre nuova logica di tracciamento rispetto alla revisione upstream di riferimento.

### Limiti del contenuto presente su GitHub

La struttura `src/Papyrus/Release/` deriva dal progetto originale e non rappresenta integralmente il pacchetto italiano disponibile su Nexus.

In particolare:

- Il file `src/Papyrus/Release/Interface/Translations/completionist_italian.txt` presente nel repository coincide con il corrispondente file inglese.
- Gli script Papyrus presenti nel checkout conservano i testi upstream.
- Il repository contiene `Completionist.esp`, ma non il distinto `Completionist ITA.esp` descritto dalla distribuzione italiana.
- Non è presente un archivio installabile della traduzione italiana né una release GitHub che lo contenga.

Per questo motivo, **il repository documenta le modifiche sorgente della DLL, ma non costituisce una riproduzione integrale dei file localizzati distribuiti su Nexus**.

La corrispondenza tra la DLL contenuta nel pacchetto Nexus e una compilazione ottenuta da questo sorgente non è attestata da una build riproducibile verificata nel repository.

## Funzionalità di Completionist NG

Le funzionalità seguenti appartengono al **progetto originale** e non sono state introdotte dal fork italiano.

### Missioni e progressione

Completionist permette di monitorare le missioni supportate di Skyrim, comprese le quest principali, secondarie, delle fazioni e dei DLC.

Il framework comprende la gestione di missioni ripetibili e di condizioni particolari di completamento, oltre al supporto per contenuti aggiuntivi attraverso i relativi dati di tracciamento.

### Oggetti e collezionabili

Il sistema originale monitora diverse categorie di contenuti, tra cui libri, armi, armature, oggetti unici, luoghi, urli e altri elementi supportati.

Il tracciamento può essere esteso mediante patch e dati aggiuntivi compatibili.

### Interfaccia MCM

L'integrazione con SkyUI offre pagine per consultare gli elementi monitorati, visualizzare gli stati di completamento e configurare le funzioni disponibili.

La struttura e il comportamento delle pagine dipendono dal progetto upstream e dalle patch effettivamente installate.

### Inventario e indicatori contestuali

Completionist include integrazioni con l'inventario e con il testo contestuale visualizzato nel mirino (*crosshair tags*).

Queste funzioni permettono di mostrare informazioni relative alla raccolta e, nelle configurazioni supportate, allo stato degli oggetti esponibili.

Le quattro stringhe localizzate in `Variables.cpp` appartengono proprio a questo ambito.

Per l'elenco completo e aggiornato delle funzionalità, delle integrazioni e delle limitazioni, consulta la [documentazione della mod originale](https://www.nexusmods.com/skyrimspecialedition/mods/46358).

## Sorgenti e compilazione

Il progetto conserva la struttura C++ di Completionist NG.

I principali file di configurazione sono:

- [`CMakeLists.txt`](CMakeLists.txt) — definizione del progetto e delle dipendenze native.
- [`CMakePresets.json`](CMakePresets.json) — preset di configurazione per le diverse varianti Skyrim.
- [`vcpkg.json`](vcpkg.json) — manifest delle dipendenze gestite con vcpkg.
- [`!Update.ps1`](!Update.ps1) — script PowerShell utilizzato dal processo di generazione e dalle operazioni successive alla compilazione.

### Ambiente previsto

La configurazione presente nel repository richiede o prevede:

- Windows e **Visual Studio 2022**, secondo il generatore indicato nei preset.
- **CMake 3.21** o successivo.
- **C++23**.
- **vcpkg**, con variabile d'ambiente `VCPKG_ROOT`.
- **CommonLibSSE-NG**, tramite `CommonLibSSEPath`.
- **DKUtil**, tramite `DKUtilPath`.
- **spdlog** e **xbyak**, dichiarati nel manifest vcpkg.
- **PowerShell**, invocato durante la configurazione e dopo la build.

Sono definiti i preset `AE`, `SE`, `VR`, `ALL`, `PRE-AE` e `FLATRIM`.

La compilazione è configurata per essere eseguita fuori dalla directory sorgente. Lo script `!Update.ps1` genera l'elenco dei sorgenti e gestisce anche operazioni successive alla build.

Queste informazioni derivano direttamente dai file di configurazione presenti nel repository.

### Stato delle verifiche

Non sono presenti workflow GitHub Actions, suite di test automatizzati o release binarie in questo fork.

Non viene pertanto dichiarata una compilazione riuscita o una procedura di build riproducibile certificata. Chi intende ricompilare il progetto deve predisporre le dipendenze richieste ed esaminare gli script di build prima dell'esecuzione.

La versione `7.0.0.1` presente nei manifest CMake/vcpkg è un identificativo della configurazione sorgente e **non deve essere confusa** con la versione Completionist 5.0.0.4 a cui è destinata la traduzione Nexus.

## Licenza e attribuzione

Il repository contiene il testo della **GNU General Public License versione 3** e le eccezioni riprese dal progetto upstream.

La documentazione del progetto dichiara l'applicazione della **GPL-3.0-or-later**, insieme alle seguenti eccezioni:

- **Modding Exception**.
- **GPL-3.0 Linking Exception (with Corresponding Source)**.

Per i termini completi consulta:

- [`LICENSE`](LICENSE)
- [`EXCEPTIONS.md`](EXCEPTIONS.md)
- [`README.txt`](README.txt), che conserva l'avviso di provenienza e licenza della localizzazione.

Le eccezioni contengono disposizioni specifiche per il collegamento con codice modificato e librerie di modding, inclusi requisiti relativi al sorgente corrispondente.

Non sostituiscono il testo integrale della GPL né autorizzano automaticamente la redistribuzione di tutti gli asset di terzi.

Le condizioni relative ai materiali del gioco, alle risorse di altri autori e ai pacchetti Nexus devono essere considerate separatamente, secondo i diritti e le autorizzazioni applicabili.

### Copyright e crediti

**Progetto originale**

Completionist NG — Copyright © Faen90 / Faen668 e rispettivi contributori.

Sorgente originale: https://github.com/Faen668/Completionist-NG

**Localizzazione italiana**

Modifiche italiane — Copyright © 2026 Maurizio Falconi (`falker47`).

Distribuzione: https://www.nexusmods.com/skyrimspecialedition/mods/192318

**Framework e componenti utilizzati dal progetto originale**

- [CommonLibSSE-NG](https://github.com/alandtse/CommonLibSSE-NG)
- [Skyrim Script Extender (SKSE)](https://skse.silverlock.org/)
- DKUtil, spdlog e le altre dipendenze indicate nei file di build.
- SkyUI, Address Library e PapyrusUtil, secondo i requisiti della mod originale.

I nomi, i marchi e i contenuti di *The Elder Scrolls V: Skyrim* appartengono ai rispettivi titolari.

## Esclusione di garanzia

This program is distributed in the hope that it will be useful, but **WITHOUT ANY WARRANTY**; without even the implied warranty of **MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE**. See the GNU General Public License for more details.

Prima di modificare un'installazione Skyrim esistente, è consigliabile conservare una copia dei salvataggi e della configurazione delle mod.

---

**Completionist NG è il progetto originale di Faen90 / Faen668. Questo repository documenta il fork sorgente relativo alla localizzazione italiana di falker47.**
