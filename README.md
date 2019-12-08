The Punk Nova font
==================

This is an OpenType implementation of Donald Knuth’s
[Punk font][1].

Punk is a dynamic font, every time a glyph is requested Matafont draws
a unique instance of it. On the other hand, OpenType is static; glyph
outlines are drawn once and stored in the font and the renderer can not
alter those outlines. To emulate the dynamic nature of Punk, we generate
several alternate shapes of each glyph and store them in the font.
Alternate shapes are mapped to the base character using OpenType
[“randomize”][2] feature (`rand`), which tells the renderer to select
glyphs randomly from the list of alternate shapes.

Since 2010 was the 2⁵ anniversary of TeX, each lower case letter have 2⁵
variants, 2⁴ for each upper case and 2³ for the rest.

Unfortunately, the randomize feature is not widely supported (HarfBuzz
supports it, as well as some other less widely used applications).
In applications not supporting the randomize feature, only default shapes
will be shown.

The original METAFONT sources were adapted to a more MetaPost friendly
form by Taco Hoekwater et al.

The PostScript outlines of the glyphs were generated by MetaPost, a
Python script then used FontForge to import the glyphs into an OpenType
CFF font.

This font is distributed under the terms of Open Font License (OFL).

The MetaPost source has the following notice:

> This file is a merge of the original punk files by Donald Knuth, who
> added this comment:
>
>   Font inspired by Gerard and Marjan Unger's lectures,
>   Feb 1985
>
> The regular punk files are part of TeXLive and in Metafont format. All
> errors introduced are ours. We also changed the encoding to unicode. In
> due time we might add a few more more characters. We still need to
> improve some of the metrics which involves a bit of trial and error. The
> font just covers basic latin shapes but in ConTeXt MkIV we add virtual
> composed shapes. There is a module m-punk.tex that implements this. This
> derivate is also used in mk.tex (mk.pdf) which is one of our tests for
> LuaTeX. We published an article on it in the MAPS (NTG magazine).
>
> 2008, Taco Hoekwater & Hans Hagen

The MAPS article is [available online][3].

[1]: http://tug.org/TUGboat/Articles/tb09-2/tb21knut.pdf
[2]: http://www.microsoft.com/typography/otspec/features_pt.htm#rand
[3]: http://www.ntg.nl/maps/37/
