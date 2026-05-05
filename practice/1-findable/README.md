# Praktiskais uzdevums 1.5 — Bagātā vs minimālā eksportu salīdzinājums

**Sesija:** 1 (F: Atrodami) — 2026-05-05, 10:05–10:25
**Bloks:** 1.5 (20 min)
**Formāts:** Pasniedzējs vada demo, dalībnieki novēro live; nobeigumā multi-select aptauja par mazāko uzlabojumu rīt. Čats sesijas laikā netiek lasīts (auditorijas mērogs ~197).
**Mērķis:** redzēt, kā vienai un tai pašai datu kopai ir vairāki paralēli metadatu eksporti, un kā lauku aizpildīšanas kvalitāte (ne platforma) ietekmē atklājamību

> **Vērtēšanas instrumenti:**
> - Šajā uzdevumā lietojam **detalizētu salīdzinājuma kontrolsarakstu** (4. sadaļa zemāk) — pielāgots empīriskai eksporta struktūras analīzei.
> - Pēc kursa lietojiet **`DataverseLV_kontrolsarakstu_V3.0`** ([lejupielādēt no dataverse.lv](https://dataverse.lv/wp-content/uploads/2025/12/DataverseLV_kontrolsaraksts_V3.0.docx)) — oficiālais VPC publicēšanas pirmskontroles instruments, ko lietojiet katrai jaunai datu kopai pirms publicēšanas.
>
> **Kanoniskie avoti** (`materials/references/dataverse-lv/celvedis/`):
> - FAIR principi: `02-petijumu-planosana/03-fair-principi.md`
> - Metadatu veidi: `05-ilgtermina-saglabasana/01g-metadatu-veidi.md`
> - Metadatu standarti: `05-ilgtermina-saglabasana/01h-metadatu-elementi-un-standarti.md`
> - Pastāvīgie identifikatori: `05-ilgtermina-saglabasana/04-pastavigie-identifikatori.md`

---

## 1. Ko mēs darīsim

Apskatīsim **divas reālas datu kopas no divām dažādiem FAIR repozitorijiem** — vienu ar bagātīgi aizpildītiem metadatiem (dataverse.lv), otru ar minimāli aizpildītiem (Zenodo). Katrai datu kopai apskatīsim **trīs metadatu eksportus**:

- **schema.org JSON-LD** — tas, ko redz Google Dataset Search
- **DataCite XML** — tas, ko redz DOI reģistrs un akadēmiskās citēšanas sistēmas
- **Dublin Core (oai_dc)** — tas, ko redz bibliotēku katalogi un OpenAIRE

Salīdzināsim, kuri lauki ir aizpildīti, kas trūkst, un kāpēc tas ir svarīgi.

> **Kāpēc divas dažādas platformas?** dataverse.lv kopumā tur metadatu kvalitāti vienmērīgi augstu (datu kuratoru darbs un pirms-publicēšanas kontrolsaraksts), tādēļ dabīgā minimāli aizpildītā piemēra _dataverse.lv_ vidē grūti atrast. Minimālo piemēru ņemam no Zenodo (starptautiska FAIR repozitorija, kur autori paši deponē bez kuratora pārbaudes). Bonuss: vienlaikus redzam, ka schema.org / DataCite / Dublin Core ir _platformu-pārskatošas_ standarti — tas pats lauku salīdzinājums strādā jebkurā repozitorijā.

---

## 2. Datu kopas

### 2.1 Bagātā datu kopa

**Nosaukums:** _Biogrāfisko interviju transkripcijas projektā "Konversijas un parāvumi: latviešu filozofijas epistēmiskās stratēģijas padomju periodā (1944-1991)"_

**Autors:** Andrejs Balodis (Latvijas Kultūras akadēmija)

**DOI:** [`10.71782/DATA/QVUERT`](https://doi.org/10.71782/DATA/QVUERT)

**Landing page:** <https://dv.dataverse.lv/dataset.xhtml?persistentId=doi:10.71782/DATA/QVUERT>

### 2.2 Minimālā datu kopa

**Nosaukums:** _Party financial declarations, Latvia, 2002-2024_

**Autors:** Jānis Ikstens (Latvijas Universitāte), ORCID [0000-0003-3191-6305](https://orcid.org/0000-0003-3191-6305)

**DOI:** [`10.5281/zenodo.19311915`](https://doi.org/10.5281/zenodo.19311915)

**Repozitorijs:** Zenodo (CERN-uzturēta, starptautiska)

**Landing page:** <https://zenodo.org/records/19311915>

---

## 3. Eksporta URL — uzziniet, kā paši piekļūt

Abas platformas eksportus piedāvā caur publisko API. Atslēga nav nepieciešama publicētām datu kopām.

### 3.0 dataverse.lv URL formāts

```
https://dv.dataverse.lv/api/datasets/export?exporter={FORMĀTS}&persistentId=doi:{DOI}
```

Iespējamie `{FORMĀTS}` parametri (kopā 11 dataverse.lv 6.7 versijā):

| Parametrs | Formāts | Mērķauditorija |
|-----------|---------|----------------|
| `schema.org` | JSON-LD | Google Dataset Search |
| `Datacite` | XML (DataCite 4) | DOI reģistrs, DataCite Commons |
| `oai_dc` | XML (Dublin Core) | OpenAIRE, BASE, bibliotēkas |
| `oai_datacite` | XML (DataCite + OAI envelope) | OAI-PMH harvestēri |
| `ddi` | XML (DDI Codebook 2.5) | Sociālo zinātņu datu arhīvi |
| `dcterms` | XML (DCMI Terms) | Detalizētāks DC |
| `OAI_ORE` | JSON (resursu karte) | Aglomerāciju harvestēri |
| `dataverse_json` | JSON (Dataverse iekšējais) | Dataverse API klienti |
| `oai_ddi` | XML (DDI + OAI envelope) | DDI harvestēri |
| `html` | HTML | Cilvēklasāms attēlojums |

### 3.0b Zenodo URL formāts

```
https://zenodo.org/records/{RECORD_ID}/export/{FORMĀTS}
```

Galvenie `{FORMĀTS}` parametri Zenodo platformā:

| Parametrs | Formāts | Mērķauditorija |
|-----------|---------|----------------|
| `json-ld` | JSON-LD (schema.org) | Google Dataset Search |
| `datacite-xml` | XML (DataCite 4) | DOI reģistrs, DataCite Commons |
| `dublincore` | XML (Dublin Core) | OpenAIRE, BASE, bibliotēkas |
| `dcat-ap` | XML (DCAT-AP) | EU atvērto datu portāli |
| `marcxml` | XML (MARC 21) | Bibliotēku katalogi |
| `csl` | JSON (CSL) | Citētāji (Zotero, Mendeley) |
| `bibtex` | BibTeX | LaTeX citēšana |
| `json` | JSON (Zenodo iekšējais) | Zenodo API klienti |

> **Pievērsiet uzmanību:** divām platformām ir _atšķirīgi_ URL paterni un _atšķirīgi_ formāta nosaukumi (piem., `oai_dc` vs `dublincore`), bet **iznākumi ir tie paši standarti** — schema.org Dataset, DataCite Schema 4, Dublin Core. Tā ir FAIR principa praktiska izpausme: standarti ir universāli, platformu UI var atšķirties.

### 3.1 Šīsdienas demo URL — 6 saites

**Bagātā kopa (Balodis, dv.dataverse.lv):**

1. <https://dv.dataverse.lv/api/datasets/export?exporter=schema.org&persistentId=doi:10.71782/DATA/QVUERT>
2. <https://dv.dataverse.lv/api/datasets/export?exporter=Datacite&persistentId=doi:10.71782/DATA/QVUERT>
3. <https://dv.dataverse.lv/api/datasets/export?exporter=oai_dc&persistentId=doi:10.71782/DATA/QVUERT>

**Minimālā kopa (Ikstens, Zenodo):**

4. <https://zenodo.org/records/19311915/export/json-ld>
5. <https://zenodo.org/records/19311915/export/datacite-xml>
6. <https://zenodo.org/records/19311915/export/dublincore>

---

## 4. Salīdzinājuma kontrolsaraksts

Sekojiet līdzi sesijas laikā. Pēc katra eksporta atzīmējiet, ko redzat.

### 4.1 Aprakstošie metadati (F2)

| Lauks                      | Bagātā | Minimālā | Piezīmes |
|----------------------------|:------:|:--------:|----------|
| Nosaukums (`name`/`title`) | ☐      | ☐        | Vai ir bilingvāls? |
| Apraksts (`description`)   | ☐      | ☐        | Cik garš? Vai bilingvāls? |
| Apraksta tips (DataCite)   | ☐      | ☐        | Vienkāršs Abstract vai vairāki tipi? |
| Atslēgvārdi (`keywords`)   | ☐      | ☐        | Cik daudz? Cik kvalitatīvi? |
| Tēmas joma (`subject`)     | ☐      | ☐        | Cik plaša/precīza? |

### 4.2 Aģentu identifikatori (F2 layer 2)

| Lauks                  | Bagātā | Minimālā | Piezīmes |
|------------------------|:------:|:--------:|----------|
| Autors ar ORCID        | ☐      | ☐        | Visi autori? Daži? Neviens? |
| Autora piederība       | ☐      | ☐        | Tikai teksts vai ar ROR? |
| Kontaktpersona         | ☐      | ☐        | Skaidri norādīta? |

### 4.3 Atklājamības lauki (F4 — ietekmē Google Dataset Search redzamību)

| Lauks                | Bagātā | Minimālā | Piezīmes |
|----------------------|:------:|:--------:|----------|
| `spatialCoverage`    | ☐      | ☐        | Ģeogrāfija |
| `temporalCoverage`   | ☐      | ☐        | Laika diapazons |
| `funder`             | ☐      | ☐        | Finansējuma avots |
| `variableMeasured`   | ☐      | ☐        | Mērītie mainīgie |
| `version`            | ☐      | ☐        | Versija |

### 4.4 Atkārtotas izmantošanas lauki (R1.1, R1.2 — atgriezīsies vēlāk šodien 4. sesijā)

| Lauks                | Bagātā | Minimālā | Piezīmes |
|----------------------|:------:|:--------:|----------|
| `license`            | ☐      | ☐        | URL formātā? |
| Piekļuves režīms     | ☐      | ☐        | Atvērts / ierobežots |
| Provenance / metode  | ☐      | ☐        | Ietverta `description`? |

---

## 5. Aptauja: mazākais uzlabojums rīt

Bloka beigās (apmēram 10:21) MS Teams atvērs **vienu multi-select aptauju**. Anonīma. Vairākas atbildes ir gaidāmas — lielākajai daļai dalībnieku būs vairāki iespējami uzlabojumi.

> **Jautājums:** _Kas ir mazākā lieta, ko jūs varētu uzlabot rīt savos esošajos vai topošajos metadatos?_
>
> - (a) Aizpildīt `description` bagātāk (>50 zīmēm, bilingvāli LV+EN)
> - (b) Pievienot ORCID autoriem
> - (c) Pievienot atslēgvārdus / Subject klasifikāciju
> - (d) Norādīt licenci (piem., CC BY 4.0)
> - (e) Vēl nav metadatu, ko uzlabot — vēl neesmu deponējis
> - (f) Cits

Šī ir _intent-formation_ aptauja, ne zināšanu pārbaude. Jūsu atbilde palīdz pasniedzējam izprast auditorijas faktiskās prioritātes un, ja kāda opcija dominē, sniegs papildu komentāru par tā uzlabojuma praktisko ieviešanu.

> **Piezīme:** sesijas laikā čats netiek lasīts (auditorijas mērogs ~197). Ja jums ir formāls jautājums, lūdzu, ievietojiet to **Q&A panelī** — Mikus tos apkopo un pasniedzējs atbild pa pārtraukumu vai sesijas beigās.

---

## 6. Pēc sesijas — pārbaudiet savas datu kopas paši

Ja jums jau ir publicēta datu kopa (dataverse.lv, Zenodo, vai citā FAIR repozitorijā):

### 6.0 Izejiet cauri oficiālajam DataverseLV kontrolsarakstam

Atveriet [`DataverseLV_kontrolsaraksts_V3.0.docx`](https://dataverse.lv/wp-content/uploads/2025/12/DataverseLV_kontrolsaraksts_V3.0.docx) un secīgi pārbaudiet katru punktu pret savu datu kopu. Šis ir tas pats kontrolsaraksts, ko datu kuratori lieto Latvijā pirms publicēšanas — ja kāda atbilde ir "nē", lauks vai dokuments papildināms. Lielākā daļa punktu der jebkurai FAIR-spējīgai platformai.

### 6.1 Pārbaudiet schema.org JSON-LD

Atveriet vienu no šiem URL (aizvietojiet ar savu DOI vai Zenodo record ID):

```
# dataverse.lv:
https://dv.dataverse.lv/api/datasets/export?exporter=schema.org&persistentId=doi:JŪSU/DOI

# Zenodo:
https://zenodo.org/records/JŪSU_RECORD_ID/export/json-ld
```

Pārbaudiet:
- Vai `description` ir vismaz 50 zīmes? (Google obligātais minimums)
- Vai `description` ir bilingvāls (LV + EN)?
- Vai katram autoram ir ORCID (`sameAs` vai `@id`)?
- Vai `keywords` (vai tā ekvivalents) ir bagātīgi un bez akronīmu pārpratumiem?
- Vai `license` ir SPDX-standartlicence (CC BY 4.0, MIT, u.c.) vai customlicence?

### 6.2 Pārbaudiet, vai Google Dataset Search atrod jūsu kopu

Atveriet <https://datasetsearch.research.google.com/> un ielīmējiet jūsu DOI URL kā vaicājumu. Indeksācija aizņem 1–7 dienas pēc publicēšanas.

### 6.3 Pārbaudiet Signposting Link header (papildu)

Termināļa logā:

```bash
# dataverse.lv:
curl -I "https://dv.dataverse.lv/dataset.xhtml?persistentId=doi:JŪSU/DOI" | grep -i ^link:

# Zenodo:
curl -I "https://zenodo.org/records/JŪSU_RECORD_ID" | grep -i ^link:
```

Sagaidāms: ~18 saistīti elementi — `cite-as`, `describedby` (vairāki eksporta formāti), `author` (jūsu ORCID), `license`, `linkset`, u.c. Abas platformas implementē [FAIR Signposting Profile](https://signposting.org/FAIR/).

---

## 7. Resursi padziļinātai izpētei

| Resurss                                      | URL                                                                  |
|----------------------------------------------|----------------------------------------------------------------------|
| **DataverseLV ceļvedis — FAIR principi**     | <https://dataverse.lv/fair-principi/>                                 |
| **DataverseLV ceļvedis — Metadatu veidi**    | <https://dataverse.lv/metadatu-veidi/>                                |
| **DataverseLV ceļvedis — Metadatu standarti** | <https://dataverse.lv/metadatu-elementi-un-standarti/>               |
| **DataverseLV ceļvedis — Pastāvīgie identifikatori** | <https://dataverse.lv/pastavigie-identifikatori/>             |
| **DataverseLV deposita procedūra**           | `materials/references/dataverse-lv/datu-deponesana/files/Datu_deponesanas_procedura_19.06.2026.pdf` |
| **DataverseLV metadatu pamācība**            | `materials/references/dataverse-lv/datu-deponesana/files/Metadati_pamaciba_v06-ID.pdf` |
| Google Dataset Search guidelines             | <https://developers.google.com/search/docs/appearance/structured-data/dataset> |
| schema.org `Dataset` v30.0                   | <https://schema.org/Dataset>                                          |
| DataCite Metadata Schema 4.7                 | <https://datacite-metadata-schema.readthedocs.io/en/4.7/>             |
| DCMI Metadata Terms                          | <https://www.dublincore.org/specifications/dublin-core/dcmi-terms/>   |
| FAIR Signposting Profile                     | <https://signposting.org/FAIR/>                                       |
| F-UJI FAIR assessment tool                   | <https://www.f-uji.net/?action=test>                                  |
| dataverse.lv eksporta API (pilna dokumentācija) | <https://guides.dataverse.org/en/latest/api/dataaccess.html>      |
| Zenodo API (records + export endpoints)      | <https://developers.zenodo.org/#records>                              |
| Zenodo eksporta formāti (json-ld, datacite-xml, dublincore, dcat-ap, marcxml, csl, bibtex) | `https://zenodo.org/records/{ID}/export/{format}` |
| FAIR-Aware self-assessment (DANS)            | <https://fairaware.dans.knaw.nl/>                                     |

---

## 8. Atgriezeniskā saite

Kursa beigās (vai pēc sesijas e-pastā) — ja jūs uzlabojāt savu datu kopu pēc šīs sesijas, lūdzu, dalieties ar to: nosaukums, kas mainījās, vai pamanījāt atklājamības atšķirību. Tas palīdzēs nākamajām VPC apmācībām.
