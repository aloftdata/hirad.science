---
title: Productive coding sprint in Amsterdam
description: At last week's coding sprint, we developed new functionality to process and explore data from both small-scale bird radars and weather radars. 
author: Bart Kranstauber
background:
  img: /assets/backgrounds/2025-05-21-coding-sprint.jpg
  by: Judy Shamoun-Baranes
tags: [WP2, meeting, software, open data]
---

As part of the HiRAD project, last week 11 people collectively took part in a coding sprint. In Amsterdam and online, we worked for three days on software for aeroecology. For the [birdscanR](https://github.com/BirdScanCommunity/birdscanR) package, a [website](https://birdscancommunity.github.io/birdscanR/) and readme were created, and continuous testing was implemented. Furthermore, a function to construct a vertical profile time series was implemented, and [numerous](https://github.com/BirdScanCommunity/birdscanR/commits/develop/?since=2025-05-12&until=2025-05-16) other improvements were made. In the [getRad](https://github.com/aloftdata/getRad) package, functionality to download polar volume data from the United States was added so that now [seven](https://aloftdata.github.io/getRad/articles/supported_countries.html) countries are covered, including metadata. Vertical profile time series can now be loaded directly from [aloft](https://aloftdata.eu/) and the [RMI](https://www.meteo.be/services/birdDetection/#/?lang=en_), the behaviour of `get_pvol` and `get_vpts` is synchronized, and documentation was improved. These updates will be released to CRAN soon. Smaller updates were made to the [bioRad](https://github.com/adokter/bioRad) and [birdR](https://gitlab.com/uva_ibed_ame/robin_radar/birdar) package, and the [NAAVRE](https://naavre.net/) environment was explored to create a pipeline for processing radar data. The sprint allowed us to communicate directly, so many questions and discussions could be efficiently resolved.
