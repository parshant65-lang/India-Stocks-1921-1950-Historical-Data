# India-Stocks-1921-1950-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1921 to 1950)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1921-1950-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1921 to 1950)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1921 | `PRASOLCHEM` | Prasol Chemicals Limited | `PRASOLCHEM.NS` |
| 1922 | `PRAVEG` | Praveg Limited | `PRAVEG.NS` |
| 1923 | `PRAXIS` | Praxis Home Retail Limited | `PRAXIS.NS` |
| 1924 | `PRECAM` | Precision Camshafts Limited | `PRECAM.NS` |
| 1925 | `PRECOT` | Precot Limited | `PRECOT.NS` |
| 1926 | `PRECWIRE` | Precision Wires India Limited | `PRECWIRE.NS` |
| 1927 | `PREMCO` | Premco Global Limited | `PREMCO.NS` |
| 1928 | `PREMEXPLN` | Premier Explosives Limited | `PREMEXPLN.NS` |
| 1929 | `PREMIER` | Premier Limited | `PREMIER.NS` |
| 1930 | `PREMIERPOL` | Premier Polyfilm Limited | `PREMIERPOL.NS` |
| 1931 | `PRICOLLTD` | Pricol Limited | `PRICOLLTD.NS` |
| 1932 | `PRIMESECU` | Prime Securities Limited | `PRIMESECU.NS` |
| 1933 | `PRIMO` | Primo Chemicals Limited | `PRIMO.NS` |
| 1934 | `PRINCEPIPE` | Prince Pipes And Fittings Limited | `PRINCEPIPE.NS` |
| 1935 | `PRIORITY` | Priority Jewels Limited | `PRIORITY.NS` |
| 1936 | `PRISMX` | Prismx Global Ventures Limited | `PRISMX.NS` |
| 1937 | `PRITI` | Priti International Limited | `PRITI.NS` |
| 1938 | `PRITIKAUTO` | Pritika Auto Industries Limited | `PRITIKAUTO.NS` |
| 1939 | `PROSTARM` | Prostarm Info Systems Limited | `PROSTARM.NS` |
| 1940 | `PROTEAN` | Protean eGov Technologies Limited | `PROTEAN.NS` |
| 1941 | `PROZONER` | Prozone Realty Limited | `PROZONER.NS` |
| 1942 | `PRSMJOHNSN` | Prism Johnson Limited | `PRSMJOHNSN.NS` |
| 1943 | `PRUDENT` | Prudent Corporate Advisory Services Limited | `PRUDENT.NS` |
| 1944 | `PRUDMOULI` | Prudential Sugar Corporation Limited | `PRUDMOULI.NS` |
| 1945 | `PSB` | Punjab & Sind Bank | `PSB.NS` |
| 1946 | `PSPPROJECT` | PSP Projects Limited | `PSPPROJECT.NS` |
| 1947 | `PTC` | PTC India Limited | `PTC.NS` |
| 1948 | `PTL` | PTL Enterprises Limited | `PTL.NS` |
| 1949 | `PUNJABCHEM` | Punjab Chemicals & Crop Protection Limited | `PUNJABCHEM.NS` |
| 1950 | `PURVA` | Puravankara Limited | `PURVA.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream PRASOLCHEM 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1921-1950-Historical-Data/main/PRASOLCHEM/1m/2026/10/PRASOLCHEM_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
