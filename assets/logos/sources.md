# The logos of the title slide, where each file comes from, and how the slide embeds them

The four files are the original downloads of 2026-10-17, renamed.
Each file is the latest version that its organization publishes, and none has been edited.

| file | logo | downloaded from | linked by |
|---|---|---|---|
| `mit-logo-black.png` | the MIT logo in black, the RGB file `mit_logo_std_rgb_black.png` of the MIT brand downloads | [the file in the Dropbox of CEE](https://www.dropbox.com/scl/fi/1al0vga8utps044e0n94h/mit_logo_std_rgb_black.png?rlkey=admyqw8kjmr9bdvjz5uvmbwwf&dl=0) | [CEE Brand Assets](https://cee.mit.edu/resources/cee-brand-assets), under MIT Logo Files |
| `mit-cee-logo-colour.png` | the word mark of MIT Civil and Environmental Engineering in colour, `MITCEE_logo.png` | [the file in the Dropbox of CEE](https://www.dropbox.com/scl/fi/5q29to0ig4yqxfhd97dn8/MITCEE_logo.png?rlkey=rpp7fyeaoeojmnn18zq1zgaot&dl=0) | [CEE Brand Assets](https://cee.mit.edu/resources/cee-brand-assets), under MIT CEE Logo Files |
| `mit-lids-logo-and-wordmark-black.png` | the logo and word mark of LIDS in black, `PNG Files/Lids logo and wordmark-black.png` | [the logo folder of LIDS](https://www.dropbox.com/scl/fo/talnr5u99sot0ncd00gmd/AG40XtoXW8NOfd3IQ5XqDZE?rlkey=76ragyntq9vbg7in33jl0o9e4&dl=0) | [LIDS Logo & Branding](https://lids.mit.edu/lids-portal/logo-branding) |
| `mit-idss-logo-colour.png` | the logo of IDSS in colour, `IDSS_Square.png` | [the file on the IDSS site](https://idss.mit.edu/files/2026/04/IDSS_Square.png) | the header of [the IDSS home page](https://idss.mit.edu/) |

The MIT brand downloads at [brand.mit.edu/downloads](https://brand.mit.edu/downloads) need a Touchstone login.
The RGB folder of their zip of the MIT logo holds PNG and SVG files.

## The title slide embeds a smaller copy of each file

The cells `title-logo-cee`, `title-logo-lids`, `title-logo-idss` and `title-logo-mit` of `sections/1-opening.drawio.xml` hold the logos as data URIs, because the draw.io editor shows only a picture that sits inside the file.
`skills/deck-skeleton/place-logos.py` of this repository wrote the cells from the four files, with the command that the how-to on placing the logos of `skills/deck-skeleton.md` gives.
To replace a logo, replace its file and run the same command again.
