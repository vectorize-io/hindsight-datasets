# broken-media

**Does a knowledge bank take odd, broken and huge files without breaking?**

There are 26 files, one per problem a sweep of about 5,000 real-world files found in Hindsight's knowledge banks. Among them: a video whose metadata isn't UTF-8, an AVI without an index, a PDF that crashes pdfium, a Word file with tables nested thousands deep, and a page of labels with no full stop. Each file was the smallest one that showed its problem.

`manifest.json` lists each case:
- `file`: where it is in this folder;
- `source`: where it came from;
- `issue`: what went wrong with it;
- `expect`: what the server must do with it. That is `ready`, optionally with a search `query` that must find it and `text_contains` that its passages must hold; or `failed` / `rejected`, with `error_contains` that the reason must hold;
- `sha256`: the file's checksum.

[hindsight-system-evals](https://github.com/vectorize-io/hindsight/tree/main/hindsight-system-evals)'s `test_kb_edge_cases.py` downloads this folder at a pinned commit and runs every case against a server.

## What is not here

The sweep's full corpus (3.3 GB: Govdocs1, SafeDocs, pdf.js, Apache POI, FFmpeg FATE, Pillow, PngSuite, HEIF conformance) stays with its upstreams. Only the files that showed a problem are copied here.

## Sources and licenses

| Source | Cases | License |
| --- | --- | --- |
| [FFmpeg FATE suite](https://fate-suite.ffmpeg.org/) | `video/non-utf8-metadata.mov`, `video/no-index.avi`, `video/damaged-packets.mov`, `audio/damaged-packets.aac`, `video/cut-off.mkv`, `image/photo.heic`, `video/unsupported-codec.mp4` | Test samples that the FFmpeg project hosts and redistributes for testing |
| [pdf.js test corpus](https://github.com/mozilla/pdf.js/tree/master/test/pdfs) | `pdf/broken-page.pdf`, `pdf/encrypted.pdf`, `pdf/renderer-crash.pdf`, `pdf/no-sentence-ends.pdf` | Apache-2.0 |
| [Apache POI test-data](https://github.com/apache/poi/tree/trunk/test-data) | `office/visa-form.docx`, `office/deep-table.docx`, `office/header-only.docx`, `office/markitdown-keyerror.docx` | Apache-2.0 |
| [Pillow test images](https://github.com/python-pillow/Pillow/tree/main/Tests/images) | `image/float32.tiff` | MIT-CMU (Pillow's license) |
| [Govdocs1](https://digitalcorpora.org/corpora/file-corpora/files/) | `text/census-table.csv`, `text/two-bodies.html` | Public domain (US government works) |
| Made by the Hindsight team | the rest | MIT |
