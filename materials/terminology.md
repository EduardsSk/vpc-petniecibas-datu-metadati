# Terminoloģija

Terminu uzziņa semināra dalībniekiem — angļu termins, latviešu kanoniskā forma un īsa definīcija. Latviešu formas atbilst dataverse.lv glosārijam un _Latvijas atvērtās zinātnes stratēģijai_; tās ir vienotas visos kursa materiālos.

**Piezīme par FAIR formām:** FAIR principus kursā lieto daudzskaitlī un piesaistītus datiem — _dati ir atrodami, pieejami, sadarbspējīgi, atkārtoti izmantojami_. Vienskaitļa formas ("atrodams", "pieejams") nelieto.

## FAIR principi

| EN | LV | Skaidrojums |
|----|----|-------------|
| FAIR | FAIR | Findable, Accessible, Interoperable, Reusable — saīsinājumu netulko. |
| Findable | atrodami | datus var atrast cilvēks un mašīna (pastāvīgs identifikators, bagātīgi metadati). |
| Accessible | pieejami | metadatus un datus var izgūt ar standartizētu protokolu. |
| Interoperable | sadarbspējīgi | dati izmanto formālu valodu un kopīgas vārdnīcas (bez "ī" pirms "spēj"). |
| Reusable | atkārtoti izmantojami | datus var izmantot atkārtoti — skaidra licence, izcelsme, nozaru standarti. |

FAIR apakšprincipu īsformas (kā redzamas FAIR kartē slaidos):

| Apakšprincips | LV etiķete | Skaidrojums |
|---------------|-----------|-------------|
| F1 | pastāvīgs ID | globāli unikāls, pastāvīgs identifikators. |
| F2 | bagātīgi metadati | resurss aprakstīts ar plašiem metadatiem. |
| F3 | ID metadatos | metadati skaidri norāda datu identifikatoru. |
| F4 | reģistrēts | (meta)dati reģistrēti meklējamā resursā. |
| A1 | protokols | izgūstams ar standartizētu protokolu. |
| A1.1 | atvērts protokols | protokols ir atvērts, brīvs, vispārēji ieviešams (piemēram, HTTPS). |
| A1.2 | autorizācija protokolā | protokols atļauj autentifikāciju un autorizāciju, kur nepieciešams. |
| A2 | nezūdoši metadati | metadati paliek pieejami arī tad, kad datu vairs nav. |
| I1 | formālā valoda | zināšanu izteikšanai izmanto formālu, kopīgu valodu (RDF, XML, JSON). |
| I2 | FAIR vārdnīcas | metadati lieto vārdnīcas, kas pašas seko FAIR principiem. |
| I3 | jēgpilnas attiecības | tipētas, nozīmīgas saites uz citiem (meta)datiem, ne tikai URL. |
| R1 | bagātīgs apraksts | dati aprakstīti ar precīziem, būtiskiem atribūtiem. |
| R1.1 | licence | skaidra, pieejama datu lietošanas licence. |
| R1.2 | izcelsme | dokumentēta datu izcelsme (provenance). |
| R1.3 | nozaru standarti | metadati atbilst disciplīnas kopienas standartiem. |

## Metadati

| EN | LV | Skaidrojums |
|----|----|-------------|
| metadata | metadati | strukturēta informācija par resursu. |
| descriptive metadata | aprakstošie metadati | identificē un apraksta resursu. |
| structural metadata | strukturālie metadati | resursa iekšējā organizācija. |
| administrative metadata | administratīvie metadati | piekļuve, tiesības, saglabāšana. |
| metadata schema | metadatu shēma | strukturāls metadatu modelis ar laukiem un datu tipiem. |
| metadata standard | metadatu standarts | sabiedriski apstiprināta shēma (Dublin Core, DataCite, schema.org). |
| metadata export | metadatu eksports | viens un tas pats ieraksts citā formātā vai standartā. |
| metadata harvesting | metadatu ievākšana | OAI-PMH protokola process, kurā agregatori savāc metadatus. |
| metadata quality | metadatu kvalitāte | pilnīgums, precizitāte, konsekvence, savlaicīgums. |

## Identifikatori un repozitoriji

| EN | LV | Skaidrojums |
|----|----|-------------|
| persistent identifier | pastāvīgs identifikators | identifikators, kas saglabājas laikā (DOI, ORCID, Handle, ARK). |
| DOI | DOI | datu kopu un publikāciju pastāvīgais identifikators. |
| ORCID | ORCID iD | pētnieka pastāvīgais identifikators. |
| ROR | ROR identifikators | pētniecības organizācijas identifikators. |
| repository | repozitorijs | platforma datu kopu glabāšanai un publicēšanai. |

## Datu pārvaldība

| EN | LV | Skaidrojums |
|----|----|-------------|
| data management | datu pārvaldība | datu plānošana, vākšana, apstrāde, saglabāšana. |
| data management plan (DMP) | datu pārvaldības plāns | dokuments, kas apraksta datu apstrādi visā dzīves ciklā. |
| data curator | datu kurators | speciālists, kas pārvalda un kūrē pētniecības datus (oficiālais termins; ne "datu stjuarts"). |
| open science | atvērtā zinātne | pieeja, kas padara pētniecības procesu un rezultātus caurspīdīgus un brīvi pieejamus. |
| provenance | izcelsme | datu izcelsme — kā un kad tie radīti, apstrādāti un mainīti. |
| reproducibility | reproducējamība | iespēja atkārtot pētījumu, izmantojot tos pašus datus un metodes. |

## Standarti un formāti

| EN | LV | Skaidrojums |
|----|----|-------------|
| serialization | serializācija | viena metadatu ieraksta pieraksts konkrētā formātā (XML, JSON-LD u.c.). |
| validation | validācija | metadatu atbilstības pārbaude shēmai (XSD, JSON Schema). |
| machine-readable | mašīnlasāms | formāts, ko mašīna spēj nolasīt. |
| machine-actionable | mašīnnolasāms | formāts, uz kura pamata mašīna spēj rīkoties bez cilvēka iejaukšanās. |

## Saistītie dati un vārdnīcas

| EN | LV | Skaidrojums |
|----|----|-------------|
| Linked Data | saistītie dati | dati, kas savienoti, izmantojot URI un RDF. |
| Semantic Web | semantiskais tīmeklis | tīmeklis, kurā datiem ir mašīnsaprotama nozīme. |
| triple | trijnieks | RDF pamatvienība: subjekts–predikāts–objekts (ne "triplets"). |
| controlled vocabulary | kontrolētā vārdnīca | apstiprināts terminu kopums ar noteiktu nozīmi (ne "kontrolētais vārdu krājums"). |
| thesaurus | tēzaurs | vārdnīca ar hierarhiskām un asociatīvām attiecībām starp jēdzieniem. |
| taxonomy | taksonomija | hierarhiska jēdzienu klasifikācija. |
| ontology | ontoloģija | formāls jēdzienu un to attiecību modelis. |
| concept (SKOS) | jēdziens | `skos:Concept` — vārdnīcas pamatvienība. |
| crosswalk | savietojuma karte | atbilstība starp diviem metadatu standartiem vai vārdnīcām. |
| URI dereferencing | URI dereferēšana | URI atrisināšana, lai iegūtu dokumentu vai vērtību. |

## Licences un izcelsme

| EN | LV | Skaidrojums |
|----|----|-------------|
| license | licence | datu vai metadatu lietošanas noteikumi. |
| Creative Commons | Creative Commons | licenču saime (CC0, CC BY, CC BY-SA u.c.); netulko. |
| attribution | atribūcija | prasība norādīt autoru, izmantojot datus. |
| embargo | embargo | laikposms, kurā dati vēl nav publiski pieejami. |
| token (SPDX) | marķieris (token) | kontrolētas vārdnīcas atomārā vienība (piemēram, licences kods `CC-BY-4.0`). |

## Novērtēšana

| EN | LV | Skaidrojums |
|----|----|-------------|
| FAIR assessment | FAIR novērtējums | datu atbilstības FAIR principiem novērtēšana. |
| F-UJI | F-UJI | pārlūkā darbināms FAIR novērtējuma rīks. |
| FAIR-Aware | FAIR-Aware | DANS pašnovērtējuma rīks (rīka nosaukumu netulko). |
| metric | metrika | konkrēts, izmērāms FAIR novērtējuma rādītājs. |

---

_Pilnā kursa terminoloģijas vārdnīca (ar avotu prioritātēm un piezīmēm) ir lektora iekšējais dokuments. Šī ir publiskā, dalībniekiem orientētā versija. Materiāli publicēti ar CC BY 4.0 licenci._
