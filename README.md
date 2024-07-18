# Streamflow Prediction using LSTM

This project aims to predict the streamflow for various river basins in Chile using Long Short-Term Memory (LSTM) neural networks. The prediction model is trained on historical temperature, precipitation, and streamflow data, along with static catchment attributes. The model's performance is evaluated using metrics like Root Mean Squared Error (RMSE) and Nash-Sutcliffe Efficiency (NSE).

## Table of Contents

- [Project Structure](#project-structure)
- [Data Description](#data-description)
- [Preprocessing](#preprocessing)
- [Model Architecture](#model-architecture)
- [Training and Evaluation](#training-and-evaluation)
- [Results](#results)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Project Structure

```
streamflow-prediction/
│
├── data/
│   ├── catchment_attributes.csv
│   ├── tmean_cr2met_C_day_cleaned.csv
│   ├── precip_cr2met_mm_day.csv
│   └── q_m3s_day.csv
│
├── src/
│   ├── preprocess.py
│   ├── model.py
│   ├── train.py
│   └── evaluate.py
│
├── notebooks/
│   ├── data_analysis.ipynb
│   └── model_training.ipynb
│
├── README.md
├── requirements.txt
└── LICENSE
```

## Data Description

- `catchment_attributes.csv`: Contains static attributes for each gauge such as area, elevation, and land cover.
- `tmean_cr2met_C_day_cleaned.csv`: Contains daily mean temperature data.
- `precip_cr2met_mm_day.csv`: Contains daily precipitation data.
- `q_m3s_day.csv`: Contains daily streamflow data.

The data is collected from different gauge basins across Chile.

## Preprocessing

1. **Normalization**: The temperature, precipitation, and streamflow data are normalized to ensure that the model performs well.
2. **Data Splitting**: The data is split into training, validation, and test sets.
3. **Windowing**: The data is segmented into windows of a fixed size to capture temporal dependencies.

## Model Architecture

The LSTM model takes in a sequence of temperature and precipitation data along with static attributes for each gauge. The architecture is as follows:

- **Input Layer**: Takes in the sequence data and attribute data.
- **LSTM Layer**: Processes the sequence data to capture temporal dependencies.
- **Fully Connected Layer**: Combines the output of the LSTM with the static attributes.
- **Output Layer**: Predicts the streamflow.

## Training and Evaluation

The model is trained using the Mean Squared Error (MSE) loss function and the Adam optimizer. The training process includes:

- Forward pass
- Backward pass and optimization
- Evaluation on validation data

The model's performance is evaluated using RMSE and NSE metrics.

## Results

The model's predictions are compared against the actual streamflow values. The performance is visualized using plots that include the gauge ID and the performance metrics (RMSE and NSE).

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/streamflow-prediction.git
   ```
2. Navigate to the project directory:
   ```bash
   cd streamflow-prediction
   ```
3. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Preprocess the data**:
   ```python
   python src/preprocess.py
   ```
2. **Train the model**:
   ```python
   python src/train.py
   ```
3. **Evaluate the model**:
   ```python
   python src/evaluate.py
   ```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

This README file provides a comprehensive overview of the project, guiding users through the setup, usage, and understanding of the work you've done. Feel free to customize it further as per your project's specifics.
