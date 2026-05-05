# Praktiskais uzdevums 4.5 — SPARQL hands-on

**Sesija:** 4 (R praksē — bagātīgs apraksts un atkārtota izmantošana praksē) — 2026-05-05, 15:50–16:15
**Bloks:** 4.5 (25 min — _kursa lielākais_ praktiskais bloks)
**Formāts:** _Dalībnieki vispirms_ — jūs paši palaižat trīs SPARQL šablonus pret Wikidata Query Service (klusuma darba laiks ~16 min), tad noslēdzošā Aptauja 3 fiksē jūsu T3 atziņu, tad pasniedzējs demonstrē T3 vaicājumu, izklāstot atbilstoši Aptaujas 3 rezultātam. **Tas ir _strukturāls_ apgrieziens** no 1. un 2. sesijas demonstrācijas-vispirms modeļa — šeit jūs paši pirmie palaižat vaicājumus, pasniedzējs pēc tam kalibrē Bloka 4.6 noslēguma F2 ≡ R1 inversijas atrunu.
**Mērķis:** Padarīt SPARQL **konkrētu un personīgu** — ielīmēt vaicājumu, nospiest pogu, redzēt rezultātu. Iegūt operatīvu pierādījumu, ka **F2 ≡ R1** — _tas pats Wikidata lauks `wdt:P6782` (ROR ID), ko T1 izmantojam, lai _atrastu_ Latvijas iestādes, T3 izmantojam, lai pievienotu kontekstu _atkārtotai izmantošanai_. Lauks nemainās; mainās jautājums._

> **Mijiedarbības piezīme:** Sesijas laikā **čats netiek lasīts** (auditorijas mērogs ~197). Ja jums ir formāls jautājums, lūdzu, ievietojiet to **Q&A panelī** — Mikus tos apkopo un pasniedzējs atbild pa pārtraukumu vai sesijas beigās. 4. sesija ietver **četras aptaujas** (Aptauja 1 par R apakšprincipu pieredzi Bloka 4.1 vidū; Aptauja 2 par licences izvēli Bloka 4.2 vidū; **Aptauja 3 par SPARQL iznākuma atziņu šī Bloka 4.5 noslēgumā**; Aptauja 4 par jūsu nākamo R-uzlabojumu Bloka 4.6 vidū).
>
> **Kanoniskie avoti** (`materials/references/dataverse-lv/celvedis/` un ārējie):
> - SPARQL 1.1: [W3C Recommendation 2013-03-21](https://www.w3.org/TR/sparql11-query/)
> - Wikidata Query Service: <https://query.wikidata.org/>
> - Wikidata SPARQL kursa lapa: <https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service>
> - 3. sesijas Bloka 3.4 ievada vaicājums (T1 atkārtošanās): <https://github.com/eduardssk/vpc-petniecibas-datu-metadati>

---

## 2. Ko mēs darīsim

Strādāsim ar **Wikidata Query Service** (`https://query.wikidata.org/`) — pasaulē vienu no lielākajiem publiski pieejamajiem SPARQL galapunktiem. Trīs vaicājumi, **pakāpeniska sarežģītība**, _identiska_ apakšstruktūra:

- **T1** — _kuras Latvijas iestādes ir reģistrētas ROR (Research Organization Registry)?_ Identisks tam, ko 3. sesijas Bloka 3.4 demonstrācijā redzējāt. Šis ir jūsu pirmais SPARQL palaišanas darbs.
- **T2** — _no T1 iestādēm — kuras ir universitātes?_ Vienīgā maiņa: pievienota viena rinda Wikidata īpašības filtram. Tā pati `wdt:P6782` ROR savienojuma struktūra; viens kvalifikators.
- **T3** — _no T1 iestādēm — kāds konteksts ļauj atkārtoti izmantot to datus?_ Tas pats `wdt:P6782` lauks; pievienoti dibināšanas gads (`wdt:P571`) un mītnes pilsēta (`wdt:P159`). **Šis ir F2 ≡ R1 saiknes pierādījums** — tas pats lauks, divi jautājumi.

Jūs **klusumā** ielīmējat un palaižat katru no trim vaicājumiem savā pārlūkā: T1 ~8 minūtes, T2 ~4 minūtes, T3 ~4 minūtes. Tad **Aptauja 3** fiksē jūsu T3 atziņu; tad pasniedzējs demonstrē T3 vaicājumu, izklāstot atbilstoši aptaujas rezultātam.

> **Kāpēc nav SPARQL gramatikas pamācība?** Tas ir 3-stundu tēma, ne 25-minūšu tēma. Šis bloks māca **mehānismu** — ielīmējat, palaižat, redzat rezultātu — ne sintaksi. Pēc kursa: SPARQL primer atrodas resursu sarakstā (10. sadaļā).

> **Kāpēc Wikidata, ne kāds cits SPARQL galapunkts?** Wikidata ir (a) publisks (nav login); (b) Latvijai relevants (Latvijas iestādes ROR savienojumā); (c) atbilstošs F2 ≡ R1 demonstrācijai — tas pats `wdt:P6782` lauks darbojas gan F (atrast iestādi), gan R (raksturīgs konteksts) jautājumiem.

---

## 3. Solis pa solim — jūsu darbība (klusuma darba laiks, ~16 min)

> **PIRMS LASĪT 4. + 5. + 6. + 7. + 8. SADAĻAS — IZPILDIET 3. SADAĻU.** 4. sadaļa zemāk dod jums trīs SPARQL šablonus; 5. sadaļa rāda sagaidāmos rezultātus; 6. sadaļa rāda Aptauja 3 jautājumu un opcijas — neskatieties tās līdz aptauja parādās ekrānā.

**Jūsu protokols (5 soļi, ~16 min):**

1. **Atveriet** <https://query.wikidata.org/> jaunā cilnē. Wikidata redaktors parādās ar tukšu vaicājumu lauku.
2. **Ielīmējiet T1 vaicājumu** (no 4.1 sadaļas zemāk vai protokola slaida `<pre>` bloka). `Ctrl+A` lai iezīmētu redaktora saturu, `Ctrl+V` lai ielīmētu.
3. **Spiediet ▶ Run** (zilā poga ar bultiņu, augšējā labajā stūrī). Aplūkojiet rezultāta tabulu zem koda. **T1 sagaidāms iznākums:** 12 rindas (~0,2 sek); LU, RTU, LKA, Latvijas Banka u.c.
4. **Atkārtojiet ar T2 un T3.** T2 sagaidāms 10 rindas (~0,3 sek); T3 sagaidāms 8 rindas (~0,3 sek; sakārtotas pēc dibināšanas gada augšupejoši — Rīgas Būvniecības koledža 1872 → Latvijas Sporta pedagoģijas akadēmija 1921).
5. **Aptauja 3** parādīsies pēc T3 vaicājuma palaišanas (~minūte 22 no Bloka 4.5 sākuma) — fiksē jūsu T3 atziņu; pasniedzējs T3 demonstrē _pēc_ aptaujas slēgšanas.

**Ja cilne neielādējas vai vaicājums neatbild 1 minūtes laikā** — atveriet lokāli saglabāto failu `data/topic4-block4.5/wdqs-result-fallback.html` (saturs identisks: visi 3 vaicājumi + saglabātās rezultāta tabulas). Šis fails atveramā jūsu pārlūkā bez login un bez interneta, ja jūs to lejupielādējāt kursa materiālu pakā.

**Ja jūs neredzat ▶ Run pogu vai redzat sintakses kļūdu** — rakstiet Q&A panelī "kur ir Run poga?" vai "redzu sintakses kļūdu". Mikus atbildēs ar paste/sintakses ievirzi.

**Vidus-loga orientācijas pārbaude (~minūte 8 no Bloka sākuma):** pasniedzējs ievietos atrunu — _"vēl ~4 minūtes T1 vaicājumam; ja vaicājums neielādējas vai redzat sintakses kļūdu, rakstiet Q&A panelī — Mikus palīdzēs."_ Tas nav pārtraukums — vienkārši orientācija. Turpiniet darbu.

**T1 → T2 transition (~minūte 12):** _"T1 — pabeigts. Tagad T2: viens elements maināms — institūcijas Q-numurs. Vaicājuma teksts ir nākamajā slaidā."_

**T2 → T3 transition (~minūte 16):** _"T2 — pabeigts. T3 ir pēdējais vaicājums; tā pati P6782 īpašība, divi OPTIONAL atribūti — laiks un vieta. Tas ir F2 ≡ R1 saiknes pierādījums. Vaicājums nākamajā slaidā."_

---

## 4. SPARQL šabloni

Trīs vaicājumi, visi verificēti dzīvi 2026-05-04 PM. Visi mērķē uz `https://query.wikidata.org/`. Faili: `data/topic4-block4.5/template-{1,2,3}.txt`.

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
- `LIMIT 12` = atgriezt ne vairāk par 12 rindām (neierobežots vaicājums būtu lēns un nelasāms)

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

Tas filtrē rezultātu, lai paliek tikai tās iestādes, kas Wikidata ir klasificētas kā "universitāte". **Pedagoģiskais punkts:** vienīgais kas mainās — jūs pievienojat _vienu_ kvalifikatoru, kas sašaurina rezultātu. Tā pati `wdt:P6782` struktūra; cits konkrētais jautājums.

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

**Pievienotie laukus:** `?inception` (P571 — dibināšanas gads, _nepieciešams_) + `?hqLabel` (P159 — mītne, _opcionāls_).

- `wdt:P571` = inception ([Property:P571](https://www.wikidata.org/wiki/Property:P571))
- `wdt:P159` = headquarters location ([Property:P159](https://www.wikidata.org/wiki/Property:P159))
- `OPTIONAL { ... }` = ja ieraksts par šo lauku nav — neslēpj rindu (atstāj lauku tukšu)
- `ORDER BY ?inception` = sakārto pēc dibināšanas gada (vecākās augšā)

**Pedagoģiskais punkts:** `wdt:P6782` (ROR ID) ir _tas pats lauks_, ko T1 izmantojām, lai _atrastu_ iestādes (F2 — Findable). T3 šis pats lauks nāk ar dibināšanas gadu un mītnes pilsētu — kas piešķir kontekstu _atkārtotai izmantošanai_ (R1 — Reusable). **Lauks nemainās. Mainās jautājums.**

---

## 5. Rezultātu sagaidāmie iznākumi (verificēti dzīvi 2026-05-04 PM)

### 5.1 T1 sagaidāmais — 12 rindas (~0,2 sek)

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

**Pamaniet:** RTU Rēzeknes akadēmijai ir **divi ROR ID** (`04d6the49` + `0510ppv76`) — tas ir reāls Wikidata ↔ ROR savienojuma raksts (institūcija pastāv vairāk kā vienā ROR ierakstā vēsturisku iemeslu dēļ; viens primārs, viens vēsturisks). Tas ir pedagoģisks novērojums R1.3 par "saites starp reģistriem ne vienmēr ir 1:1; un tas ir kopienas standartu darbības raksts".

### 5.2 T2 sagaidāmais — 10 rindas (~0,3 sek)

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

### 5.3 T3 sagaidāmais — 8 rindas (~0,3 sek; sakārtotas pēc dibināšanas gada)

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

**Pamaniet:** **astoņas vecākās** Latvijas iestādes ar dokumentētu dibināšanas gadu — visas pirms 1922. gada. Sešas no tām atrodas Rīgā. Tas ir _bagātīgs apraksts_ (R1) — un visi šie metadati nāk no _tā paša lauka_ (`wdt:P6782` ROR ID), ko mēs izmantojām T1 _atrašanai_ (F2).

> **Ja jūsu rezultāts neatbilst šīm tabulām** — tas ir _live Wikidata_ izmaiņas (Wikidata atjauninās minūšu līmenī). Saglabātās tabulas ir 2026-05-04 PM moments; jūsu live rezultāts ir derīgs; saglabātais ir uzziņa. Pedagoģiskais saturs nemainās.

---

## 6. Aptauja 3 — SPARQL iznākuma kalibrācija (viena atbilde)

**Aptauja 3 (Bloks 4.5, klusuma darba beigās, ~minūte 22 no Bloka sākuma):**

> _"Pēc trim SPARQL šabloniem (T1, T2, T3): kura no šīm atziņām jums šobrīd ir vissvarīgākā?"_ (viena atbilde)

- (a) Es saprotu, ka SPARQL ir reāli izmantojams rīks, ne tikai akadēmisks koncepts
- (b) Es saprotu, kā ROR / ORCID identifikatori savieno datus starp sistēmām
- (c) Es saprotu, ka F2 un R1 ir viens un tas pats lauks no diviem leņķiem
- (d) Es nezinu — vajag laiku to apdomāt
- (e) SPARQL šobrīd nav prioritāte manai praksei

**Atbildes nav pareizas vai nepareizas — tās ir kalibrācijas dati pasniedzēja T3 demonstrācijai.** Pasniedzējs T3 demonstrēs ~1.5 min pēc Aptaujas slēgšanas; demonstrācijas ievada veids pielāgojas dominējošajai opcijai.

---

## 7. Pēc aptaujas — pasniedzēja T3 demonstrācija

Pēc Aptaujas 3 slēgšanas pasniedzējs atver `query.wikidata.org` ar T3 vaicājumu, palaiž to, un izklāsta atbilstoši Aptaujas rezultātam. **Ja Aptauja 3 (c) opcija ≥30 % — pasniedzējs to atzīmē kā Bloka 4.6 noslēguma F2 ≡ R1 inversijas priekšstāstījumu.**

Galvenais konstatējums, ko pasniedzējs demonstrēs (lai jūs pēc sesijas varētu pārlasīt):

> _"Pamaniet, _kas tieši_ T3 saka. Mēs T1 lietojām `wdt:P6782` — ROR ID — lai _atrastu_ Latvijas iestādes. T3 lieto **to pašu** `wdt:P6782` — un pievieno `wdt:P571` dibināšanas gadu un `wdt:P159` mītnes pilsētu. **Lauks nemainās. Mainās jautājums.** T1 jautājums bija 'kuras iestādes pastāv?' — F kategorijas jautājums (Findable). T3 jautājums ir 'kāds konteksts ļauj atkārtoti izmantot iestādes datus?' — R kategorijas jautājums (Reusable). **Tas pats lauks. Divi jautājumi.** Tas ir F2 ≡ R1."_

Šī ir Bloka 4.5 noslēguma _payoff_ un Bloka 4.6 _ievada_ saikne. Bloks 4.6 turpinās ar 60-sekunžu F2 ≡ R1 _inversijas_ atrunu — _kursa pedagoģisko kulmināciju_.

---

## 8. F2 ≡ R1 sintēze — pēc sesijas izlasīt

> **NB:** Šī sadaļa ir _pēc sesijas_ uzziņai. **Neaizpildiet to klusuma darba laikā** — 3. sadaļa ir jūsu darbība klusuma laikā; 8. sadaļa ir lasīšana pēc sesijas, lai stiprinātu, ko mehāniski ieraudzījāt T3 demonstrācijā.

### 8.1 Tas pats lauks; divi jautājumi

| Lauks | T1 jautājums (F2 — Findable) | T3 jautājums (R1 — Reusable) |
|-------|------------------------------|-------------------------------|
| `wdt:P6782` ROR ID | "Kuras Latvijas iestādes pastāv ROR reģistrā?" | "Kāds konteksts ļauj atkārtoti izmantot to datus?" |
| `wdt:P17` country | (filtrs uz Latviju) | (filtrs uz Latviju) |
| `wdt:P571` inception | _(neizmantots T1)_ | "Kad iestāde dibināta?" — atkārtotai izmantošanai |
| `wdt:P159` headquarters | _(neizmantots T1)_ | "Kur iestāde atrodas?" — atkārtotai izmantošanai |

T1 izmanto _vienu_ savienojumu (`?inst wdt:P6782 ?ror`) ar valsts filtru — pietiek atrast iestādi. T3 izmanto _to pašu_ `wdt:P6782` plus divus papildus laukus, kas piešķir kontekstu — pietiek izmantot atkārtoti.

### 8.2 Bloka 4.6 inversijas atruna (kursa pedagoģiskā kulminācija)

Bloka 4.6 vidū pasniedzējs piegādā 60-sekunžu inversijas atrunu (verbatim, nepārstrādājot). Tās saturs:

> _"Mēs šodien aizpildījām R rindu. Bet vissvarīgākā lieta nav 'mēs aizpildījām R'. Vissvarīgākā lieta — atskaņojums no 1. sesijas. Mēs 1. sesijā saucām vienu Andreja Baloža metadatu lauku — _datus apraksta bagātīgi metadati_ — par F2. Mēs šajā sesijā to pašu lauku saucām par R1. **Tas ir viens un tas pats lauks.** Jūs to esat redzējuši piecas stundas. Jūs to esat aizpildījuši piecsimt reižu projektos. Atšķirība starp 'F' un 'R' nav atšķirība laukā — tā ir atšķirība jautājumā, ko mēs uzdodam. Jautājums 'kas padara atrodamu?' ir F2. Jautājums 'kas padara izmantojamu?' ir R1. Lauks nemainās. Jūsu darbs nemainās. Mainās jautājums — un FAIR karte ir aizpildīta."_

### 8.3 Kāpēc tas ir svarīgi praksē

FAIR principu rīks (F-UJI un kompānija) novērtē jūsu metadatus pa atsevišķiem laukiem — vai pastāv DOI? vai pastāv licence? vai pastāv apraksts? Bet pēdējais novērojums — F2 ≡ R1 — saka: **vairums no jums jau aizpilda R1 metadatus, kad aizpildāt F2 metadatus**. Jūsu darba vairāk-mazāk strukturālā daļa _jau ir_ FAIR; jums vēl jāizpilda **R1.1 (licence ar SPDX žetonu), R1.2 (atbildības saites caur DataCite Date / Contributor / RelatedIdentifier / Funding), R1.3 (jūsu disciplīnas standarts)**. Tie ir mazi pievienojumi, ne strukturāla pārveide.

---

## 9. Pēc sesijas — palaidiet pats SPARQL

Trīs soļi, ko varat veikt pēc sesijas, lai SPARQL palaišana paliek konkrēta jūsu praksē:

1. **Atveriet** <https://query.wikidata.org/> un palaidiet T1 vēlreiz. Eksperimentējiet — `wd:Q211` (Latvija) → `wd:Q35` (Dānija); `LIMIT 12` → `LIMIT 30`. Apskatieties, kā mainās rezultāts.
2. **Mainiet T2** — `wd:Q3918` (university) → `wd:Q31855` (research institute). Cik LV pētniecības institūtu pastāv ROR savienojumā?
3. **Mainiet T3** — pievienojiet `OPTIONAL { ?inst wdt:P856 ?website }` — official website. Cik no 8 vecākajām LV iestādēm ir oficiāla mājaslapa Wikidata ierakstā?

Ja jūsu darbs prasa konkrētu SPARQL prasmi (pētniecības datu atrašana caur ROR identifikatoriem; jūsu disciplīnas datu kopu apkopošana DataCite Commons + Wikidata krustojumā) — runājiet ar VPC datu kuratoriem (`vpc@vpc.gov.lv`) vai sazinieties pasniedzējam (`eduards.skvireckis@lnb.lv`).

---

## 10. Resursi padziļinātai izpētei

### 10.1 SPARQL un Wikidata pamati

- **W3C SPARQL 1.1 Query Language** ([w3.org/TR/sparql11-query](https://www.w3.org/TR/sparql11-query/)) — kanoniskā specifikācija (Recommendation 2013-03-21)
- **Wikidata Query Service tutorial**: <https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/queries> — example query gallery
- **Wikidata SPARQL kursa lapa**: <https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service> — full documentation

### 10.2 Identifikatoru reģistri (R1.3 kontekstā)

- **ROR (Research Organization Registry)**: <https://ror.org/> — meklēt jūsu iestādes ROR ID
- **ORCID**: <https://orcid.org/> — ja jums vēl nav, reģistrējiet (15 minūšu darbs)
- **Wikidata**: <https://www.wikidata.org/> — Q numuri citu iestāžu meklēšanai

### 10.3 DataCite + Wikidata krustojums

- **DataCite Commons**: <https://commons.datacite.org/> — meklēt datu kopas pēc DOI / autora / iestādes
- **DataCite ↔ Wikidata savienojums**: <https://commons.datacite.org/integrations/wikidata> — eksperimentāls projekts, kas atspoguļo DataCite metadatus Wikidata ierakstos

### 10.4 Linked Data 5-zvaigžņu modelis (atskaite uz 3. sesiju)

- **Berners-Lee 2010**: <https://www.w3.org/DesignIssues/LinkedData.html> — 5-zvaigžņu publicēšanas kāpne (★ līdz ★★★★★). SPARQL hands-on padara redzamu, ka jūs esat ★★★★ patērētājs — Wikidata datus saistāt ar jūsu jautājumu.

### 10.5 Kanoniskie kursa avoti

- **Phase 4a lecturer master**: `admin/research/05-topic4-practical.md` — pasniedzēja darba dokumentācija
- **Phase 1 deep research**: `admin/research/03-topic4-reusable-practice-deep.md` — R1/R1.1/R1.2/R1.3 verificētie avoti
- **Materiālu pakas URL**: pieejama kursam beidzoties — sk. Bloka 4.6 noslēgumā paziņoto adresi
- **Sazināšanās**: <eduards.skvireckis@lnb.lv> (atbildu darba dienā; ne vienmēr ar gala atbildi, bet vienmēr ar nākamo soli)

---

## 11. Atgriezeniskā saite

Pēc sesijas, lūdzu, atstājiet īsu atgriezenisko saiti ar:

- Vai trīs SPARQL šabloni (T1 / T2 / T3) bija pieņemamā sarežģītības līmenī jums? Pārāk vienkārši / piemēroti / pārāk sarežģīti?
- Cik no trim vaicājumiem jūs paspējāt palaist dzīvi 16 minūšu klusuma darba laikā?
- Vai F2 ≡ R1 saiknes pierādījums (T3) bija jums skaidrs pēc T3 demonstrācijas? Ja ne — kas palika neskaidrs?
- Vai 25 minūšu Bloka 4.5 budžets bija pietiekams / par maz / par daudz?
- Vai vēlaties pēc kursa eksperimentēt ar SPARQL pret Wikidata? Norādiet sajūsmīgi — VPC datu kuratori var palīdzēt savienoties ar SPARQL kopienu.

Atbildes (anonīmas) tiks iekļautas pēc-sesijas materiālu pakā un izmantotas kursa pielāgošanai nākamajam izlaidumam.

