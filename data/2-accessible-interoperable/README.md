# Topic 2 — Accessible & Interoperable: demo dati

Faili, uz kuriem atsaucas 2. sesijas slaidi (Accessible & Interoperable — pieejami un sadarbspējīgi). Tie demonstrē trīs galvenās tēmas: DOI satura sarunas (DOI content negotiation), OAI-PMH repozitorija profilu un F-UJI FAIR novērtējuma ziņojumu.

## DOI satura sarunas (Block 2.2)

Tā pati QVUERT datu kopa iznāk dažādos formātos atkarībā no `Accept:` HTTP galvenes, ko klients sūta uz DOI URL.

| Fails | `Accept:` galvene | Saturs |
|-------|-------------------|--------|
| [`qvuert-doi.bib`](qvuert-doi.bib) | `application/x-bibtex` | BibTeX ieraksts citēšanai LaTeX dokumentos |
| [`qvuert-doi-csl.json`](qvuert-doi-csl.json) | `application/vnd.citationstyles.csl+json` | Citation Style Language JSON — Zotero/Mendeley standartu pamats |
| [`qvuert-doi-datacite.xml`](qvuert-doi-datacite.xml) | `application/vnd.datacite.datacite+xml` | DataCite kanoniskais XML profils |

**Demo loģika:** ar `curl -H "Accept: ..."` pret `https://doi.org/...` lecturer parāda, kā viens DOI iznāk vairākos formātos atkarībā no klienta vajadzībām (`A1.1` apakšprincips — atvērts un dokumentēts protokols).

## OAI-PMH repozitorija profils (Block 2.2)

| Fails | Formāts | Saturs |
|-------|---------|--------|
| [`dataverse-lv-oai-identify.xml`](dataverse-lv-oai-identify.xml) | OAI-PMH Identify atbilde | dataverse.lv repozitorija profils — ievākšanas granularitāte, kompresija, repozitorija nosaukums, baseURL |

**Demo loģika:** OAI-PMH `verb=Identify` atklāj repozitorija pamatprofilu. Šis ir vēsturisks snapshot, ne live; lecturer skaidro, ko nozīmē `granularity: YYYY-MM-DDThh:mm:ssZ` un `compression: gzip,deflate`.

## Trīs paralēlie eksporti (Block 2.2 walk-through)

| Fails | Formāts | Loma |
|-------|---------|------|
| [`qvuert-dataverse-json.json`](qvuert-dataverse-json.json) | dataverse_json (Dataverse-native) | Dataverse iekšējais formāts — visdetalizētākā lauku struktūra |
| [`qvuert-oai-ore.json`](qvuert-oai-ore.json) | OAI-ORE Resource Map | Resursu kopas (datu kopa + faili + saites) graf-fragments |

## F-UJI FAIR ziņojums (Block 2.5)

| Fails | Formāts | Saturs |
|-------|---------|--------|
| [`qvuert-fuji-report.html`](qvuert-fuji-report.html) | HTML | F-UJI ziņojuma cilvēklasāmais skats — 12 metrikas, kopvērtējums |
| [`qvuert-fuji-report.json`](qvuert-fuji-report.json) | F-UJI JSON | Mašīnlasāmais skats — tas pats saturs ar metriku ID, debug info |

**Datu kopa:** QVUERT, dataverse.lv. **Snapshot datums:** 2026-04-27.
**Galvenie skaitļi:** F=100 %, A=100 %, I=66.67 %, R=100 %, FAIR kopējais=92.31 %. Vienīgā kritušā metrika: `FsF-I2-01M` (vārdnīcu izmantošana) — pedagoģiskais kāpņu mērķis 3. sesijā.

## Saistītie praktiskie uzdevumi

- [Praktiskais uzdevums 2.5](../../../practice/2-accessible-interoperable/) — F-UJI ziņojuma walk-through
