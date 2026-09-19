# Meridian Intelligence
*An intelligence platform that turns scattered, fast-moving information into a clear, connected picture — for faster research and better-informed decisions.*

🔗 Live: [meridianintel.nl](https://meridianintel.nl/) · 🌐 Portfolio: [yassinc.nl](https://yassinc.nl/) 

![Meridian Intelligence — Map View](assets/meridian-map-view.png)


## Overview

Meridian Intelligence pulls together many disparate data sources — geospatial feeds, official registers and other intelligence sources — and resolves them into a single, connected picture. Instead of a pile of disconnected feeds, everything becomes part of one shared **entity model**: people, organisations, locations and events, with the evidence and relationships that link them.

On top of that model, analysts can search across every source at once, follow entities of interest, replay how a situation developed over time, and build a case from the signals that matter. A live, map-based view is one window onto this; investigations, timelines and watchlists are others. The goal throughout is the same: make complex, fast-moving information legible so users can research faster and decide better.

## Key features

- **Unified data sources** — geospatial feeds, official registers and custom datasets are ingested, normalised and managed from one place, each an independently toggleable source.
- **Connected entity model** — heterogeneous sources are resolved into shared entities (people, organisations, locations, events) with the relationships and evidence that connect them, so one view can draw on many sources at once.
- **Investigations** — turn scattered signals into a structured case: an investigation graph, workflow, timeline and evidence trail, with exportable reports.
- **Live map layers** — incidents, traffic flow and tracked objects render as separate, toggleable layers, with a legend and per-source visibility controls.
- **Temporal playback** — replay how a situation evolved over a chosen time window, rather than only seeing the current snapshot.
- **Geofences & alerts** — draw a zone on the map and get notified when tracked activity enters or leaves it.
- **Watchlists & anomaly detection** — flag entities of interest and surface unusual patterns automatically, with alerting and e-mail digests.
- **Global cross-entity search** — one search box across every ingested source and entity type, backed by dedicated search indexes.
- **Resilient ingestion** — sources are pulled through a queued pipeline with automatic retries and dead-letter monitoring, so one flaky feed never stalls the rest.
- **Source status at a glance** — a status bar surfaces the latest source update, the number of loaded reports, and overall system health.

## Architecture

Meridian is a full-stack system with a geospatial data backbone and a shared entity model at its core:

- **Frontend** — Next.js 16, React 19, TypeScript 5, Tailwind CSS v4
- **Backend** — Spring Boot 4 (Java 21), exposing the API and orchestrating data
- **Spatial data** — PostgreSQL + PostGIS for geospatial storage and queries (geofences, playback geometry, spatial indexing)
- **Entity model** — a layered ontology that normalises heterogeneous sources into shared entities, relationships and evidence
- **Ingestion** — Python / FastAPI services pull and normalise external sources (e.g. NDW traffic, OpenSky aviation, satellite detection, official registers)
- **Messaging** — RabbitMQ for asynchronous processing, retries and dead-letter handling between components
- **Delivery** — Dockerised services, built and shipped through an automated CI/CD pipeline (GitHub Actions → container registry → server) with isolated compose stacks per deployment

## Tech stack

`Next.js` · `React` · `TypeScript` · `Tailwind CSS` · `Spring Boot` · `Java` · `PostgreSQL/PostGIS` · `RabbitMQ` · `Python/FastAPI` · `Docker` · `GitHub Actions`

## A note on the code

This repository is a case study. Meridian's source code is intentionally private because the platform includes security-sensitive capabilities. I'm happy to walk through the architecture and technical decisions in detail — reach out via [yassinc.nl](https://yassinc.nl/).
