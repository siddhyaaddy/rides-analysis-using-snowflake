# Crypto Tracking Analysis with Snowflake

A comprehensive cryptocurrency tracking and analysis platform leveraging Snowflake's cloud data warehouse for real-time crypto market analytics, trend analysis, and automated reporting.

## 🚀 Project Overview

This project provides an end-to-end solution for cryptocurrency market analysis using Snowflake's powerful data warehouse capabilities. The system tracks multiple cryptocurrencies, performs advanced analytics, and delivers insights through interactive dashboards and automated reports.

## 📊 Dashboard Preview

<img width="1918" height="1035" alt="results" src="https://github.com/user-attachments/assets/e76f6297-a50e-4d35-aea6-25ffa0e6aa81" />

The dashboard provides real-time visualizations of cryptocurrency trends across multiple locations and timeframes, including pickup location analysis and temporal patterns.

## 📁 Project Structure

```
crypto-tracking-analysis-snowflake/
├── data/                   # Raw and processed cryptocurrency data
├── notebooks/              # Jupyter notebooks for analysis and exploration
├── sqls/                   # SQL queries and Snowflake procedures
├── src/                    # Python source code and utilities
├── README.md              # Project documentation
├── notes.md               # Development notes and documentation
├── requirements.txt       # Python dependencies
├── results.png            # Dashboard screenshot and results
└── sample.env             # Environment configuration template
```

## ✨ Features

- **Real-time Data Ingestion**: Automated cryptocurrency data pipeline
- **Snowflake Integration**: Cloud data warehouse for scalable analytics
- **Interactive Dashboards**: Visual analytics with time-series charts
- **Multi-location Analysis**: Geographic distribution of crypto activity
- **Trend Analysis**: Historical patterns and predictive insights
- **Automated Reports**: Scheduled analysis and alerting
- **Jupyter Notebooks**: Exploratory data analysis and prototyping

## 🛠️ Installation

### Prerequisites
- Python 3.8+
- Snowflake account and credentials
- Jupyter Notebook environment
- API keys for cryptocurrency data sources

### Setup Instructions

1. **Clone the repository:**
   ```bash
   git clone https://github.com/siddhyaaddy/crypto-tracking-analysis-snowflake.git
   cd crypto-tracking-analysis-snowflake
   ```

2. **Create virtual environment:**
   ```bash
   python -m venv crypto_env
   source crypto_env/bin/activate  # On Windows: crypto_env\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure environment:**
   ```bash
   cp sample.env .env
   # Edit .env with your Snowflake credentials and API keys
   ```

5. **Set up Snowflake database:**
   ```bash
   # Run SQL setup scripts
   python src/setup_snowflake.py
   ```

## 🔧 Configuration

### Environment Variables

Create a `.env` file based on `sample.env`:

```bash
# Snowflake Configuration
SNOWFLAKE_ACCOUNT=your_account
SNOWFLAKE_USER=your_username
SNOWFLAKE_PASSWORD=your_password
SNOWFLAKE_WAREHOUSE=your_warehouse
SNOWFLAKE_DATABASE=CRYPTO_DB
SNOWFLAKE_SCHEMA=PUBLIC

# API Keys
COINBASE_API_KEY=your_coinbase_key
BINANCE_API_KEY=your_binance_key
COINMARKETCAP_API_KEY=your_cmc_key

# Dashboard Configuration
REFRESH_INTERVAL=300
ALERT_THRESHOLD=0.05
```

## 🚀 Usage

### Data Pipeline

1. **Start data ingestion:**
   ```bash
   python src/data_ingestion.py
   ```

2. **Run analysis pipeline:**
   ```bash
   python src/analysis_pipeline.py
   ```

### Interactive Analysis

1. **Launch Jupyter notebooks:**
   ```bash
   jupyter notebook notebooks/
   ```

2. **Available notebooks:**
   - `01_data_exploration.ipynb`: Initial data analysis
   - `02_trend_analysis.ipynb`: Market trend identification
   - `03_location_analysis.ipynb`: Geographic analysis
   - `04_predictive_modeling.ipynb`: Price prediction models

### Dashboard

1. **Launch dashboard:**
   ```bash
   streamlit run src/dashboard.py
   ```

2. **Access at:** `http://localhost:8501`

## 📈 Analytics Features

### Market Analysis
- **Price Tracking**: Real-time cryptocurrency prices
- **Volume Analysis**: Trading volume patterns
- **Market Cap Trends**: Market capitalization changes
- **Volatility Metrics**: Risk assessment indicators

### Geographic Analysis
- **Location-based Activity**: Crypto activity by region
- **Pickup Location Analysis**: Transaction origin patterns
- **Regional Trends**: Geographic market preferences

### Temporal Analysis
- **Time Series Analysis**: Historical price movements
- **Seasonal Patterns**: Cyclical market behavior
- **Hourly/Daily Trends**: Intraday trading patterns

## 🗄️ Database Schema

### Snowflake Tables

```sql
-- Main cryptocurrency data
CREATE TABLE crypto_prices (
    timestamp TIMESTAMP,
    symbol VARCHAR(10),
    price DECIMAL(18,8),
    volume DECIMAL(18,8),
    market_cap DECIMAL(18,2),
    location VARCHAR(50)
);

-- Transaction analysis
CREATE TABLE crypto_transactions (
    transaction_id VARCHAR(64),
    timestamp TIMESTAMP,
    amount DECIMAL(18,8),
    pickup_location VARCHAR(100),
    status VARCHAR(20)
);
```

## 📊 Key Metrics

The dashboard tracks several important metrics:

- **Price Performance**: Real-time price changes and trends
- **Volume Indicators**: Trading activity levels
- **Geographic Distribution**: Location-based analysis
- **Temporal Patterns**: Time-based market behavior

## 🔍 SQL Queries

The `sqls/` directory contains optimized Snowflake queries for:

- Data aggregation and transformation
- Real-time analytics
- Historical trend analysis
- Geographic data processing
- Performance optimization

## 🔄 Automated Workflows

- **Data Refresh**: Hourly data updates
- **Alert System**: Price threshold notifications
- **Report Generation**: Daily/weekly automated reports
- **Data Quality Checks**: Validation and monitoring

## 📋 Dependencies

Key technologies used:

- **Snowflake**: Cloud data warehouse
- **Python**: Data processing and analysis
- **Jupyter**: Interactive analysis environment
- **Pandas**: Data manipulation
- **Plotly/Matplotlib**: Data visualization
- **Streamlit**: Dashboard framework

## 🚀 Performance Optimization

- **Snowflake Clustering**: Optimized table clustering
- **Query Optimization**: Efficient SQL patterns
- **Caching Strategy**: Result caching for dashboards
- **Incremental Processing**: Delta data updates

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-analysis`)
3. Make your changes
4. Add tests and documentation
5. Commit changes (`git commit -am 'Add new analysis feature'`)
6. Push to branch (`git push origin feature/new-analysis`)
7. Create a Pull Request

## 📝 Development Notes

Check `notes.md` for:
- Development progress
- Known issues and solutions
- Future enhancement ideas
- Technical decisions and rationale

## 🔒 Security

- Environment variables for sensitive data
- Snowflake connection encryption
- API key management
- Data access controls

## 📈 Future Enhancements

- Machine learning price prediction models
- Advanced sentiment analysis
- Real-time alerting system
- Mobile dashboard application
- Additional cryptocurrency exchanges

---

*This project combines the power of Snowflake's cloud data warehouse with advanced cryptocurrency analytics to provide comprehensive market insights and tracking capabilities.*
