For a full list of modifications since DOMPDF 0.6.0 beta 2 see the changes listed on this page of the [repository changelog](http://code.google.com/p/dompdf/source/list?num=88&start=472&path=/trunk).

> ### Known Issues ###

  * Table cells cannot be split over multiple pages
  * CSS float support is not yet perfected

For a full list of known issues, see the [issue tracker](http://code.google.com/p/dompdf/issues/list).

> ### Installation Notes ###

  * Starting with DOMPDF 0.6.0 the dompdf.php script will no longer allow conversion of HTML document on the local file system that are located outside of the path specified by [DOMPDF\_CHROOT](http://code.google.com/p/dompdf/source/browse/tags/dompdf_0-6-0_beta3/dompdf/dompdf_config.inc.php#109)
  * If you are installing DOMPDF on top of an existing installation you should remove any existing font metrics. This can be done manually or through the sample website (www/fonts.php).
  * When upgrading to a new version of DOMPDF you must replace dompdf\_config.inc.php with the new one. To simplify the upgrade process you can store your configuration settings in dompdf\_config.custom.inc.php (which does not need to be overwritten).

> ### DOMPDF 0.6 Roadmap ###

  * Improve Unicode support
  * Improve page breaks inside or outside tables
  * Improve support for CSS float
  * Reduce memory usage


---


> # DOMPDF 0.6.0 beta 2 #

> ## New Features ##

> ### HTML/CSS/Images support ###

  * CSS3: opacity, 2D transforms
  * CSS2: outline, letter-spacing, z-index, position: relative, overflow: hidden
  * CSS Pseudo elements :before and :after with generated content
  * CSS2 pseudo-selectors (last-child, disabled, checked, enabled)
  * CSS3 attribute selectors (ends-width, starts-width, contains)
  * Improves absolute positioning
  * Adds fixed positioning
  * CMYK colors and CMYK Jpeg images
  * 32bit PNG with alpha channel (Cpdf backend)
  * BMP images (8, 24 and 32 bit)
  * Adds support for image embedding via “data” URI
  * Adds support for ordered list
  * Adds support for embedding PDF JavaScript
  * Uses the HTML document title element and certain meta tags to populate the PDF’s meta information (title, author, keywords and subject)
  * Uses the “alt” attribute of an image when the image is inaccessible
  * Supports loading system fonts

> ### Installation / configuration ###

  * The demo page now shows the HTML file and the PDF document in an iframe
  * Adds a setup/configuration tool that provides information about the server configuration, dompdf parameters, and installed fonts.
  * The font metrics cache files can now be cleared using the setup/config tool
  * Adds a debug tool that shows side-by-side the HTML file, the rendered PDF, and a console showing memory consumption, rendering time, warning, and debug messages
  * Adds examples showing new features
  * Moves ttf2ufm out of the DOMPDF code repository and into an [external project](http://code.google.com/p/ttf2ufm/)
  * Disables inline PHP support by default
  * Disables direct input in the examples page for non-localhost access
  * Adds configuration option to help debugging (see DEBUG\_LAYOUT) which draws rectangles around the different types of blocks and frames

> ## Major bug fixes ##

  * Addresses memory leaks from running eval() on the font metrics cache
  * Reduces memory consumption caused by the font metrics (when using the Cpdf backend)
  * Updates text wrapping to prevent splitting text into more lines than needed ([issue 198](http://code.google.com/p/dompdf/issues/detail?id=198))
  * Implements a check against an infinite loop caused by table cells larger than a page
  * Improves text height and width calculations as well as placement (improves, for example, justified text rendering for text that is not iso-8859-1)
  * Updates the fallback MBString functions
  * Supports PHP 5.3 and includes improved compatibility with older versions of PHP 5
  * Improves image placement
  * Addresses problems with table flow caused by empty table cells
  * Addresses warning/errors caused by unrecognized CSS rules or selectors


For a full list of modifications since DOMPDF 0.6.0 beta 1 see the [repository changelog](http://code.google.com/p/dompdf/source/list?path=/tags/dompdf_0-6-0_beta2&num=104)

> ## Known Issues ##

  * Table cells cannot be split over multiple pages
  * Column widths of tables that span more than one page may not be consistent across pages

> ## Installation Notes ##

  * Starting with dompdf 0.6.0 dompdf.php will no longer allow conversion of HTML document on the local file system that are located outside of the path specified by DOMPDF\_CHROOT
  * The format of the font metrics cache has changed as of this release. You should manually remove any existing font metrics prior to upgrading or use the setup/configuration tool to do so immediately after.
  * Inline PHP is **disabled** by default now (see DOMPDF\_ENABLE\_PHP)
  * Because additional configuration options have been added you will need to replace your dompdf\_config.inc.php file with the new one. You may modify this file or copy your configuration settings to dompdf\_config.custom.inc.php.