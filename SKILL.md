---
name: ot-field-reference
description: Offline reference for OT/ICS cybersecurity. Looks up Purdue Model levels, IEC 62443 foundational requirements, NIST SP 800-82r3 control overlays, and classifies OT assets. Use when the user asks about Purdue levels, IEC 62443, NIST 800-82, OT controls, or asset classification (PLC, RTU, HMI, historian, engineering workstation, etc.).
---

# OT Field Reference

Offline reference for OT/ICS cybersecurity work covering Purdue Model, IEC 62443-3-3, and NIST SP 800-82r3.

## When to invoke

Call this skill whenever the user asks about a Purdue level, IEC 62443 zones or requirements, NIST 800-82 controls, OT asset classification, or wants to cross-reference a control to Purdue layers.

## Parameters

Pass a JSON object with:

- query_type: one of purdue_level, iec_lookup, nist_lookup, asset_classify, cross_reference, list_all
- value: a level number, control ID, asset name, or category

## Examples

- "What is at Purdue level 2?" becomes query_type=purdue_level, value=2
- "Tell me about SR 1.1" becomes query_type=iec_lookup, value=SR 1.1
- "What is AC-3?" becomes query_type=nist_lookup, value=AC-3
- "Where does an Allen-Bradley ControlLogix sit?" becomes query_type=asset_classify, value=Allen-Bradley ControlLogix
- "Which Purdue layers does SR 2.1 apply to?" becomes query_type=cross_reference, value=SR 2.1

## Output

Returns an HTML card. Present it to the user as-is with a one-line summary above it. Do not paraphrase the card contents.
