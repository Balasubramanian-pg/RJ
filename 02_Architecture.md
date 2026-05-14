# System Architecture

## Modules

### 1. scanner
Reads the PPTX and emits a structural inventory.

Responsibilities:
- detect masters and layouts
- enumerate shapes
- record shape geometry
- record group hierarchy
- detect text and formatting
- assign stable shape keys

### 2. matcher
Maps content blocks to layout targets.

Responsibilities:
- classify slide intent
- compare content type to layout capacity
- apply fallback rules
- enforce repeat limits
- return a deterministic mapping

### 3. replacer
Writes new content into existing shapes.

Responsibilities:
- replace text only
- preserve formatting containers
- avoid shape recreation
- flag overflow risk

### 4. validator
Produces a QA report after replacement.

Responsibilities:
- detect unmapped text blocks
- detect missing shapes
- detect likely overflow
- compare before and after structure

## Data flow

PPTX source
→ scanner
→ inventory JSON
→ matcher
→ replacement JSON
→ replacer
→ output PPTX
→ validator
→ report

## Recommended libraries

- `python-pptx` for standard slide operations
- `lxml` for lower-level XML access when needed
- `json` for config and mapping files
- `pathlib` for filesystem handling
- `logging` for traceability

## Design rule

Do not rebuild the deck object model if the object already exists. Update the existing object in place wherever possible.
