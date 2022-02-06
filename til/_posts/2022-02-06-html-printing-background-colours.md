---
layout: til
title: "Printing background colours on web pages"
---

I was surprised to find that by default browsers will hide the background colours of elements if you print the page. If you need the background printed the following CSS should do the trick:

    .print-background {
        color-adjust: exact; // Firefox
        -webkit-print-color-adjust: exact; // Edge, Chrome, Safari
    }

([Reference](https://caniuse.com/mdn-css_properties_color-adjust))