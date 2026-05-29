# 🔬Activatie van immuun- en ontstekingsroutes in reumatoïde artritis onthuld door RNA-seq analyse
<sub>Nina Fonsine Schakel - [nina.schakel\@student.nhlstenden.com](mailto:nina.schakel@student.nhlstenden.com) - NHL Stenden en Van Hall Larenstein - Module J2P4_BT Moderne DNA-technologieën

<sub>Datum: 29-05-2026

## Inleiding:
Reumatoïde artritis (RA) is een vorm van reuma die ervoor zorgt dat het immuunsysteem lichaamseigen weefsel aanvalt, voornamelijk de synoviale gewrichten. Dit leidt vaak tot pijn, ontstekingen, en zelfs schade aan bot en kraakbeen. In 2024 kregen 11.700 mensen de diagnose RA in Nederland [[1]](Referenties). Helaas is er momenteel geen genezing en wordt de ontwikkeling van effectieve therapieën bemoeilijkt door de variatie aan ziekteverloop tussen patiënten [[2]](Referenties)[[3]](Referenties).
 

Om gerichte therapieën te ontwikkelen, is het essentieel om te begrijpen wat er op moleculair niveau gebeurt in het geval van RA. Chronische ontsteking en gewrichtsschade wordt gestimuleerd door een interactie van verschillende immuuncellen en (pro-inflammatoire) cytokinen, waaronder TNF-α, IL-6 en IL-17 [[4]](Referenties)[[5]](Referenties)[[6]](Referenties). RNA sequencing (RNA-seq) is een krachtige methode die verandering in genexpressie kan detecteren op grote schaal en zo inzicht kan bieden in de onderliggende mechanismen van deze ziekte.


In dit onderzoek wordt door middel van RNA-seq geïdentificeerd welke genen differentieel tot expressie zijn gebracht in een synoviumbiopt van acht patiënten met en zonder RA. Met behulp van GO- en KEGG-analyse worden de bijbehorende biologische processen en pathways gekarakteriseerd.

## Methode: 
Ruwe sequencingdata ([FASTQ-bestanden](Data/Ruw) afkomstig van vier gezonde patiënten en vier patiënten met RA werden allereerst gemapt op het [humane referentiegenoom](Referentiegenoom) met behulp van het Rsubread (v2.25.0)[7](Referenties) package. De verkregen BAM-bestanden werden vervolgens gesorteerd en geïndexeerd met Rsamtools.

Hierna werd met featureCounts uit hetzelfde Rsubread package een [count matrix](count_matrix_RA.txt) opgesteld, waarin het aantal reads per gen per sample werd bepaald op basis van een [GTF-annotatiebestand](Referentiegenoom). Deze count matrix werd vervolgens gebruikt als input voor differentiële genexpressieanalyse met DESeq2 (v1.50.2)[8](Referenties), waarbij significante genen werden geselecteerd op basis van een adjusted p-waarde (padj < 0,05) en absolute log2 fold change waarden groter dan 1, wat overeenkomt met een verdubbeling of halvering van de genexpressie.

Voor functionele interpretatie werden Gene Ontology (GO) en KEGG pathway analyses uitgevoerd. GO-enrichment werd uitgevoerd met het goseq (v1.62.0)[9](Referenties) package, waarbij gecorrigeerd werd voor genlengtebias op basis van het humane referentiegenoom (hg19), en genannotatie werd verkregen via het org.Hs.eg.db (v3.22.0)[10](Referenties) package. KEGG-enrichment werd bepaald met het clusterProfiler (v4.18.4)[11](Referenties) package, waarbij pathway-informatie werd opgehaald via KEGGREST (v1.50.0)[12](Referenties).

Om de resultaten te visualiseren werden volcano plots en enrichment plots gemaakt met ggplot2 (v4.0.3)[13](Referenties), dplyr (v1.2.1)[14](Referenties) en EnhancedVolcano (v1.28.2)[15](Referenties) packages. Als laatste werd de pathview (v1.50.0)[16](Referenties) package gebruikt om differentiële genexpressie te tonen op de KEGG rheumatoid arthritis pathway.

Een flowschema van de volledige analysepipeline is weergegeven in [figuur 1](Flowschema.png).

<p align="center">
  <img src="Flowschema.png" alt="Flowschema.png" width="600"/>
</p>

<sub>Figuur 1. Flowschema van het onderzoek waarbij de RNA-seq data van patiëntmonsters wordt verwerkt tot een volcano plot, GO plots en de visualisatie van een specifieke pathway

## Resultaten: 
+- 200 woorden, inclusief correcte verwijzingen. Packages met versienummer en bronnen.

## Conclusie:
+- 200 woorden, inclusief aanbevelingen en onderzoek in context plaatsen.

## Referenties
Zie [Referenties](Referenties)

## AI Gebruik

## Competentie beheren
Zie [Data_Stewardship](Data_Stewardship) en [Beheren](Beheren)
