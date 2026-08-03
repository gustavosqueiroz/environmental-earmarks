# Brazil's most disaster-hit cities got no environmental earmark money

This is a scrollytelling story about how Brazil's parliamentary earmarks fail to reach the municipalities most exposed to floods and landslides, both the ones the government's own risk models flag as most vulnerable and the ones where disasters actually happened. It was created as a submission for the Lede Program in Data Journalism at Columbia University.

https://gustavosqueiroz.github.io/environmental-earmarks/

## About

Between 2023 and 2026, Brazil's Congress transferred R$ 164 billion in parliamentary earmarks (one of the country's main public-spending instruments). This project cross-referenced every environmental earmark executed in the period with Brazil's official disaster-risk model (AdaptaBrasil) and its official disaster registry (Atlas Digital de Desastres) to check if the money go where the disasters are.

The legislative term opened with the São Sebastião landslides (56 deaths) and was defined by the Rio Grande do Sul floods of 2024, the worst in the country's recorded history. Even after both, environmental earmark money did not follow the evidence.

## Key findings

- Of R$ 164.2 billion in earmarks, just R$ 54.6 million (0.03%) went to environmental measures at the municipal level, reaching 24 of Brazil's 5,570 municipalities
- 1,299 municipalities are classified as high or very high geo-hydrological risk. Only 14 of them received any environmental earmark
- The four municipalities with the maximum possible risk score (Pilõezinhos (PB), Itambé (PE), Água Preta (PE) and Afuá (PA)) received nothing
- Ipojuca (PE) recorded more geo-hydrological disasters than any other city since 2023 (47 events) and received R$ 0
- Among the ten cities with the most disasters since 2023, nine received no environmental earmark; the only exception, Brusque (SC), got R$ 340,000
- 172 municipalities recorded deaths from geo-hydrological disasters since 2023; 165 of them (96%) never received an environmental earmark
- Rio Grande do Sul concentrated 24.8% of the country's disaster events and received 1.9% of the environmental money; Pará, with 6% of the events, received zero for the environment.
- The largest environmental shares went to São Paulo (R$ 75 million, mostly animal protection) and Tocantins (R$ 71 million, accessibility and modernization).

## Data sources

- **Earmarks:** Brazil's federal [Transparency Portal](https://portaldatransparencia.gov.br/) — all parliamentary earmarks (individual, caucus and special transfers) with executed values, 2023-2026
- **Environmental classification:** the 97 environmental budget action codes compiled by the [Institute for Socioeconomic Studies (Inesc)](https://inesc.org.br/), covering disaster-risk management and climate mitigation/adaptation
- **Risk scores:** [AdaptaBrasil](https://sistema.adaptabrasil.mcti.gov.br/) (Ministry of Science and Technology), landslide and flood risk indices per municipality, 2015 model
- **Disaster events and deaths:** [Atlas Digital de Desastres](https://atlasdigital.mdr.gov.br/) (Ministry of Regional Development), civil-defense reports since 1991

## Methodology

The process included:
- reading the raw earmarks CSV
- defining the Inesc action-code
- pulling risk scores and municipal boundaries from AdaptaBrasil's API
- filtering the Atlas to five geo-hydrological event types (floods, flash floods, waterlogging, mass movements and heavy rainfall)
- averaging the two risk indices into a single score per municipality, and matching all three sources by official IBGE code.

Grouping was done by IBGE code only.

## Repository contents

- `index.html` — the website
- `*.ipynb` — data workflow
- `data/` — processed CSVs and GeoJSON files behind every chart and map

Raw source files (the Transparency Portal CSV, the Atlas spreadsheet, the Inesc PDF and the boundary files) are not included due to size.

## New skills & what could have been different

In this project I got better at producing charts and maps in Flourish, and at building scrollytelling with Jonathan Soma's Scrollama template. I also became more comfortable with data-cleaning and analysis strategies in pandas.

With more time, though, I would have used D3 for the maps (I wasn't happy with how they turned out). I would also have investigated the cited cities more deeply: what events hit them, what was promised, and what was never delivered. And I would like to look into the earmarks that did flow, and into which lawmakers distributed them.

Site based on the scrollytelling template by Jonathan Soma: https://github.com/jsoma/page-templates/
