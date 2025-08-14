# Calibration-and-Validation-of-Environmental-Low-Cost-Sensors-2025-Group19-
This project aims to monitor the environment by deploying low-cost Internet of Things (IoT) sensors. The core task is to validate the accuracy of these low-cost sensors using high-precision ones. If systematic errors are found, the low-cost sensors will be calibrated to correct their measurement data during operation, ensuring data reliability.
## Repository Structure & File Description
├── 7_9_10.csv<br>
├── co2.csv<br>
├── RH.csv<br>
├── T.csv<br>
├── Calibration.csv<br>
├── Calibration_cleaned.csv<br>
├── Validation.csv<br>
├── validation_cleaned.csv<br>
├── IOT19_Analysis.ipynb<br>
└── IOT19_Calibration&validation.ipynb

### Data Files

-   **`7_9_10.csv`**:
    -   Raw data collected from the **high-precision sensor** on July 9th and 10th, 2025. This serves as the ground truth for calibration.

-   **`co2.csv`, `RH.csv`, `T.csv`**:
    -   Raw data collected from the **low-cost sensor** for the same period (July 9th & 10th, 2025). These files contain measurements for CO2 concentration, relative humidity, and temperature, respectively.

-   **`Calibration.csv`**:
    -   The dataset created after performing time alignment between the high-precision sensor data (`7_9_10.csv`) and the low-cost sensor data (`co2.csv`, `RH.csv`, `T.csv`).

-   **`Calibration_cleaned.csv`**:
    -   The cleaned version of `Calibration.csv` after processing and removing outliers. This is the final dataset used for **training** the calibration models.

-   **`Validation.csv`**:
    -   A separate dataset recorded on July 2nd, 2025. It is used for **validating** the performance of the trained calibration models on unseen data.

-   **`validation_cleaned.csv`**:
    -   The cleaned version of `Validation.csv` after removing outliers.

### Code Files (Jupyter Notebooks)

-   **`IOT19_Analysis.ipynb`**:
    -   **Function**: This notebook contains all the pre-processing steps performed before calibration.
    -   **Details**: It includes the code for data loading, outlier detection and removal, time alignment of sensor data, and exploratory analysis in both the time and frequency domains.
    -   
## Project Workflow

1.  **Data Pre-processing**: Load raw sensor data, handle outliers, and perform time alignment (`IOT19_Analysis.ipynb`).
2.  **Model Training (Calibration)**: Train machine learning models using the cleaned calibration data to map low-cost sensor readings to high-precision sensor readings (`IOT19_Calibration&validation.ipynb`).
3.  **Model Evaluation (Validation)**: Test the trained models on a separate, unseen validation dataset to confirm their accuracy (`IOT19_Calibration&validation.ipynb`).

-   **`IOT19_Calibration&validation.ipynb`**:
    -   **Function**: This notebook contains the core logic for the calibration and validation of the low-cost sensor.
    -   **Details**: It uses the `Calibration_cleaned.csv` dataset to build and train calibration models for CO2, temperature, and relative humidity. Subsequently, it evaluates the models' performance using the `validation_cleaned.csv` dataset to ensure their accuracy and generalizability.
