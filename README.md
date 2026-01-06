# Flight Delays Analysis (2024)

This project provides a comprehensive analysis of flight delay data from 2024. It utilizes **R** and **Quarto** to explore various aspects of flight delays, including their causes, seasonality, temporal dynamics, and airline performance.

## 📂 Project Structure

The core analysis is organized into sequential Quarto markdown files located in the `qmd/` directory:

| File | Description |
|------|-------------|
| `qmd/01_data_loading_cleaning.qmd` | **Data Loading & Cleaning**: Initial processing of raw data, handling missing values, and preparing the dataset for analysis. |
| `qmd/02_descriptive_analysis_delays.qmd` | **Descriptive Analysis**: General overview of delay distributions and statistics. |
| `qmd/03_causes_and_seasonality.qmd` | **Causes & Seasonality**: Investigation into why delays happen and how they vary across different times of the year. |
| `qmd/04_temporal_dynamics_and_propagation.qmd` | **Temporal Dynamics**: Analysis of how delays propagate through the network and evolve over time. |
| `qmd/05_airline_level_analysis.qmd` | **Airline Analysis**: Comparative performance analysis of different airlines regarding punctuality. |
| `qmd/presentation.qmd` | **Presentation**: Summary slides of the project findings. |

## 🚀 Usage

This project is built as a Quarto website. To render the full analysis locally:

1.  Ensure you have **R** and **Quarto** installed.
2.  Install required R packages:
    ```r
    install.packages(c("dplyr", "ggplot2", "readxl", "tidyr", "lubridate", "car", "lmtest", "curl", "googledrive"))
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
