# Topic 3 — Interoperable: demo dati

Faili, uz kuriem atsaucas 3. sesijas slaidi (Interoperable — vārdnīcas un saistītie dati). Demonstrē divus galvenos koncepcijas: kā QVUERT iznāk kā saistīto datu graf-fragments (RDF Turtle) un kā Wikidata Query Service (SPARQL) ļauj iegūt strukturētu informāciju no Wikidata.

## Saistīto datu graf-fragments (Block 3.2)

| Fails | Formāts | Saturs |
|-------|---------|--------|
| [`topic3-block3.2-mini-graph.png`](topic3-block3.2-mini-graph.png) | PNG | D2-render mini-grafs: QVUERT datu kopa centrā, ar bultiņām uz autora ORCID, autoram bultiņa uz afiliācijas ROR, atpakaļ uz QVUERT no diviem priekšmetiem (subject) un divām citēšanas saitēm |
| [`topic3-block3.2-qvuert-turtle.txt`](topic3-block3.2-qvuert-turtle.txt) | RDF Turtle | 5-rindu Turtle paraugs no QVUERT — parāda, kā schema.org laukus var izteikt kā subject-predicate-object trīnieku |

**Demo loģika:** vienam un tam pašam saturam (kas redzams JSON-LD eksportā) ir cita izteiksme RDF Turtle formātā. Trīnieku struktūra ļauj sasaistīt datu kopu ar autoritatīvajām vārdnīcām (Wikidata, ROR, ORCID, MeSH) — kā tieši šis padara metadatus _sadarbspējīgus_ ar citām sistēmām.

## Wikidata SPARQL paraugs (Block 3.4)

| Fails | Formāts | Saturs |
|-------|---------|--------|
| [`topic3-block3.4-wikidata-sparql.txt`](topic3-block3.4-wikidata-sparql.txt) | SPARQL | Lecturer SPARQL paraugs — tipiska Wikidata Query Service vaicājuma struktūra ar prefiksiem un `wdt:`/`wd:` pasvītrojumiem |
| [`topic3-block3.4-wikidata-sparql-result.png`](topic3-block3.4-wikidata-sparql-result.png) | PNG | Vaicājuma rezultātu ekrānuzņēmums — fallback, ja WDQS lekcijas laikā nav pieejams vai lēni atbild |

**Demo loģika:** Block 3.4 lecturer atver `query.wikidata.org`, ielīmē šo vaicājumu, palaiž, parāda strukturētus rezultātus. Ja live serviss neatbild — pāriet uz fallback PNG, pedagoģiskais saturs identisks.

## Vārdnīcu integrācija (Block 3.5)

| Fails | Formāts | Saturs |
|-------|---------|--------|
| [`topic3-block3.5-cvoc-screenshot.png`](topic3-block3.5-cvoc-screenshot.png) | PNG | Dataverse CVOC widget ekrānuzņēmums — kā lietotājs datu kopas formā izvēlas terminu no autoritatīvas vārdnīcas (piem., MeSH, Local Contexts) ar autocompletion |

**Demo loģika:** vārdnīcu integrācija UI līmenī — kuratoram nav jāzina, kas ir RDF, lai datu kopas metadatos parādītos pareiza vārdnīcas saite. Tas ir Block 3.5 galvenais pedagoģiskais punkts: I2 apakšprincips netiek nodrošināts ar manuālu redzķeršanu, bet ar pareizu rīka konfigurāciju.

## Saistītie praktiskie uzdevumi

- [Praktiskais uzdevums 3.6](../../../practice/3-interoperable/) — vārdnīcu ieteikuma izstrāde (3 paraugi: QVUERT, SMGJHG, Athar)
