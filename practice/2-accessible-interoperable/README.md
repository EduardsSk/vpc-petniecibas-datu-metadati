# Praktiskais uzdevums 2 — F-UJI ziņojuma analīze

**Laiks:** ~15 min individuāli
**Mērķis:** lasīt F-UJI ziņojumu kā **diagnostiku, ne kā vērtējumu** — saprast, ko ziņojums saka, ko tas neizsaka, un kā 5 metrikas raksturo vienas datu kopas FAIR atbilstību.

---

## 1. Ko jūs darīsit

Atvērsit iepriekš sagatavotu F-UJI ziņojumu uz vienas dataverse.lv datu kopas un atzīmēsit, kā tā nostājas pret 5 izvēlētām FAIR metrikām (A1, A1.1, I1, I2, R1). Ziņojums izveidots 2026. gada 27. aprīlī, dažas stundas pēc datu kopas publicēšanas, un saglabāts kā HTML fails — atvērsies tieši pārlūkprogrammā bez interneta savienojuma.

**Centrālais princips:** F-UJI sniedz skaitli (kopējo procentu) un ziņojumu (metriku-pa-metrikai konstatējumus). _Skaitlis nav atbilde — tā ir diagnostika._ Bagātīgs ziņojums ar 60 % punktiem var pateikt vairāk nekā mehāniski iegūts 90 %.

---

## 2. Datu kopa

**Nosaukums:** _Biogrāfisko interviju transkripcijas projektā "Konversijas un parāvumi: latviešu filozofijas epistēmiskās stratēģijas padomju periodā (1944-1991)"_

**Autors:** Andrejs Balodis (Latvijas Kultūras akadēmija), ORCID [0000-0002-0688-9213](https://orcid.org/0000-0002-0688-9213)

**DOI:** [`10.71782/DATA/QVUERT`](https://doi.org/10.71782/DATA/QVUERT)

**Repozitorijs:** dv.dataverse.lv — [datu kopas lapa](https://dv.dataverse.lv/dataset.xhtml?persistentId=doi:10.71782/DATA/QVUERT)

Šo pašu kopu skatījāmies 1. sesijā kā _bagāto_ piemēru metadatu eksportu salīdzinājumā. Tagad to skatām caur diagnostikas rīku — F-UJI atklās, kur tā ir stipra un kur tai ir viena konkrēta nepilnība.

---

## 3. Faili darbam

Visi ziņojuma faili ir lokāli sagatavoti mapē [`data/`](data/).

1. [`data/qvuert-fuji-report.html`](data/qvuert-fuji-report.html) — **cilvēklasāmais ziņojums.** Atveriet pārlūkprogrammā (dubultklikšķis vai `Ctrl+O`). Tas ir galvenais darba fails.
2. [`data/qvuert-fuji-report.json`](data/qvuert-fuji-report.json) — strukturētais (mašīnlasāmais) ziņojums. Papildu fails — atveriet, ja interesē, kā F-UJI strukturē iekšējos datus, vai gribat citētus konstatējumus pa metrikām.

**F-UJI rīks tiešsaistē:** <https://www.f-uji.net/?action=test>. Pēc kursa varat palaist analīzi uz savu publicētu datu kopu (sk. § 5).

---

## 4. Kontrolsaraksts — 5 metrikas

Atzīmējiet katrai metrikai, kas redzams ziņojumā. Šī ir _jūsu_ kontrolsaraksts — pēc sesijas to var izmantot, lai tās pašas metrikas pārbaudītu savā datu kopā.

### 4.1 Score summary (kopējais Baloža kopas rezultāts)

| Pīlārs                       | Punkti | Procenti    | Atzīmēt |
| ---------------------------- | ------ | ----------- | ------- |
| **F** (Atrodami)             | 7 / 7  | **100 %**   | ☐       |
| **A** (Pieejami)             | 7 / 7  | **100 %**   | ☐       |
| **I** (Sadarbspējīgi)        | 4 / 6  | **66.67 %** | ☐       |
| **R** (Atkārtoti izmantojami)| 6 / 6  | **100 %**   | ☐       |
| **FAIR kopējais**            | 24 / 26| **92.31 %** | ☐       |

### 4.2 Piecas metrikas, kuras apspriedīsim kopā

| # | Metrika | Statuss | Punkti | Ko F-UJI pārbauda                                                                       | Atzīmēt |
|---|---------|:-------:|:------:|------------------------------------------------------------------------------------------|:-------:|
| 1 | **FsF-A1-01M** _piekļuves nosacījumi_      | pass    | 1 / 1  | Vai metadati paši dokumentē piekļuves nosacījumu (atvērts / autentificēts / ierobežots / bezsaistē-aprakstīts) | ☐       |
| 2 | **FsF-A1.1-01MD** _atvērts protokols_      | pass    | 2 / 2  | Vai piekļuves protokols ir publiski dokumentēts un vispārēji ieviešams (HTTPS — IETF RFC 9110)                | ☐       |
| 3 | **FsF-I1-01M** _formālā valoda_            | pass    | 2 / 2  | Vai metadati ir izsacīti formālā, plaši pielietojamā valodā (XML, JSON, JSON-LD)                              | ☐       |
| 4 | **FsF-I2-01M** _FAIR vārdnīcas_            | **fail**| **0 / 2** | Vai metadati izmanto reģistrētas semantiskas vārdnīcas (LOV-reģistrētas; SKOS, GEMET, MeSH u.tml.)         | ☐       |
| 5 | **FsF-R1-01M** _bagātīgs apraksts_         | pass    | 2 / 2  | Vai metadati satur bagātīgu, precīzu apraksta saturu                                                          | ☐       |

### 4.3 Pārējās 7 metrikas

F-UJI 3.5.1 ievērtē 12 metrikas kopā. Šī kontrolsaraksta § 4.2 fokusējas uz 5; atlikušās 7 paliek ziņojumā kā jūsu pašu izpētes materiāls.

| Metrika        | Joma           | Pārbauda                                            |
| -------------- | -------------- | --------------------------------------------------- |
| FsF-F1-01D     | Atrodami       | Datu identifikators (DOI, Handle u.c.)              |
| FsF-F1-02D     | Atrodami       | Identifikators ir globāli unikāls un pastāvīgs      |
| FsF-F2-01M     | Atrodami       | Bagātīgi metadati par datiem                        |
| FsF-F3-01M     | Atrodami       | Metadati nepārprotami norāda datu identifikatoru    |
| FsF-F4-01M     | Atrodami       | (Meta)dati reģistrēti meklējamā resursā             |
| FsF-A1-02MD    | Pieejami       | Datu (ne tikai metadatu) piekļuves protokols        |
| FsF-A1.2-01MD  | Pieejami       | Autentifikācijas protokols (kad nepieciešams)       |
| FsF-I3-01M     | Sadarbspējīgi  | Kvalificētas atsauces uz citiem (meta)datiem        |
| FsF-R1.1-01M   | Atkārtoti izm. | Licence                                             |
| FsF-R1.2-01M   | Atkārtoti izm. | Izcelsme (provenance)                               |
| FsF-R1.3-01M   | Atkārtoti izm. | Atbilst nozaru standartiem                          |

Pilns 12 metriku saraksts: <https://www.f-uji.net/index.php?action=methods>.

---

## 5. Pēc kursa — palaidiet F-UJI uz savu kopu

Ja jums jau ir publicēta datu kopa (dataverse.lv, Zenodo, OSF, figshare, vai citā FAIR repozitorijā):

### 5.1 Palaidiet F-UJI

1. Atveriet <https://www.f-uji.net/?action=test>
2. Ielīmējiet savu DOI URL formātā `https://doi.org/JŪSU/DOI` (vai landing page URL)
3. Atstājiet noklusējumus (Metric Set = default; Use DataCite = ieslēgts)
4. Klikšķiniet **Start FAIR Assessment**
5. Gaidiet 30–60 sek; ziņojums atveras tajā pašā lapā

### 5.2 Identificējiet zemākos punktus

Ziņojumā meklējiet metrikas, kur statuss ir **fail** vai **partial**. Tās ir lauki, kuru uzlabošana visvairāk paaugstinās jūsu kopējo punktu skaitu.

### 5.3 Veiciet vienu konkrētu uzlabojumu

Tipiski **30-min uzlabojumi**, kas dod 5–10 % punktu pieaugumu:

- **Pievienot bilingvālu aprakstu** (LV + EN, `description` laukā) — paaugstina F2 redzamību angļu meklējumos un R1-01M virsmu
- **Pievienot ORCID** katram autoram — paaugstina I3 (kvalificētas atsauces) un F2
- **Pārbaudīt `license` SPDX-formātu** — pārliecinās, ka licence ir standarta CC BY 4.0 (vai cita SPDX-reģistrēta), ne customlicense; paaugstina R1.1 automatizāciju (4. sesija)
- **Pārbaudīt, ka `subject` atbilst kontrolētai vārdnīcai** — paaugstina I2 (3. sesijas tēma)

### 5.4 Atkārtoti palaidiet F-UJI

Pēc uzlabojumu publicēšanas (var prasīt jaunu datu kopas versiju) palaidiet F-UJI vēlreiz. Salīdziniet ar pirmo rezultātu.

---

## 6. Resursi padziļinātai izpētei

| Resurss                                                  | URL                                                                         |
|----------------------------------------------------------|-----------------------------------------------------------------------------|
| **F-UJI tīmekļa rīks**                                   | <https://www.f-uji.net/?action=test>                                        |
| **F-UJI 12-metriku reference**                           | <https://www.f-uji.net/index.php?action=methods>                            |
| **F-UJI publikācija** (Devaraju & Huber, 2021, RIO)      | <https://doi.org/10.3897/rio.7.e69287>                                      |
| **F-UJI atvērtais kods** (GitHub)                        | <https://github.com/pangaea-data-publisher/fuji>                            |
| **FAIRsFAIR Data Object Assessment Metrics** (Zenodo)    | <https://doi.org/10.5281/zenodo.3775793>                                    |
| **DataverseLV ceļvedis — FAIR principi**                 | <https://dataverse.lv/fair-principi/>                                        |
| **DataverseLV ceļvedis — Metadatu standarti**            | <https://dataverse.lv/metadatu-elementi-un-standarti/>                       |
| **DataverseLV ceļvedis — Pastāvīgie identifikatori**     | <https://dataverse.lv/pastavigie-identifikatori/>                            |
| **JSON Schema 2020-12** specifikācija                    | <https://json-schema.org/draft/2020-12/json-schema-core.html>                |
| **JSON Schema pārlūka validators**                       | <https://json-schema.hyperjump.io/>                                          |
| **DataCite Metadata Schema 4.7**                         | <https://datacite-metadata-schema.readthedocs.io/en/4.7/>                    |
| **schema.org Dataset v30.0**                             | <https://schema.org/Dataset>                                                 |
| **JSON-LD 1.1** (W3C Recommendation)                     | <https://www.w3.org/TR/json-ld11/>                                           |
| **OAI-PMH 2.0** specifikācija                            | <https://www.openarchives.org/OAI/openarchivesprotocol.html>                 |
| **DataCite Content Resolver**                            | <https://support.datacite.org/docs/datacite-content-resolver>                |
| **dv.dataverse.lv eksporta API**                         | <https://guides.dataverse.org/en/latest/api/dataaccess.html>                 |
| **Linked Open Vocabularies reģistrs** (3. sesijas priekšskats) | <https://lov.linkeddata.es/>                                            |
| **FAIR Signposting Profile**                             | <https://signposting.org/FAIR/>                                              |
| **FAIR-Aware self-assessment** (DANS)                    | <https://fairaware.dans.knaw.nl/>                                            |
