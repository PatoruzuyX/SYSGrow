# Review attachment provenance manifest

G0.3 archival evidence, 28 November 2026. Repository PatoruzuyX/SYSGrow, PR #3, original baseline `2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21`. All supplied reports retain their original HOLD dispositions. Original G0 report comprises three specialist workstreams from one session, not three independently executed reviews. G0.1 and G0.2 independent session identities are reported in supplied material; not independently attested by the implementation author.

The SHA-256 values below were computed on the supplied mounted UTF-8 attachment bytes. The archive uses complete text extraction (no added header, no line-ending or trailing newline normalization); Git blob identities are compared to SHA-1 of the raw attachment bytes prefixed by the Git blob header, not to a normalized reconstruction. The attachment bytes and archive equality are distinct from fidelity to original external conversation exports, which has not been established. No external conversation export is asserted. The reviewed revisions below are historical, not approval of G0.3.

| Report | Supplied attachment | Archive | Reviewed SHA | Lines | Attachment SHA-256 |
|---|---|---|---|---|---|
| G0 initial review | Pasted text.txt | [G0-initial-review.md](G0-initial-review.md) | `3621f22a6ac015298db2778964e9058fb338cf99` | 762 | `5e767e19335905ddaee3e93604015b94afb180f24dbaf585db4b4fb9cd356065` |
| G0.1 Reviewer 1 | Pasted text(1).txt | [G0.1-reviewer-1.md](G0.1-reviewer-1.md) | `440bd0467eac17b5d2ee6f42760d84451756b4b1` | 726 | `f993e03820744c5d31c254fe1506aab41d7c2068ac4ea02df51ce753dd1b2047` |
| G0.1 Reviewer 2 | Pasted text (2).txt | [G0.1-reviewer-2.md](G0.1-reviewer-2.md) | `440bd0467eac17b5d2ee6f42760d84451756b4b1` | 665 | `c61597bfd94c31129eb4fb6b8911345d3d222dfb357294331cd6f5299760e12f` |
| G0.1 Reviewer 3 | Pasted text (3).txt | [G0.1-reviewer-3.md](G0.1-reviewer-3.md) | `440bd0467eac17b5d2ee6f42760d84451756b4b1` | 736 | `35d59c46f4e594dbd2cc4b18afdda3ae04cea1ca6f7e06e94ab325a86525902a` |
| G0.2 Reviewer 1 | Pasted text (2)(2).txt | [G0.2-reviewer-1.md](G0.2-reviewer-1.md) | `08b55b7d783059cc83e423e305e2ded4f67b29c2` | 617 | `67e458db55d2a7e1f15d2c9d4935d4a51de31f0974f943059dd6a0c157cf576a` |
| G0.2 Reviewer 2 | Pasted text(3).txt | [G0.2-reviewer-2.md](G0.2-reviewer-2.md) | `08b55b7d783059cc83e423e305e2ded4f67b29c2` | 757 | `4c3d9476302a5d20d5d553fdd91ca68a549e1bc6a6c5fa9f009bfc16ac07a9c3` |
| G0.2 Reviewer 3 | Pasted text (3)(1).txt | [G0.2-reviewer-3.md](G0.2-reviewer-3.md) | `08b55b7d783059cc83e423e305e2ded4f67b29c2` | 679 | `bd375b1203508bf3617c6f27ce656b74909409d1fbf94a3ef0ed725b6d4e29fd` |

Final archive tree/byte comparison and candidate SHA belong to the PR evidence record. Prior G0.1 archived blobs are retained unmodified. Original CP0–CP2 qualification reports are not these reviews and remain unrecovered as complete durable originals. See [evidence workstreams](../EVIDENCE-WORKSTREAMS.md).

## R1 rebaseline independent reviewer attachments

Reviewed candidate `a10107a4f78eea8c37a0b1a6ab7d616a61b4df87`, tree `6afe5fa9a1838137e80a290ccbb35eab6ea70172`, original baseline `2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21`. Retrieved all three complete texts from Library by exact file identity and contiguous line windows. Raw materialization unavailable; reconstructed text joined using original line separators, UTF-8 SHA-256 recomputed and matched all previously supplied attachment checksums exactly. This establishes attachment-content fidelity, not independent session authentication or original CP reports. All original HOLD dispositions retained, no edits to review text.

| Report | Original attachment | Archive | Bytes | Lines | SHA-256 |
|---|---|---|---:|---:|---|
| R1 Architecture/governance | Pasted text(6).txt | [reviewer 1](EVIDENCE-REBASELINE-reviewer-1.md) | 47593 | 938 | c8a6de045b5be670154b480bb65d38ab763c1f70cb9c6f12c94543bd78c41b53 |
| R2 Security/physical safety | Pasted text (2)(5).txt | [reviewer 2](EVIDENCE-REBASELINE-reviewer-2.md) | 71468 | 1149 | 881199c804d0c241a6f7d143e34630711645d3e5fe23d0423d610662122cc93a |
| R3 Evidence/integration/ML | Pasted text (3)(4).txt | [reviewer 3](EVIDENCE-REBASELINE-reviewer-3.md) | 61751 | 1358 | 809cfedd98a1b95f6ffa671f290bbee24ac1b15b6458ff315dd84c3e6ded6918 |

Final archive Git blob readback equality and candidate tree identity must be verified before branch update and recorded in PR evidence. No original report provenance claim.
