# Test Plan

## Test 1: Scan only

Input:
- source PPTX

Expected:
- JSON inventory is created
- masters and layouts are identified
- shapes are indexed

## Test 2: Basic replacement

Input:
- source PPTX
- replacement JSON

Expected:
- text updates in existing boxes
- formatting remains visually consistent
- no shape recreation

## Test 3: Long content

Input:
- replacement text longer than original

Expected:
- overflow is flagged
- no silent corruption occurs

## Test 4: Mixed formatting

Input:
- shape with bold, italic, and normal runs

Expected:
- replacement logic preserves formatting where possible
- risky shapes are reported

## Test 5: Layout reuse

Input:
- 26-slide manifest
- 8 to 10 layout families

Expected:
- layouts are reused intelligently
- repetition limits are respected
- slide intent is preserved

## Validation checklist

- master name captured
- layout name captured
- shape bounds captured
- group hierarchy captured
- text extracted
- formatting preserved
- output PPTX opens cleanly
- no broken hyperlinks or media references
