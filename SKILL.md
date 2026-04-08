---
name: ot-field-reference
description: Offline reference for OT/ICS cybersecurity. Looks up Purdue Model levels, IEC 62443 foundational requirements, NIST SP 800-82r3 control overlays, and classifies OT assets. Use when the user asks about Purdue levels, IEC 62443, NIST 800-82, OT controls, or asset classification (PLC, RTU, HMI, historian, engineering workstation, etc.).
---

# OT Field Reference

Offline reference for OT/ICS cybersecurity covering Purdue Model, IEC 62443-3-3, and NIST SP 800-82r3.

## How to use

When the user asks about Purdue levels, IEC 62443 zones or requirements, NIST 800-82 controls, OT asset classification, or wants to cross-reference a control to Purdue layers, you MUST call the `run_js` tool with a JSON object in this exact schema:

- query_type: one of purdue_level, iec_lookup, nist_lookup, asset_classify, cross_reference, list_all
- value: the level number, control ID, asset name, or category

## Examples

User asks "What is at Purdue level 2?" → call run_js with {"query_type": "purdue_level", "value": "2"}

User asks "Tell me about SR 1.1" → call run_js with {"query_type": "iec_lookup", "value": "SR 1.1"}

User asks "What is AC-3?" → call run_js with {"query_type": "nist_lookup", "value": "AC-3"}

User asks "Where does an Allen-Bradley ControlLogix sit?" → call run_js with {"query_type": "asset_classify", "value": "Allen-Bradley ControlLogix"}

User asks "Which Purdue layers does SR 2.1 apply to?" → call run_js with {"query_type": "cross_reference", "value": "SR 2.1"}

User asks "Show me all Purdue levels" → call run_js with {"query_type": "list_all", "value": "purdue"}

## Output

The run_js tool returns an HTML card. Present it to the user as-is with a one-line summary above it. Do not paraphrase the card contents.
