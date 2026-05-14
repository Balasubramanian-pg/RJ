# Replacement Rules

## Hard rules

1. Preserve the template object.
2. Replace text in place.
3. Do not reset the font if the current font is already defined in the shape.
4. Do not recreate the shape unless no safe edit path exists.
5. Flag anything with mixed formatting for review if safe replacement cannot preserve runs.

## Matching rules

Prefer the following in order:

1. Same placeholder role
2. Same shape name
3. Same shape type
4. Same position and size
5. Same group path
6. Same text pattern
7. Same capacity class

## Overflow rules

- If text fits, write directly.
- If text risks overflow, flag it.
- If configured to allow shrink, apply the smallest possible change.
- If configured to preserve exact formatting, do not auto-shrink unless explicitly permitted.

## Reuse rules

A layout may be reused multiple times, but avoid repetitive patterns.

Suggested controls:
- max consecutive reuse count
- preferred alternate layouts
- density-based fallback
- section-divider exceptions

## Client-centric control points

The client should be able to control:

- which layouts are allowed
- how often a layout can repeat
- whether long content gets split
- whether optional sections can be dropped
- whether overflow should trigger a hard stop
