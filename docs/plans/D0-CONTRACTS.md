# D0 — proposed foundational contract ownership

Status: G0.2 documentation proposal. No ADR accepted or implementation authorized. D0 follows qualified G0 integration; accept individual design records and resolve interface questions with explicit validation designs before authorizing each dependent package. No downstream implementation success required for design acceptance, but implementation gates require actual evidence.

| Contract | Accountable owner | Proposed ADR | Consumers | Questions to resolve / planned validation |
|---|---|---|---|---|
| Installation identity, exclusive process ownership and fencing | EP-001 | ADR-002 | EP-002/003A/004/005/007 | Lock boundary, process death, stale-owner exclusion and epoch; separate-process FT-001/025/036 |
| Passive construction and activation lifecycle | EP-001 | ADR-003 | EP-002/005 | Startup side effects, CLI/web roles and inhibition; FT-001/016 |
| Quiescence and disposal | EP-002 | ADR-003/005 | EP-001/003F | In-flight operations, queued work and ownership release; FT-016/031 |
| Classification and final command admission | EP-003A | ADR-004 | EP-001/003C/D/E/007 | Command origins, default denial, authoritative admission ordering, no raw bypass; FT-007/019/027/035 |
| Principal/resource authorization and revocation | EP-007 | ADR-004 extended candidate | EP-003A/C, HTTP/socket/scheduler/adapter boundaries | Verified identity, service principal scopes, topology and policy revision, revocation ordering and broker identities; FT-017/018/027/028/036 |
| Typed outcomes and transport certainty | EP-003B | ADR-004/005 | EP-003A/C/D/F/002 | Acknowledgement correlation, expiry/fencing support, delayed delivery and evidence freshness; FT-008–011/029/032/042 |
| Irrigation authorization policy | EP-003C | ADR-004/006 | EP-003A/D/E/004/007 | Approval validity, cancellation, delayed timing and policy changes; FT-002–004/030 |
| Physical resource identity, reservation and quarantine policy | EP-003D | ADR-005/006 | EP-001/003A/C/F/004 | Shared topology, owner tokens, quarantine independent of TTL; FT-012–014/026/037/040 |
| Observation and calibration eligibility | EP-003E | ADR-004/009 | EP-003A/C/D | Freshness, calibration provenance and device-specific bounds; FT-005/006 |
| Independent protection, recovery and rearm | EP-003F | ADR-005 | EP-001/002/003A/B/D/007 | Device-specific protection, emergency scopes, stale-work invalidation and rearm; FT-015/033/038/039 |
| Atomic admission, claim, durable operation and quarantine persistence | EP-004 | ADR-006 | EP-001/003A/C/D/F | Commit/rollback, pre-dispatch records, crash/restore uncertainty and owner epochs; FT-020/025/034/035/041 |
| Deployment profile and ownership enforcement | EP-005 | ADR-007/002 | EP-001/002/007 | Clean builds, supported platforms, actual lock sharing, no implicit activation; profile evidence |

One accountable decision owner per contract. EP-007 determines identity/resource permission; EP-003A enforces all required decisions at final admission; EP-004 owns atomic persistence and recovery evidence, not authorization policy; EP-003D owns resource quarantine policy; EP-003B owns evidence interpretation. D0 defines contracts, not implementations. R1a/R1b default inhibition until prerequisites exist; minimum R2a recovery before consequential dispatch. R2b bounded ownership only, full F-001 closure Q. No unknown interface may be silently accepted. Record each ADR's context, alternatives, unresolved questions, owner design acceptance, consumers, validation and subsequent implementation authorization; if a required question is unresolved, D0 remains HOLD for that contract. See [ADR register](../architecture/adr/README.md), [remediation](REMEDIATION.md).
