# KALA KO BA UULAN?!

### An Academic Research Website on Anticipating Meteorological Forecast Errors

**Research Title:** *Autocorrelation-Aware Evaluation of Entropy-Based Feature Spaces for Anticipating Meteorological Forecast Errors in Philippine Urban Environments, with Emphasis on Approaches from Information Theory and Topological Data Analysis*

---

## About the Project

**KALA KO BA UULAN?!** is an undergraduate research project investigating whether information-theoretic and topological features extracted from historical meteorological observations can help anticipate the magnitude of numerical weather prediction (NWP) errors.

Weather forecasts support everyday decision-making, disaster preparedness, and climate-sensitive activities. However, numerical weather prediction systems are subject to uncertainty arising from atmospheric complexity, imperfect initial conditions, and limitations in numerical modeling.

Forecast verification allows us to assess how accurately a forecasting system performed, but it is generally retrospective. This study explores a complementary approach: examining whether characteristics of recent meteorological time series can provide useful information about subsequent forecast errors.

This repository contains an academic website presenting the study's background, research question, methodology, feature extraction framework, model comparisons, and expected contributions.

## Research Objectives

The study aims to:

1. Describe the temporal characteristics of selected meteorological variables and their corresponding forecast errors.
2. Extract entropy-based and conventional statistical features from rolling historical observation windows.
3. Examine the relationships between extracted features and subsequent absolute forecast errors.
4. Develop time-series regression models using different predictor configurations.
5. Evaluate whether entropy-based features provide incremental predictive information beyond conventional statistical features and baseline models.

## Study Scope

| Component | Description |
|---|---|
| Study location | Quezon City, Philippines |
| Study period | January 1, 2022 to October 26, 2026 |
| Meteorological variables | Air temperature, relative humidity, and precipitation |
| Forecast lead time | 72 hours |
| Historical observation window | 672 consecutive hours (28 days) |
| Primary response | Pointwise absolute forecast error |
| Primary modeling approach | ARIMAX (dynamic regression with ARIMA errors) |

The forecast error is defined as:

\[
AE_{v,t} = |O_{v,t} - F^{(72)}_{v,t}|
\]

where:

- \(O_{v,t}\) is the observed value of variable \(v\) at valid time \(t\).
- \(F^{(72)}_{v,t}\) is the corresponding forecast issued 72 hours before valid time \(t\).
- \(AE_{v,t}\) is the absolute forecast error.

## Methodology

### 1. Data Preparation

Meteorological observations and archived forecasts are aligned according to location, variable, forecast initialization time, valid time, and forecast lead time.

DOST-PAGASA data are the primary intended source. If the required archived observations and forecasts are unavailable, Open-Meteo historical weather data and JMA GSM Day 3 forecasts serve as the proposed fallback.

**Data interpretation note:** When model-based historical reference values are used instead of direct station observations, the resulting discrepancies must not be interpreted as direct verification against observed atmospheric conditions.

### 2. Rolling-Window Feature Extraction

A 28-day historical window containing 672 hourly observations is used to characterize the recent behavior of each meteorological variable.

Features are extracted using two broad approaches:

- **Conventional statistical features:** Descriptors of central tendency, variability, trend, and temporal dependence.
- **Entropy-based features:** Measures of complexity, uncertainty, and temporal organization.

### 3. Entropy-Based Feature Families

The study examines five entropy approaches:

| Feature family | Analytical focus |
|---|---|
| Shannon Entropy | Distributional uncertainty |
| Sample Entropy | Temporal regularity and complexity |
| Permutation Entropy | Ordinal patterns and temporal structure |
| Spectral Entropy | Distribution of power across frequencies |
| Persistent Entropy | Topological characteristics of data representations |

Persistent Entropy is evaluated separately for the zeroth and first homology dimensions (H0 and H1).

### 4. Predictive Modeling

The study compares different predictor configurations:

- **Baseline:** ARIMA model.
- **Conventional-only:** Conventional statistical features.
- **Entropy-only:** Entropy-based features.
- **Combined:** Conventional and entropy-based features.

ARIMAX models are used to evaluate whether the extracted features contribute useful information to the prediction of subsequent absolute forecast errors.

### 5. Model Evaluation

Model performance is evaluated using chronological out-of-sample validation to preserve temporal ordering and reduce information leakage.

The evaluation metrics include:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Coefficient of Determination (R²)

The comparison focuses on whether entropy-based representations improve predictive performance beyond conventional features and the baseline model.

## Research Contributions

The study explores three principal contributions:

**Forecast-error anticipation**

Investigates whether recent meteorological time-series characteristics can help anticipate subsequent forecast discrepancies.

**Information-theoretic feature evaluation**

Assesses the predictive value of multiple entropy-based representations relative to conventional statistical descriptors.

**Topological data analysis**

Examines whether Persistent Entropy provides additional predictive information beyond established entropy measures and conventional features.

## Scope and Limitations

The findings are limited to the selected study location, meteorological variables, forecasting system, and fixed forecast lead time.

Additional limitations include:

- Availability and quality of archived forecast and observation data.
- Sensitivity of entropy estimates to parameter selection and computational settings.
- Potential serial dependence among temporally adjacent observations.
- The ability of ARIMAX models to represent nonlinear relationships and complex interactions.
- Limited generalizability beyond the study's specified setting.

This is a predictive study. It does not establish causal relationships, identify the physical causes of forecast errors, or directly improve the underlying numerical weather prediction system.

## Website

This repository includes a standalone, browser-based academic website presenting the research project.

### Run Locally

1. Download or clone this repository.
2. Open the website's HTML file in a web browser.

No package installation or backend server is required.

### Deploy with GitHub Pages

1. Upload the website file to the repository.
2. For the simplest GitHub Pages setup, name the main HTML file `index.html` and place it in the repository root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select the `main` branch and the `/ (root)` folder.
6. Save the settings and wait for GitHub Pages to publish the site.

## Technologies

- HTML5
- CSS3
- JavaScript

## Research Status

This repository presents the research project and its methodological framework. It should not be interpreted as a repository of completed empirical findings unless corresponding analyses and results are separately documented and released.

## Author

**John Aaron B. Llobrera**  
BS Statistics  
University of the Philippines Los Baños

---

*Research documentation and website content are subject to revision as the study progresses and the final methodology is established.*
