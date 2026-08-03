# Brazil's most disaster-hit cities got no environmental earmark money

This is a scrollytelling story about how Brazil's parliamentary earmarks fail to reach the municipalities most exposed to floods and landslides — both the ones the government's own risk models flag as most vulnerable and the ones where disasters actually happened. It was created as a submission for the Lede Program in Data Journalism at Columbia University.

**Live site:** https://YOUR_USER.github.io/YOUR_REPO/

## About

Between 2023 and 2026, Brazil's Congress transferred R$ 164 billion in parliamentary earmarks — one of the country's main public-spending instruments. This project cross-referenced every earmark executed in the period with Brazil's official disaster-risk model (AdaptaBrasil) and its official disaster registry (Atlas Digital de Desastres) to answer one question: does the money go where the disasters are?

The short answer is no. The legislative term opened with the São Sebastião landslides (56 deaths) and was defined by the Rio Grande do Sul floods of 2024, the worst in the country's recorded history. Even after both, environmental earmark money kept missing the map.

## Key findings

- Of R$ 164.2 billion in earmarks, just **R$ 54.6 million (0.03%)** went to environmental measures at the municipal level, reaching **24 of Brazil's 5,570 municipalities**
- **1,299 municipalities** are classified as high or very high geo-hydrological risk. Only **14** of them received any environmental earmark
- The four municipalities with the **maximum possible risk score** — Pilõezinhos (PB), Itambé (PE), Água Preta (PE) and Afuá (PA) — received nothing
- **Ipojuca (PE)** recorded more geo-hydrological disasters than any other city since 2023 (47 events) and received R$ 0
- Among the **ten cities with the most disasters** since 2023, nine received no environmental earmark; the only exception, Brusque (SC), got R$ 340,000
- **172 municipalities** recorded deaths from geo-hydrological disasters since 2023; **165 of them (96%)** never received an environmental earmark
- **Rio Grande do Sul** concentrated 24.8% of the country's disaster events and received 1.9% of the environmental money; **Pará**, with 6% of the events, received R$ 4.6 billion in general earmarks — and zero for the environment
- The largest environmental shares went to **São Paulo** (R$ 75 million, mostly animal protection) and **Tocantins** (R$ 71 million, accessibility and modernization), two states with barely 3% of the recorded events between them

## Data sources

- **Earmarks:** Brazil's federal [Transparency Portal](https://portaldatransparencia.gov.br/) — all parliamentary earmarks (individual, caucus and special transfers) with executed values, 2023-2026
- **Environmental classification:** the 97 environmental budget action codes compiled by the [Institute for Socioeconomic Studies (Inesc)](https://inesc.org.br/), covering disaster-risk management and climate mitigation/adaptation
- **Risk scores:** [AdaptaBrasil](https://sistema.adaptabrasil.mcti.gov.br/) (Ministry of Science and Technology), landslide and flood risk indices per municipality, 2015 model
- **Disaster events and deaths:** [Atlas Digital de Desastres](https://atlasdigital.mdr.gov.br/) (Ministry of Regional Development), civil-defense reports since 1991

## Methodology

The full workflow is documented in the Jupyter notebook. The process included reading the raw earmarks CSV, extracting the Inesc action-code table from a PDF, pulling risk scores and municipal boundaries from AdaptaBrasil's API, filtering the Atlas to five geo-hydrological event types (floods, flash floods, waterlogging, mass movements and heavy rainfall), averaging the two risk indices into a single score per municipality, and matching all three sources by official IBGE code.

Municipality names in the Atlas appear under variant spellings, so all grouping was done by IBGE code only. Of the 269 environmental earmarks in the period, 239 (about 89%) were allocated at the state or federal level and could not be traced to a specific municipality; municipal-level analysis uses the 30 that could. The notebook reflects the actual reporting process, including dead ends and fixes — such as no-data municipalities silently falling into the highest risk bracket, and name-based grouping splitting the same city into multiple rows.

## Repository contents

- `index.html` — the website
- `*.ipynb` — the full data workflow and analysis
- `data/` — processed CSVs and GeoJSON files behind every chart and map
- `img/` — header photo and the waffle-chart images used in the scrollytelling

Raw source files (the Transparency Portal CSV, the Atlas spreadsheet, the Inesc PDF and the boundary files) are not included due to size; the links above point to each original source.

## New skills & what could have been different

The main goal of this project was to practice a full data-journalism pipeline: messy public data, a real hypothesis, and a published story. It pushed me further into pandas and geopandas, working with government APIs, extracting tables from PDFs, and building choropleth maps from raw GeoJSON. All charts and maps were built in Flourish, and the scrollytelling uses Jonathan Soma's Scrollama template. I used AI to help polish some of the JavaScript and HTML, and going back through that code to understand it was part of the learning.

With more time, I would investigate who wrote the earmarks that did flow — the São Paulo animal-protection and Tocantins modernization amendments raise obvious follow-up questions — and interview officials in the zero-funding municipalities about what prevention work is going undone.

Site based on the scrollytelling template by Jonathan Soma: https://github.com/jsoma/page-templates/
