# CLAUDE.md - mneme

## At a glance

Design-phase repo for the fleet's deductive storage engine. No code
yet - the engine lives in aletheia (krites) and promotes here after the
overhaul phases complete. Do not port code here ahead of that gate.

## Standards

Fleet standards come from forkwright/kanon `crates/basanos/standards/`.
Most relevant once promotion lands: RUST.md, DATALOG.md, STORAGE.md,
STORAGE-TIERS.md.

## Planning

Roadmap / state / phase plans live in kanon `projects/mneme/` - not in
this repo. The promotion is gated on aletheia Phase 05g (krites
overhaul) + 05b (unified storage); the phase ladder after that runs:
extraction -> unified Provenance -> Extractor trait -> MCP surface ->
async/partitions/isolation -> rule hot-reload -> differential dataflow ->
aletheia migration -> gnomon/dioptron/akroasis activation.

## Boundaries

- Always: keep this repo's docs consistent with kanon planning; link,
  do not restate volatile detail.
- Never: promote engine code before the aletheia prerequisite phases
  and fleet standards are met (earn-then-promote is a locked decision);
  embed rules as macros (Prolog-syntax text is locked).
