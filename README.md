# Massimo: A Responsive Typographic Grid

## Intro

Massimo is a responsive grid system inspired by the [Vignelli Canon](http://www.vignelli.com/canon.pdf) from the prolific Modernist designer, [Massimo Vignelli](http://en.wikipedia.org/wiki/Massimo_Vignelli). It has a strong baseline grid with tight size and proportion relationships tied to one anchoring metric&mdash;body text. This brings the focus of the site design to its main purpose&mdash;the content.

## Features

### The Baseline Grid

The baseline grid of Massimo is created by the line-height of the body text, which is set on the `<body>` element to begin the appropriate cascade. All other elements on the page should take the body line-height into consideration when making decisions on height, margins, and padding. Top and/or bottom margins, for example, should be multiples of the line-height value in order to adhere to the grid.

[Example &rarr;](http://alchemyindesign.com/massimo/example.html)

### The Columnar Grid

Massimo uses a 12-column grid system. Twelve was chosen due to its flexibility in proportional combinations, switching between symmetrical and asymmetrical layouts with ease. The 12-columns can divide the page in half, thirds, quarters or any common offset like 9-column/3-column or 8-column/4-column. On the smaller screens, the grid sizes down to one fluid column to size into the multitude of viewports

### Nesting

One of the issues I wanted to find an alternative for was the ability to nest columns without an additional alpha/omega or first/last class. This is made possible through the use of modularized base classes for the columnar grid and dividing the content into horizontal sections using container elements, which most of us probably already do. 

Using [SMACSS](http://smacss.com/) [Open/Closed](http://en.wikipedia.org/wiki/Open/closed_principle) [Principle](http://csswizardry.com/2012/06/the-open-closed-principle-applied-to-css/), every column has the base class of `.l-col` applied with an extender class `.l-col-(n)`, the `(n)` being the column number. In addition, to primarily clear floats, a class of `.l-row` is applied to the parent container. Et voil&agrave;! All grid elements are treated the same in the mark-up.

### Widths

All widths have been measured in the [`rem`](http://www.w3.org/TR/css3-values/#rem-unit) unit. This keeps the designer conscious of the relationship between font-size and any supporting graphical elements such as images, video, rulers, etc. It is especially important when considering the word count or the character count per line block. Even though the translation is not literal, a container with a width of 22.5rem will yield a character count of roughly 2.5 times the width. That leaves us with approximately 57 characters, divided by an average of 6 characters per word or about 9 words per line&mdash;an optimal word count for comfortable reading! I consider this a promotion of designing for the content instead of designing for the device.

### Headings

The heading elements `<h1>` through `<h6>` have been set with consideration of two metrics&mdash;font-size and line-height. From baseline to [cap height](http://en.wikipedia.org/wiki/Cap_height), the `<h1>` spans three lines of text. The line-height is the literal equivalent of three times the line-height of the body text. The tricky value is font-size&mdash;this is purely optical and can change between fonts. From there, the `<h2>` is two lines of text and the `<h3>` is one.

The `<h4>`, where traditionally is equal to the body text font-size, has been sized down so that it is smaller than the main body text. It is perfect for heading supplemental text, as well as the `<h5>`. The `<h6>` will be for fine print or `<small>` headings. So, this leaves you with an even split of three heading sizes for main text and three heading sizes for smaller auxiliary text.

\(They may not always line up perfectly in every browser. C'est la Web.\)

### Type Sizes

All type should be limited to the six font-sizes that are demonstrated by the headings 1-6. These sizes were built around the primary body text font-size in order to create a supporting hierarchy and emphasize readability. Sizes are set on their respective elements, but can also be found as display type classes \(for hierarchy\) and text type classes \(for body copy\). Font-weight and font-style can be used to make the typographic system more robust.

### Type Size and Columns

I went back and forth on this several times because I didn't want to make too many design decisions for anyone interested in using this grid system. One of my biggest complaints about popular frameworks out there is that you, as the implementor, spend a decent amount of time modifying them in order to get them to work with your design (at least that's been my experience).

That being said, built into Massimo are default type size changes in relation to the grid column you are using. I did this to optimize readability and to emphasize hierarchy. One of the benefits of doing this is that the text maintains its visual hierarchy even on the one-column layout of mobile. It is a feature that is easy to turn off with CSS comments.

[Example &rarr;](http://alchemyindesign.com/massimo/example.html)

### Rulers

Because rulers \(or rules\) have always been such a signature element of Modern design, I thought it would be an oversight to not include them. They have a default of three weights to accentuate the hierarchy of information. The baseline grid consideration is built into their varying weights, margins, and padding. They can be used at the top or bottom of any container or can be used at the paragraph level on `<hr>`s.

## Caveats and Challenges

### Font Choice

As touched on above, the choice of font will affect the overall baseline grid as well as the baseline to cap height standard that `<h1>`, `<h2>`, and `<h3>` follow. If you choose another font, and I encourage you to do so, you will more than likely have to adjust the font-size of the larger headings.

Why is that? The font-size variation between font families is due to a combination of factors that can affect the overall visual size of the font. Differences in ascender height, cap height, x-height, and descender height can all play a part. The default settings should have you most of the way there, it will just be up to you to tweak and adjust.

### Browser Support

FireFox \(on Mac\) seems to have curious issues with larger heading sizes, especially with Helvetica. The differences in rendering can throw off the baseline grid for those headings, leaving you with type that floats 2-3px above the baseline. I am currently looking for a fix and am definitely [open to suggestions](http://alchemyindesign.com/contact.html).

This project is more of an experiment with rem units and the application of the Vignelli Canon to the web. IE8 and below doesn't seem to like rem units much, but Massimo offers support by way of a [pixel fall-back](http://snook.ca/archives/html_and_css/font-size-with-rem), as described by Jonathan Snook.

NOTE: IE8 and below will only recieve a fixed width site&mdash;no responsive design. I did this for the sake of maintenance and my own sanity ;\-\)

## Closing

### Acknowledgements

Massimo wouldn't have come to be if it weren't for the works and contributions of others in the community.

- [Massimo Vigelli](https://twitter.com/vignelli) | for his [entire life's work](http://www.vignelli.com/)
- [Nathan Smith](https://twitter.com/nathansmith) | for the [960 Grid System](http://960.gs/)
- [Dave Gamache](https://twitter.com/dhg) | for [Skeleton](http://www.getskeleton.com/)
- [Jonathan Snook](https://twitter.com/snookca) | for [SMACSS](http://smacss.com/)
- [Nicole Sullivan](https://twitter.com/stubbornella) | for [OOCSS](https://github.com/stubbornella/oocss/wiki)
- [Nicolas Gallagher](https://twitter.com/necolas) | for [Normalize.css](http://necolas.github.com/normalize.css/)
- [Harry Roberts](https://twitter.com/csswizardry) | for [expanding ideas](http://csswizardry.com/) on OOCSS

And also...

- [Patrick Kranzlmüller](https://twitter.com/sehmaschine/) | for feedback when Massimo was in beta and his wonderful work on [MUELLER](http://www.muellergridsystem.com/)
- [Ryan Deba](https://twitter.com/ryandeba) | for feedback and advice all the way through Massimo's creation.
- And everyone else I bugged on Twitter for feedback :\-D

### Final Thoughts

Massimo was created out of personal interest. Being from the world of print and having a long standing admiration for the work of the masters, it is a nod in the direction of those who came before us in the visual design world. Although web is NOT print and should be [treated as its own medium](http://www.alistapart.com/articles/the-web-aesthetic/), I still feel that we can borrow many ideas and philosophies that have been maintained in the print world for centuries. 

Massimo is for you to play with, experiment with, and build upon. I tried not to make more design decisions than needed to get the point across, so hopefully it is easy to modify as well.

Best regards to all. Cheers!