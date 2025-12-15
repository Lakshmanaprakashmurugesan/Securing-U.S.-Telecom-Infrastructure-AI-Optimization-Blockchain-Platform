# Telecom Supply Chain Resilience Platform

## 🎯 Project Purpose
AI-driven optimization tools for telecom infrastructure planning and device verification.

## 🔧 Quick Start

```bash
# Install
git clone https://github.com/Lakshmanaprakashmurugesan/telecom-resilience-platform.git
cd telecom-resilience-platform
pip install -r requirements.txt

# Run basic example
python examples/basic_demo.py
```

## 📁 Project Structure
```
telecom-resilience-platform/
├── forecasting/          # Demand prediction models
├── optimization/         # Inventory algorithms  
├── verification/         # Device checking utilities
├── examples/            # Usage examples
└── tests/               # Test suite
```

## 💡 Core Features

### 1. Demand Forecasting
```python
# Example: Predict component needs
from forecasting import predict_demand

data = load_historical_data("component_usage_2023.csv")
predictions = predict_demand(
    data, 
    horizon=30,  # next 30 days
    model="arima"
)
print(f"Predicted units needed: {predictions.mean():.0f}")
```

### 2. Inventory Analysis
```python
# Example: Optimize stock levels
from optimization import calculate_optimal_inventory

current_stock = {"tower_components": 150, "fiber_cable": 5000}
demand_estimate = {"tower_components": 180, "fiber_cable": 5200}

recommendation = calculate_optimal_inventory(
    current_stock, 
    demand_estimate,
    lead_time_days=14
)
```

### 3. Device Verification
```python
# Example: Check IMEI validity
from verification import validate_imei, check_manufacturer

imei = "490154203237518"
is_valid = validate_imei(imei)

if is_valid:
    manufacturer = check_manufacturer(imei)
    print(f"Valid device from {manufacturer}")
else:
    print("Invalid or malformed IMEI")
```

## 📊 Example Output
```python
# Running the main analysis
from main import analyze_supply_chain

results = analyze_supply_chain("config/regional_scenario.yaml")
print(results.summary())

# Sample output:
# Components at risk: 3
# Recommended actions: Increase buffer stock for 5G radios
# Verification passed: 94% of sampled devices
```

## 🧪 Testing
```bash
# Run tests
pytest tests/ -v

# Test specific module
pytest tests/test_forecasting.py
```

## 📚 Documentation
- [API Reference](docs/api.md)
- [Data Format Guide](docs/data_formats.md)
- [Example Notebooks](examples/notebooks/)

## 🤝 Contributing
1. Fork the repository
2. Create a feature branch
3. Add tests for new functionality
4. Submit a pull request



---

*This is a research and development project demonstrating technical approaches to telecom supply chain challenges.*
