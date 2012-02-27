While building and testing code meant to properly handle arbitrary UTF-8 strings, I had need for some Unicode test documents or files that included every possible codepoint: including control codes like NULL, EOT, XOFF, CAN and the never-seen-used DC2 right past 7-bit US-ASCII and on to the deep recesses of Unicode.

You never know what garbage people or errors will throw at your system, so here you'll find the gamut of representable characters / code points.


Raw Character Sequences
=======================

unseparated/*.txt documents contain every UTF-8 code point in a given range, raw, without any separation between characters / code points.


Readable Character Sequences
============================

separated/*.txt documents contain every UTF-8 code point in a given range separated by spaces with newlines every 50 characters / code points to aid readability.

separated/*.html documents contain the same sequences as the separated/*.txt files but as XHTML with UTF-8 specified.


Variants
========
- printable characters / code points
- assigned code points (including unprintable codepoints as-is)
- assigned code points (including unprintable codepoints, but these replaced by Unicode Character 'REPLACEMENT CHARACTER' (U+FFFD))
- assigned and unassigned code points (including unprintable codepoints as-is)
- assigned and unassigned code points (including unprintable codepoints, but these replaced by Unicode Character 'REPLACEMENT CHARACTER' (U+FFFD))

Note that these documents really do contain every character / code point in the specified range, including potentially unexpected control characters like NULL, ESC, End of Transmission (EOT), etc…  Many usual tools can have difficulty working with them because they contain rarely seen characters, and the larger ranges have a lot in them.

For you to be able to see a given character, your system must have at least one installed font that contains a glyph for that code point for you to be able to see it.  To see all these wonderous and unexpected characters, you may want to obtain:

- James Kass' Code2000, Code2001 and Code2002 fonts. http://en.wikipedia.org/wiki/Code2000 explains that James' site is long gone, but thankfully Internet Archive's Wayback Machine saved it at http://web.archive.org/web/20110108105420/http://code2000.net/
- George Douros's Symbola font http://users.teilar.gr/~g1951d/ covers Unicode 6.0