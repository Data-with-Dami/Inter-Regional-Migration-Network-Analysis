# Network Analysis of Inter-Regional Migration Patterns in England & Wales

## Overview
This project applies network analysis to explore inter-regional migration 
patterns across 10 regions in England and Wales using 2021 Census and NOMIS 
origin-destination data. By modelling regions as nodes and migration flows as 
weighted directed edges, the analysis identifies dominant migration hubs, 
bridge regions, isolated communities, and the structural patterns that 
underpin the UK's North-South divide.

The findings carry direct implications for government policy on regional 
inequality, housing, and economic development across England and Wales.

---

## Key Findings
- London and the South-East dominate the migration network across every 
  measure such as attraction power, sending power, and bridging capacity.
- London is the only net migration loser despite being the most populous 
  region, possibly driven by high housing and living costs pushing residents outward.
- Two distinct migration communities were identified using the Louvain 
  algorithm, providing quantitative confirmation of the North-South divide.
- Wales clusters behaviourally with northern England despite its geographic 
  position, reflecting shared economic marginalisation rather than proximity.
- Yorkshire & the Humber (betweenness centrality: 0.2222) is the sole 
  northern bridge region, its weakening would effectively split the national 
  migration network into two disconnected components.
- The North-East recorded zero betweenness centrality, confirming it as the 
  most isolated and peripheral region in the national migration network.

---

## Network Visualisation

![Migration Network Graph](gephi_network_graph<img width="1024" height="768" alt="gephi_network_graph" src="https://github.com/user-attachments/assets/a832d079-93a8-44ff-9e7e-d5a42f966a45" />
)

*Directed weighted network of inter-regional migration flows across England 
and Wales. Node size reflects weighted in-degree centrality (migration 
attraction power). Node colour indicates community membership detected via 
the Louvain algorithm — green nodes form the southern migration corridor 
(London, South-East, East of England, South-West) and pink nodes form the 
northern cluster (North-West, Yorkshire & the Humber, West Midlands, East 
Midlands, North-East, Wales). Edge thickness represents migration volume.*

---

## Tools & Technologies
| Tool | Purpose |
|------|---------|
| SAS Studio | Data cleaning, network modelling, statistical analysis |
| PROC NETWORK | Network construction, centrality analysis, community detection |
| PROC SGPLOT | Data visualisation (bar charts, bubble charts, heatmaps) |
| PROC SQL | Flow aggregation and data summarisation |
| SAS Viya | Interactive dashboard development |
| Gephi | Network graph visualisation |

Note: SAS code is available in this repository as `migration_network_analysis.txt`. 
Open in SAS Studio or any text editor to view and run.
---

## Data Sources
All data is publicly available and sourced from NOMIS official census and 
labour market statistics:

- **Edge dataset:** NOMIS Origin-Destination Migration Data (Region) — 
  captures inter-regional migration flows from the 2021 Census
- **Node dataset:** NOMIS 2021 Census — Usual Residents in Househo[migration_network_analysis.txt](https://github.com/user-attachments/files/28200914/migration_network_analysis.txt)

lds and 
  Communal Establishments, used to represent regional population sizes

To replicate this project, download both datasets from 
[NOMIS](https://www.nomisweb.co.uk/) and update the file paths in the SAS 
code to match your local directory.

---

## Methodology

### Network Structure
| Feature | Description |
|---------|-------------|
| Nodes | 10 regions (England & Wales) |
| Edges | 90 directed migration flow connections |
| Network type | Directed |
| Edge weight | Number of migrants |

### Analytical Approach
1. **Data cleaning** — Raw NOMIS data was cleaned, column names standardised, 
   irrelevant rows removed, and region codes assigned for network compatibility
2. **Network construction** — Built using PROC NETWORK in SAS Studio, 
   modelling directed weighted edges between all regional pairs with 
   self-links removed
3. **Centrality analysis** — Degree, betweenness, closeness, and eigenvector 
   centralities calculated based on edge weights to identify the most 
   influential nodes
4. **Community detection** — Louvain algorithm applied to detect regional 
   migration communities by maximising modularity
5. **Visualisation** — Migration flows visualised using heatmaps, bubble 
   charts, bar charts in SAS Viya, and a full network graph in Gephi


   ---

## Policy Implications
The analysis reveals a structurally fragile national migration network 
over-concentrated around London and the South-East. Key recommendations 
include targeted investment in northern connectivity, particularly the 
North-East and Wales which are dangerously isolated from national migration 
flows, strengthening Yorkshire's bridging role through infrastructure 
investment, developing the North-West as a viable secondary hub, and 
addressing housing affordability in London to reduce forced outmigration.

---

## Author
Damilola Ajibade | MSc Data Science, University of Wolverhampton  
[LinkedIn](https://linkedin.com/in/your-linkedin-url) | 
[GitHub](https://github.com/your-github-username)
