# Praktiskais uzdevums 4 — SPARQL hands-on

**Laiks:** ~16 min individuāli (T1 ~8 min, T2 ~4 min, T3 ~4 min)
**Mērķis:** palaist trīs SPARQL šablonus pret Wikidata Query Service un redzēt, ka **F2 ≡ R1** ir viens un tas pats lauks (`wdt:P6782` ROR ID) no diviem leņķiem — lauks nemainās, mainās jautājums.

---

## 1. Ko jūs darīsit

Strādāsit ar **Wikidata Query Service** (<https://query.wikidata.org/>) — pasaulē vienu no lielākajiem publiski pieejamajiem SPARQL galapunktiem. Trīs vaicājumi, **pakāpeniska sarežģītība**, _identiska_ apakšstruktūra:

- **T1** — kuras Latvijas iestādes ir reģistrētas ROR (Research Organization Registry)? Identisks tam, ko 3. sesijas Bloka 3.4 demonstrācijā redzējāt.
- **T2** — no T1 iestādēm: kuras ir universitātes? Vienīgā maiņa: pievienota viena rinda Wikidata īpašības filtram.
- **T3** — no T1 iestādēm: kāds konteksts ļauj atkārtoti izmantot to datus? Tas pats `wdt:P6782` lauks; pievienots dibināšanas gads (`wdt:P571`) un mītnes pilsēta (`wdt:P159`). **Šis ir F2 ≡ R1 saiknes pierādījums** — tas pats lauks, divi jautājumi.

Ielīmējat un palaižat katru no trim vaicājumiem savā pārlūkā, salīdziniet rezultātu ar sagaidāmajām tabulām 5. sadaļā.

> **Kāpēc nav SPARQL gramatikas pamācība?** Tas ir 3-stundu tēma, ne 16-minūšu tēma. Šis bloks māca **mehānismu** — ielīmējat, palaižat, redzat rezultātu — ne sintaksi. SPARQL primer atrodas resursu sarakstā 6. sadaļā.

---

## 2. Faili darbam

Visi trīs SPARQL šabloni un sagaidāmo rezultātu offline-snapshot ir lokāli sagatavoti mapē [`data/topic4-block4.5/`](data/topic4-block4.5/).

1. [`data/topic4-block4.5/template-1.txt`](data/topic4-block4.5/template-1.txt) — T1 vaicājums
2. [`data/topic4-block4.5/template-2.txt`](data/topic4-block4.5/template-2.txt) — T2 vaicājums
3. [`data/topic4-block4.5/template-3.txt`](data/topic4-block4.5/template-3.txt) — T3 vaicājums
4. [`data/topic4-block4.5/wdqs-result-fallback.html`](data/topic4-block4.5/wdqs-result-fallback.html) — visi trīs vaicājumi + saglabātās rezultāta tabulas (atveramā pārlūkā bez interneta)

> **Padoms.** Atveriet <https://query.wikidata.org/> jaunā cilnē, ielīmējiet T1, spiediet ▶ Run, aplūkojiet rezultāta tabulu zem koda. Atkārtojiet ar T2 un T3. Ja vaicājums neatbild 1 minūtes laikā vai redzat sintakses kļūdu — atveriet `wdqs-result-fallback.html`.

---

## 3. Solis pa solim

1. **Atveriet** <https://query.wikidata.org/> jaunā cilnē. Wikidata redaktors parādās ar tukšu vaicājumu lauku.
2. **Ielīmējiet T1 vaicājumu** (4.1 sadaļā). `Ctrl+A` lai iezīmētu redaktora saturu, `Ctrl+V` lai ielīmētu.
3. **Spiediet ▶ Run** (zilā poga ar bultiņu, augšējā labajā stūrī). Aplūkojiet rezultāta tabulu zem koda. **T1 sagaidāms iznākums:** 12 rindas (~0,2 sek); LU, RTU, LKA, Latvijas Banka u.c.
4. **Atkārtojiet ar T2 un T3.** T2 sagaidāms 10 rindas (~0,3 sek); T3 sagaidāms 8 rindas (~0,3 sek; sakārtotas pēc dibināšanas gada augšupejoši — Rīgas Būvniecības koledža 1872 → Latvijas Sporta pedagoģijas akadēmija 1921).
5. **Salīdziniet** savus rezultātus ar sagaidāmajām tabulām 5. sadaļā.

---

## 4. SPARQL šabloni

Visi trīs vaicājumi verificēti dzīvi 2026-05-04 PM. Visi mērķē uz `https://query.wikidata.org/`.

### 4.1 T1 — Latvijas iestādes ar ROR ID

```sparql
SELECT ?inst ?instLabel ?ror
WHERE {
  ?inst wdt:P6782 ?ror .
  ?inst wdt:P17 wd:Q211 .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "lv,en" }
}
LIMIT 12
```

**Ko šis vaicājums prasa:** atrast visus Wikidata ierakstus, kuriem ir (1) `wdt:P6782` īpašība — _Research Organization Registry (ROR) identifier_ — un (2) `wdt:P17 wd:Q211` — _country = Latvia_. Pievienot LV vai EN apzīmējumu (`?instLabel`). Atgriezt 12 rindas.

**Atslēgas Wikidata īpašības:**

- `wdt:P6782` = ROR ID ([Property:P6782](https://www.wikidata.org/wiki/Property:P6782))
- `wdt:P17` = country ([Property:P17](https://www.wikidata.org/wiki/Property:P17))
- `wd:Q211` = Latvia ([Q211](https://www.wikidata.org/wiki/Q211))
- `SERVICE wikibase:label { ... }` = pievieno apzīmējumus rezultāta tabulai (LV ja pieejams, citādi EN)
- `LIMIT 12` = atgriezt ne vairāk par 12 rindām

### 4.2 T2 — Latvijas universitātes (viena modifikācija no T1)

```sparql
SELECT ?inst ?instLabel ?ror
WHERE {
  ?inst wdt:P6782 ?ror .
  ?inst wdt:P17 wd:Q211 .
  ?inst wdt:P31 wd:Q3918 .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "lv,en" }
}
LIMIT 10
```

**Vienīgā maiņa salīdzinājumā ar T1:** pievienota rinda `?inst wdt:P31 wd:Q3918 .` un `LIMIT` mainīts no 12 uz 10.

- `wdt:P31` = instance of ([Property:P31](https://www.wikidata.org/wiki/Property:P31))
- `wd:Q3918` = university ([Q3918](https://www.wikidata.org/wiki/Q3918))

Tas filtrē rezultātu, lai paliek tikai tās iestādes, kas Wikidata ir klasificētas kā "universitāte". Vienīgais, kas mainās — jūs pievienojat _vienu_ kvalifikatoru, kas sašaurina rezultātu. Tā pati `wdt:P6782` struktūra; cits konkrētais jautājums.

### 4.3 T3 — F2 ≡ R1 closing payoff

```sparql
SELECT ?inst ?instLabel ?ror ?inception ?hqLabel
WHERE {
  ?inst wdt:P6782 ?ror .
  ?inst wdt:P17 wd:Q211 .
  ?inst wdt:P571 ?inception .
  OPTIONAL { ?inst wdt:P159 ?hq }
  SERVICE wikibase:label { bd:serviceParam wikibase:language "lv,en" }
}
ORDER BY ?inception
LIMIT 8
```

**Pievienotie lauki:** `?inception` (P571 — dibināšanas gads, _nepieciešams_) + `?hqLabel` (P159 — mītne, _opcionāls_).

- `wdt:P571` = inception ([Property:P571](https://www.wikidata.org/wiki/Property:P571))
- `wdt:P159` = headquarters location ([Property:P159](https://www.wikidata.org/wiki/Property:P159))
- `OPTIONAL { ... }` = ja ieraksts par šo lauku nav — neslēpj rindu (atstāj lauku tukšu)
- `ORDER BY ?inception` = sakārto pēc dibināšanas gada (vecākās augšā)

**Pedagoģiskais punkts:** `wdt:P6782` (ROR ID) ir _tas pats lauks_, ko T1 izmantojām, lai _atrastu_ iestādes (F2 — Atrodami). T3 šis pats lauks nāk ar dibināšanas gadu un mītnes pilsētu — kas piešķir kontekstu _atkārtotai izmantošanai_ (R1 — Atkārtoti izmantojami). **Lauks nemainās. Mainās jautājums.**

---

## 5. Sagaidāmie rezultāti (verificēti dzīvi 2026-05-04 PM)

### 5.1 T1 — 12 rindas (~0,2 sek)

| Iestāde | Wikidata | ROR ID |
|---------|----------|---------|
| Latvijas Banka | Q687709 | 000cf1839 |
| Rīgas Juridiskā augstskola | Q850355 | 05wh3xd46 |
| Rīgas Tehniskā universitāte | Q411895 | 00twb6c09 |
| Latvijas Universitāte | Q498407 | 05g3mes96 |
| Latvijas Organiskās sintēzes institūts | Q4201643 | 01a92vw29 |
| Transporta un sakaru institūts | Q4201765 | 01628w679 |
| Latvijas Jūras akadēmija | Q4254869 | 00xxekd18 |
| Latvijas Kultūras akadēmija | Q4254872 | 03f18y477 |
| Liepājas Universitāte | Q3498695 | 01gzemj61 |
| RTU Rēzeknes akadēmija | Q3801493 | 04d6the49 |
| RTU Rēzeknes akadēmija | Q3801493 | 0510ppv76 |
| Rīgas Ekonomikas augstskola | Q3931927 | 00qaje814 |

**Pamaniet:** RTU Rēzeknes akadēmijai ir **divi ROR ID** (`04d6the49` + `0510ppv76`) — institūcija pastāv vairāk kā vienā ROR ierakstā vēsturisku iemeslu dēļ; viens primārs, viens vēsturisks. Saites starp reģistriem ne vienmēr ir 1:1; un tas ir kopienas standartu darbības raksts.

### 5.2 T2 — 10 rindas (~0,3 sek)

| Iestāde | Wikidata | ROR ID |
|---------|----------|---------|
| Liepājas Universitāte | Q3498695 | 01gzemj61 |
| Daugavpils Universitāte | Q1854796 | 01mrkb883 |
| Rīgas Stradiņa universitāte | Q2007643 | 03nadks56 |
| Jāzepa Vītola Latvijas Mūzikas akadēmija | Q2570442 | 014zenb08 |
| Baltijas Starptautiskā akadēmija | Q4076909 | 02r52cf76 |
| Latvijas Jūras akadēmija | Q4254869 | 00xxekd18 |
| Latvijas Kultūras akadēmija | Q4254872 | 03f18y477 |
| Rīgas Starptautiskā ekonomikas un biznesa administrācijas augstskola | Q4394523 | 00pc6v375 |
| Latvijas Biozinātņu un tehnoloģiju universitāte | Q1342858 | 03f077y84 |
| Starptautiskā praktiskās psiholoģijas augstskola | Q15649513 | 00skfd876 |

### 5.3 T3 — 8 rindas (~0,3 sek; sakārtotas pēc dibināšanas gada)

| Iestāde | ROR ID | Dibināšanas gads | Mītne |
|---------|---------|------------------|-------|
| Rīgas Būvniecības koledža | 05xgx1b08 | 1872 | _(nav)_ |
| Paula Stradiņa klīniskā universitātes slimnīca | 00h1aq868 | 1910 | Rīga |
| Latvijas Republikas Ekonomikas ministrija | 00kzfz874 | 1918 | Rīga |
| Latvijas Republikas Iekšlietu ministrija | 05503d050 | 1918 | _(nav)_ |
| Latvijas Republikas Izglītības un zinātnes ministrija | 02hcxaq60 | 1918-11-18 | Rīga |
| Latvijas Republikas Viedās administrācijas un reģionālās attīstības ministrija | 03b7ffd73 | 1918-11-18 | Rīga |
| Latvijas Mākslas akadēmija | 015j3ky41 | 1919-08-20 | Rīga |
| Latvijas Sporta pedagoģijas akadēmija | 02h9hn661 | 1921 | _(nav)_ |

**Pamaniet:** astoņas vecākās Latvijas iestādes ar dokumentētu dibināšanas gadu — visas pirms 1922. gada. Sešas no tām atrodas Rīgā. Tas ir _bagātīgs apraksts_ (R1) — un visi šie metadati nāk no _tā paša lauka_ (`wdt:P6782` ROR ID), ko mēs izmantojām T1 _atrašanai_ (F2).

> **Ja jūsu rezultāts neatbilst šīm tabulām** — Wikidata atjauninās minūšu līmenī. Saglabātās tabulas ir 2026-05-04 PM moments; jūsu live rezultāts ir derīgs; saglabātais ir uzziņa.

---

## 6. Pēc kursa — palaidiet pats SPARQL

Trīs soļi, ko varat veikt savai praksei:

1. **Atveriet** <https://query.wikidata.org/> un palaidiet T1 vēlreiz. Eksperimentējiet — `wd:Q211` (Latvija) → `wd:Q35` (Dānija); `LIMIT 12` → `LIMIT 30`. Apskatieties, kā mainās rezultāts.
2. **Mainiet T2** — `wd:Q3918` (university) → `wd:Q31855` (research institute). Cik LV pētniecības institūtu pastāv ROR savienojumā?
3. **Mainiet T3** — pievienojiet `OPTIONAL { ?inst wdt:P856 ?website }` — official website. Cik no 8 vecākajām LV iestādēm ir oficiāla mājaslapa Wikidata ierakstā?

Ja jūsu darbs prasa konkrētu SPARQL prasmi (pētniecības datu atrašana caur ROR identifikatoriem; jūsu disciplīnas datu kopu apkopošana DataCite Commons + Wikidata krustojumā) — runājiet ar VPC datu kuratoriem (`datukuratori@vpc.lv`) vai sazinieties ar pasniedzēju (`eduards.skvireckis@lnb.lv`).

---

## 7. Resursi padziļinātai izpētei

| Resurss | URL |
|---------|-----|
| **W3C SPARQL 1.1 Query Language** | <https://www.w3.org/TR/sparql11-query/> |
| **Wikidata Query Service** | <https://query.wikidata.org/> |
| **Wikidata SPARQL kursa lapa** | <https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service> |
| **Wikidata SPARQL example query gallery** | <https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/queries> |
| **ROR (Research Organization Registry)** | <https://ror.org/> |
| **ORCID** | <https://orcid.org/> |
| **Wikidata** | <https://www.wikidata.org/> |
| **DataCite Commons** | <https://commons.datacite.org/> |
| **DataCite ↔ Wikidata savienojums** | <https://commons.datacite.org/integrations/wikidata> |
| **Berners-Lee — Linked Data 5-zvaigžņu modelis** | <https://www.w3.org/DesignIssues/LinkedData.html> |
| **DataverseLV ceļvedis — Pastāvīgie identifikatori** | <https://dataverse.lv/pastavigie-identifikatori/> |
