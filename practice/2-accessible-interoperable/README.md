# Praktiskais uzdevums 2.5 — F-UJI ziņojums uz Baloža datu kopas

**Sesija:** 2 (A: Pieejami + I1: Sadarbspējīgi) — 2026-05-05, 11:40–12:10
**Bloks:** 2.5 (30 min)
**Formāts:** Pasniedzējs vada iepriekš sagatavota F-UJI ziņojuma walk-through; dalībnieki novēro un seko līdzi 5-metriku kontrolsarakstam; bloka beigās — viena slēdzošā multi-select aptauja par mazāko konkrēto darbību rītdienai.
**Mērķis:** Iemācīties lasīt F-UJI ziņojumu kā **diagnostiku, ne kā vērtējumu** — saprast, kas ir metrika, kas ir punktu skaits, ko ziņojums saka un ko tas neizsaka.

> **Mijiedarbības piezīme:** Sesijas laikā **čats netiek lasīts** (auditorijas mērogs ~197). Ja jums ir formāls jautājums, lūdzu, ievietojiet to **Q&A panelī** — Mikus tos apkopo un pasniedzējs atbild pa pārtraukumu vai sesijas beigās. Šī sesija ietver **trīs aptaujas**: Aptauja 1 par F-UJI iepriekšējo pieredzi (Bloka 2.1 sākumā), Aptauja 2 par formātu lasāmību ar acīm (Bloka 2.3 beigās, pēc trim cilnēm) un slēdzošā Aptauja 3 par mazāko konkrēto darbību rītdienai (Bloka 2.5 beigās).
>
> **Kanoniskie avoti** (`materials/references/dataverse-lv/celvedis/`):
> - FAIR principi: `02-petijumu-planosana/03-fair-principi.md`
> - Metadatu standarti: `05-ilgtermina-saglabasana/01h-metadatu-elementi-un-standarti.md`
> - Pastāvīgie identifikatori: `05-ilgtermina-saglabasana/04-pastavigie-identifikatori.md`

---

## 1. Ko mēs darīsim

Pasniedzējs parāda **iepriekš sagatavotu F-UJI ziņojumu** uz tās pašas Baloža datu kopas, ar kuru strādājām 1. sesijas Bloka 1.4–1.5 brīdī. Ziņojums izveidots 2026. gada 27. aprīlī, dažas stundas pēc datu kopas publicēšanas; tas ir ekrāna koplietošanā kā saglabāts HTML fails.

Walk-through ir lecturer-vadīts: Eduards iet cauri **5 izvēlētām metrikām** no kopā 12, kuras tieši saistās ar šīs sesijas saturu — A apakšprincipi (Bloka 2.2), I1 formālā valoda (Bloka 2.3) un priekšskats uz I2 vārdnīcām (3. sesija) un R1 atribūtiem (4. sesija). Pārējās 7 metrikas ir resursu sarakstā padziļinātai izpētei pēc kursa.

**Centrālais princips šim blokam:** F-UJI sniedz **skaitli** (kopējo procentu) un **ziņojumu** (metriku-pa-metrikai konstatējumus). _Skaitlis nav atbilde — tā ir diagnostika._ Mēs šodien skatāmies uz konstatējumiem, ne uz kopējo. Bagātīgs ziņojums ar 60 % punktiem var pateikt vairāk nekā mehāniski iegūts 90 %.

**Kāpēc viena datu kopa, ne divas:** 1. sesijas Bloks 1.5 jau ieviesa rich vs minimal kontrastu (Balodis dv.dataverse.lv vs Ikstens Zenodo). Topic 2 šo kontrastu neatkārto. Viens uzmanīgs F-UJI ziņojuma lasījums veido diagnostikas mentālo modeli; divi paralēli lasījumi rada salīdzinājuma nogurumu.

---

## 2. Datu kopa

**Nosaukums:** _Biogrāfisko interviju transkripcijas projektā "Konversijas un parāvumi: latviešu filozofijas epistēmiskās stratēģijas padomju periodā (1944-1991)"_

**Autors:** Andrejs Balodis (Latvijas Kultūras akadēmija), ORCID [0000-0002-0688-9213](https://orcid.org/0000-0002-0688-9213)

**DOI:** [`10.71782/DATA/QVUERT`](https://doi.org/10.71782/DATA/QVUERT)

**Repozitorijs:** dv.dataverse.lv

**Landing page:** <https://dv.dataverse.lv/dataset.xhtml?persistentId=doi:10.71782/DATA/QVUERT>

**Kāpēc šī datu kopa:**

- **Caurviju anchor visās 4 tēmās** — 1. sesijā skatījāmies metadatu eksportus, šajā sesijā skatāmies F-UJI diagnostiku, 3. sesijā atgriezīsimies pie I2 vārdnīcām (kas šajā ziņojumā neizdodas), 4. sesijā — pie R1.x (licence, izcelsme, nozaru standarti).
- **Bezsaistē-aprakstīts piekļuves modelis** (4. modelis no Bloka 2.2 atrunas) — interesants A1.2/A2 piemērs. Repozitorijā tikai metadati + ReadMe; transkripcijas tur pētnieks bezsaistē.
- **Bilingvāls description, ORCID-saistīts autors, customlicence** — pietiekami metadatu, lai F-UJI sniegtu nozīmīgu ziņojumu (FAIR=92.31 %), bet ar **vienu konkrētu nepilnību** (I2), kas ir tieši 3. sesijas tēma.

---

## 3. F-UJI rīks

**URL:** <https://www.f-uji.net/?action=test>

**Rīks ir bezmaksas** (web demo) un **brīvi pieejams** (atvērts kods MIT licencē, GitHub `pangaea-data-publisher/fuji`). Strādā jebkurā mūsdienu pārlūkā bez instalācijas.

**Kā lieto:**

| Lauks | Vērtība šim demo | Skaidrojums |
|-------|------------------|-------------|
| **Object Identifier (URL/PID)** | `https://doi.org/10.71782/DATA/QVUERT` | Datu kopas DOI vai landing page URL |
| **Metric Set** | (default) | Atstāj noklusējumu — F-UJI izvēlas jaunāko stabilo metriku versiju |
| **Use DataCite** | ☑ ieslēgts | F-UJI papildus pārbaudīs DataCite Content Resolver (paralēlais A1 kanāls) |
| **Start FAIR Assessment** | klikšķis | Sākas vērtēšana; aizņem 30–60 sek |

**Kas notiek pēc klikšķa:**
1. Atrisinā DOI un atrod landing page
2. Sūta DOI satura izsaukuma (content negotiation) pieprasījumus (CSL JSON, BibTeX, DataCite XML)
3. Apmeklē repozitorijas eksportus (DataCite XML, schema.org JSON-LD, OAI-DC)
4. Pārbauda FAIR Signposting Link headers
5. Salīdzina atrastos metadatus pret 12 metrikām
6. Aprēķina kopējo punktu skaitu un atklāj sekciju-pa-sekcijai ziņojumu

**Šajā blokā Eduards F-UJI nepalaiž tiešraidē** — saglabātais 2026-04-27 ziņojums ir bloka kanoniskais avots. Iemesls: ~197 dalībniekiem dalītā uzmanība uz 30–60 sek tehnisko procesu maksā vairāk nekā ieguvums; turklāt vēsturisks fakts par 2026-04-27 stāvokli ir stabilāks pedagoģiskais pamats nekā tiešraides tehniskais sniegums.

---

## 4. F-UJI ziņojuma 5-metriku kontrolsaraksts

Sekojiet līdzi sesijas laikā. Pēc katras metrikas atzīmējiet, ko redzat. Šī ir _jūsu_ kontrolsaraksts — pēc sesijas to var izmantot, lai pārbaudītu tās pašas metrikas savā datu kopā.

### 4.1 Score summary (kopējais Baloža kopas rezultāts)

| Pīlārs | Punkti | Procenti | Atzīmēt |
|--------|--------|----------|---------|
| **F** (Atrodami) | 7 / 7 | **100 %** | ☐ |
| **A** (Pieejami) | 7 / 7 | **100 %** | ☐ |
| **I** (Sadarbspējīgi) | 4 / 6 | **66.67 %** | ☐ |
| **R** (Atkārtoti izmantojami) | 6 / 6 | **100 %** | ☐ |
| **FAIR kopējais** | 24 / 26 | **92.31 %** | ☐ |

> **Atruna:** _F-UJI dod skaitli. Skaitlis nav atbilde. Tā ir diagnostika — tā parāda, kur skatīties._ Mēs šodien skatāmies uz konstatējumiem, ne uz kopējo. Kāds varētu sasniegt 100 %? Reti. Vai 60 % ir slikti? Atkarīgs no _kuriem_ 60 %.

### 4.2 5 metrikas, kuras Eduards apspriež

| # | Metrika | Statuss | Punkti | Ko F-UJI pārbauda | Atzīmēt |
|---|---------|:-------:|:------:|--------------------|:-------:|
| 1 | **FsF-A1-01M** _Metadata access protocol_ | pass | 1/1 | Vai metadati paši dokumentē piekļuves nosacījumu (atvērts / autentificēts / ierobežots / bezsaistē-aprakstīts) | ☐ |
| 2 | **FsF-A1.1-01MD** _Atvērts protokols_ | pass | 2/2 | Vai piekļuves protokols ir publiski dokumentēts un universally implementable (HTTPS — IETF RFC 9110) | ☐ |
| 3 | **FsF-I1-01M** _Formāla valoda_ | pass | 2/2 | Vai metadati izsacīti formālā, plaši pielietojamā valodā (XML, JSON, JSON-LD) | ☐ |
| 4 | **FsF-I2-01M** _FAIR vārdnīcas_ | **fail** | **0/2** | Vai metadati izmanto reģistrētas semantiskas vārdnīcas (LOV-reģistrētas; SKOS, GEMET, MeSH u.tml.) | ☐ |
| 5 | **FsF-R1-01M** _Bagātīgs apraksts_ | pass | 2/2 | Vai metadati satur bagātīgu, precīzu apraksta saturu | ☐ |

**Galvenais atklājums:** **vienīgā metrika, kas neizdodas Baloža kopā, ir FsF-I2-01M (FAIR vārdnīcas).** Tas nenozīmē, ka Baloža kopa ir slikti dokumentēta — atslēgvārdi ir brīvtekstā ("filozofija Latvijā, padomju filozofija"), nevis kontrolētas vārdnīcas atsauces. **Šī nepilnība ir tieši 3. sesijas tēma** — kontrolētās vārdnīcas (SKOS, GEMET) un Linked Data konteksts.

> **Piezīme par 2-metriku 5-segmenta:** F-UJI 3.5.1 versijā A apakšprincipam nav atsevišķas FsF-A2-01M metrikas — A2 (metadatu un datu ceļu neatkarība) ir implicit caur DOI reģistrāciju + DataCite resolver slāni. Tāpēc 5-metriku walk-through ietver FsF-A1.1-01MD (atvērts protokols) divreiz savienojošā funkcijā: A1.1 pass apstiprina 1. sesijas FAIR ≠ atvērti atrunu un Bloka 2.2 atrunas precizēšanu (4 piekļuves modeļi).

### 4.3 Pārējās 7 metrikas (ne walk-through, bet ziņojumā redzamas)

F-UJI 3.5.1 ievērtē 12 metrikas kopā. Walk-through aptver 5; atlikušās 7 paliek ziņojumā kā jūsu pašu izpētes materiāls:

| Metrika | Joma | Pārbauda |
|---------|------|----------|
| FsF-F1-01D | Atrodami | Datu identifikators (DOI, Handle u.c.) |
| FsF-F1-02D | Atrodami | Identifikators ir globāli unikāls un pastāvīgs |
| FsF-F2-01M | Atrodami | Bagātīgi metadati par datiem |
| FsF-F3-01M | Atrodami | Metadati nepārprotami norāda datu identifikatoru |
| FsF-F4-01M | Atrodami | (Meta)dati reģistrēti meklējamā resursā |
| FsF-A1-02MD | Pieejami | Datu (ne tikai metadatu) piekļuves protokols |
| FsF-A1.2-01MD | Pieejami | Autentifikācijas protokols (kad nepieciešams) |
| FsF-I3-01M | Sadarbspējīgi | Kvalificētas atsauces uz citiem (meta)datiem |
| FsF-R1.1-01M | Atkārtoti izm. | Licence |
| FsF-R1.2-01M | Atkārtoti izm. | Izcelsme (provenance) |
| FsF-R1.3-01M | Atkārtoti izm. | Atbilst nozaru standartiem |

(Kopā 12 metrikas — sk. <https://www.f-uji.net/index.php?action=methods> visu metriku oficiālajai references lapai.)

---

## 5. Ko F-UJI walk-through atklāj — tilti uz 3. un 4. sesiju

### 5.1 Atklājums 1: A1.2 pass empīriski apstiprina iepriekšējās sesijas atrunu

Iepriekšējā sesijā Bloka 1.1 atrunā teicām: _"FAIR principi neparedz obligātu datu atvēršanu — tie nodrošina, ka dati ir labi organizēti un dokumentēti pat tad, ja piekļuve ir ierobežota."_ 2. sesijas Bloks 2.2 to precizēja kā 4 piekļuves modeļus (atvērts / autentificēts / ierobežots / bezsaistē-aprakstīts).

F-UJI to apstiprina automātiski:
- **A1.2 pass** ar `auth_method: TLS, BASIC` — atvērts protokols + standartizēta autorizācija
- Baloža kopa ir _bezsaistē-aprakstīts_ piekļuves modelis (transkripcijas tur pētnieks bezsaistē)
- Bet **autentifikācijas mehānisms** ir caur HTTP standartu, kas dokumentēts metadatos
- Tāpēc A1.2 izpildīts pilnībā

**Mācība:** ja jūsu kopa ir slēgta vai bezsaistē-aprakstīta, **tas neietekmē A vērtējumu** — kamēr vien jūsu repozitorijs metadatos dokumentē piekļuves nosacījumu.

### 5.2 Atklājums 2: I2 fail — tas ir 3. sesijas tilts (ne F-UJI kļūda)

F-UJI atrod 24 namespace URI Baloža metadatos. Pēc default filtrēšanas (XMLSchema, schema.org, ogp.me — _foundational_, ne FAIR vārdnīcas) paliek **0 namespace**, kas būtu reģistrēti Linked Open Vocabularies reģistrā (`https://lov.linkeddata.es/`).

**Iemesls:** Baloža atslēgvārdi ir brīvtekstā:

> _"filozofija Latvijā, padomju filozofija, konversijas, pārrāvumi, epistēmiskās stratēģijas"_

Tas ir labi atklāšanai un cilvēklasāmībai. Bet tas **nav saistīts** ar reģistrētu vārdnīcu — piemēram, _Library of Congress Subject Headings_, _GEMET_, _MeSH_, vai humanitāro zinātņu specifisku tēzauru.

**Mācība:** I2 (FAIR vārdnīcas) prasa ne tikai piepildīt subject lauku, bet arī **savienot** ar reģistrētu vārdnīcu. To risina **kontrolētās vārdnīcas** un Dataverse CVOC mehānisms. **Pēcpusdienā 3. sesijā** mēs redzēsim, kā SKOS / GEMET / MeSH integrējas dataverse.lv un kā Baloža kopas atslēgvārdus var piesaistīt reģistrētai vārdnīcai.

### 5.3 Atklājums 3: R 100 % ir virsma, ne dziļums — tas ir 4. sesijas tilts

F-UJI dod 100 % R pīlāram. Bet F-UJI **virsma** pārbauda — vai licence URL eksistē, vai izcelsmes lauks ir aizpildīts, vai subject atbilst nozarei. Tas neapskata, vai _saturs_ ir labs.

Wilkinson 2016 R principu īsi:
- **R1.1** _atvērta data izmantošanas licence_ — Vai licence ir patiešām saprātīga? Vai tā ļauj atkārtotu izmantošanu? Vai SPDX-standartlicence vai customlicense?
- **R1.2** _detalizēta izcelsme (provenance)_ — Vai izcelsmes apraksts ir patiešām detalizēts? Vai cits pētnieks varētu reproducēt jūsu datu radīšanas procesu?
- **R1.3** _atbilstība nozaru standartiem_ — Vai jūs reāli atbilstat savas nozares standartiem (DDI sociālajām zinātnēm, EML ekoloģijai u.tml.)?

**Mācība:** F-UJI ir labs sākumpunkts, ne FAIR audita aizvietotājs. **Pēcpusdienas 4. sesijā** mēs ejam dziļāk — kā izvēlēties licenci, kā dokumentēt izcelsmi, kā atbilst nozarei.

---

## 6. Aptauja 3 (priekšskats — sesijas laikā parādīsies MS Teams aptaujā)

Bloka beigās (apmēram 12:07) MS Teams atvērs **vienu multi-select aptauju**. Anonīma. Vairākas atbildes ir gaidāmas — lielākajai daļai dalībnieku būs vairāki iespējami uzlabojumi.

> **Aptauja 3 — multi-select:** _"Kas ir mazākā konkrētā darbība, ko jūs varētu izdarīt rītdien savā vai sava darba kopā — pamatojoties uz to, ko F-UJI ziņojums uz Baloža kopas mums tikko parādīja?"_
>
> - (a) **Pievienot** bilingvālu apraksta tekstu (LV + EN), kā Baloža `description` 1703 zīmes
> - (b) **Pievienot** ORCID identifikatoru visiem autoriem
> - (c) **Pārbaudīt** licences SPDX-formātu — vai tā ir standartlicence (CC BY 4.0 u.tml.) vai customlicense
> - (d) **Palaist** F-UJI uz savu publicētu datu kopu nedēļas laikā (`https://www.f-uji.net/?action=test`)
> - (e) Plānoju savu pirmo datu kopas publicēšanu — F-UJI būs orientieris jaunajai kopai
> - (f) Cits

> **Piezīme par opciju formu:** opcijas izmanto **darbības verbus** (Pievienot, Pārbaudīt, Palaist) vai nodoma izteikumus (Plānoju savu pirmo publicēšanu). Tās **nav** F-UJI kategoriju nosaukumi (Findability / Accessibility / Interoperability / Reusability). Iemesls: aptauja ir _intent-formation_ — jums jāizvēlas konkrēts solis rītdienai, ne FAIR principa kategorijas pārbaude. (Pedagoģisks dizains; precīzāk — Bloka 1.2 audita precedentā uzskatu, ka klasifikācijas aptaujas tieši pēc atbilstoša ekrāna ir struktūras-līmenī kļūdainas.)

Šī ir _intent-formation_ aptauja, ne zināšanu pārbaude. Jūsu atbilde palīdz pasniedzējam izprast auditorijas faktiskās prioritātes un, ja kāda opcija dominē, sniegs papildu komentāru par tā uzlabojuma praktisko ieviešanu (piemēram, ja >50 % izvēlas (a) bilingvālu description, Eduards komentē, ka tas ir vienīgais lielākais sviras punkts un 30 minūtes papildu darba dod faktoru-2 atklājamību).

---

## 7. Pēc sesijas — palaidiet F-UJI uz savu kopu

Ja jums jau ir publicēta datu kopa (dataverse.lv, Zenodo, OSF, figshare, vai citā FAIR repozitorijā):

### 7.1 Palaidiet F-UJI

1. Atveriet <https://www.f-uji.net/?action=test>
2. Ielīmējiet savu DOI URL formātā `https://doi.org/JŪSU/DOI` (vai landing page URL)
3. Atstājiet noklusējumus (Metric Set = default; Use DataCite = ieslēgts)
4. Klikšķiniet **Start FAIR Assessment**
5. Gaidiet 30–60 sek; ziņojums atveras tajā pašā lapā

### 7.2 Identificējiet zemākos punktus

Ziņojumā meklējiet metrikas, kur statuss ir **fail** vai **partial**. Tās ir lauki, kuru uzlabošana visvairāk paaugstinās jūsu kopējo punktu skaitu.

### 7.3 Veiciet vienu konkrētu uzlabojumu

Tipiski **30-min uzlabojumi**, kas dod 5–10 % punktu pieaugumu:
- **Pievienot bilingvālu aprakstu** (LV + EN, `description` laukā) — paaugstina F2 redzamību angļu meklējumos un R1-01M virsmu
- **Pievienot ORCID** katram autoram — paaugstina I3 (kvalificētas atsauces) un F2
- **Pārbaudīt `license` SPDX-formātu** — pārliecinās, ka licence ir standarta CC BY 4.0 (vai cita SPDX-reģistrēta), ne customlicense. Paaugstina R1.1 automatizāciju (4. sesija)
- **Pārbaudīt, ka `subject` atbilst kontrolētai vārdnīcai** (3. sesijā skatīsim, kā to izdarīt) — paaugstina I2

### 7.4 Atkārtoti palaidiet F-UJI

Pēc uzlabojumu publicēšanas (var prasīt jaunu datu kopas versiju) palaidiet F-UJI vēlreiz. Salīdziniet ar pirmo rezultātu. **Šī ir intent-formation Aptaujas 3 (d) opcijas konkrētā realizācija** — ja izvēlējāties (d), šis ir solis-pa-solim plāns rītdienai.

---

## 8. Resursi padziļinātai izpētei

| Resurss | URL |
|---------|-----|
| **F-UJI tīmekļa rīks** | <https://www.f-uji.net/?action=test> |
| **F-UJI 12-metriku reference** | <https://www.f-uji.net/index.php?action=methods> |
| **F-UJI publikācija** (Devaraju & Huber, 2021, RIO Journal) | <https://doi.org/10.3897/rio.7.e69287> |
| **F-UJI atvērtais kods** (GitHub) | <https://github.com/pangaea-data-publisher/fuji> |
| **FAIRsFAIR Data Object Assessment Metrics** (Zenodo) | <https://doi.org/10.5281/zenodo.3775793> |
| **DataverseLV ceļvedis — FAIR principi** | <https://dataverse.lv/fair-principi/> |
| **DataverseLV ceļvedis — Metadatu standarti** | <https://dataverse.lv/metadatu-elementi-un-standarti/> |
| **DataverseLV ceļvedis — Pastāvīgie identifikatori** | <https://dataverse.lv/pastavigie-identifikatori/> |
| **JSON Schema 2020-12** specifikācija | <https://json-schema.org/draft/2020-12/json-schema-core.html> |
| **JSON Schema pārlūka validators** | <https://json-schema.hyperjump.io/> |
| **DataCite Metadata Schema 4.7** (release 2026-03-03) | <https://datacite-metadata-schema.readthedocs.io/en/4.7/> |
| **schema.org Dataset v30.0** (release 2026-03-19) | <https://schema.org/Dataset> |
| **JSON-LD 1.1** (W3C Recommendation) | <https://www.w3.org/TR/json-ld11/> |
| **OAI-PMH 2.0** specifikācija | <https://www.openarchives.org/OAI/openarchivesprotocol.html> |
| **DataCite Content Resolver** | <https://support.datacite.org/docs/datacite-content-resolver> |
| **dv.dataverse.lv eksporta API** | <https://guides.dataverse.org/en/latest/api/dataaccess.html> |
| **Linked Open Vocabularies reģistrs** (3. sesijas priekšskats) | <https://lov.linkeddata.es/> |
| **FAIR Signposting Profile** | <https://signposting.org/FAIR/> |
| **W3C XML Schema 1.1** | <https://www.w3.org/TR/xmlschema11-1/> |
| **FAIR-Aware self-assessment** (DANS) | <https://fairaware.dans.knaw.nl/> |

---

## 9. Atgriezeniskā saite

Kursa beigās (vai pēc sesijas e-pastā) — ja jūs palaidāt F-UJI uz savu kopu un veiksiet uzlabojumus, lūdzu, dalieties ar to:

- Kāds bija sākotnējais punktu skaits?
- Kuru metriku jūs uzlabojāt? (FsF-I2-01M ir parastais, jo lielākajā daļā kopu vārdnīcas vēl nav piesaistītas)
- Kāds bija jaunais punktu skaits pēc uzlabojuma?
- Vai pamanījāt atklājamības atšķirību (Google Dataset Search rezultāti, OpenAIRE indeksācija u.tml.)?

Tas palīdzēs uzlabot nākamās VPC apmācības un sniegt konkrētus piemērus turpmākiem dalībniekiem.
