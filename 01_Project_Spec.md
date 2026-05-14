# Project Specification

## Goal

Build a config-driven Python tool that reads a PPTX file, identifies slide masters, layouts, shapes, containers, and text objects, then performs 1 to 1 content replacement without overwriting the template's formatting.

## Primary outcomes

- Preserve the original PPT design structure
- Preserve font family, size, bold, italic, color, alignment, and spacing where possible
- Support repeated reuse of 8 to 10 layout families across 26+ slides
- Allow client-centric control through configuration files
- Produce a validation report for unmatched or risky objects

## In scope

- Slide scanning
- Master and layout identification
- Shape inventory
- Group hierarchy mapping
- Placeholder detection
- Text extraction
- Config-driven layout selection
- In-place text replacement
- Basic overflow and mismatch detection
- Export of JSON inventory and replacement logs

## Out of scope for v1

- SmartArt decomposition
- Image OCR
- Chart data rewriting
- Complex table restructuring
- Auto-design of new layouts
- Semantic rewriting of content

## Success criteria

- A source deck can be scanned into JSON
- A content file can be mapped to existing slide objects
- Replacement can occur without flattening formatting
- A report can flag unsafe edits before the deck is saved

## Operating principle

The template controls structure. The content file controls text. The engine only brokers the mapping.
