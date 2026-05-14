# PPTX Content Replacement Project Pack

This pack defines the project structure for a config-driven Python system that:

- scans a PPTX deck
- inventories slides, masters, layouts, shapes, and formatting
- maps source content to template objects
- replaces text while preserving original formatting
- validates the result for overflow, mismatch, and layout drift

## Included files

- `01_Project_Spec.md` - business and functional scope
- `02_Architecture.md` - system design and data flow
- `03_JSON_Schema.md` - config and inventory schema
- `04_Replacement_Rules.md` - matching and replacement rules
- `05_Test_Plan.md` - validation and QA checklist
- `sample_layout_config.json` - layout registry sample
- `sample_content_manifest.json` - slide content manifest sample
- `sample_replacement_map.json` - replacement payload sample
- `starter_script.py` - Python scaffold for scan and replace workflows

## Core principle

Do not recreate shapes during replacement. Edit the existing text containers in place so the font family, font size, alignment, spacing, and styling remain intact.
