# 🇮🇩 Indonesia Corruption Forensics (2004-2025)

![Jupyter](https://img.shields.io/badge/Analysis-Forensic-red)
![Data Source](https://img.shields.io/badge/Data-KPK_Open_Data-lightgrey)
![Status](https://img.shields.io/badge/Impact-High_Value-critical)

> **"Follow the Money."** A data-driven investigation into 20 years of corruption cases, institutional graft patterns, and state financial losses in Indonesia.

## 🕵️‍♂️ Executive Summary
This project analyzes the lifecycle of corruption cases handled by the **KPK (Komisi Pemberantasan Korupsi)** from 2004 to early 2025. By processing unstructured reports and case files, we uncover patterns in how corruption has evolved—from conventional bribery in regional governments to mega-scandals in State-Owned Enterprises (BUMN).

**Key Focus Areas:**
* **Institutional Vulnerability:** Which government bodies are most prone to graft?
* **Mega-Corruption Tracking:** Analysis of the "Top 10" cases causing >Rp 500 Trillion in state losses.
* **Judicial Latency:** Analyzing the time gap between case exposure and verdict (Inkracht).

---

## 🚨 Key Findings (Data Highlights)

### 1. The "Big Fish" Index (Top State Losses)
Analysis of the highest-impact cases reveals a massive financial drain, primarily in the Natural Resources and Finance sectors.

| Rank | Case / Scandal | Est. Loss (Rp) | Year Revealed | Status |
| :--- | :--- | :--- | :--- | :--- |
| 🥇 | **Korupsi PT Timah Tbk** | **300.0 T** | 2024 | 🚧 Penyidikan |
| 🥈 | **Tata Kelola Minyak (Pertamina)** | **193.7 T** | 2023 | ✅ Tidak Bersalah |
| 🥉 | **BLBI** | **138.0 T** | 1997 | 🚧 Penyidikan |
| 4 | Duta Palma Group (Sawit) | 78.0 T | 2022 | ⚖️ Vonis |
| 5 | PT TPPI (Petrochemical) | 37.8 T | 2011 | ⚖️ Vonis |
| 6 | PT Asabri (Insurance) | 22.7 T | 2021 | ⚖️ Vonis |

> *Insight: The top 3 cases alone account for more financial loss than the combined budget of several ministries.*

### 2. Institutional Vulnerability Heatmap (2004-2025)
Based on confirmed investigation data, these institutions have the highest frequency of graft cases:

* 🏛️ **Kementerian/Lembaga:** **515 Kasus** (Highest Risk Sector)
* 🏢 **Pemerintah Provinsi:** **224 Kasus**
* 🏭 **BUMN/BUMD:** **192 Kasus**
* ⚖️ **DPR RI:** **86 Kasus**

---

## 🔬 Technical Methodology

This project utilizes **Python** for data cleaning and forensic visualization. The raw data contained inconsistent formatting across 20 years of records, requiring significant preprocessing.

### Workflow:
1.  **Data Extraction:** Parsing diverse Excel/CSV reports (`Data_KPK_2025.xlsx`).
2.  **Normalization:** Standardizing institution names (e.g., merging "Pemkab" and "Kabupaten").
3.  **Temporal Analysis:** Tracking the volume of "Penyelidikan" vs "Eksekusi" to measure KPK's clearance rate.

### Code Snippet: Visualizing Media Lifespan
We analyzed how long high-profile cases stay in the media spotlight versus their legal processing time.

```python
# Snippet from Olah-Data Kasus Korupsi.ipynb
plt.figure(figsize=(12, 6))
for i, row in df_kasus.iterrows():
    # Plotting the timeline from exposure to media fade-out
    plt.plot([row['Tahun Terungkap'], row['Rentang Waktu di Media Massa']], 
             [i, i], marker='o', color='firebrick')

plt.yticks(range(len(df_kasus)), df_kasus['Kasus_Singkat'])
plt.title('Media Lifespan of Major Corruption Scandals')
```

📂 Project Structure
```Bash

├── 📓 Olah-Data Kasus Korupsi.ipynb   # Main Analysis Notebook
├── 📊 Data_KPK_2025.xlsx              # Raw Dataset (Rekap & Instansi)
├── 📉 10 Kasus Besar...xlsx           # High-value case data
└── 📄 README.md
```
🚀 Usage
To replicate this forensic analysis:

1. Clone the Repo

```Bash

git clone [https://github.com/zaghokun/indonesia-corruption-analyze-data.git](https://github.com/zaghokun/indonesia-corruption-analyze-data.git)
```
1. Launch Jupyter

```Bash

jupyter notebook "Olah-Data Kasus Korupsi.ipynb"
```
📢 Disclaimer
This analysis is based on public data available up to Jan 2025. State loss figures are based on prosecutorial estimates and court rulings available at the time of data entry.
