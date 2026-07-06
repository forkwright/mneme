# mneme

*μνήμη - memory as faculty. The engine that answers "what follows."*

Deductive storage engine for the forkwright fleet: stores facts, accepts
rules, derives new facts by inference, and maintains materialized views
incrementally as base facts change. The Tier-3 storage primitive,
complementing [pinax](https://github.com/forkwright/pinax) (relational,
"what is") - the two bridge through pinax's changelog feeding mneme's
fact-ingest.

**Status:** design phase - no code here yet, deliberately. The engine
exists today inside [aletheia](https://github.com/forkwright/aletheia)
(the krites Datalog engine and mneme facade) and promotes into this repo
only after it clears aletheia's krites overhaul and unified-storage
phases plus fleet standards. Earn-then-promote: the repo exists so the
promotion is executable without re-deriving the plan.

## Locked design decisions

- **Datalog as the query language.** Prolog-syntax text, not
  macro-embedded rules - operator-editable rule files and agent-authored
  rules over the MCP surface stay possible.
- **One engine, many applications.** Consumers bring their own schema,
  ingest pipelines, and annotation shapes; they share the engine, the
  provenance type, and the MCP surface.
- **Dual-engine incremental maintenance.** Semi-naive fixpoint for
  ad-hoc queries; differential dataflow for consumer-declared
  materialized views.
- **Content-addressed facts, supersede-based retraction.** Facts are
  immutable; change is supersession with provenance, and the supersede
  chain stays queryable.
- **Unified provenance.** Every fact and annotation carries the same
  Provenance type (actor, session, validity interval, supersedes, tier,
  confidence, evidence) so cross-consumer reasoning works.
- **Vector + FTS via heurema.** Mneme owns no HNSW or BM25; it consumes
  them as index kinds.

## Planned consumers

aletheia episteme (first, via migration off its internal engine), gnomon
ACU exploration, dioptron facts tier, akroasis convergence detection.

## License

PolyForm Shield 1.0.0 (code) - see [LICENSE](LICENSE). Documentation
under CC BY-NC-ND 4.0 - see [LICENSE-DOCS](LICENSE-DOCS).
