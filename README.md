# City Energy Consumption Analysis & Prediction System

A comprehensive machine learning system for analyzing daily electricity usage patterns across different city zones and predicting future energy demand.

## 🏙️ Project Overview

This system analyzes synthetic energy consumption data for 5 different city zones over a full year (365 days) and provides:
- **Data Analysis**: Pattern identification and statistical insights
- **Visualizations**: Interactive and static charts showing consumption trends
- **ML Prediction**: Two machine learning models for next-day consumption forecasting
- **Interactive Interface**: User-friendly console interface for real-time predictions

## 📊 Dataset Features

The system works with the following data structure:

| Feature | Description | Type |
|---------|-------------|------|
| Date | Day of the reading | DateTime |
| ZoneID | Unique identifier for city zone | Categorical |
| AvgTemperature | Average temperature (°C) | Numeric |
| Humidity | Percentage humidity | Numeric |
| SpecialEvent | Binary indicator (0=No event, 1=Special event) | Binary |
| EnergyConsumption | Total energy consumed (kWh) | Numeric (Target) |

### Zone Types
- **ZONE_001**: Residential area (base: 450 kWh)
- **ZONE_002**: Commercial district (base: 680 kWh)
- **ZONE_003**: Industrial zone (base: 1200 kWh)
- **ZONE_004**: Mixed-use area (base: 520 kWh)
- **ZONE_005**: Downtown core (base: 890 kWh)

## 🚀 Quick Start

### Prerequisites
```python
pip install pandas numpy matplotlib seaborn plotly scikit-learn
```

### Running the System
1. **Generate Dataset**: The system automatically creates synthetic data
2. **Run Analysis**: Execute the notebook to perform comprehensive analysis
3. **View Results**: Check visualizations and model performance
4. **Make Predictions**: Use the interactive interface

```python
# Run the complete analysis
python city_energy_analysis.py

# Use interactive prediction interface
prediction_system.run_interactive_session()
```

## 📈 Key Features

### 1. Data Generation
- **Realistic Patterns**: Incorporates seasonal temperature variations, humidity correlations, and zone-specific characteristics
- **Special Events**: Models weekends, holidays, and special events (15% of days)
- **Noise Simulation**: Adds realistic random variations to consumption patterns

### 2. Comprehensive Analysis
- **Monthly Trends**: Average consumption patterns across months
- **Zone Comparisons**: Statistical analysis of different city areas
- **Correlation Analysis**: Relationships between weather, events, and consumption
- **Seasonal Patterns**: Energy usage variations throughout the year

### 3. Advanced Visualizations

#### Static Plots (Matplotlib/Seaborn)
- Monthly energy usage trends by zone
- Feature correlation heatmap
- Event vs non-event consumption comparison
- Temperature-consumption scatter plots
- Seasonal distribution box plots
- Weekly consumption patterns

#### Interactive Visualizations (Plotly)
- Dynamic monthly trend analysis
- Interactive zone comparison charts
- Hover-enabled data exploration

### 4. Machine Learning Models

#### Linear Regression
- **Features**: Temperature, Humidity, Special Events, Month, Day of Week, Zone
- **Preprocessing**: StandardScaler normalization
- **Performance**: Mean Absolute Error and R² metrics

#### Random Forest
- **Parameters**: 100 estimators, optimized for energy prediction
- **Features**: Same as Linear Regression
- **Advantages**: Handles non-linear relationships and feature interactions
- **Feature Importance**: Identifies most influential factors

### 5. Interactive Prediction Interface
- **User-Friendly**: Console-based input system
- **Validation**: Comprehensive input error checking
- **Multi-Model**: Predictions from both ML models
- **Real-Time**: Instant consumption forecasting

## 📊 Key Insights Discovered

### Temperature Relationships
- **Extreme Weather Impact**: Higher consumption during very hot or cold days
- **Zone Sensitivity**: Commercial and downtown areas show higher temperature sensitivity
- **Seasonal Variations**: 15-20% consumption difference between seasons

### Special Events Impact
- **Commercial Zones**: +20% consumption during events
- **Residential Areas**: -20% consumption during events (people away from home)
- **Industrial Zones**: Minimal event impact

### Zone Characteristics
- **Industrial (ZONE_003)**: Highest and most consistent consumption
- **Residential (ZONE_001)**: Lowest consumption with high weather sensitivity
- **Commercial (ZONE_002)**: Strong weekday/weekend variations

### Model Performance
- **Random Forest**: Better overall performance (lower MAE)
- **Linear Regression**: Faster predictions, good baseline performance
- **Feature Importance**: Temperature and Zone type are top predictors

## 🎯 Usage Examples

### Basic Prediction
```python
# Predict consumption for Zone 1 on a warm day with special event
result = prediction_system.predict_consumption(
    zone_id="ZONE_001", 
    temperature=28, 
    humidity=60, 
    special_event=1
)
print(f"Predicted consumption: {result['average_prediction']:.2f} kWh")
```

### Interactive Session
```python
prediction_system.run_interactive_session()
# Follow prompts to enter:
# - Zone ID (ZONE_001 to ZONE_005)
# - Tomorrow's temperature (-50 to 60°C)
# - Tomorrow's humidity (0-100%)
# - Special event indicator (0 or 1)
```

## 📁 File Structure
```
city-energy-analysis/
│
├── city_energy_analysis.py    # Main analysis script
├── README.md                  # This documentation
├── requirements.txt           # Python dependencies
└── outputs/
    ├── visualizations/        # Generated plots
    └── predictions/           # Prediction results
```

## 🔧 System Architecture

### Data Flow
1. **Data Generation** → Synthetic dataset creation
2. **Preprocessing** → Cleaning and feature engineering  
3. **Analysis** → Statistical pattern identification
4. **Visualization** → Chart and plot generation
5. **Modeling** → ML model training and evaluation
6. **Prediction** → Interactive forecasting interface

### Error Handling
- **Input Validation**: Comprehensive checks for all user inputs
- **Data Quality**: Automatic handling of missing values
- **Model Robustness**: Multiple model comparison for reliability
- **Graceful Degradation**: System continues operation despite minor errors

## 📊 Performance Metrics

### Model Evaluation
- **Mean Absolute Error (MAE)**: Average prediction error in kWh
- **R² Score**: Percentage of variance explained by the model
- **Cross-Validation**: Robust performance assessment

### Typical Results
- **Linear Regression**: MAE ~25-35 kWh, R² ~0.85-0.90
- **Random Forest**: MAE ~20-30 kWh, R² ~0.90-0.95

## 🔮 Future Enhancements

### Potential Improvements
1. **Time Series Modeling**: LSTM/ARIMA for temporal dependencies
2. **Weather Integration**: Real weather API integration
3. **Anomaly Detection**: Identification of unusual consumption patterns
4. **Grid Optimization**: Load balancing recommendations
5. **Cost Analysis**: Economic impact assessment
6. **Real-time Updates**: Live data streaming capabilities

### Additional Features
- **Web Interface**: Browser-based dashboard
- **Mobile App**: Smartphone prediction interface
- **Alert System**: Consumption threshold notifications
- **Batch Predictions**: Multiple zone forecasting
- **Historical Comparison**: Year-over-year analysis

## 🤝 Contributing

This is an educational project demonstrating energy consumption analysis. Contributions welcome for:
- Additional visualization types
- New machine learning models
- Enhanced user interface
- Performance optimizations

## 📝 License

This project is for educational purposes. Feel free to use and modify for learning and research.

## 🆘 Troubleshooting

### Common Issues

**Import Errors**
```bash
pip install --upgrade pandas numpy matplotlib seaborn plotly scikit-learn
```

**Memory Issues**
- Reduce dataset size or use data sampling
- Close unused plots and variables

**Prediction Accuracy**
- Check input data quality
- Verify feature preprocessing
- Consider additional features

### Support
- Check system requirements
- Verify data format consistency
- Review error messages for specific guidance

## 🎓 Educational Value

This project demonstrates:
- **Data Science Pipeline**: Complete workflow from data generation to prediction
- **Feature Engineering**: Creating meaningful predictors from raw data
- **Model Comparison**: Evaluating different ML approaches
- **Visualization**: Effective data communication techniques
- **User Interface**: Building interactive prediction systems
- **Error Handling**: Robust system design principles

Perfect for learning data science, machine learning, and energy analytics concepts!
