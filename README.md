# Physics Data Explorer – CERN Open Data (CMS Dimuon Sample)

This repository contains a small analysis of real proton–proton collision data
from the **CMS experiment** at CERN, using the public dimuon dataset  
`Dimuon_DoubleMu.csv` from the [CERN Open Data portal](https://opendata.cern.ch/record/545).

The goal of this project is to demonstrate basic high-energy physics data analysis
using the standard Python scientific stack:

- **NumPy** for numerical work  
- **pandas** for data handling  
- **Matplotlib** and **Seaborn** for visualisation  

---

## Notebook

Main notebook:

- `Physics_Data_Explorer_CERN_Open_Data.ipynb`

The notebook is written as a step-by-step mini analysis and includes:

1. **Data loading**
   - Load the CSV file `Dimuon_DoubleMu.csv` from CERN Open Data into a pandas DataFrame.
   - Inspect the structure, data types, and first few events.

2. **Data cleaning**
   - Drop rows with missing values.
   - Apply simple quality cuts:
     - Require positive energy (`E1`, `E2`) and transverse momentum (`pt1`, `pt2`) for both muons.

3. **Summary statistics**
   - Compute mean, median, and standard deviation for:
     - Muon energies: `E1`, `E2`
     - Muon transverse momenta: `pt1`, `pt2`
     - Dimuon invariant mass: `M`
   - Cross-check results using both **pandas** and **NumPy**.

4. **Visualisation**  
   Using **Matplotlib** and **Seaborn**:

   - **Histograms**
     - Compare `E1` vs `E2` energy distributions.
     - Compare `pt1` vs `pt2` transverse momentum distributions.
     - Plot the dimuon invariant mass `M` to look for structures (e.g. Z-boson region).

   - **Line plot (NumPy running average)**
     - Convert the dimuon mass column to a NumPy array.
     - Compute a running (moving) average using `np.convolve`.
     - Plot raw event-by-event masses together with the smoothed curve.

   - **Scatter plots**
     - `E1` vs `pt1` and `E2` vs `pt2` (full range and zoomed views).
     - Visualise how energy and transverse momentum are related for each muon.

   - **Correlation heatmap**
     - Compute the Pearson correlation matrix for `E1`, `E2`, `pt1`, `pt2`, and `M`.
     - Display it as a Seaborn heatmap to summarise relationships between key variables.

5. **Simple physics interpretation**
   - Discuss the typical energy and momentum scales of the muons.
   - Comment on the shape of the dimuon mass distribution and the region compatible
     with Z→μ⁺μ⁻ decays.
   - Compare muon kinematics in different dimuon mass regions (e.g. low-mass vs
     Z-peak) in a basic way.

6. **Conclusion**
   - Summarise what was learned from the dataset.
   - Outline possible next steps (e.g. fitting the Z peak, background studies,
     or extending to other CMS Open Data samples).

---

## Dataset

- **Source:** CERN Open Data – CMS experiment  
- **Record:** [Dimuon_DoubleMu – Education and outreach dataset](https://opendata.cern.ch/record/545)  
- **File used:** `Dimuon_DoubleMu.csv`

Each row corresponds to one dimuon event, with columns including:

- `E1`, `E2` – energies of muon 1 and muon 2 (GeV)  
- `px1`, `py1`, `pz1`, `pt1`, `eta1`, `phi1` – kinematics of muon 1  
- `px2`, `py2`, `pz2`, `pt2`, `eta2`, `phi2` – kinematics of muon 2  
- `M` – dimuon invariant mass (GeV)  
- Additional event and detector information  

---

## Technologies

- Python 3  
- [NumPy](https://numpy.org/)  
- [pandas](https://pandas.pydata.org/)  
- [Matplotlib](https://matplotlib.org/)  
- [Seaborn](https://seaborn.pydata.org/)  

---

## How to run the notebook

1. **Clone this repository**

   ```bash
   git clone https://github.com/Mahsuba/cern-physics-data-explorer.git
   cd cern-physics-data-explorer
Install dependencies

It is recommended to use a virtual environment, but for a simple test:

bash

`pip install numpy pandas matplotlib seaborn`



Open the notebook

You can run the notebook in:

Jupyter Notebook / JupyterLab

VS Code with the Python & Jupyter extensions

Google Colab by uploading the .ipynb file

Then run the cells from top to bottom to reproduce all results and plots.

## Notes
This project is intentionally kept at an introductory level.
It is not a full physics analysis, but it demonstrates:

Working with real CERN Open Data

Using the Python scientific ecosystem for exploratory data analysis

Producing clear visualisations

Connecting plots to basic physical interpretation

It can be extended with more advanced techniques, such as fitting the dimuon
mass peak to extract the Z boson mass and width, estimating backgrounds, or
incorporating additional CMS Open Data samples.
