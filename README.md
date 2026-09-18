# Life-Science Remote MCP Server List (Audit Update)

**Verified: 2026-09-18**
This is a differential update of the previous version (https://hackmd.io/zTFMecEjQzSx2WY-IQrIXw ). Not every endpoint in the main table was re-probed each cycle (most are not directly reachable from this environment and were checked via web sources). Completeness is not claimed; open items are listed at the end.

Subject areas have been normalized to English controlled/established vocabulary (previous mixed Japanese/English values replaced after confirming meaning).

---

## A. Public hosted remote MCP

| MCP server | Subject area | Public remote endpoint | Provider | Remote type | Auth / notes |
|---|---|---|---|---|---|
| **Ask Helena Public Knowledge** | genomics; biomedical knowledge; information retrieval | `https://api.helena.bio/ask/v1/mcp` | Helena Bioinformatics | official-public | No auth, read-only. Search with source citations. Sources: [Helena llms resource](https://www.helena.bio/llms-full.txt), [MCPBeat: Ask Helena](https://mcpbeat.com/mcp-servers/helena-bioinformatics/ask-helena/) |
| **EMBL-EBI Ontology Lookup Service (OLS) MCP** | biomedical ontologies; ontology search; semantic search | `https://www.ebi.ac.uk/ols4/api/mcp` | EMBL-EBI | official-public | Streamable HTTP, no auth. GO/EFO/HPO/MONDO/ChEBI etc. Sources: [EMBL-EBI OLS MCP](https://www.ebi.ac.uk/ols4/mcp), [OLS4 GitHub](https://github.com/EBISPOT/ols4) |
| **Expasy SPARQL Assistant MCP** | RDF data integration; SPARQL query generation; proteins | `https://chat.expasy.org/mcp` | SIB Swiss Institute of Bioinformatics | official-public | Official repo states the public server URL explicitly. Assists SPARQL query generation/execution over SIB endpoints (UniProt/Bgee/OMA/SwissLipids/Cellosaurus etc.). No auth. Public endpoint confirmed in official repo on 2026-09-18. Source: [sib-swiss/sparql-llm](https://github.com/sib-swiss/sparql-llm) |
| **Folklore Variant Evidence MCP** | genetic variation; variant interpretation; human genome | `https://api.helena.bio/folklore/v1/mcp` | Helena Bioinformatics | official-public | Read-only, no auth. GRCh38 germline variant evidence. Source: [Folklore integrations](https://folklore.helena.bio/integrations) |
| **GWAS Catalog MCP** | genome-wide association study; genetic variation; phenotypes | `https://ebi.ac.uk/gwas/mcp` | GWAS Catalog / EMBL-EBI | official-public | Official hosted version, no install required. Source: [GWAS Catalog MCP](https://github.com/gwas-catalog/mcp) |
| **Open Targets Platform MCP** | target–disease associations; drug discovery | `https://mcp.platform.opentargets.org/mcp` | Open Targets | official-public | Official, no auth. Source: [Open Targets Platform MCP](https://github.com/opentargets/platform-mcp) |
| **PubMed MCP — Anthropic life-sciences** | literature search | `https://pubmed.mcp.claude.com/mcp` | Anthropic | official-public | No auth. Source: [Anthropic life-sciences](https://github.com/anthropics/life-sciences) |
| **STRING MCP** | protein interactions; functional enrichment; sequence similarity | `https://mcp.string-db.org/` | STRING (meringlab) | official-public | **Updated: previously "in development" → now documented as a production service.** Streamable HTTP. STRING Chat (`https://string-db.org/cgi/chat`) is a working example that uses this MCP. Third-party health check reported "Healthy" on 2026-09-13. Repo: meringlab/string-mcp. Sources: [STRING Help: MCP](https://string-db.org/help/mcp/), [mcp.string-db.org](https://mcp.string-db.org/), [Glama health check](https://glama.ai/mcp/connectors/org.string-db/string-mcp) |
| **TogoMCP** | life-science data integration; RDF/SPARQL; identifier mapping | `https://togomcp.rdfportal.org/mcp` | DBCLS | official-public | Confirmed live via `initialize` probe on 2026-09-18 (serverInfo `TogoMCP: RDF Portal MCP Server` v2.19.0, no auth). Integrates 20+ DBs/APIs. Sources: [TogoMCP](https://togomcp.rdfportal.org/), 2026-09-18 endpoint probe |
| **Synapse MCP** | research data management; data sharing | `https://mcp.synapse.org/mcp` | Sage Bionetworks | official-auth | OAuth2. Source: [Synapse MCP](https://github.com/Sage-Bionetworks/synapse-mcp) |
| **BioContextAI Knowledgebase MCP** | data integration; proteins; pathways; protein interactions | `https://mcp.biocontext.ai/mcp/` | BioContextAI | community-public | Public remote service, fair-use limits. Integrates UniProt/Reactome/STRING/InterPro/PRIDE/Open Targets etc. Source: [BioContextAI Knowledgebase](https://docs.kb.biocontext.ai/latest/) |
| **Cellosaurus MCP — QuentinCody** | cell lines; cross-references | `https://cellosaurus-mcp-server.quentincody.workers.dev/mcp` | QuentinCody / community | community-public-likely | Community implementation of the SIB Cellosaurus API. Cloudflare Workers deployment domain is stated, but a `deployed and ready` claim is weaker, so treated at lower confidence. Not the official Cellosaurus MCP. Source: [Cellosaurus MCP GitHub](https://github.com/QuentinCody/cellosaurus-mcp-server) |
| **ClinPGx MCP — QuentinCody** | pharmacogenomics; drug–gene interactions; clinical guidelines | `https://clinpgx-mcp-server.quentincody.workers.dev/mcp` | QuentinCody | community-public | README states a deployed remote endpoint. CPIC/DPWG guidelines. Not the official ClinPGx MCP. Source: [ClinPGx MCP GitHub](https://github.com/QuentinCody/clinpgx-mcp-server) |
| **Ensembl MCP — cyanheads** | genomics; sequence analysis; variant effect prediction; orthologs | `https://ensembl.caseyjhand.com/mcp` | cyanheads | community-public | Public hosted instance. Source: [cyanheads/ensembl-mcp-server](https://github.com/cyanheads/ensembl-mcp-server) |
| **Europe PMC MCP — QuentinCody** | literature search; full-text mining; citations | `https://europepmc-mcp-server.quentincody.workers.dev/mcp` | QuentinCody | community-public | README states a public remote endpoint. Not the official Europe PMC MCP. Source: [Europe PMC MCP GitHub](https://github.com/QuentinCody/europepmc-mcp-server) |
| **FDA Purple Book MCP — QuentinCody** | biologics; biosimilars; drug regulation | `https://fda-purple-book-mcp-server.quentincody.workers.dev/mcp` | QuentinCody | community-public | README states a public remote endpoint. Not an official FDA MCP. Source: [FDA Purple Book MCP GitHub](https://github.com/QuentinCody/fda-purple-book-mcp-server) |
| **IEDB MCP — QuentinCody** | immunology; immune epitopes; MHC binding | `https://iedb-mcp-server.quentincody.workers.dev/mcp` | QuentinCody | community-public | README states a deployed remote endpoint. Not the official IEDB MCP. Source: [IEDB MCP GitHub](https://github.com/QuentinCody/iedb-mcp-server) |
| **PubMed MCP — cyanheads** | literature search; information retrieval | `https://pubmed.caseyjhand.com/mcp` | cyanheads | community-public | Public hosted instance. PubMed / Europe PMC / PMC / Unpaywall. Source: [cyanheads/pubmed-mcp-server](https://github.com/cyanheads/pubmed-mcp-server) |
| **UniProt MCP — cyanheads** | proteins; sequence analysis; taxonomy; identifier mapping | `https://uniprot.caseyjhand.com/mcp` | cyanheads | community-public | Public hosted instance. Uses the UniProt REST API. Source: [cyanheads/uniprot-mcp-server](https://github.com/cyanheads/uniprot-mcp-server) |
| **BioStudies MCP — Pipeworx** | research data; information retrieval | `https://gateway.pipeworx.io/biostudies/mcp` | Pipeworx | gateway | Hosted MCP on the Pipeworx gateway. EMBL-EBI BioStudies search and study metadata. Not the official EMBL-EBI MCP. Source: [Pipeworx BioStudies documentation](https://pipeworx.io/docs/reference/biostudies/search_studies/) |
| **GWAS Catalog MCP — Pipeworx** | genome-wide association study; genetic variation; phenotypes | `https://gateway.pipeworx.io/gwas-catalog/mcp` | Pipeworx | gateway | Separate implementation from the EBI official version. Source: [Pipeworx GWAS Catalog MCP](https://github.com/pipeworx-io/mcp-gwas-catalog) |
| **Genomic Intelligence MCP** | regulatory genomics; gene expression; sequence analysis | `https://mcp.genomicintelligence.ai/mcp` | Genomic Intelligence | commercial-public | Public demo available; API key extends quota. Predicts promoter/splice/enhancer/chromatin/expression. Source: [Genomic Intelligence MCP](https://docs.genomicintelligence.ai/mcp) |
| **AdisInsight MCP** | drug pipeline intelligence; clinical trials; pharmacovigilance | `https://adisinsight-mcp.springer.com/mcp` | Springer Nature | commercial-auth | OAuth 2.0, for AdisInsight subscribers. Sources: [AdisInsight MCP](https://adisinsight-mcp.springer.com/), [AdisInsight](https://adisinsight.springer.com/insight-hub) |
| **BioRender MCP** | scientific illustration; figure generation | `https://mcp.services.biorender.com/mcp` | BioRender | commercial-auth | Official MCP connector. Authenticate with a BioRender account. Template/icon search, figure generation. Sources: [BioRender MCP connector](https://help.biorender.com/hc/en-gb/articles/30870978672157-How-to-use-the-BioRender-MCP-connector), [Claude Connector Directory](https://claude.com/connectors/biorender) |
| **Consensus MCP** | literature search; systematic review; evidence synthesis | `https://mcp.consensus.app/mcp` | Consensus | commercial-auth | OAuth or Bearer token. Sources: [Consensus MCP documentation](https://docs.consensus.app/docs/mcp), [Consensus MCP](https://consensus.app/home/mcp/) |
| **Cortellis Regulatory Intelligence MCP** | regulatory intelligence; drug regulation; medical devices | `https://api.clarivate.com/lifesciences/mcp-regulatory/mcp` | Clarivate | commercial-auth | Streamable HTTP, OAuth 2.0. Requires a Cortellis Regulatory Intelligence subscription. Sources: [Clarivate MCP documentation](https://api.clarivate.com/lifesciences/mcp-regulatory/documentation/copilot-studio), [Clarivate announcement](https://clarivate.com/news/clarivate-expands-access-to-trusted-regulatory-intelligence-within-claude/) |
| **Medidata MCP** | clinical trials; clinical research; site selection | `https://mcp.imedidata.com/mcp` | Medidata Solutions | commercial-auth | Official MCP. Platform Help and Intelligent/Predictive Site Ranking etc. Requires Medidata credentials. Sources: [Medidata + Anthropic MCP](https://www.medidata.com/en/clinical-trial-data-with-ai/), [Claude Connector Directory](https://claude.com/connectors/medidata) |
| **Owkin MCP** | digital pathology; histopathology; survival analysis | `https://mcp.k.owkin.com/mcp` | Owkin | commercial-auth | Requires Owkin credentials. Sources: [Owkin announcement](https://www.owkin.com/newsfeed/owkins-specialized-biological-ai-agent-pathology-explorer-launches-with-anthropics-claude-for-healthcare-and-life-sciences), [Claude Connector Directory](https://claude.com/connectors/owkin) |
| **PatSnap Biology Modality MCP** | biological sequences; antibodies; proteins; patent search | `https://connect.patsnap.com/06e741/logic-mcp?apikey=<API_KEY>` | PatSnap | commercial-auth | Official remote MCP. API key required. Source: [PatSnap Biology Modality MCP](https://www.patsnap.com/resources/blog/articles/how-to-set-up-patsnap-biology-modality-mcp/) |
| **PatSnap Chemical Molecular MCP** | cheminformatics; small molecules; ADMET | `https://connect.patsnap.com/713886/logic-mcp?apikey=<API_KEY>` | PatSnap | commercial-auth | Official remote MCP. API key required. Source: [PatSnap Chemical Molecular MCP](https://www.patsnap.com/resources/blog/articles/open-how-to-predict-admet-properties-with-ai/) |
| **PatSnap Clinical Trials MCP** | clinical trials; drug development; competitive intelligence | `https://connect.patsnap.com/051cd3/logic-mcp?apikey=<API_KEY>` | PatSnap | commercial-auth | Official remote MCP. API key required. Source: [PatSnap Clinical Trials MCP](https://www.patsnap.com/resources/blog/articles/open-how-to-search-and-analyze-clinical-trials-with-ai/) |
| **PatSnap Company & Deal Intelligence MCP** | business intelligence; licensing; mergers and acquisitions | `https://connect.patsnap.com/1f8934/logic-mcp?apikey=<API_KEY>` | PatSnap | commercial-auth | Official remote MCP. API key required. Source: [PatSnap Company & Deal Intelligence MCP](https://www.patsnap.com/resources/blog/articles/open-how-to-research-biotech-licensing-deals-with-ai/) |
| **PatSnap Drug & Asset MCP** | drug assets; drug development; targets | `https://connect.patsnap.com/30cd71/logic-mcp?apikey=<API_KEY>` | PatSnap | commercial-auth | Official remote MCP. API key required. Source: [PatSnap Drug & Asset MCP](https://www.patsnap.com/resources/blog/articles/open-how-to-track-drug-assets-through-development-pipelines-with-ai/) |
| **PatSnap Pharma Intelligence MCP** | drug pipeline intelligence; drug development; competitive intelligence | `https://connect.patsnap.com/096456/logic-mcp?apikey=<API_KEY>` | PatSnap | commercial-auth | Official remote MCP. API key required. Source: [PatSnap Pharma Intelligence MCP](https://www.patsnap.com/resources/blog/articles/open-how-to-research-pharma-pipelines-with-ai/) |
| **PatSnap Regulatory & Guidelines MCP** | drug regulation; clinical guidelines | `https://connect.patsnap.com/6415c2/logic-mcp?apikey=<API_KEY>` | PatSnap | commercial-auth | Official remote MCP. API key required. Source: [PatSnap Regulatory & Guidelines MCP](https://www.patsnap.com/resources/blog/articles/open-how-to-search-fda-labels-and-clinical-guidelines-in-claude/) |
| **PatSnap Scientific & Translational Evidence MCP** | translational research; target validation; clinical evidence | `https://connect.patsnap.com/9c333c/logic-mcp?apikey=<API_KEY>` | PatSnap | commercial-auth | Official remote MCP. API key required. Source: [PatSnap Scientific & Translational Evidence MCP](https://www.patsnap.com/resources/blog/articles/open-how-to-find-translational-evidence-for-a-drug-target-with-ai/) |
| **PatSnap Target & Disease MCP** | target biology; disease; epidemiology | `https://connect.patsnap.com/2a2645/logic-mcp?apikey=<API_KEY>` | PatSnap | commercial-auth | Official remote MCP. API key required. Source: [PatSnap Target & Disease MCP](https://www.patsnap.com/resources/blog/articles/open-how-to-map-a-drug-target-to-related-diseases-with-ai/) |
| **Seqera MCP** | bioinformatics workflows; workflow execution; sequence data retrieval | `https://mcp.seqera.io/mcp` | Seqera | commercial-auth | OAuth 2.1 / PAT. Nextflow/nf-core, SRA/ENA/GEO. Source: [Seqera MCP documentation](https://docs.seqera.io/platform-cloud/seqera-mcp/overview) |
| **Wiley Scholar Gateway MCP** | literature search; information retrieval; evidence synthesis | `https://connector.scholargateway.ai/mcp` | Wiley / Scholar Gateway | commercial-auth | OAuth 2.1, CONNECT SSO. Institutional subscription or trial. Sources: [Wiley Scholar Gateway documentation](https://docs.scholargateway.ai/), [Wiley AI Solutions](https://www.wiley.com/en-us/solutions-partnerships/ai-solutions/) |
| **Benchling MCP** | electronic laboratory notebook; research data management | `https://<tenant>.mcp.benchling.com/mcp` | Benchling | tenant-specific | Tenant-specific, OAuth 2.1. Source: [Benchling MCP configuration](https://help.benchling.com/hc/en-us/articles/40342713479437-Configure-Benchling-s-MCP-Server-for-other-MCP-clients) |
| **SHARP-on-MCP .NET** | health data interoperability; FHIR | `https://dotnet.fhir-mcp.promptopinion.ai/mcp` | SHARP-on-MCP | test | Public test environment. Source: [SHARP-on-MCP](https://sharponmcp.com/getting-started) |
| **SHARP-on-MCP TypeScript** | health data interoperability; FHIR | `https://ts.fhir-mcp.promptopinion.ai/mcp` | SHARP-on-MCP | test | Public test environment. Source: [SHARP-on-MCP](https://sharponmcp.com/getting-started) |

---

## B. Held / needs re-confirmation

| Candidate | Subject area | Candidate endpoint | Provider | Reason held | Next to confirm | Source |
|---|---|---|---|---|---|---|
| **CIViC MCP** | cancer genomics; somatic variants; clinical interpretation | `https://civic-mcp-server.quentincody.workers.dev/mcp` | Griffith Lab / QuentinCody | Paper now peer-reviewed and published (updated). The official chat `https://civicdb.org/mcp-chat` is a web UI, not an MCP transport endpoint. The Workers URL is presented in README/Glama as "replace with your own subdomain" = a deployment template, so a permanent public endpoint cannot be confirmed. | Whether civicdb.org exposes a hosted transport endpoint reachable by a standard MCP client, or whether the Workers URL is an author-operated permanent service | [griffithlab/civic-mcp-server](https://github.com/griffithlab/civic-mcp-server), [Schimmelpfennig et al. 2026, Bioinform Adv](https://doi.org/10.1093/bioadv/vbag209) |
| **Identifiers.org MCP** | identifier resolution; compact identifiers; data integration | `https://resolver.api.identifiers.org/sse` | EMBL-EBI (Identifiers.org) | Exists as a Claude connector (has connection history, SSE transport), but no primary-source MCP documentation could be confirmed, and the endpoint could not be probed from this environment (domain reachability limits). | Official Identifiers.org / EMBL-EBI MCP page; endpoint probe | Claude connector directory (connection history) |
| **PubDictionaries MCP** | text annotation; dictionaries; named entity recognition | `https://pubdictionaries.org/mcp` | DBCLS (PubDictionaries) | Exists as a Claude connector (has connection history), but no primary-source MCP documentation could be confirmed, and the endpoint could not be probed from this environment. | Official PubDictionaries MCP page; endpoint probe; whether auth is required | Claude connector directory (connection history) |
| **GrEBI (Graphs@EBI) MCP** | biomedical knowledge graph; data integration | `https://www.dev.ebi.ac.uk/kg` | EMBL-EBI (EBISPOT) | The paper states a publicly accessible MCP server, but the URL is given as an API/MCP base URL and it is unclear whether it is the transport endpoint itself. **Not re-verified this round (carried forward as-is).** | Exact MCP transport path; permanence of the `dev` domain | [GrEBI GitHub](https://github.com/EBISPOT/GrEBI), [McLaughlin et al. 2026](https://doi.org/10.64898/2026.08.03.742514) |

---

## C. Remote-capable / self-hosted MCP implementations

**No changes this round (carried forward as-is; individual items not re-verified).**

| MCP | Subject area | Remote use / status |
|---|---|---|
| BioMCP | cancer genomics; genetic variation; clinical trials; literature search | Streamable HTTP supported; no official public hosted endpoint confirmed |
| Galaxy MCP | bioinformatics workflows; tool execution | `/api/mcp` supported; enablement on public Galaxy instances is instance-dependent |
| GEOmcp | gene expression; sequence data retrieval | HTTP server supported; no public standing endpoint confirmed |
| PLSDB MCP | plasmids; sequence databases | Primarily stdio/self-hosted |
| UCSC Cell Browser MCP | single-cell transcriptomics | Primarily stdio/self-hosted |
| scmcp | single-cell transcriptomics; data analysis | Streamable HTTP supported; self-hosted |
| CellRank MCP | single-cell transcriptomics; trajectory inference | Streamable HTTP supported; self-hosted |
| BioinfoMCP | bioinformatics; command-line tool integration | local/Docker deployment |
| ProteinMCP | protein engineering | MCP framework/tool ecosystem |
| Coala | workflow conversion (CWL → MCP) | generic self-hosted MCP server |
| Holy Bio MCP | bioinformatics (collection) | Primarily local/stdio |
| 10x Genomics MCP | single-cell transcriptomics; spatial transcriptomics | MCPB/local distribution |
| ToolUniverse | scientific tools (collection) | MCPB/local distribution |

---

## Changes this round (2026-09-18)

- **Added (main table):**
  - Expasy SPARQL Assistant MCP (SIB, official-public) — public endpoint confirmed in official repo
- **Updated:**
  - STRING MCP — previously "in development" → now documented as a production service; source changed to `string-db.org/help/mcp/`; repo and health check added
  - TogoMCP — re-confirmed live on 2026-09-18 (v2.19.0)
  - Normalized the `Subject area` column across the whole main table to English controlled/established vocabulary (resolved Japanese/English mixing)
- **Added to / updated in the held table:**
  - CIViC MCP — reflected the peer-reviewed publication and official chat, but held pending an unconfirmed MCP transport endpoint
  - Identifiers.org MCP, PubDictionaries MCP
- **Removed:** none
- **Evidence-only updates:** STRING source URL
- **Confirmed unchanged:** self-hosted table, 13 entries (individual items not re-verified; previous state retained)

---

## Considered but not added to the main table

- **Wikidata MCP** (`https://wd-mcp.wmcloud.org/mcp`) — a general-purpose knowledge base without a primarily life-science-specific function; out of scope.
- **Apify-hosted EBI scrapers** (OLS/Proteins/BioStudies etc., `mcp.apify.com`) — Actor wrappers hosted by Apify that require an Apify account/OAuth; a gateway type. Not EMBL-EBI official and are scraper implementations, so not added this round (can be listed separately in a gateway table if needed).
- **cBioPortal MCP** (`docs.cbioportal.org/ai-integrations/mcp`) — cancer genomics. Official docs state "prototypes / work in progress" and no hosted remote endpoint is confirmed, so treated as self-hosted/in-development (re-check next round).

---

## Open items / caveats

1. Many of the commercial/community endpoints in this table are not directly reachable from this environment and were confirmed only via web information (official docs/repos/third-party health checks).
2. Identifiers.org and PubDictionaries have Claude connector connection history, but their MCP endpoints are not yet confirmed against primary sources and are therefore held.
3. GrEBI and the self-hosted table were not individually re-verified this round; their previous state is retained. Endpoint probing and official-path confirmation are recommended next round.
4. No claim of covering "all MCPs worldwide." Discovery sources: official docs/repos, papers (PMC/bioRxiv), Glama/mcpservers.org/MCPBeat, Claude connector directory, GitHub.