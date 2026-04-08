# OT Field Reference

Offline OT/ICS cybersecurity reference skill for [Google AI Edge Gallery](https://github.com/google-ai-edge/gallery). Works fully on-device with Gemma 4 — no internet, no cloud, no data leaving your phone.

Built for plant-floor lookups where connectivity is unreliable.

## What it covers

- **Purdue Enterprise Reference Architecture** — Levels 0 through 5 (plus 3.5 iDMZ), with typical assets, protocols, threats, and IEC zone mapping for each
- **IEC 62443-3-3** — All 7 Foundational Requirements (FR 1–7) and the most-referenced System Requirements (SRs) with Purdue-level applicability
- **NIST SP 800-82r3** — Key OT-overlay controls across AC, AU, CM, CP, IA, IR, SC, and SI families
- **OT Asset Classifier** — Type a vendor/model/role (e.g., “Allen-Bradley ControlLogix”, “PI Historian”, “Siemens HMI”) and get back the Purdue level, IEC zone, typical threats, and field notes
- **Cross-Reference** — Pick any control (SR or NIST) and see which Purdue levels it touches

## Example queries

- “What’s at Purdue level 2?”
- “Tell me about SR 1.1”
- “What is AC-3 in OT context?”
- “Where does an Allen-Bradley ControlLogix sit?”
- “What’s the historian’s Purdue level?”
- “Which Purdue layers does SR 5.1 apply to?”
- “Show me all the Foundational Requirements”

## Installing on iOS

1. Open the Google AI Edge Gallery app
1. Make sure a Gemma 4 model is downloaded
1. Open the **Agent Skills** use case
1. Tap the **Skills** chip → **(+)** → **Load skill from URL**
1. Paste the raw GitHub URL to this repo’s `SKILL.md`:
   
   ```
   https://raw.githubusercontent.com/REPLACE_WITH_YOUR_USERNAME/ot-field-reference/main/SKILL.md
   ```
1. The app will fetch `SKILL.md` and `scripts/index.html` and register the skill
1. Ask any of the example queries above

## Files

```
ot-field-reference/
├── SKILL.md              # Skill manifest + instructions for the LLM
├── scripts/
│   └── index.html        # Reference data + lookup logic + HTML rendering
└── README.md             # This file
```

## Sources & accuracy

- **Purdue Model**: Public reference architecture, widely documented
- **IEC 62443-3-3**: Summarized from public sources. The official IEC standard text is paywalled — for any audit or compliance deliverable, verify against the licensed standard
- **NIST SP 800-82r3**: Public document, summarized for field use. Verify against the official PDF for compliance work

This skill is a quick-reference tool for working OT cyber professionals. It is not a substitute for the authoritative standards.

## License

MIT — do whatever you want with it.