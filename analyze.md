---
title: Data Analysis
nav-menu: true
layout: post
image: assets/images/southern_gel.jpg
---

<p style="font-size: 0.9rem;font-style: italic;"><img style="display: block;" src="https://live.staticflickr.com/68/205777138_995cea4253.jpg" alt="DNA - Blue"><a href="https://www.flickr.com/photos/99941535@N00/205777138">"DNA - Blue"</a><span> by <a href="https://www.flickr.com/photos/99941535@N00">Spanish Flea</a></span> is licensed under <a href="https://creativecommons.org/licenses/by-nc-nd/2.0/?ref=ccsearch&atype=html" style="margin-right: 5px;">CC BY-NC-ND 2.0</a><a href="https://creativecommons.org/licenses/by-nc-nd/2.0/?ref=ccsearch&atype=html" target="_blank" rel="noopener noreferrer" style="display: inline-block;white-space: none;margin-top: 2px;margin-left: 3px;height: 22px !important;"><img style="height: inherit;margin-right: 3px;display: inline-block;" src="https://search.creativecommons.org/static/img/cc_icon.svg?image_id=9b079eff-5fcd-41c8-80aa-6c74188f12e2" /><img style="height: inherit;margin-right: 3px;display: inline-block;" src="https://search.creativecommons.org/static/img/cc-by_icon.svg" /><img style="height: inherit;margin-right: 3px;display: inline-block;" src="https://search.creativecommons.org/static/img/cc-nc_icon.svg" /><img style="height: inherit;margin-right: 3px;display: inline-block;" src="https://search.creativecommons.org/static/img/cc-nd_icon.svg" /></a></p>

Next, you would want to analyze your datasets. We have included a report generation tool detailed in `examples/example_report/README.md` that generates a index.html page from a Rmd report. This initial report provides instructions on dataset creation used by the KnitR process to create normalization and distribution fitting results, distance matrix selection, and finally clustering analysis.

I encourage you to check out the [CLI documentation](/quickstart#usage) for details on what functions are used for normalization, dimensionality reduction, and distance matrix generation.

Also, please take a look at [the example_report README.md](https://github.com/MatthewRalston/kmerdb/tree/master/examples/example_report) for more details about how to populate the report with metadata about an analysis of samples via kdb.

And finally, please check out the template [index.Rmd](https://github.com/MatthewRalston/kmerdb/blob/master/examples/example_report/index.Rmd) for information about the statistical analyses performed and how these become the primary index.html page for the results.
