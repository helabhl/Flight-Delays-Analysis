# Flight Delays Analysis (2024)

This project provides a comprehensive analysis of flight delay data from 2024. It utilizes **R** and **Quarto** to explore various aspects of flight delays, including their causes, seasonality, temporal dynamics, and airline performance.

## � Dataset

The analysis is based on the `flight_2024.csv` dataset, sourced remotely. It contains flight records for the year 2024 with the following key variables:

*   **Temporal**: `year`, `month`, `day_of_month`, `day_of_week`, `fl_date`.
*   **Carrier & Flight**: `op_unique_carrier`, `op_carrier_fl_num`.
*   **Origin & Destination**: `origin`, `dest`, city and state names.
*   **Performance Metrics**: `dep_delay`, `arr_delay` (in minutes), `cancelled`, `diverted`.
*   **Delay Causes**: `carrier_delay`, `weather_delay`, `nas_delay`, `security_delay`, `late_aircraft_delay`.

## 🛠️ Methodology & Analysis

The project is structured into sequential modules, each addressing specific research questions using statistical tests and data visualization.

### 1. Data Loading & Cleaning
*   **File**: [`qmd/01_data_loading_cleaning.qmd`](qmd/01_data_loading_cleaning.qmd)
*   **Process**: Importing data from Google Drive, inspecting structure, handling missing values, and removing duplicated records to ensure data integrity.

### 2. Descriptive Statistics
*   **File**: [`qmd/02_descriptive_statistics.qmd`](qmd/02_descriptive_statistics.qmd)
*   **Focus**: Analyzing the distribution of arrival delays.
*   **Key Insight**: Delay data is strongly right-skewed. We distinguish between minor delays and significant delays (>15 minutes), which are critical for operational assessment.

### 3. Causes & Seasonality
*   **File**: [`qmd/03_causes_and_seasonality.qmd`](qmd/03_causes_and_seasonality.qmd)
*   **Focus**: Investigating *why* and *when* delays occur.
*   **Methods**:
    *   Comparison of internal (carrier, late aircraft) vs. external (weather, security) causes.
    *   **Kruskal-Wallis Test**: Confirmed significant seasonal differences in delay distributions.
    *   **Spearman Correlation**: Analyzed the relationship between flight volume and delay severity.

### 4. Temporal Dynamics
*   **File**: [`qmd/04_temporal_dynamics.qmd`](qmd/04_temporal_dynamics.qmd)
*   **Focus**: Evolution of delays over time.
*   **Key Insight**: Identified propagation effects where late aircraft delays cascade, correlating strongly with carrier delays. Outlier analysis highlights specific days with extreme systemic disruptions.

### 5. Airline Performance
*   **File**: [`qmd/05_airline_performance.qmd`](qmd/05_airline_performance.qmd)
*   **Focus**: Comparative analysis of carriers.
*   **Key Insight**: Statistical tests reveal significant heterogeneity in on-time performance across different airlines, suggesting distinct operational strategies or constraints.

## 🔑 Key Findings

*   **Operational factors dominate**: Internal issues and late aircraft arrivals are the primary drivers of total delay minutes, outweighing weather or security events.
*   **Seasonality matters**: There are significant monthly variations in delay patterns, driven by demand peaks (Summer/Fall) and weather conditions.
*   **Propagation effects**: Delays are not isolated; they propagate through the network, creating intense disruption episodes.

## 🚀 Usage

This project is built as a Quarto website. To render the full analysis locally:

1.  Ensure you have **R** and **Quarto** installed.
2.  Install required R packages:
    ```r
    install.packages(c("dplyr", "ggplot2", "readxl", "tidyr", "lubridate", "car", "lmtest"))
    ```
3.  Render the project:
    ```bash
    quarto render
    ```
    Or use the provided R script:
    ```r
    source("render-all.R")
    ```

The output will be generated in the `docs/` directory.

## 👤 Author

**Hela Bouhlel**
