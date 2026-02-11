---
title: New data available on the Aloft data portal
description: VPTS data were added for radars in Greece, Hungary, Iceland, Ireland, Lithuania, Malta, and Romania.
background: /assets/backgrounds/2026-02-11-aloft-new-countries.png
author: Peter Desmet
tags: [WP1, weather radar, open data]
toc: true
---

EUMETNET has recently updated the list of OPERA member countries that grant access to single site radar data and data products. Cyprus, Greece, Hungary, Iceland, Ireland, Latvia, Lithuania, Malta, Romania, and Serbia have joined the agreement. Israel has left.

As with all countries in the agreement, PVOL data (if available) are processed by BALTRAD to VPTS data. Those **VPTS data** are subsequently synchronized to the [Aloft data portal](https://aloftdata.eu/browse/). See [Desmet et al. (2025)](https://doi.org/10.1038/s41597-025-04641-5) for more information on the process. Data became available on **2025-12-09** for most of the new countries.

## Additional countries

You can explore the new data in [CROW](https://crow.aloftdata.eu/#/). We also enabled access to new radars from existing countries ([dksam](https://crow.aloftdata.eu/#/?radar=dksam), [ptflr](https://crow.aloftdata.eu/#/?radar=ptflr), [ptsmg](https://crow.aloftdata.eu/#/?radar=ptsmg), [sevax](https://crow.aloftdata.eu/#/?radar=sevax)) ([aloftdata/crow#21](https://github.com/aloftdata/crow/pull/21)).

Country | Radars with data
--- | ---
Cyprus | no data yet
Greece | [grand](https://crow.aloftdata.eu/#/?radar=grand)
Hungary | [hubud](https://crow.aloftdata.eu/#/?radar=hubud), [huhar](https://crow.aloftdata.eu/#/?radar=huhar), [hunap](https://crow.aloftdata.eu/#/?radar=hunap), [hupog](https://crow.aloftdata.eu/#/?radar=hupog), [husze](https://crow.aloftdata.eu/#/?radar=husze)
Iceland | [isbjo](https://crow.aloftdata.eu/#/?radar=isbjo), [iskef](https://crow.aloftdata.eu/#/?radar=iskef), [isska](https://crow.aloftdata.eu/#/?radar=isska)
Ireland | [iesha](https://crow.aloftdata.eu/#/?radar=iesha)
Latvia | no data yet
Lithuania | [ltlau](https://crow.aloftdata.eu/#/?radar=ltlau), [ltvil](https://crow.aloftdata.eu/#/?radar=ltvil)
Malta | no data yet
Romania | [robar](https://crow.aloftdata.eu/#/?radar=robar), [robob](https://crow.aloftdata.eu/#/?radar=robob), [robuc](https://crow.aloftdata.eu/#/?radar=robuc), [rocra](https://crow.aloftdata.eu/#/?radar=rocra), [romed](https://crow.aloftdata.eu/#/?radar=romed), [roora](https://crow.aloftdata.eu/#/?radar=roora), [rotim](https://crow.aloftdata.eu/#/?radar=rotim)
Serbia | no data yet

## Radar metadata update

As part of this update, we synchronized [radar metadata](https://aloftdata.eu/radars/) from the source files maintained by OPERA ([aloftdata/aloftdata.eu#22](https://github.com/aloftdata/aloftdata.eu/pull/22)). Five radar stations have changed codes:

Location | Previous code | Current code | Year(s) of change
--- | --- | --- | ---
Puntijarka | HRZAG | [HRPUN](https://aloftdata.eu/radars/#hrpun) | 2021/2024
Sierra de Fuentes (Caceres) | ESBAD | [ESSFT](https://aloftdata.eu/radars/#essft) | 2023/2025
Corbera (Barcelona) | ESBAR | [ESGLD](https://aloftdata.eu/radars/#esgld) | 2023/2025
Torrejon de Velasco (Madrid) | ESMAD | [ESTJV](https://aloftdata.eu/radars/#estjv) | 2023/2025
Alhaurin el Grande (Malaga) | ESMAL | [ESAHR](https://aloftdata.eu/radars/#esahr) | 2023/2025

See [Table 2](https://www.nature.com/articles/s41597-025-04641-5/tables/2) in Desmet et al. (2025) for previous code changes.

## Data access

Use the [getRad R package](https://aloftdata.github.io/getRad/) to access the new data and metadata. As always, beware of the [caveats](https://aloftdata.eu/faq/#data-quality).

``` r
library(getRad)
library(dplyr, warn.conflicts = FALSE)

# Get VPTS data
get_vpts(radar = "robar", datetime = "2026-02-01", source = "baltrad")
#>                    Irregular time series of vertical profiles (class vpts)
#> 
#>            radar:  robar 
#>       # profiles:  263 
#> time range (UTC):  2026-02-01 00:00:00 - 2026-02-01 21:45:00 
#>    time step (s):  min: 0     max:  900

# Get radar metadata
wr <- get_weather_radars()
wr |> filter(country == "Romania") |> select(radar, location)
#> # A tibble: 8 × 3
#>   radar location             geometry
#>   <chr> <chr>             <POINT [°]>
#> 1 robar Barnova   (27.58255 47.01184)
#> 2 romed Medgidia  (28.25059 44.24336)
#> 3 robob Bobohalma (24.22523 46.36022)
#> 4 rotim Timisoara (21.25773 45.77174)
#> 5 roora Oradea    (21.94289 47.09218)
#> 6 robuc Bucuresti (26.07735 44.51267)
#> 7 rocra Craiova   (23.86743 44.31029)
#> 8 roopa Oradea          (21.94 47.09)
```
