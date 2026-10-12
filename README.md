Aviation Accidents Safety Analysis
Project overview
This project explores the severity of recorded aviation accidents to inform an airline/aircraft insurer's assessment of aircraft makes and models. It compares the proportion of occupants seriously or fatally injured and the proportion of accidents resulting in aircraft destruction, separately for aircraft grouped by recorded occupant count.
The analysis uses historical aviation accident data covering 1948–2023, with the assessment restricting the analytical period to 1983 onward. The analysis also examines how weather condition and phase of flight relate to injury severity and aircraft damage.
Business questions
Which aircraft manufacturers have lower mean serious/fatal injury fractions and aircraft destruction rates in the recorded accidents?
Which individual aircraft models appear favorable when sufficient accident observations are available?
How do outcomes differ for accidents with fewer than 20 occupants versus 20 or more?
How are weather conditions and phases of flight associated with accident severity?
Repository contents
File	Description
`Aviation_Accidents_Cleaning.ipynb`	Loads, inspects, filters and cleans the original dataset; creates analytical variables and exports a cleaned CSV.
`Aviation_Accidents_Data_Analysis.ipynb`	Produces grouped summary statistics, visualizations and written interpretation.
`README.md`	Project background, methodology, findings, limitations and usage.
Data source
Aviation accident dataset: Kaggle — Acidentes de Avião até 2023.
Download the original CSV and place it in your local project directory. The original and cleaned CSV files are not included in this repository unless explicitly added.
Methods
Cleaning: Inspect missing values and data types; restrict to records from 1983 onward; apply professional-build filtering; clean manufacturer/model and other relevant fields.
Safety measures: Calculate the fraction of recorded occupants seriously or fatally injured and a binary indicator for destroyed aircraft.
Size comparison: Separate accident records using a 20-occupant threshold.
Manufacturer comparisons: Rank makes by average injury fraction and aircraft destruction rate, with sample-count checks.
Model comparisons: Compare specific aircraft types using at least 10 valid injury observations per type.
Contributing factors: Examine weather condition and phase of flight using summary tables and bar charts for injury and destruction outcomes.
Findings and interpretation
The analysis notebook contains the computed manufacturer/model rankings and plots. The findings should be interpreted jointly: a low average injury fraction alone does not establish that an aircraft is a safer insurance risk if destruction rates are high or the sample size is small.
The exploratory weather analysis indicates that recorded accidents under instrument meteorological conditions (IMC) have more severe outcomes on average than those under visual meteorological conditions (VMC). This is an association within recorded accidents, not proof of causation.
The flight-phase comparison also shows variation in injury severity across phases. Some phase-level estimates are based on relatively small numbers of valid observations and require caution.
Final shortlist: Insert the verified small-aircraft and large-aircraft manufacturer/model recommendations from the analysis notebook after reviewing their injury rates, destruction rates, and sample sizes.
Important limitations
This is an accident-only dataset. It does not contain the number of flights or flight hours by model, so it cannot estimate the overall probability of an accident per flight.
The 20-occupant split is based on occupants recorded in an accident, not certified aircraft seating capacity. A large aircraft carrying fewer than 20 occupants may be classified in the small group. Confirm model capacity before making real-world aircraft-size recommendations.
Filtering to 1983 onward does not prove that a model remains in service today.
Missing injury or damage values and differences in sample sizes may bias group comparisons.
Observed weather and flight-phase associations do not establish causality.
Running the notebooks
Install Python/Jupyter and the required packages:
```bash
   pip install pandas numpy matplotlib seaborn notebook
   ```
Download the dataset and open `Aviation_Accidents_Cleaning.ipynb` in Jupyter Notebook.
Update the CSV path in the cleaning notebook to your local file location, run all cells, and save `AviationData_Cleaned.csv`.
Update the cleaned CSV path in `Aviation_Accidents_Data_Analysis.ipynb` and run all cells.
> **Portability note:** The current notebooks contain local Windows file paths. Update these paths before running on another computer; project-relative paths are recommended for reproducibility.
Assessment deliverables
Completed cleaning notebook (`.ipynb`)
Completed analysis notebook (`.ipynb`)
GitHub repository link containing documentation and analysis
Further improvements
Validate model seating capacities, standardize remaining manufacturer-name variants, quantify uncertainty in rates, and supplement accident records with flight exposure and maintenance data before making underwriting decisions.
