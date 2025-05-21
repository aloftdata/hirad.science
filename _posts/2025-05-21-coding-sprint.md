---
title: Productive coding sprint in Amsterdam
description: >
  At last week's coding sprint, we developed new functionality to process and explore data from both small-scale bird radars and weather radars.
author: Bart Kranstauber
background:
  img: /assets/backgrounds/2025-05-21-coding-sprint.jpg
  by: Judy Shamoun-Baranes
tags: [WP2, meeting, software, open data]
toc: true
---

As part of the HiRAD project, last week 11 people collectively took part in a coding sprint. In Amsterdam and online, we worked for three days on software for aeroecology.

## birdscanR

For the [birdscanR](https://github.com/BirdScanCommunity/birdscanR) R package, a [website](https://birdscancommunity.github.io/birdscanR/) and readme were created, and continuous testing was implemented. Furthermore, a function to construct a vertical profile time series was implemented, and [numerous other improvements](https://github.com/BirdScanCommunity/birdscanR/commits/develop/?since=2025-05-12&until=2025-05-16) were made.

## getRad

In the [getRad](https://github.com/aloftdata/getRad) R package, functionality to download polar volume data was extended to the United States. [Seven countries](https://aloftdata.github.io/getRad/articles/supported_sources.html) are now supported. Vertical profile time series data can be loaded directly from the [Aloft bucket](https://aloftdata.eu/browse/) and the [RMI](https://opendata.meteo.be/geonetwork/srv/eng/catalog.search#/metadata/RMI_DATASET_CROW). In addition, the behaviour of the `get_pvol()` and `get_vpts()` functions is synchronized, and documentation was improved. These updates will be released to CRAN soon.

## Other

Smaller updates were made to the [bioRad](https://github.com/adokter/bioRad) and [birdR](https://gitlab.com/uva_ibed_ame/robin_radar/birdar) R packages, and the [NAAVRE](https://naavre.net/) environment was explored to create a pipeline for processing radar data. The sprint allowed us to communicate directly, so many questions and discussions could be resolved efficiently.
