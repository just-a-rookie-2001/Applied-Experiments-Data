# Applied-Experiments-Data

## Overview (Python)
This Python script generates a synthetic dataset resembling Uber ride data. It uses the `pandas` library for data manipulation, `tqdm` for progress bar visualization, and `Faker` for generating fake personal information. The dataset includes details such as ride IDs, rider names, driver IDs, whether a promotion was used, wait times, ride durations, ride costs, and revenue earned.

## Features
- **Randomized Data**: Ensures a diverse dataset by using random number generation for ride IDs, wait times, and ride durations.
- **Beta Distribution**: Utilizes beta distribution to simulate ride costs, reflecting more realistic variability.
- **Progress Bar**: Includes a progress bar for visual feedback during the dataset creation process.

## Dataset Structure
Each entry in the dataset represents a single ride and includes the following fields:
- `ride ID`: A unique identifier for the ride.
- `rider name`: The name of the rider, generated using `Faker`.
- `driver ID`: A random identifier for the driver (randomly generated from range of 1-0.1(len(sample_size), repeats allowed)).
- `promotion used?`: Indicates if a promotion was used during the ride period (3 possibilities - ‘pre-ctrl’, 'pre-trt', ‘yes’, and ‘no’ - assumption that pre exp data was taken in same length of time, 2 weeks so the total number of rides shows that there was a significant increase due to people adopting the treatment and taking discounted rides).
- `wait time`: The time the rider waited for the ride (random int from 1-30, longer wait times implemented for during experiment to mimic an effect of increased demand).
- `ride duration`: The duration of the ride(random int from 1-30).
- `ride cost`: The cost of the ride, calculated using a formula that includes a beta distribution factor .
- `revenue earned`: The revenue earned from the ride, calculated as a fraction of the ride cost.

---

## Overview (R)
This R project is designed to analyze a synthetic dataset that simulates Uber ride data. The analysis is performed using various R packages to manipulate and model the data, with a focus on understanding the impact of promotions on revenue earned.

## Features
- **Data Import**: Reads the synthetic dataset from a CSV file.
- **Factor Conversion**: Converts the `promotion used?` column to a factor for proper analysis.
- **Treatment Coding**: Creates binary variables for treatment and post-treatment periods.
- **Model Fitting**: Fits linear models to estimate the effect of promotions on revenue.

## Analysis Structure
The analysis includes the following steps:
- **Data Preparation**: The dataset is loaded and prepared for analysis, with necessary transformations.
- **Modeling**: Two linear models are fitted:
  - `did_model`: A model to estimate the effect of treatment and post-treatment on revenue earned.
  - `placebo_did_model`: A placebo model to check for pre-treatment effects.
 
## Results
### Regressiong Modelling
![Screenshot 2024-04-23 at 23 25 51](https://github.com/just-a-rookie-2001/Applied-Experiments-Data/assets/52151660/7b1bfe12-8bf3-4cf1-9598-bcf2d1cf5891)
### Placebo Test
![Screenshot 2024-04-23 at 23 26 25](https://github.com/just-a-rookie-2001/Applied-Experiments-Data/assets/52151660/f843d1dc-ee6d-4e73-bd14-40f787875233)

