# Topic 4 — Reusable: demo dati

Faili, uz kuriem atsaucas 4. sesijas slaidi (Reusable — atkārtota izmantojamība). Demonstrē, kā R1 apakšprincipi (R1.1 atvērta licence, R1.2 detalizēta proveniences informācija, R1.3 kopienas standarti) iznāk reālos metadatu eksportos no trim datu kopām: **QVUERT** (bagāts R1 aizpildījums), **Zenodo Ikstens** (vidējs aizpildījums) un **Krodznieka 6KFIIY** (LKA Dataverse ar specifiskām licences detaļām).

## QVUERT R1 atribūti (Block 4.2)

Tā pati QVUERT datu kopa kā 1.–3. sesijā, bet šeit lasāma specifiski caur R1 prizmu.

| Fails | Formāts | R1 saturs |
|-------|---------|-----------|
| [`qvuert-r1-datacite.xml`](qvuert-r1-datacite.xml) | DataCite XML | `<rights>` lauks (R1.1 — licence ar URL), `<contributors>` ar lomām (R1.2 — provenience) |
| [`qvuert-r1-dataverse_json.json`](qvuert-r1-dataverse_json.json) | dataverse_json | `termsOfUse` + `license` + `dataAccessPlace` + `useConditions` (R1.1+R1.2 detaļas Dataverse-iekšējā formātā) |
| [`qvuert-r1-schema-org.json`](qvuert-r1-schema-org.json) | schema.org JSON-LD | `license` URL + `creator`/`contributor` ar `affiliation` (tīmekļa atklāšanas slāņa R1) |

**Demo loģika:** vienai datu kopai R1 informācija iznāk **vienlaicīgi** trīs paralēlos formātos — meklētājsistēmām (schema.org), DOI reģistrācijas slānim (DataCite) un Dataverse iekšējam UI (dataverse_json). Visiem trim ir savs R1 lauku komplekts; pareiza aizpildīšana vienā vietā (Dataverse formā) automātiski parādās visās trijās.

## Zenodo Ikstens kontrasts (Block 4.2)

| Fails | Formāts | Saturs |
|-------|---------|--------|
| [`zenodo-19311915-deposit-api.json`](zenodo-19311915-deposit-api.json) | Zenodo Deposit API | Tās pašas datu kopas R1 lauki, bet caur Zenodo Deposit API atbildi (UTF-8 normalizēts) |

**Demo loģika:** **side-by-side kontrasts** ar QVUERT. Ikstens-Zenodo R1 aizpildījums ir mazāks; lecturer parāda, kuras laukas iztrūkst un kā tas ietekmē atkārtotas izmantošanas iespējas. Ne par platformu izvēli, bet par metadatu kvalitāti pašā lauku aizpildījumā.

## Krodznieka 6KFIIY (LKA Dataverse)

| Fails | Formāts | Saturs |
|-------|---------|--------|
| [`lka-6kfiiy-datacite-commons.json`](lka-6kfiiy-datacite-commons.json) | DataCite Commons API | DataCite Commons publiskā API atbilde — agregētais R1 skats |
| [`lka-6kfiiy-dataverse_json.json`](lka-6kfiiy-dataverse_json.json) | dataverse_json | LKA Dataverse iekšējais R1 atribūtu komplekts |

**Demo loģika:** trešais R1 paraugs no humanitāro zinātņu konteksta (LKA — Latvijas Kultūras akadēmija). Lecturer demonstrē, ka R1 nav tikai datu zinātņu vai biomedicīnas problēma — visās disciplīnās der tās pašas atribūtu prasības, ja datu kopu plāno saglabāt atkārtotai izmantošanai.

## Saistītie praktiskie uzdevumi

- [Praktiskais uzdevums 4.5](../../../practice/4-reusable/) — Wikidata Query Service SPARQL praktiskais (3 šabloni)
