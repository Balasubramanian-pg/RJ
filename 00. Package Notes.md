# Package Notes

This is a starter pack.

The first build should focus on:

- scanning the source PPTX into inventory JSON
- validating master and layout discovery
- writing a replacement map that targets existing shapes
- preserving all existing font formatting unless explicitly overridden

Recommended next implementation step:
- refine the scanner to capture placeholder types, group nesting, and paragraph/run formatting
- then upgrade the replacer to handle mixed-format text without flattening styles
