\# ⚽ WorldCup Analytics



A data-driven \*\*FIFA World Cup player analytics and performance segmentation system\*\* built with Python and Machine Learning. The project processes detailed player data, engineers meaningful performance metrics, applies unsupervised learning to identify player profiles, and produces analytical rankings and visualizations.



\---



\## 📌 Project Overview



\*\*WorldCup Analytics\*\* is a machine learning and data analytics project designed to analyze football player performance using detailed player statistics.



The system transforms raw JSON player data into a structured analytical dataset and applies \*\*feature engineering, feature scaling, K-Means clustering, and Principal Component Analysis (PCA)\*\* to identify different player performance profiles.



The project ultimately provides:



\* Player performance analysis

\* Goal and assist analysis

\* Performance scoring

\* Player segmentation using clustering

\* Cluster-based player profiling

\* Player impact ranking

\* Top-player identification

\* PCA-based dimensionality visualization

\* Analytical charts and reports



\---



\## 🎯 Objectives



The main objectives of this project are:



1\. Process and clean raw football player data.

2\. Extract useful information from nested JSON structures.

3\. Handle missing and inconsistent data.

4\. Engineer meaningful player-performance features.

5\. Develop a composite performance score.

6\. Segment players using machine learning.

7\. Visualize player clusters using PCA.

8\. Rank players based on their overall impact.

9\. Identify the best-performing player from each cluster.

10\. Generate reusable analytical datasets and visualizations.



\---



\## 🧠 Machine Learning Approach



The project follows an end-to-end analytics pipeline:



```text

Raw JSON Player Data

&#x20;       ↓

Data Extraction

&#x20;       ↓

Data Cleaning

&#x20;       ↓

Feature Engineering

&#x20;       ↓

Feature Selection

&#x20;       ↓

Feature Scaling

&#x20;       ↓

K-Means Clustering

&#x20;       ↓

PCA Dimensionality Reduction

&#x20;       ↓

Player Profiling

&#x20;       ↓

Impact Ranking

&#x20;       ↓

Visualizations \& Reports

```



\---



\## 📊 Dataset



The project uses detailed football player data stored as JSON files.



The raw dataset contains information such as:



\* Player identity

\* Team information

\* Position

\* Nationality

\* Age / birth date

\* Height and weight

\* Captain status

\* Injury information

\* Contract information

\* Market value

\* Transfer value

\* Match statistics

\* Goals

\* Assists

\* Player ratings



\### Dataset Processing



The raw data contains nested structures, so relevant information was extracted from multiple JSON levels.



For example, recent match statistics were processed to calculate:



\* Goals

\* Assists

\* Match ratings



The final processed dataset contains \*\*1,243 unique players\*\* with \*\*no duplicate player IDs\*\*.



\---



\## 🧹 Data Cleaning \& Preprocessing



The preprocessing stage includes:



\* JSON file loading

\* Nested JSON extraction

\* Column normalization

\* Data type conversion

\* Missing-value analysis

\* Duplicate-player detection

\* Boolean normalization

\* Numeric conversion

\* Date handling

\* Feature validation



\### Data Quality



```text

Total Players:       1,243

Unique Player IDs:   1,243

Duplicate IDs:           0

```



This ensures that each player is represented by a unique analytical record.



\---



\## ⚙️ Feature Engineering



Several features were created to improve player analysis.



\### Goal + Assist Total



```text

goal\_assist\_total = goals + assists

```



This represents a player's overall direct contribution to goals.



\### Goal/Assist Ratio



A goal-assist relationship was also calculated to distinguish players who contribute primarily through scoring from those who contribute through creation.



\### Performance Score



A composite performance metric was developed using player rating and attacking contribution.



Conceptually:



```text

Performance Score

&#x20;       ↓

Player Rating

&#x20;       +

Goal Contribution

```



This provides a more comprehensive measure than using goals or rating independently.



\---



\## 🤖 Player Clustering



The project uses \*\*K-Means clustering\*\* to segment players into performance groups.



Four clusters were identified.



\### Player Segments



| Cluster | Player Profile                  |

| ------: | ------------------------------- |

|       0 | 🏆 Elite / Top Performers       |

|       1 | 📉 Low-Performance Players      |

|       2 | 🎯 Creative / Attacking Players |

|       3 | ⚡ Goal-Oriented Players         |



\### Cluster Distribution



| Player Profile               |   Players |

| ---------------------------- | --------: |

| Elite / Top Performers       |       188 |

| Low-Performance Players      |       231 |

| Creative / Attacking Players |       387 |

| Goal-Oriented Players        |       437 |

| \*\*Total\*\*                    | \*\*1,243\*\* |



\---



\## 📈 Cluster Performance



The cluster analysis produced the following average statistics:



| Cluster                      | Goals | Assists | Rating | Goal + Assist | Performance Score |

| ---------------------------- | ----: | ------: | -----: | ------------: | ----------------: |

| Elite / Top Performers       | 16.98 |    9.65 |   6.46 |         26.64 |             10.26 |

| Low-Performance Players      |  1.32 |    0.58 |   2.74 |          1.90 |              1.88 |

| Creative / Attacking Players |  3.93 |    3.82 |   5.59 |          7.75 |              4.74 |

| Goal-Oriented Players        |  3.28 |    1.93 |   5.59 |          5.21 |              4.17 |



These clusters provide a useful way to understand different types of player contribution.



\---



\## 🔬 PCA Analysis



\*\*Principal Component Analysis (PCA)\*\* was used to reduce the dimensionality of the player-performance feature space.



The first two principal components explain:



```text

PC1: 65.86%

PC2: 19.77%



PC1 + PC2: 85.63%

```



Therefore, the first two components provide a strong 2D representation of the main variation in the selected player-performance features.



PCA is primarily used here for \*\*visual interpretation of the clusters\*\* rather than replacing the original analytical features.



\---



\## 🏆 Player Ranking



A final ranking system was developed to identify high-impact players.



The ranking incorporates the project's engineered performance metrics and cluster information to provide a more comprehensive player-impact assessment.



The final ranking dataset contains:



```text

1,243 ranked players

```



The project also identifies the \*\*best-performing player within each player cluster\*\*.



\---



\## 📊 Visualizations



The project generates three primary visualizations.



\### 1. Player Distribution by Cluster



Shows the number of players belonging to each performance segment.



```text

reports/figures/cluster\_distribution.png

```



\### 2. Average Performance by Cluster



Compares average performance metrics across the four player profiles.



```text

reports/figures/cluster\_performance.png

```



\### 3. Top 20 Player Performance Ranking



Displays the highest-ranked players based on the project's impact-scoring methodology.



```text

reports/figures/top\_20\_players.png

```



\---



\## 📁 Project Structure



```text

WorldCup Analytics/

│

├── data/

│   ├── raw/

│   │   └── players/

│   │       └── \*.json

│   │

│   └── processed/

│       ├── worldcup\_player\_clusters.csv

│       ├── final\_player\_ranking.csv

│       └── best\_player\_by\_cluster.csv

│

├── notebooks/

│   └── WorldCup\_Analytics.ipynb

│

├── reports/

│   └── figures/

│       ├── cluster\_distribution.png

│       ├── cluster\_performance.png

│       └── top\_20\_players.png

│

├── .gitignore

├── requirements.txt

└── README.md

```



> The exact notebook filename can be changed to match the file in your project.



\---



\## 🛠️ Technologies Used



\### Programming Language



\* Python



\### Data Analysis



\* Pandas

\* NumPy



\### Machine Learning



\* Scikit-learn



\### Visualization



\* Matplotlib



\### Development Environment



\* Jupyter Notebook

\* Python Virtual Environment

\* Git \& GitHub



\### Core ML Techniques



\* Feature Engineering

\* Feature Scaling

\* K-Means Clustering

\* Principal Component Analysis (PCA)

\* Composite Performance Scoring

\* Player Ranking



\---



\## 📦 Installation



\### 1. Clone the repository



```bash

git clone https://github.com/yourusername/WorldCup-Analytics.git

cd WorldCup-Analytics

```



Replace `yourusername` with your GitHub username.



\### 2. Create a virtual environment



Windows:



```bash

python -m venv .venv

```



\### 3. Activate the environment



Windows PowerShell:



```bash

.venv\\Scripts\\Activate.ps1

```



Windows CMD:



```bash

.venv\\Scripts\\activate

```



\### 4. Install dependencies



```bash

pip install -r requirements.txt

```



\---



\## ▶️ Running the Project



Launch Jupyter Notebook:



```bash

jupyter notebook

```



Then open the project notebook and execute the cells sequentially.



The notebook performs:



```text

Data Loading

&#x20;   ↓

Data Exploration

&#x20;   ↓

Data Cleaning

&#x20;   ↓

Feature Engineering

&#x20;   ↓

Clustering

&#x20;   ↓

PCA

&#x20;   ↓

Player Ranking

&#x20;   ↓

Visualization

&#x20;   ↓

Export Processed Data

```



\---



\## 📤 Generated Outputs



After running the analysis, the following datasets are generated:



\### Player Clusters



```text

data/processed/worldcup\_player\_clusters.csv

```



Contains player information, engineered features, cluster assignments, and cluster names.



\### Final Player Ranking



```text

data/processed/final\_player\_ranking.csv

```



Contains the complete player ranking and impact scores.



\### Best Player by Cluster



```text

data/processed/best\_player\_by\_cluster.csv

```



Contains the highest-impact player identified from each player segment.



\---



\## 📌 Key Results



The analysis successfully processed:



\* \*\*1,243 unique players\*\*

\* \*\*0 duplicate player IDs\*\*

\* \*\*4 distinct player-performance clusters\*\*

\* \*\*85.63% variance explained by the first two PCA components\*\*



The clustering results reveal four broad player profiles:



\### 🏆 Elite / Top Performers



Players with substantially higher overall attacking contribution and performance scores.



\### 📉 Low-Performance Players



Players with comparatively low goals, assists, ratings, and overall performance scores.



\### 🎯 Creative / Attacking Players



Players who demonstrate stronger assist and creative contribution relative to their overall scoring output.



\### ⚡ Goal-Oriented Players



Players whose contribution is more strongly associated with goal production.



\---



\## 💡 Why This Project?



Football generates enormous amounts of player data, but raw statistics alone do not always provide an intuitive understanding of player profiles.



This project demonstrates how \*\*machine learning and data analytics can transform raw football statistics into meaningful player segments and rankings\*\*.



Instead of looking at a single statistic, the system combines multiple performance indicators to discover patterns across players.



\---



\## 🚀 Potential Applications



The analytical framework could be useful for:



\* Football scouting

\* Player comparison

\* Talent identification

\* Team recruitment

\* Performance analysis

\* Sports analytics dashboards

\* Player profiling

\* Data-driven decision making



\---



\## 🔮 Future Improvements



Possible future extensions include:



\* Interactive Streamlit dashboard

\* Match-level performance prediction

\* Player similarity/recommendation system

\* Position-specific performance models

\* Player market-value prediction

\* Team-level analytics

\* World Cup match prediction

\* Time-series player performance analysis

\* Advanced clustering comparison

\* Automated data collection pipeline



\---



\## ⚠️ Limitations



The current analysis has several limitations:



\* Player statistics depend on the available source data.

\* Some player attributes contain missing values.

\* Performance scoring is a project-defined metric rather than an official football rating.

\* K-Means assumes relatively spherical cluster structures.

\* Player performance can vary significantly by position, competition, and playing time.

\* The analysis does not fully account for tactical roles or team strength.



Therefore, the results should be interpreted as \*\*analytical player profiles rather than definitive measures of football ability\*\*.



\---



\## 📜 License



This project is licensed under the \*\*MIT License\*\*.



See the `LICENSE` file for details.



\---



\## 👨‍💻 Author



\*\*Devendra Khanal\*\*



BSc.CSIT Student \& Developer



Interested in:



\* Machine Learning

\* Data Science

\* Artificial Intelligence

\* Web Development

\* Software Engineering



\---



\## ⭐ Project Highlights



```text

✔ 1,243 unique players analyzed

✔ Nested JSON data processing

✔ Data cleaning \& preprocessing

✔ Feature engineering

✔ Performance scoring

✔ K-Means player segmentation

✔ 4 player performance profiles

✔ PCA dimensionality reduction

✔ 85.63% variance explained by PC1 + PC2

✔ Player impact ranking

✔ Cluster-based best-player identification

✔ Automated analytical visualizations

✔ Exportable CSV datasets

```



\---



\## ⭐ Support



If you find this project useful or interesting, consider giving the repository a ⭐ on GitHub.



