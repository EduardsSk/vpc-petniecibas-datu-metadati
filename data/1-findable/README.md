# Topic 1 — Findable: demo dati

Faili, uz kuriem atsaucas 1. sesijas slaidi (Findable — atrodami metadati). Visi ir reāli metadatu eksporti no divām publicētām datu kopām: **QVUERT** (Balodis, dataverse.lv) un **Zenodo 19311915** (Ikstens). Slaidos tos lieto, lai parādītu, ka vienai datu kopai pastāv vairāki paralēli eksporta formāti — un kāda ir kvalitātes atšķirība starp bagātīgu un minimālu lauku aizpildīšanu.

## QVUERT eksporti (dataverse.lv)

| Fails | Formāts | Saturs |
|-------|---------|--------|
| [`qvuert-datacite.xml`](qvuert-datacite.xml) | DataCite XML 4.x | DOI reģistrācijas profils — autori, virsraksts, izdevējs, gads, identifikators |
| [`qvuert-dcterms.xml`](qvuert-dcterms.xml) | Qualified Dublin Core | DC Terms ar `dcterms:` qualifikatoriem (datums, valoda, tiesības) |
| [`qvuert-oai-dc.xml`](qvuert-oai-dc.xml) | OAI Dublin Core | OAI-PMH minimālais 15-elementu komplekts — kas iet uz citām meklētājsistēmām |
| [`qvuert-schema-org.json`](qvuert-schema-org.json) | schema.org JSON-LD | Tīmekļa atklāšanas slānis (Google Dataset Search ielasa šo) |
| [`qvuert-linkset.json`](qvuert-linkset.json) | RFC 9264 linkset | Signposting linkset — saites uz cite-as, type, license u.c. |
| [`qvuert-signposting.txt`](qvuert-signposting.txt) | HTTP `Link:` galvenes | Tāda pati informācija kā linkset, bet HTTP-līmeņa galveņu formātā |

## Zenodo 19311915 eksporti (Ikstens)

| Fails | Formāts | Salīdzinājums |
|-------|---------|--------------|
| [`zenodo-19311915-datacite.xml`](zenodo-19311915-datacite.xml) | DataCite XML | Tāds pats slānis kā QVUERT, **bet ar mazāku lauku aizpildījumu** |
| [`zenodo-19311915-oai-dc.xml`](zenodo-19311915-oai-dc.xml) | OAI Dublin Core | Vēl mazāk — minimālais OAI-DC profils |
| [`zenodo-19311915-schema-org.json`](zenodo-19311915-schema-org.json) | schema.org JSON-LD | Zenodo-noklusējuma JSON-LD (mazāka kvalitāte nekā QVUERT) |
| [`zenodo-19311915-signposting.txt`](zenodo-19311915-signposting.txt) | HTTP `Link:` galvenes | Zenodo Signposting galvenes |

## Kā lasīt šos failus

- **DataCite XML** un **OAI-DC XML** lasāmi jebkurā tekstu redaktorā vai pārlūkprogrammā
- **JSON-LD** un **linkset.json** — derīgs JSON; var atvērt arī kā JSON Schema validācijas avotu
- **Signposting `.txt`** — viena rinda HTTP `Link:` galvene formātā; reāli serveri to atdod kā HTTP atbildes galveni, šeit saglabāts kā tekstu, lai būtu redzams

## Saistītie praktiskie uzdevumi

- [Praktiskais uzdevums 1.5](../../../practice/1-findable/) — eksportu salīdzinājums (Balodis vs Ikstens)
