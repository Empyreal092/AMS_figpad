# Padding figures for publishing (in AMS journals)

This does not work, unfortunately
> Our vendor (who creates the proofs and implements the proof corrections) has instructions to remove extraneous padding space from around figures as part of the standard figure processing specifications
If you are here, you must care about the details of how your figures appear in your paper.
> Hopefully, you found this repo before you decided to submit to one of the AMS journals. If not, know that I share your misery.

American Meteorological Society (AMS) journal (e.g., JPO, JAS, etc.) production team would much prefer it if the figures in the paper are 19 (one column), 27, 33, or 39 picas. See the [AMS website](https://www.ametsoc.org/ams/publications/author-information/figure-information-for-authors/#Size). And I quote a copyeditor for my paper:

> Because of the layout constraints of the PDF format, we must adhere to our standard figure sizing. [...] figures that need to be larger than a single column must be set at one of the other three sizes (27, 33, or 39 picas).

This is a tool for converting figures to these four sizes. Right now, this only works for `.png` (raster) and `.pdf` (vector). But the notebooks can be modified to work on other formats without much work.
 - [`png_pad.ipynb`](https://github.com/Empyreal092/AMS_figpad/blob/main/png_pad.ipynb): is for padding raster images. It should work for other raster formats no problem. It uses the [`Pillow`](https://pillow.readthedocs.io/en/stable/) package.
 - [`pdf_pad.ipynb`](https://github.com/Empyreal092/AMS_figpad/blob/main/pdf_pad.ipynb): is for padding vector images. It is more complex and perhaps is not the best solution. It convert `.pdf` files to `.svg`, then uses [`svgutils`](https://svgutils.readthedocs.io/en/latest/) to do the padding. The final conversion from `.svg` back to `.pdf` is done using [`rsvg-convert`](https://manpages.ubuntu.com/manpages/plucky/man1/rsvg-convert.1.html) in the command line.

Hope this helps.
