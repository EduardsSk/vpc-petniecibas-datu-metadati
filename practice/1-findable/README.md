# Praktiskais uzdevums 1 — eksportu salīdzinājums

**Laiks:** ~15 min individuāli
**Mērķis:** redzēt, kā vienai datu kopai pastāv vairāki paralēli metadatu eksporti dažādos standartos, un kā lauku aizpildīšanas kvalitāte (ne platforma) ietekmē atrodamību.

---

## 1. Ko jūs darīsit

Salīdzināsit **divas reālas datu kopas no diviem FAIR repozitorijiem** — vienu ar bagātīgi aizpildītiem metadatiem (dataverse.lv), otru ar minimāli aizpildītiem (Zenodo). Katrai datu kopai sagatavoti **trīs metadatu eksporti** trijos starptautiskos standartos:

- **schema.org JSON-LD** — tas, ko redz Google Dataset Search.
- **DataCite XML** — tas, ko redz DOI reģistrs un akadēmiskās citēšanas sistēmas.
- **Dublin Core (oai_dc) XML** — tas, ko redz bibliotēku katalogi un OpenAIRE.

Atveriet failus pa pāriem (pilnīgais ↔ minimālais), salīdziniet, kuri lauki ir aizpildīti, kuri trūkst, un atzīmējiet to kontrolsarakstā 4. sadaļā.

---

## 2. Datu kopas

### 2.1 Pilnīgā datu kopa

**Nosaukums:** _Biogrāfisko interviju transkripcijas projektā "Konversijas un parāvumi: latviešu filozofijas epistēmiskās stratēģijas padomju periodā (1944-1991)"_
**Autors:** Andrejs Balodis (Latvijas Kultūras akadēmija)
**DOI:** [`10.71782/DATA/QVUERT`](https://doi.org/10.71782/DATA/QVUERT)
**Repozitorijs:** dv.dataverse.lv — [datu kopas lapa](https://dv.dataverse.lv/dataset.xhtml?persistentId=doi:10.71782/DATA/QVUERT)

### 2.2 Minimālā datu kopa

**Nosaukums:** _Party financial declarations, Latvia, 2002-2024_
**Autors:** Jānis Ikstens (Latvijas Universitāte), ORCID [0000-0003-3191-6305](https://orcid.org/0000-0003-3191-6305)
**DOI:** [`10.5281/zenodo.19311915`](https://doi.org/10.5281/zenodo.19311915)
**Repozitorijs:** Zenodo — [datu kopas lapa](https://zenodo.org/records/19311915)

---

## 3. Faili darbam

Visi seši metadatu eksporti ir lokāli sagatavoti mapē [`data/`](data/). Atveriet tos teksta redaktorā vai pārlūkprogrammā — XML un JSON ir cilvēklasāmi formāti.

**Bagātā kopa (Balodis, dataverse.lv):**

1. [`data/qvuert-schema-org.json`](data/qvuert-schema-org.json) — schema.org JSON-LD
2. [`data/qvuert-datacite.xml`](data/qvuert-datacite.xml) — DataCite XML
3. [`data/qvuert-oai-dc.xml`](data/qvuert-oai-dc.xml) — Dublin Core (oai_dc) XML

**Minimālā kopa (Ikstens, Zenodo):**

4. [`data/zenodo-19311915-schema-org.json`](data/zenodo-19311915-schema-org.json) — schema.org JSON-LD
5. [`data/zenodo-19311915-datacite.xml`](data/zenodo-19311915-datacite.xml) — DataCite XML
6. [`data/zenodo-19311915-oai-dc.xml`](data/zenodo-19311915-oai-dc.xml) — Dublin Core (oai_dc) XML

> **Padoms.** Atveriet failus pa pāriem — vispirms abus schema.org failus blakus, tad abus DataCite, tad abus Dublin Core. Tā ātri redzēsit, kas atšķiras starp bagāto un minimālo eksportu, un kas atšķiras starp pašiem standartiem.

---

## 4. Salīdzinājuma kontrolsaraksts

Atzīmējiet, ko atrodat katrā eksportā. Fokuss: **kuri lauki vispār ir aizpildīti** un **cik bagātīgs ir saturs**.

### 4.1 Aprakstošie metadati (F2)

| Lauks                      | Pilnīgā | Minimālā | Piezīmes                             |
| -------------------------- | :-----: | :------: | ------------------------------------ |
| Nosaukums (`name`/`title`) |    ☐    |    ☐     | Vai ir bilingvāls?                   |
| Apraksts (`description`)   |    ☐    |    ☐     | Cik garš? Vai bilingvāls?            |
| Apraksta tips (DataCite)   |    ☐    |    ☐     | Vienkāršs Abstract vai vairāki tipi? |
| Atslēgvārdi (`keywords`)   |    ☐    |    ☐     | Cik daudz? Cik kvalitatīvi?          |
| Tēmas joma (`subject`)     |    ☐    |    ☐     | Cik plaša/precīza?                   |

### 4.2 Aģentu identifikatori (F2 — otrais slānis)

| Lauks            | Pilnīgā | Minimālā | Piezīmes                    |
| ---------------- | :-----: | :------: | --------------------------- |
| Autors ar ORCID  |    ☐    |    ☐     | Visi autori? Daži? Neviens? |
| Autora piederība |    ☐    |    ☐     | Tikai teksts vai ar ROR?    |
| Kontaktpersona   |    ☐    |    ☐     | Skaidri norādīta?           |

### 4.3 Atklājamības lauki (F4 — ietekmē Google Dataset Search redzamību)

| Lauks              | Pilnīgā | Minimālā | Piezīmes          |
| ------------------ | :-----: | :------: | ----------------- |
| `spatialCoverage`  |    ☐    |    ☐     | Ģeogrāfija        |
| `temporalCoverage` |    ☐    |    ☐     | Laika diapazons   |
| `funder`           |    ☐    |    ☐     | Finansējuma avots |
| `variableMeasured` |    ☐    |    ☐     | Mērītie mainīgie  |
| `version`          |    ☐    |    ☐     | Versija           |

### 4.4 Atkārtotas izmantošanas lauki (R1.1, R1.2 — sīkāk skatīsim 4. sesijā)

| Lauks               | Pilnīgā | Minimālā | Piezīmes                |
| ------------------- | :-----: | :------: | ----------------------- |
| `license`           |    ☐    |    ☐     | URL formātā?            |
| Piekļuves režīms    |    ☐    |    ☐     | Atvērts / ierobežots    |
| Provenance / metode |    ☐    |    ☐     | Ietverta `description`? |

---

## 5. Pēc kursa — pielietojiet savai datu kopai

Ja jums jau ir publicēta datu kopa (dataverse.lv, Zenodo, vai citā FAIR repozitorijā), to pašu salīdzinājumu varat veikt savai kopai.

### 5.1 Oficiālais pirms-publicēšanas kontrolsaraksts

[`DataverseLV_kontrolsaraksts_V3.0.docx`](https://dataverse.lv/wp-content/uploads/2025/12/DataverseLV_kontrolsaraksts_V3.0.docx) — secīgi pārbaudiet katru punktu pret savu datu kopu. Tas pats kontrolsaraksts, ko datu kuratori lieto Latvijā pirms publicēšanas; lielākā daļa punktu der jebkurai FAIR-spējīgai platformai.

### 5.2 Eksportu URL — savai datu kopai

**dataverse.lv:**

```
https://dv.dataverse.lv/api/datasets/export?exporter={FORMĀTS}&persistentId=doi:{JŪSU/DOI}
```

`{FORMĀTS}` vērtības: `schema.org`, `Datacite`, `oai_dc` (un vēl 8 — `dataverse_json`, `ddi`, `dcterms`, `OAI_ORE`, `oai_datacite`, `oai_ddi`, `html`).

**Zenodo:**

```
https://zenodo.org/records/{JŪSU_RECORD_ID}/export/{FORMĀTS}
```

`{FORMĀTS}` vērtības: `json-ld`, `datacite-xml`, `dublincore`, `dcat-ap`, `marcxml`, `csl`, `bibtex`, `json`.

> Abām platformām atšķiras URL paterns un formātu nosaukumi (piem., `oai_dc` vs `dublincore`), bet **iznākumi ir tie paši starptautiskie standarti** — schema.org Dataset, DataCite Schema 4, Dublin Core. Tā ir FAIR praktiska izpausme: standarti universāli, platformu UI var atšķirties.

### 5.3 Pārbaudiet, vai Google Dataset Search atrod jūsu kopu

Atveriet <https://datasetsearch.research.google.com/> un ielīmējiet jūsu DOI URL kā vaicājumu. Indeksācija aizņem 1–7 dienas pēc publicēšanas.

### 5.4 Pārbaudiet schema.org JSON-LD kvalitāti

Atveriet sava eksporta schema.org URL un pārbaudiet:

- Vai `description` ir vismaz 50 zīmes? (Google obligātais minimums.)
- Vai `description` ir bilingvāls (LV + EN)?
- Vai katram autoram ir ORCID (`sameAs` vai `@id`)?
- Vai `keywords` ir bagātīgi un bez akronīmu pārpratumiem?
- Vai `license` ir SPDX-standartlicence (CC BY 4.0, MIT u.c.)?

### 5.5 Pārbaudiet Signposting Link header

Termināļa logā:

```bash
# dataverse.lv:
curl -I "https://dv.dataverse.lv/dataset.xhtml?persistentId=doi:JŪSU/DOI" | grep -i ^link:

# Zenodo:
curl -I "https://zenodo.org/records/JŪSU_RECORD_ID" | grep -i ^link:
```

Sagaidāms: ~18 saistīti elementi — `cite-as`, `describedby` (vairāki eksporta formāti), `author` (jūsu ORCID), `license`, `linkset` u.c. Abas platformas implementē [FAIR Signposting Profile](https://signposting.org/FAIR/).

---

## 6. Resursi padziļinātai izpētei

| Resurss                                              | Atrašanās vieta                                                       |
|------------------------------------------------------|-----------------------------------------------------------------------|
| **DataverseLV ceļvedis — FAIR principi**             | <https://dataverse.lv/fair-principi/>                                  |
| **DataverseLV ceļvedis — Metadatu veidi**            | <https://dataverse.lv/metadatu-veidi/>                                 |
| **DataverseLV ceļvedis — Metadatu standarti**        | <https://dataverse.lv/metadatu-elementi-un-standarti/>                 |
| **DataverseLV ceļvedis — Pastāvīgie identifikatori** | <https://dataverse.lv/pastavigie-identifikatori/>                      |
| **DataverseLV deposita procedūra**                   | `materials/references/dataverse-lv/datu-deponesana/files/Datu_deponesanas_procedura_19.06.2026.pdf` |
| **DataverseLV metadatu pamācība**                    | `materials/references/dataverse-lv/datu-deponesana/files/Metadati_pamaciba_v06-ID.pdf` |
| Google Dataset Search guidelines                     | <https://developers.google.com/search/docs/appearance/structured-data/dataset> |
| schema.org `Dataset` v30.0                           | <https://schema.org/Dataset>                                           |
| DataCite Metadata Schema 4.7                         | <https://datacite-metadata-schema.readthedocs.io/en/4.7/>              |
| DCMI Metadata Terms                                  | <https://www.dublincore.org/specifications/dublin-core/dcmi-terms/>    |
| FAIR Signposting Profile                             | <https://signposting.org/FAIR/>                                        |
| F-UJI FAIR assessment tool                           | <https://www.f-uji.net/?action=test>                                   |
| FAIR-Aware self-assessment (DANS)                    | <https://fairaware.dans.knaw.nl/>                                      |
| dataverse.lv eksporta API (pilna dokumentācija)      | <https://guides.dataverse.org/en/latest/api/dataaccess.html>           |
| Zenodo API (records + export endpoints)              | <https://developers.zenodo.org/#records>                               |
