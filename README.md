# cloud-itonami-isco-4131

Open Occupation Blueprint for **ISCO-08 4131**: Typists and Word Processing Operators.

This repository designs a forkable OSS business for an independent typist/transcriptionist: a document-scanning robot performs page scanning and physical filing of source materials under a governor-gated actor, so the practice keeps its own processing records instead of renting a closed transcription SaaS.

## Robotics premise

All cloud-itonami verticals are designed on the premise that a **robot performs
the physical domain work**. Here a document-scanning robot performs page scanning and physical filing of source materials under an actor that proposes
actions and an independent **Typing Transcription Governor** that gates them. The governor never
dispatches hardware itself; `:high`/`:safety-critical` actions (such as
handling confidential or regulated source documents) require human sign-off.

A live sample of the operator console (robotics safety console, shared template) is rendered in [docs/samples/operator-console.html](docs/samples/operator-console.html) — pure-data HTML output of `kotoba.robotics.ui`.

## Core Contract

```text
document batch + formatting spec + confidentiality policy
        |
        v
Transcription Advisor -> Typing Transcription Governor -> transcribe/format, or human sign-off
        |
        v
robot actions (gated) + operating records + audit ledger
```

No automated advice can dispatch a robot action the governor refuses, suppress
an operating record, or disclose sensitive data without governor approval and
audit evidence.

## Capability layer

Resolves via [`kotoba-lang/occupation`](https://github.com/kotoba-lang/occupation)
(ISCO-08 `4131`). Required capabilities:

- :robotics
- :forms
- :audit-ledger
- :bpmn

See [`docs/business-model.md`](docs/business-model.md) and
[`docs/operator-guide.md`](docs/operator-guide.md).

## License

AGPL-3.0-or-later.
