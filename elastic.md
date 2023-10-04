Priscilla Parodi, Elastic Principal Developer Advocate
September 27th, 2023

Search is not just a box
  Uber: GPS coordinates
  Tinder: matching people
  Logs, metrics, traceability

Typical search architecture
 - ingest (200+ connectors) agents, web crawler, python connector API, database connectors
 Transform (enrich) Logstash, ETL pre-processors
 Store (Index/store): Elasticsearch, collection of documents with fields
 Search (visualize/consume): Kibana, custom search apps or websites, RESTful

Text search revisited
"the best way to secure Elasticsearch" -> tokenize -> best|way|secure|Elasticsearch -> BM25 ranking function, measures relevants based on frequencey and rarity of terms

Text search is useful for many cases
Where it works:
 - well understood
 - interpretable

Where it may fall short:
 - vocabulary mismatch
 - context (semantic mismatch)

Users expect more from search: vector search enables semantic search

What about context-aware text embeddings?
With elastic: import and deploy proprietary or third party NLP models

Dense vector retrieval performs well
Where it works
 - can beat other approaches for semantic search

Where it may fall short
 - domain adaptation (keywords and terms for a specific industry): you can fine tune a model though
 - not easily interpretable (no exact match)

Learned sparse retrieval: an alternative approach for semantic search

Provides trade-offs over dense retrival and tradiational sparse retrieval methods (BM25)

Does Term Expansion - identifies contextual importants between terms, uses knowledge to improve sparse vector embeddings

i.e. comfortable -> term expansion -> landscape, relax, calm, sleep, sofa, etc.

Elastic has a built-in option for this approach

Learned sparese retrieval is an improvement over text search
Where it works:
 - interpretable/well understood (tokens)
 - vocabulary/semantic matching

Where it may fall short
 - larger index (terms/tokens)
 - dense vector retriveal can outperform learned sparse retrieval for semantic search

Is a combined approach a better idea? Hybrid retrieval

Lexical score (BM25) + Vector score (dense, sparse) -> Linear combination with manual boosting OR reciprocal rank fusion (RRF) blend multiple ranking methods

term expansion is called Elser and is pre-trained
