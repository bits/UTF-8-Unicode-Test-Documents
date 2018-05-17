Every Unicode code point
========================
While building and testing code meant to properly handle arbitrary UTF-8 strings, there is often a need for some Unicode test documents that included every possible codepoint, including control codes like `NULL`, `EOT`, `XOFF`, `CAN`cel and the never-seen-used `DC2`, right through 7-bit US-ASCII and on to the deepest recesses of Unicode.

You never know what garbage people or errors will throw at your system, so here you'll find **the gamut of representable characters / code points to test with**.


## Human-Readable Character Sequences

The `UTF-8_sequence_separated/*.txt` are UTF-8 encoded plaintext documents containing every UTF-8 code point in a given range separated by spaces with newlines every 50 code points to aid readability.  

Your viewer might need to be told that the files are UTF-8 for them to show properly.  As is recommended with UTF-8, no Byte Order Marks (BOM) are employed. Opening the files from your filesystem in your browser will not likely work because there's nothing to tell the browser that it's dealing with UTF-8 encoded content and not your system's current character encoding.  Serve them from a web server that indicates their UTF-8-ness with a `Content-Type: text/plain; charset=utf-8` HTTP header and all is well.  GitHub-served "raw" files do this.  Alternatively, your viewer or editor may have a command to open a file as UTF-8.

Similarly, the `UTF-8_sequence_separated/*.html` documents contain the same sequences as the `UTF-8_sequence_separated/*.txt` files as UTF-8 encoded XHTML documents **without any character entity encoding**.  Note that even characters such as < > & and ' that MUST BE encoded into their character entiry representations to be valid XML/XHTML have intentionally not been, so these are **not valid XML**.  They are nonetheless useful in testing.


## Raw Character Sequences

The `UTF-8_sequence_unseparated/*.txt` are UTF-8 encoded plaintext documents containing every UTF-8 code point in a given range, raw, without any separation between characters / code points.


## Variants

- printable characters / code points
- assigned code points (including unprintable codepoints as-is)
- assigned code points (including unprintable codepoints, but these replaced by Unicode Character 'REPLACEMENT CHARACTER' (U+FFFD))

and for completeness:

- assigned and unassigned code points (including unprintable codepoints as-is)
- assigned and unassigned code points (including unprintable codepoints, but these replaced by Unicode Character 'REPLACEMENT CHARACTER' (U+FFFD))


## Unicode Code Planes Covered

0000–​FFFF Plane 0: Basic Multilingual Plane
10000–​1FFFF Plane 1: Supplementary Multilingual Plane
20000–​2FFFF Plane 2: Supplementary Ideographic Plane
30000–​DFFFF Planes 3–13: *Unassigned*
E0000–​EFFFF Plane 14: Supplement­ary Special-purpose Plane
F0000–​10FFFF Planes 15–16: Supplement­ary Private Use Area

The documents' filenames indicate the range of characters / code points they contain.  Refer to the above to see how these map to the various Unicode planes.


## All characters — even the rarely/never used control characters

These documents really do contain every character / code point in the specified range, including potentially unexpected control characters like NULL, ESC, End of Transmission (EOT), etc…  Many common tools can have difficulty working with these files because of these characters.


## Non-characters omitted

- High and low surrogate halves used by UTF-16 (U+D800 through U+DFFF) are not legal Unicode values, and the UTF-8 encoding of them is an invalid byte sequence. Not included.
- 0xFDD0 through 0xFDEF are non-characters and not included.
- likewise, 0xFFFE, 0xFFFF, 0x1FFFE, 0x1FFFF, …, 0xfFFFE, 0xFFFFF, 0x10FFFE, 0x10FFFF are non-characters and are not included in any of the files.


## Fonts to see them by

For you to be able to see a given character, your system must have at least one installed font that contains a glyph for that code point for you to be able to see it.  To see all these wonderous and unexpected characters, you may want to obtain:

- Google Noto fonts https://www.google.com/get/noto/
- Google Noto CJK comprehensively covers Simplified Chinese, Traditional Chinese, Japanese, and Korean in a unified font family https://www.google.com/get/noto/help/cjk/
- George Douros's Symbola font http://users.teilar.gr/~g1951d/
- James Kass' Code2000, Code2001 and Code2002 fonts. http://en.wikipedia.org/wiki/Code2000 explains that James' site is long gone, but thankfully Internet Archive's Wayback Machine saved it at http://web.archive.org/web/20110108105420/http://code2000.net/

# Show me the code

 Absolutely.  You want your bits freshly generated.  Stored bits are just not the same.  I understand.  :) See exactly how these files were generated, or generate your own UTF-8 character sequences with the flexible generator/utf8_sequence_generator.pl
