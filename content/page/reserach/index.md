---
title: Research
lastmod: 2026-10-28
menu:
    main:
        weight: 2
        params:
            icon: atom
comments: false
---

I use **remote sensing, GeoAI, and geospatial analysis** to study the built environment and environmental change. My current work connects building footprints, elevation, and aerial imagery with open data and interactive tools.

## Building footprints and open data

**US Building Footprint (USBF)** is my main research project. I develop methods for selective refinement of GlobalBuildingAtlas outlines using aerial imagery, signed elevation, and model evidence. The published six-state update contains **25.1 million buildings**, retaining original geometry, source heights, stable identifiers, and edit provenance.

![Aerial imagery and building-boundary comparisons](/images/usbf-boundaries.png)

*Local boundary proposals from the September 2026 research version; the methods post reports the corresponding evaluation.*

[Project overview](/projects/usbf/) · [Dataset](https://source.coop/opengeos/us-buildings) · [Code](https://github.com/Feng96/USBF_src) · [Methods and experiments](/p/building-footprint-extraction/)

## Geospatial tools: US Buildings

I designed and built **US Buildings**, a browser workspace for exploring USBF and comparison inventories. It brings together footprint inspection, available-height 3D display, local data import, scoped analysis, and map and data export.

[Open US Buildings](https://feng96.github.io/USBF_site/) · [Website source](https://github.com/Feng96/USBF_site)

## From footprints to LoD2 roof geometry

I am exploring roof reconstruction using NAIP imagery and 3DEP LiDAR. Recent experiments examine canopy contamination, roof-support preservation, and local geometric correction. These are small-scale research results; independent roof-geometry evaluation remains an important next step.

[Interactive experiments](https://feng96.github.io/research-daily/lod2/) · [Method comparison](https://feng96.github.io/research-daily/lod2/paper/)

## Building geometry and energy modeling

During my work with the National Building Energy Model team at Oak Ridge National Laboratory, I integrated and standardized building-footprint datasets for AutoBEM and investigated how footprint area and geometry affect simulated energy use. This connects the quality of remote sensing products to their downstream use.

## Environmental remote sensing

Earlier work used GRACE and MODIS observations to examine the spatial mismatch between water resources and grain-planting changes in China, and Landsat time series to study fine-scale human disturbance. These projects continue to shape my interest in connecting spatial data to environmental questions.

[Publications](/publications/) · [CV and resume](/cv/) · [Research Daily](https://feng96.github.io/research-daily/)
