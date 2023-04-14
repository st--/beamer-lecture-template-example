# beamer-lecture-template-example

Template structure for consistent LaTeX/Beamer slides&amp;handouts

## Directory and file structure

- lec-example/{content.tex,Makefile}: example lecture template - copy for different lectures
- template/preamble.tex: all lecture-independent settings for the overall template
- template/shorthands.tex: helper commands like `\GP` instead of `\mathcal{GP}`
- Makefile: for building all slides at once

## How to build slides

The Makefile in the root directory recursively runs the requested target in all `lec*` subdirectories. To build only an individual lecture, simply change into its directory for running the make target.

Targets:
- `make slides`: build the slides (for presentation, with transitions split across multiple pages of the PDF)
- `make handout`: build handout version (for sharing with students; transitions collapsed for easier viewing)
- `make clean`: clean up all temporary build files (keeps PDFs around)
- (mainly relevant within an individual subdirectory:) `make continuous TARGET=slides` / `make continuous TARGET=handout`: continuous LaTeX build for automatic updates while developing slides (assumes `evince` as PDF previewer; you can set your own by passing `PDF_PREVIEWER=` as well)
