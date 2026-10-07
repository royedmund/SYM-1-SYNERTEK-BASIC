# Synertek SYM-1 BASIC — trigonometric functions and examples

A collection of SYM-1 BASIC examples and a trigonometric-function extension providing `SIN`, `COS`, `TAN` and `ATN`.

## Files

| File | Purpose |
| --- | --- |
| [TRIGFNS.HEX](TRIGFNS.HEX) | Supplied machine-code extension in HEX format |
| [SINWAVE.BAS](SINWAVE.BAS) | Sine-wave text output example |
| [3DPLOT.BAS](3DPLOT.BAS) | Three-dimensional text plot example |
| [technotes.pdf](technotes.pdf) | Technical reference for the extension |

## Setup and limitations

Read the technical notes before loading machine code. The BASIC listings reserve memory for the extension on a 4 KB system and include a DATA/POKE loader starting at decimal `3783` (`$0EC7`). They also refer to an entry address of `$0F68` through `POKE 196,104: POKE 197,15`.

`3DPLOT.BAS` calls its loader and installs the entry pointer. In `SINWAVE.BAS`, the corresponding `GOSUB` and pointer setup are commented out; that example expects the extension to have been loaded and attached separately. Do not assume that importing it and typing `RUN` is sufficient.

The comments and loader bounds are not entirely consistent: the loop extends to decimal `4096` (`$1000`), beyond the commented `$0FFF` end address. Verify the technical notes, memory reservation and DATA count on your SYM-1 before running the loader. These hardware-specific routines are not intended for an unmodified desktop BASIC interpreter.

## Repository structure

The flat layout keeps the original listings, HEX file and technical notes together. Preserve the uppercase filenames for transfers to older systems. This repository does not currently include a standalone licence file; retain the existing source attribution, including the Creative Computing credits in the BASIC examples.
