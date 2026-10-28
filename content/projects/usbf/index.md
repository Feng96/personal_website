---
title: "US Building Footprint (USBF)"
description: "Open building footprints, traceable geometry refinement, and a browser workspace for exploring the built environment."
slug: "usbf"
date: 2026-10-28
lastmod: 2026-10-28
image: "usbf-boundaries.png"
comments: false
---

[Explore the map](https://feng96.github.io/USBF_site/) · [Download data](https://source.coop/opengeos/us-buildings) · [Reproducible code](https://github.com/Feng96/USBF_src) · [Research Daily](https://feng96.github.io/research-daily/)

I develop **USBF**, a building-footprint dataset and processing workflow that brings together aerial imagery, elevation, and existing building inventories. The goal is to make local geometry changes inspectable while preserving useful information from the source data.

## Published data

The completed six-state update covers **Alabama, Arizona, Arkansas, California, Colorado, and Connecticut**. It contains **25,092,517 buildings**, including **913,169 with recorded geometry modifications**. A recorded modification describes an action; it does not by itself establish improved accuracy.

The broader public catalog contained **150,261,726 records in 3,522 files** in the October 27, 2026 publication snapshot. It combines the updated six-state product with existing GBA-based records elsewhere. Those catalog totals do not mean that every building has undergone the new refinement workflow. Regional production is continuing.

Downloads use GeoParquet and retain building identifiers, original and final geometry, edit provenance, source attributes, and coverage information. Published heights are **inherited GBA attributes**; this workflow does not estimate new heights. Missing height values remain missing.

[Source Cooperative dataset](https://source.coop/opengeos/us-buildings) · [Current publication manifest](https://data.source.coop/opengeos/us-buildings/USBF_v1/manifest.json)

## How the workflow works

RGB–height segmentation models propose local changes to existing GlobalBuildingAtlas footprints. Image boundaries, model evidence, elevation availability, and neighbor constraints help determine whether a proposed change is accepted. Keeping the source geometry alongside the result makes changes traceable.

The released minimal workflow includes frozen B0/B1 checkpoints, real example inputs, checksummed downloads, local inference, and paired geometry evaluation. The verified small example and fixed-geometry evaluation replay have different scopes from complete national regeneration or historical model retraining.

[Source and releases](https://github.com/Feng96/USBF_src) · [Earlier methods and experiment notes](/p/building-footprint-extraction/)

## US Buildings: use the data in a browser

I designed and built [US Buildings](https://feng96.github.io/USBF_site/), a browser GIS that connects to the current USBF publication. It supports footprint and attribute inspection, comparison sources, available-height LoD1 display, source-data export, and experimental roof-model browsing. Recent workspace tools add local and URL imports, scoped statistics and spatial analysis, drawing, coordinate conversion, and map export.

The viewer loads bounded neighborhoods for interactive use. Statistics describe the loaded source records and the chosen analysis scope. Experimental LoD2 models remain a small research collection.

![US Buildings browser workspace](/images/us-buildings-workspace.png)

*Earlier workspace view with the GBA footprints and heights comparison layer.*

## Research context

My broader work investigates how imagery, elevation, and geometry can support a useful building inventory, and how footprint choices affect downstream applications such as building energy modeling. Current roof-reconstruction experiments extend this direction toward LoD2 geometry and require further independent validation.

[Roof experiments](https://feng96.github.io/research-daily/lod2/) · [Dated research records](https://feng96.github.io/research-daily/)

Dataset counts above are a dated snapshot. Use the live manifest for current inventory totals, and consult the dataset's component-specific attribution and license terms when reusing data.
