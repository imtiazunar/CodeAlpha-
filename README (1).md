# 📊 India Unemployment Analysis

A Python-based data analysis project exploring unemployment trends in India, with a focus on the **impact of Covid-19** and the 2020 national lockdown.

---

## 📁 Dataset

Two CSV datasets sourced from [Kaggle](https://www.kaggle.com/):

| File | Period | Records |
|------|--------|---------|
| `Unemployment in India.csv` | May 2019 – Jun 2020 | 768 rows |
| `Unemployment_Rate_upto_11_2020.csv` | Jan 2020 – Oct 2020 | 267 rows |

**Features include:**
- Region (State)
- Date (Monthly)
- Estimated Unemployment Rate (%)
- Estimated Employed
- Estimated Labour Participation Rate (%)
- Area (Rural / Urban)
- Geographic coordinates (lat/lon)

---

## 🚀 Getting Started

### Prerequisites

Make sure you have Python 3.7+ installed.

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/india-unemployment-analysis.git
cd india-unemployment-analysis
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Add the Dataset

Place the following files in the project root (or a `/data` folder):
- `Unemployment in India.csv`
- `Unemployment_Rate_upto_11_2020.csv`

### 4. Run the Analysis

```bash
python unemployment_analysis.py
```

The script will generate a dashboard image: `unemployment_analysis.png`

---

## 📦 Requirements

```
pandas
numpy
matplotlib
seaborn
```

Or install via:

```bash
pip install pandas numpy matplotlib seaborn
```

---

## 📈 Analysis Highlights

### Covid-19 Impact
- Unemployment **doubled** from ~9.8% (pre-lockdown) to **22.75%** during April–May 2020
- National peak: **23.24% in May 2020**
- Rapid recovery to ~9.6% by October 2020

### Key Visualizations
1. **National Timeline** — Full unemployment trend from May 2019 to Oct 2020
2. **Pre/During/Post Lockdown** — Bar chart comparing the three phases
3. **Rural vs Urban** — Comparative trend lines; urban areas hit harder
4. **State-wise Rankings** — Horizontal bar chart across all Indian states
5. **Heatmap** — Monthly unemployment across the 15 most volatile states
6. **Employment Volume** — Total employed persons trend (millions)
7. **Labour Participation Scatter** — Relationship between participation and unemployment

### Most Affected States
| State | Avg Unemployment Rate |
|-------|----------------------|
| Haryana | 27.5% |
| Tripura | 25.1% |
| Jharkhand | 19.5% |
| Bihar | 19.5% |
| Delhi | 18.4% |

---

## 🗂️ Project Structure

```
india-unemployment-analysis/
│
├── data/
│   ├── Unemployment in India.csv
│   └── Unemployment_Rate_upto_11_2020.csv
│
├── unemployment_analysis.py   # Main analysis script
├── unemployment_analysis.png  # Output dashboard
├── requirements.txt
└── README.md
```

---

## 💡 Policy Insights

- Urban informal workers need **targeted relief** during economic shutdowns
- States like Haryana and Tripura require **structural economic diversification**
- India's labour market shows resilience post-lockdown but is vulnerable to sudden shocks
- Stronger **social safety nets** and rural schemes (e.g. MGNREGA) are key buffers

---

## 🛠️ Tech Stack

- **Python 3** — Core language
- **Pandas** — Data cleaning & manipulation
- **NumPy** — Numerical operations
- **Matplotlib** — Visualizations
- **Seaborn** — Heatmap & styling

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 🙋 Author

**Your Name**
- GitHub: [@your-username](https://github.com/your-username)
- LinkedIn: [your-linkedin](https://linkedin.com/in/your-profile)
