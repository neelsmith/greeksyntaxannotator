# `greeksyntaxannotator`

> *Work in progress on a vibe-coded single-page web app for annotating the syntax of ancient Greek.*


## Screen shot

![Screen shot](./annotator.png)


## Summary

**Status**: pre-release. Basic interactive functionality is complete to tokenize a string, annotate the identified tokens, and display the analysis in various forms, including a graph diagram that can be downloaded as a PNG file.

**TBD**:


I/O functionality:

- load text from CITEable sources
- identify tokens with CTS URNs
- download analysis as a delimited-text file

UI functionality:

- delete rows from table of verbal units

**Contents**:

- `syntaxannotator.html`: current draft of web app.
- `treebankprompting.md`: text of prompts pasted into chat with Gemini 2.5 pro.
- `versions`: web pages of incremental builds

## Caveats

The web app was written entirely by gemini-2.5-pro. The code passes some sanity tests, but I have not even looked at the javascript. When I encountered errors, I let gemini fix them. Use the code as you like, but be aware that I have no idea what it does or how it works.