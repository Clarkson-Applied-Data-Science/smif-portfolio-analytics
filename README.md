# smif-portfolio-analytics
# SMIF Real-Money Portfolio Analytics

> **Analyzing $500K+ in actual student investment capital—what backtests don't tell you**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Status](https://img.shields.io/badge/Status-Active-success.svg)]()

---

## 📊 Project Overview

This project analyzes the **Clarkson University Student Managed Investment Fund (SMIF)**, a $452K portfolio with 45 positions generating 85.91% returns. Unlike typical academic projects that backtest strategies on historical data, this examines **real portfolio performance** with actual transaction costs, market impact, and capital constraints.

**Why this matters:** Most quantitative finance projects simulate "what could happen." This analyzes "what did happen" when managing institutional capital.

---

## 🎯 Key Findings

### Performance Metrics
- **Portfolio Value:** $452,462
- **Total Return:** 85.91%
- **Win Rate:** 84.4% (38 winners, 7 losers)
- **Profit Factor:** 44.04
- **Top 3 Contribution:** 41.7% of total gains

### Critical Insights

1. **Concentration Beats Diversification**
   - Top 3 positions (AAPL, UNH, META) generated $87,130—representing 41.7% of total portfolio profits
   - Despite these comprising only ~20% of portfolio value

2. **Position Sizing Impact**
   - Average winner (+1.73%) was **8.2x** larger than average loser (-0.21%)
   - Demonstrates effective risk management and stop-loss discipline

3. **Over-Diversification Problem**
   - 45 positions with top 10 representing only 0.48% concentration
   - HHI of 0.03 indicates extreme diversification may be diluting alpha

4. **Sector Bet Paid Off**
   - Technology exposure (40.9%) generated $103K in gains
   - Quality-focused picks (AAPL, META, COST, INTU) drove performance

---

## 📁 Project Structure

```
smif-portfolio-analytics/
├── analysis/
│   ├── smif_portfolio_analysis.py      # Core analytics engine
│   ├── portfolio_visualizations.py     # Visualization suite
│   ├── advanced_analytics.py           # Risk & attribution models
│   └── example_usage.py                # Complete workflow demo
├── outputs/
│   ├── SMIF_Portfolio_Analysis_Report.docx     # 20-page professional report
│   ├── SMIF_Portfolio_Analysis_Presentation.pptx  # 10-slide deck
│   ├── portfolio_dashboard.png         # Main visual dashboard
│   ├── top_positions.png              # Holdings breakdown
│   ├── pnl_attribution.png            # P&L waterfall
│   └── position_scatter.png           # Risk/return scatter
├── data/
│   ├── SMIF_Holdings_20250905.xlsx    # Portfolio snapshot (anonymized)
│   └── Annual_Sector_Returns.xlsx     # Benchmark data
├── docs/
│   ├── PROJECT_ROADMAP.md             # Development plan
│   ├── EXECUTIVE_SUMMARY.md           # Quick reference
│   └── METHODOLOGY.md                 # Technical details
├── README.md
├── requirements.txt
└── LICENSE
```

---

## 🚀 Quick Start

### Installation

```bash
# Clone repository
git clone https://github.com/chimagr/smif-portfolio-analytics
cd smif-portfolio-analytics

# Install dependencies
pip install -r requirements.txt
```

### Basic Usage

```python
from analysis.smif_portfolio_analysis import SMIFPortfolioAnalyzer
from analysis.portfolio_visualizations import PortfolioVisualizer

# Initialize analyzer
analyzer = SMIFPortfolioAnalyzer(
    holdings_path='data/SMIF_Holdings_20250905.xlsx'
)

# Generate portfolio summary
summary = analyzer.portfolio_summary()
print(summary)

# Performance attribution
attribution = analyzer.performance_attribution(top_n=10)
print(attribution['top'])

# Create visualizations
viz = PortfolioVisualizer(analyzer)
dashboard = viz.create_dashboard(output_path='dashboard.png')
```

---

## 📈 Sample Outputs

### Performance Attribution
```
Top 5 Contributors to P&L:
Symbol    P&L         Return    Contribution
AAPL      $40,016     8.88%     19.1%
UNH       $26,880     9.36%     12.9%
META      $20,234     1.89%     9.7%
COST      $10,708     0.94%     5.1%
INTU      $10,659     2.25%     5.1%
```

### Risk Metrics
```
Win Rate: 84.4%
Profit Factor: 44.04
Cross-Sectional Sharpe: 0.50
Sortino Ratio: 9.60
Average Winner: +1.73%
Average Loser: -0.21%
```

### Concentration Analysis
```
HHI: 0.03 (Highly Diversified)
Top 10 Concentration: 0.48%
Effective Number of Positions: 292,604
Gini Coefficient: 0.44
```

---

## 💡 Key Contributions

### What Makes This Project Unique

| Typical Student Project | This Project |
|------------------------|--------------|
| Backtest on historical data | Real $500K portfolio |
| Simulated transactions | Actual P&L with costs |
| Hypothetical positions | 45 real holdings |
| Theoretical risk | Managing institutional capital |
| No consequences | Fiduciary responsibility |

### Technical Features

- **Performance Attribution** - Quantifies which positions drive returns
- **Concentration Risk** - HHI and Gini coefficient analysis
- **Risk-Adjusted Metrics** - Sharpe, Sortino, Profit Factor
- **Statistical Analysis** - Z-score outlier detection
- **Sector Mapping** - Industry allocation analysis
- **Professional Reporting** - Automated Word/PowerPoint generation

---

## 📚 Documentation

### Core Reports
- **[20-Page Analysis Report](outputs/SMIF_Portfolio_Analysis_Report.docx)** - Comprehensive written analysis
- **[10-Slide Presentation](outputs/SMIF_Portfolio_Analysis_Presentation.pptx)** - Executive summary deck
- **[Project Roadmap](docs/PROJECT_ROADMAP.md)** - Development timeline
- **[Executive Summary](docs/EXECUTIVE_SUMMARY.md)** - Quick reference

### Technical Details
- **[Methodology](docs/METHODOLOGY.md)** - Calculation methods
- **[API Documentation](docs/API.md)** - Function reference
- **[Example Notebooks](notebooks/)** - Jupyter tutorials

---

## 🔬 Methodology

### Data Sources
- Portfolio holdings snapshot (September 5, 2025)
- Historical sector returns (2007-2025)
- Individual position cost basis and P&L

### Analytical Framework
1. **Performance Attribution** - Dollar contribution to total P&L
2. **Concentration Metrics** - HHI, Gini, effective # of bets
3. **Risk Analytics** - Cross-sectional Sharpe/Sortino ratios
4. **Sector Analysis** - Industry exposure mapping
5. **Outlier Detection** - Z-score analysis for anomalies

---

## 💼 Real-World Applications

### For Portfolio Managers
- Identify which positions actually drive returns
- Assess concentration risk vs. opportunity cost
- Track risk-adjusted performance over time
- Generate client-ready reports automatically

### For Quantitative Researchers
- Study backtest vs. live performance gaps
- Analyze position sizing effectiveness
- Research portfolio construction challenges
- Validate theoretical optimization methods

### For Students & Educators
- Learn institutional portfolio management
- Understand real P&L attribution
- Practice professional financial reporting
- Bridge academic theory with market reality

---

## 🛠️ Requirements

```
Python 3.8+
pandas>=1.5.0
numpy>=1.23.0
matplotlib>=3.6.0
seaborn>=0.12.0
openpyxl>=3.0.0
```

---

## 📊 Future Enhancements

### Planned Features
- [ ] Time-series performance tracking (monthly snapshots)
- [ ] Benchmark comparison (SPY, sector ETFs)
- [ ] Factor attribution (Fama-French)
- [ ] Transaction cost analysis
- [ ] Portfolio optimization engine
- [ ] Monte Carlo simulation
- [ ] Interactive Streamlit dashboard
- [ ] Automated email reports

---

## 🎓 Academic Context

**Institution:** Clarkson University  
**Program:** Master's in Applied Data Science  
**Course:** Fund Management (Professor Alan Zebedee)  
**Fund:** Student Managed Investment Fund (SMIF)  
**Portfolio Value:** $500K+  
**Author:** Rufaro Chimaga

This project demonstrates:
- Real-world application of quantitative finance
- Institutional-grade portfolio analytics
- Data-driven investment decision making
- Professional financial reporting

---

## 📝 Citation

If you use this framework in your research:

```bibtex
@misc{chimaga2026smif,
  author = {Chimaga, Rufaro},
  title = {SMIF Real-Money Portfolio Analytics Framework},
  year = {2026},
  institution = {Clarkson University},
  howpublished = {\url{https://github.com/chimagr/smif-portfolio-analytics}}
}
```

---

## 🤝 Contributing

Contributions welcome! Areas of interest:
- Additional risk metrics and analytics
- Machine learning for position sizing
- Live market data integration
- Enhanced visualization techniques

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## 📧 Contact

**Rufaro Chimaga**  
Graduate Student, Applied Data Science  
Clarkson University  
Manager, Student Managed Investment Fund

- LinkedIn: [linkedin.com/in/rufaro-chimaga](https://www.linkedin.com/in/rufaro-chimaga)
- GitHub: [@chimagr](https://github.com/chimagr)
- Email: chimagr@clarkson.edu

---

## ⚖️ Disclaimer

This framework is for educational and research purposes only. Portfolio holdings and performance data represent historical snapshots and are not investment recommendations. Past performance does not guarantee future results.

The Student Managed Investment Fund is an educational program at Clarkson University. Holdings and strategies may not be suitable for all investors. Always conduct your own due diligence and consult with qualified financial advisors before making investment decisions.

---

## 🏆 Acknowledgments

- **Professor Alan Zebedee** - Faculty Advisor, Fund Management Course
- **Clarkson University** - Student Managed Investment Fund program support
- **SMIF Committee** - Investment oversight and research collaboration

---

**⭐ Star this repo if you find it useful!**

**Last Updated:** January 6, 2026  
**Portfolio Snapshot:** September 5, 2025  
**Version:** 1.0.0
