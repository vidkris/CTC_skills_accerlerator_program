# NOC x CTC Skills Accelerator 2026: Future Leaders Challenges


This repo contains the three challenges:

| # | Challenge | STEM stream | Main data source |
|---|-----------|-------------|------------------|
| 1 | Glider deployment: metadata and ocean temperature | Data Analysis / Oceanography | BODC Deployment Catalogue + ERDDAP |
| 2 | Storm surge: which ports were affected? | Oceanography | NTSLF surge model archive |
| 3 | Breaking the ice | Oceanography | Evolution of Sea Ice Age in the Arctic Ocean |

---

## Repository contents

```
.
├── README.md
├── docs/
│   └── <challenge-briefs>.docx
├── notebooks/
│   └── <challenge-1-notebook>.ipynb
└── data/
    └── <sample-data>.xlsx
```
## [!CAUTION]
### All details of the challenge can be found within the docs folder. A brief outline is show below.
---

## Challenge 1: Glider deployment, metadata and ocean temperature

**Idea:** Ocean gliders collect temperature and depth data for weeks at a time. Students investigate a real glider deployment: who ran it, what instruments it carried, and what its data show.

### Tasks

1. **Explore the metadata.** Use the BODC Deployment Catalogue to record everything about the deployment (who deployed it, instruments fitted, what each instrument measured). Note anything missing or hard to find, and use it to explain why good metadata matters.
2. **Graph the data.** Use ERDDAP's built-in graphing tool to plot temperature vs depth and temperature vs time. Subset to a specific date range so the graphs are readable. Look for a thermocline (the boundary between warmer and colder water), and ask whether temperature changes randomly or in a pattern over days and weeks. Think about how this affects animals living at those depths.
3. **Python extension** (for teams who attended the Python sessions). Export a small subset of the data to CSV, then use Python packages (e.g. `pandas`, `matplotlib`) to plot graphs, including any others the team thinks are of interest.

### Poster should show

- A deployment "fact file": platform, instruments, PI, dates, location.
- At least two clearly labelled graphs of real temperature data.
- A plain-English explanation of patterns found (e.g. thermocline).
- A reflection on missing or unclear metadata and why it matters.

### Key resources

| Focus | Link |
|-------|------|
| BODC Deployment Catalogue | https://platforms.bodc.ac.uk/deployment-catalogue/ |
| BODC ERDDAP server | https://linkedsystems.uk/erddap/index.html |
| Example dataset (Bowmore glider) | https://linkedsystems.uk/erddap/tabledap/Bowmore_712_R.html |
| Run Python with no install | https://colab.research.google.com/ |

### Running the notebook

To run locally:

```bash
pip install pandas matplotlib jupyter
jupyter notebook notebooks/<challenge-1-notebook>.ipynb
```

ERDDAP can return any dataset as CSV by changing the file extension in the URL, which `pandas.read_csv` can read directly. Skip the second row, which holds the units:

```python
import pandas as pd

url = "https://linkedsystems.uk/erddap/tabledap/Bowmore_712_R.csv?time,PRES,TEMP"
data = pd.read_csv(url, skiprows=[1])
```

---

## Challenge 2: Storm surge, which ports were affected?

**Idea:** A storm surge is extra water pushed towards the coast by low pressure and strong winds. The **residual** is the difference between the actual sea level and the level the normal tide alone would give. Students use the NTSLF surge model archive, which compares the model's predictions with tide gauge observations, to work out which ports a real storm affected.

### Tasks

1. **Read about the storm.** Choose a storm and read about its impacts and which parts of the UK it affected. Example: Storm Ciarán (November 2023), where the strongest winds were expected on the southern coasts of England.
2. **Shortlist ports.** List 3-4 ports in the affected area, plus one port well away from the storm as a comparison.
3. **Open the surge model archive.** Choose a port, then the year and month of the storm. Repeat for each port on the shortlist.
4. **Find the most affected port.** Look for where the model and the observations differ most during the storm.
5. **Investigate.** Study that port's data for the storm month, compare with the quiet port, and explain the findings for a non-technical audience.

### Poster should show

- The storm, the areas it affected, and the ports shortlisted.
- The surge plot for the chosen port and a comparison port.
- A plain-English explanation of tide vs surge vs residual.
- Why comparing the model to real observations matters for flood warnings.

### Key resources

| Focus | Link |
|-------|------|
| NTSLF surge model archive (2020 onwards) | https://ntslf.org/storm-surges/surge-model/monthly-surge-plots |
| NTSLF surge model archive (2004-2019) | https://ntslf.org/storm-surges/surge-model/monthly-surge-plots-pre2020 |
| What is a storm surge? | https://ntslf.org/storm-surges/about-storm-surges |
| Example storm (Met Office, Storm Ciarán) | https://www.metoffice.gov.uk/about-us/news-and-media/media-centre/weather-and-climate-news/2023/storm-ciaran-latest |

---

## Notes for challenge setters

- The archive shows **one port at a time**. It does not rank ports or flag the most affected ones, so the brief tells students which region to start from.
- The NTSLF **skew surge history** pages only use data up to 1 January 2013. They are useful for older storms but cannot be used for recent ones such as Storm Ciarán.
- The Met Office Ciarán link is a **forecast written before the storm**. It shows expected winds and warnings, not measured surge impacts.
- Before finalising a brief, check the example dates and ports still return good plots, as external websites can change.

---
---

## Challenge 3: Evolution of sea ice age in the Arctic Ocean


### Idea:
Arctic sea ice supports wildlife (seals, walruses, polar bears, birds) and coastal communities, and its bright surface reflects most incoming sunlight back into space (high albedo), which helps stabilise the global climate. NOC's "Breaking the Ice" portal shows 40 years of change in Arctic sea ice age, from 1984 to 2024. Students explore the data and its metadata, then compare September 1984 with September 2024.

The portal offers three views: by month, year by year, and a 40-year monthly average. The dataset's metadata is at the bottom of the portal.

### Tasks
+ Explore the metadata. Identify the metadata for the portal's sea ice age dataset and explain what it reveals about the data.
+ Find the methods. Identify the scientific methods used to gather sea ice age data.
+ Find the extremes. Identify which years have the least sea ice in the Arctic Ocean, and which month has the most sea ice on average.
### Python extension (for teams who attended the Python sessions).
+ Explore age_of_sea_ice_statistics.csv with pandas and matplotlib. The file holds monthly statistics: the mean and standard deviation of sea ice age by month and year, and the area covered by each age category (0-1, 1-2, 2-3, 3-4 and more than 4 years old). Try plotting how the mean sea ice age changes over time, or how the area in each age category changes. A metadata.txt file explains each column.

+ Compare two Septembers. Compare the sea ice of September 1984 and September 2024, explain how the albedo has changed, and describe the likely impact on the Arctic environment, wildlife and communities.
### Poster should show
+ A brief introduction to the sea ice age dataset, including its metadata.
+ The methods used to gather sea ice age data.
+ The years with the least sea ice, and the month with the most sea ice on average.
+ Findings: the difference in albedo between September 1984 and September 2024, and the impact on the Arctic environment, wildlife and community, with a portal screenshot for each case.
+ Conclusions or key takeaways.
### References to sources.
Key resources
| Focus | Link |
|-------|------|
| "Breaking the Ice" portal (NOC) | https://sap.breakingtheice.noc.ac.uk/ |
| EASE-Grid Sea Ice Age, Version 4 (NSIDC) | https://nsidc.org/data/nsidc-0611/versions/4#anchor-data-access-tools |
| Sea ice: why it matters (NSIDC) | https://nsidc.org/learn/parts-cryosphere/sea-ice/why-sea-ice-matters |


## Notes for challenge setters
+ Challenge 3 refers to age_of_sea_ice_statistics.csv and metadata.txt.
+ Make sure students can reach both (for example by adding them to the repo or linking the portal page that hosts them).
+ Before finalising a brief, check the example dates and ports still return good plots, as external websites can change.
