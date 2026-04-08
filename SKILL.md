-----

## name: ot-field-reference
description: Offline reference for OT/ICS cybersecurity professionals. Looks up Purdue Model levels, IEC 62443 foundational requirements and zones, NIST SP 800-82r3 control overlays, and classifies OT assets by Purdue level + IEC zone. Use whenever the user asks about Purdue levels, IEC 62443, NIST 800-82, OT/ICS controls, asset classification (PLC, RTU, HMI, historian, engineering workstation, etc.), or which security controls apply to a specific layer of an industrial network.
metadata:
homepage: https://github.com/CKing722/ot-field-reference
author: CK (Crypto King)
version: 1.0.0

# OT Field Reference

A field-ready offline reference for OT/ICS cybersecurity work covering the Purdue Enterprise Reference Architecture, IEC 62443-3-3 foundational requirements, and NIST SP 800-82r3 control overlays. Built for plant-floor lookups where connectivity is unreliable.

## When to invoke this skill

Call this skill whenever the user:

- Asks about a **Purdue level** (0–5) or what assets belong at a level
- Asks about **IEC 62443** zones, conduits, foundational requirements (FRs), or system requirements (SRs)
- Asks about **NIST SP 800-82** controls or control overlays
- Names an **OT asset** (PLC, RTU, HMI, SCADA server, historian, engineering workstation, jump host, domain controller, etc.) and wants to know its level/zone/applicable controls
- Wants a **cross-reference** between a control and the Purdue layers it applies to
- Asks “what level is X” or “what controls apply to Y”

## Parameters

When invoking, pass a JSON object with these fields:

|Field       |Values                                                                                           |Description                                                                                 |
|------------|-------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
|`query_type`|`purdue_level` | `iec_lookup` | `nist_lookup` | `asset_classify` | `cross_reference` | `list_all`|The type of lookup                                                                          |
|`value`     |string or number                                                                                 |Level number (0–5), control ID (e.g., `SR 1.1`, `AC-3`), asset name, or empty for `list_all`|

## Examples

- User asks “What’s at Purdue level 2?” → `{"query_type": "purdue_level", "value": "2"}`
- User asks “Tell me about SR 1.1” → `{"query_type": "iec_lookup", "value": "SR 1.1"}`
- User asks “What is AC-3?” → `{"query_type": "nist_lookup", "value": "AC-3"}`
- User asks “Where does an Allen-Bradley ControlLogix sit?” → `{"query_type": "asset_classify", "value": "Allen-Bradley ControlLogix"}`
- User asks “What’s the historian’s Purdue level?” → `{"query_type": "asset_classify", "value": "historian"}`
- User asks “Which Purdue layers does SR 2.1 apply to?” → `{"query_type": "cross_reference", "value": "SR 2.1"}`
- User asks “Show me all Purdue levels” → `{"query_type": "list_all", "value": "purdue"}`

## Output

The skill returns a structured HTML card with the requested reference information. Present the card to the user as-is and add a brief one-line summary in your own words above it. Do not paraphrase or restate the card contents — the user wants the authoritative reference, not a rewording of it.

## Important

- This skill contains reference data only. It does not make security recommendations specific to a particular environment.
- For NIST SP 800-82r3, the data reflects the public NIST overlay summaries. Always verify against the official document for compliance work.
- For IEC 62443-3-3, the SR descriptions are summarized from public sources. The official IEC standard text is paywalled and should be the authoritative source for any audit or compliance deliverable.
