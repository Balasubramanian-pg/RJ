# JSON Schema Notes

## 1. Layout registry

Describes each layout family and what kind of content it can absorb.

Fields:
- `layout_id`
- `layout_name`
- `master_name`
- `allowed_content_types`
- `capacity`
- `repeat_policy`
- `fallback_layouts`

## 2. Slide content manifest

Describes what each slide should contain before matching.

Fields:
- `slide_id`
- `content_type`
- `title`
- `subtitle`
- `sections`
- `priority`
- `layout_preferences`

## 3. Inventory output

Describes what was found in the source PPTX.

Fields:
- `slide_index`
- `master_name`
- `layout_name`
- `shapes`
- `shape_key`
- `shape_type`
- `group_path`
- `z_order`
- `bounds`
- `text`
- `style_signature`

## 4. Replacement map

Describes the final 1 to 1 edit instructions.

Fields:
- `shape_key`
- `new_text`
- `replace_mode`
- `preserve_formatting`
- `overflow_policy`

## Shape key recommendation

Use a stable key like:

`slide_index / shape_name / path`

Example:
`5/Title 1`
`12/GroupA/TextBox3`
