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
Analysis of the highest-impact cases reveals a shift towards natural resource exploitation and financial engineering.

| Rank | Case / Scandal | Est. State Loss | Status |
| :--- | :--- | :--- | :--- |
| 🥇 | **PT Timah Tbk** | **Rp 300.0 T** | 🚧 Penyidikan |
| 🥈 | **Tata Kelola Minyak (Pertamina)** | **Rp 193.7 T** | ✅ Tidak Bersalah |
| 🥉 | **BLBI** | **Rp 138.0 T** | 🚧 Penyidikan |
| 4 | Duta Palma Group (Lahan Sawit) | Rp 78.0 T | ⚖️ Vonis |

> *Insight: The top 3 cases alone account for more financial loss than the combined budget of several ministries.*

### 2. Institutional Heatmap
*Which institutions have the highest frequency of cases?*
*(Based on 2004-2025 historical data)*

* **Kementerian/Lembaga:** 515+ Cases (Highest Risk)
* **Pemerintah Provinsi:** 224+ Cases
* **BUMN/BUMD:** 192+ Cases

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
