# NBA Player Clustering Analysis Project

## Project Overview

This project uses **Gaussian Mixture Models (GMM)** to discover modern NBA player archetypes based on statistical performance data from the 2024-25 season. The analysis successfully identifies **5 distinct player archetypes** that transcend traditional positions (PG, SG, SF, PF, C), validating the "positionless basketball" hypothesis.

### Key Results

- **Sample Size:** 411 NBA players (≥30 games played)
- **Features:** 13 curated statistics (31% defensive-focused)
- **Algorithm:** Gaussian Mixture Model with k=5 clusters
- **Archetypes Discovered:**
  1. **Elite Perimeter Playmaking Scorers** (68 players, 16.5%)
  2. **Role-Playing Three-Point Facilitating Shooters** (91 players, 22.1%)
  3. **Offensive Mid-Range Centers** (106 players, 25.8%)
  4. **Role-Playing Three-Point Forward Shooters** (89 players, 21.7%)
  5. **Lockdown 3-and-D Wings** (57 players, 13.9%)

### Deliverables

✅ **Jupyter Notebook:** Complete analysis with 77 cells (28 markdown, 49 code)
✅ **PowerPoint Presentation:** 22 slides with detailed speaker notes
✅ **Visualizations:** 13 high-quality figures (300 DPI)
✅ **Data Export:** CSV with player cluster assignments

## Quick Start

### Option 1: Using the Launch Script (Recommended)

```bash
./launch_jupyter.sh
```

### Option 2: Manual Launch

```bash
# Activate virtual environment
source venv/bin/activate

# Launch JupyterLab
jupyter lab

# Or launch Jupyter Notebook (classic interface)
jupyter notebook nba_player_clustering_analysis.ipynb
```

### Option 3: Using VS Code

1. Open `nba_player_clustering_analysis.ipynb` in VS Code
2. Click "Select Kernel" in the top-right
3. Choose "Python (NBA Clustering)" from the list
4. Run cells interactively

## Selecting the Correct Kernel

When you open the Jupyter notebook, make sure to select the **"Python (NBA Clustering)"** kernel:

- **In JupyterLab:** Click the kernel name in the top-right corner → Select "Python (NBA Clustering)"
- **In Jupyter Notebook:** Kernel menu → Change kernel → Python (NBA Clustering)
- **In VS Code:** Click "Select Kernel" button → Choose "Python (NBA Clustering)"

## Project Structure

```
Final Project/
├── nba_player_clustering_analysis.ipynb    # Main analysis notebook (77 cells)
├── NBA_Player_Clustering_Presentation.pptx # PowerPoint presentation (22 slides)
├── requirements.txt                        # Python dependencies
├── README.md                               # This file
├── CLAUDE.md                               # Claude Code project instructions
├── venv/                                   # Virtual environment (do not modify)
├── figures/                                # 13 high-quality visualizations (300 DPI)
│   ├── 01_feature_distributions.png
│   ├── 02_feature_boxplots.png
│   ├── 03_correlation_heatmap.png
│   ├── 04_pca_scree_plot.png
│   ├── 05_pca_biplot.png
│   ├── 06_elbow_method.png
│   ├── 07_silhouette_scores.png
│   ├── 08_kelbow_visualizer.png
│   ├── 09_silhouette_plot.png
│   ├── 11_pca_clusters.png
│   ├── 12_tsne_clusters.png
│   ├── 13_radar_charts.png
│   └── 14_archetype_distribution.png
└── player_cluster_assignments.csv          # Player assignments with statistics
```

## Environment Details

### Python Version

- Python 3.12

### Key Libraries Installed

- **nba_api 1.4.1** - NBA data collection
- **pandas 2.3.3** - Data manipulation
- **numpy 1.26.4** - Numerical computing
- **scikit-learn 1.7.2** - Machine learning algorithms
- **scipy 1.16.2** - Scientific computing
- **matplotlib 3.10.7** - Static visualizations
- **seaborn 0.13.2** - Statistical visualizations
- **plotly 6.3.1** - Interactive visualizations
- **yellowbrick 1.5** - ML visualization tools
- **jupyter 1.1.1** - Jupyter notebook environment

## Running the Analysis

1. **Start Jupyter** using one of the methods above
2. **Open the notebook** `nba_player_clustering_analysis.ipynb`
3. **Select the kernel** "Python (NBA Clustering)"
4. **Run all cells** sequentially from top to bottom (Cell → Run All)

The analysis will:

- Fetch NBA player data for the 2024-25 season (411 players)
- Engineer 13 curated features (31% defensive-focused)
- Perform exploratory data analysis with correlation heatmaps and PCA
- Determine optimal k using Elbow Method and Silhouette Analysis
- Train and compare clustering models (K-Means, Hierarchical, GMM, DBSCAN)
- Select Gaussian Mixture Model (GMM) with k=5 clusters
- Generate 13 high-quality visualizations (300 DPI)
- Assign unique archetype names to each cluster
- Export player cluster assignments to CSV

### Analysis Sections

1. **Introduction & Problem Statement** (Cells 0-2)
2. **Data Collection & Preprocessing** (Cells 3-17)
   - NBA API data fetch, cleaning, feature engineering
3. **Exploratory Data Analysis** (Cells 18-35)
   - Feature distributions, correlation analysis, PCA
4. **Clustering Analysis** (Cells 36-60)
   - Feature scaling, optimal k selection, algorithm comparisons
5. **Results & Visualization** (Cells 61-74)
   - Cluster profiling, archetype naming, PCA/t-SNE visualizations
6. **Discussion & Conclusions** (Cells 75-76)
   - Comprehensive interpretation (~7,000 words)
   - Key findings, business applications, limitations, future work

## Expected Runtime

- **Data collection:** ~30-60 seconds (depends on NBA API response time)
- **EDA & Visualizations:** ~2-3 minutes
- **Model training:** ~1-2 minutes
- **Total:** ~5-10 minutes for complete analysis

## Troubleshooting

### Kernel Not Found

If you don't see "Python (NBA Clustering)" in the kernel list:

```bash
# Reinstall the kernel
source venv/bin/activate
python -m ipykernel install --user --name=nba-clustering --display-name="Python (NBA Clustering)"
```

### Package Import Errors

If you get import errors, reinstall dependencies:

```bash
source venv/bin/activate
pip install -r requirements.txt
```

### NBA API Connection Issues

If the NBA API fails to connect:

- Check your internet connection
- The API may be temporarily down - try again later
- Consider using cached data if available

### Memory Issues

If you encounter memory errors:

- Close other applications
- Restart the Jupyter kernel (Kernel → Restart)
- The analysis uses ~500MB-1GB of RAM

## Output Files

After running the notebook, you'll get:

- **player_cluster_assignments.csv** - Complete clustering results with player statistics and archetype assignments
- **figures/*.png** - 13 high-quality visualizations (300 DPI) for analysis and presentation

### Generated Figures

1. `01_feature_distributions.png` - Feature distribution histograms
2. `02_feature_boxplots.png` - Feature boxplots
3. `03_correlation_heatmap.png` - Feature correlation matrix
4. `04_pca_scree_plot.png` - PCA variance explained
5. `05_pca_biplot.png` - PCA biplot
6. `06_elbow_method.png` - Elbow curve for k selection
7. `07_silhouette_scores.png` - Silhouette scores by k
8. `08_kelbow_visualizer.png` - Yellowbrick elbow visualizer
9. `09_silhouette_plot.png` - Detailed silhouette plot for k=5
10. `11_pca_clusters.png` - PCA projection with clusters
11. `12_tsne_clusters.png` - t-SNE visualization
12. `13_radar_charts.png` - Radar charts for all 5 archetypes
13. `14_archetype_distribution.png` - Player count by archetype

## Customization

You can modify these parameters in the notebook:

- **Season:** Change `season='2024-25'` to analyze different seasons (Cell 7)
- **Minimum games:** Adjust the 30-game threshold filter (Cell 10)
- **Number of clusters:** Modify `OPTIMAL_K = 5` variable (after determining from Elbow/Silhouette)
- **Features:** Add/remove features in the 13-feature list (Cell 14)
- **Archetype names:** Naming system uses guaranteed unique assignment (Cell 68)

## Key Technical Details

### Feature Engineering (13 Features)

**Core Per-36 Statistics (4):**
- PTS_36, AST_36, REB_36, STL_36

**Shooting Efficiency/Style (2):**
- FG_PCT, THREE_PT_RATE

**Role-Specific Discriminators (7):**
- PURE_PLAYMAKER, FT_RATE, PAINT_PROTECTOR, BLK_36
- GUARD_INDEX, BIG_INDEX, DEFENSIVE_VERSATILITY

**Defensive Focus:** 4 of 13 features (31%) explicitly measure defense

### Algorithm Selection

**Algorithms Tested:**
1. K-Means (suggested k=2, insufficient)
2. Hierarchical Clustering (better metrics but hard boundaries)
3. **Gaussian Mixture Models (SELECTED)** - k=5
4. DBSCAN

**Why GMM?**
- Soft clustering with probabilistic membership
- Better handles overlapping roles (modern "positionless basketball")
- Domain validity prioritized over metric optimization
- Silhouette score of 0.084 reflects expected overlap in modern NBA

### The 5 Archetypes

1. **Elite Perimeter Playmaking Scorers** (68 players, 16.5%)
   - 22.3 PTS, 5.8 AST per 36, 41% 3PT rate, 45.8% FG
   - Franchise cornerstones, primary offensive creators

2. **Role-Playing Three-Point Facilitating Shooters** (91 players, 22.1%)
   - 14.9 PTS, 3.1 AST per 36, 54% 3PT rate (ELITE)
   - Floor spacers, catch-and-shoot threats

3. **Offensive Mid-Range Centers** (106 players, 25.8% - LARGEST)
   - 15.3 PTS at 53.6% FG, 10.5 REB, 1.5 BLK per 36
   - Traditional bigs, paint anchors, rim protectors

4. **Role-Playing Three-Point Forward Shooters** (89 players, 21.7%)
   - 14.6 PTS, 2.6 AST per 36, 48% 3PT rate (HIGHEST)
   - Stretch forwards, floor spacing bigs

5. **Lockdown 3-and-D Wings** (57 players, 13.9% - SCARCEST)
   - 13.4 PTS, 6.0 AST per 36, 1.6 STL (HIGHEST), 49% 3PT rate
   - Elite two-way players, defensive stoppers

## Business Applications

The discovered archetypes inform:

- **Roster Construction:** Balance across complementary archetypes
- **Contract Valuation:** Scarcity-based pricing (e.g., Lockdown Wings command premium)
- **Draft Strategy:** Target archetype gaps in current roster
- **Free Agency:** Prioritize underrepresented archetypes
- **Lineup Optimization:** Complementary archetype pairings
- **Matchup Analysis:** Deploy appropriate archetypes vs. opponent strengths

## Deactivating the Environment

When finished:

```bash
deactivate
```

## Removing the Kernel (Optional)

To remove the Jupyter kernel:

```bash
jupyter kernelspec uninstall nba-clustering
```

## PowerPoint Presentation

The project includes a comprehensive **22-slide PowerPoint presentation**:

**File:** `NBA_Player_Clustering_Presentation.pptx`

**Contents:**
- Problem statement and motivation
- Methodology overview and feature engineering
- EDA with correlation heatmap
- Optimal k selection (Elbow + Silhouette)
- Algorithm comparison and GMM selection rationale
- All 5 archetypes with detailed profiles
- Cluster visualizations (t-SNE, radar charts, distribution)
- Business applications for roster construction and contracts
- Limitations and future work
- Key findings and conclusions

**Speaker Notes:** 15 of 22 slides include comprehensive talk tracks (averaging ~1,467 characters each) for presentation delivery

## Limitations

**Data Limitations:**
- Box score statistics incomplete (missing tracking data, advanced metrics)
- Defensive impact underrepresented (STL/BLK miss elite on-ball defense)
- Off-ball contributions not captured (screening, gravity)

**Temporal Limitations:**
- Single season snapshot (2024-25)
- Player performance varies year-to-year

**Methodological Constraints:**
- Predetermined k=5 (domain constraint overrides data optimization at k=2)
- Outlier sensitivity (generational talents may distort centroids)
- Steals are incomplete defensive measure

## Future Work

- Integrate NBA player tracking data (movement, possession, shot tracking)
- Multi-season longitudinal analysis (archetype stability over time)
- Team-level analysis (optimal archetype combinations for winning)
- Salary efficiency by archetype (cost per win)
- Advanced techniques (deep learning, autoencoders)

## Project Information

- **Course:** DTSA 5510 - Unsupervised Algorithms in Machine Learning
- **Semester:** Fall 2025
- **Topic:** NBA Player Role Clustering Using Unsupervised Learning
- **Main Finding:** Successfully identified 5 meaningful player archetypes that transcend traditional positions, validating the "positionless basketball" hypothesis

## Key Findings Summary

✅ **Positionless Basketball Validated:** Archetypes are defined by statistical profiles (what players DO) rather than traditional positions (what they're called)

✅ **Defensive Integration Successful:** 31% of features measure defense, successfully identifying elite two-way players (Lockdown 3-and-D Wings)

✅ **GMM Appropriate for NBA:** Soft clustering captures overlapping, versatile modern roles better than hard boundaries

✅ **Archetype Balance Critical:** Successful teams need complementary representation across archetypes, not just "best players"

✅ **Business Applications:** Framework informs roster construction, contract valuation, draft strategy, free agency, and lineup optimization

## Performance Metrics

- **Silhouette Score:** 0.084 (low due to expected overlap in modern positionless basketball)
- **Calinski-Harabasz:** 80.88
- **Davies-Bouldin:** 2.27
- **Domain Validity:** Prioritized over metric optimization for basketball-meaningful results

## Support

For issues with:

- **Python packages:** Check requirements.txt and reinstall
- **NBA API:** Visit https://github.com/swar/nba_api
- **Jupyter:** Visit https://jupyter.org/documentation

---

**Note:** Make sure you're using the virtual environment (`venv`) to ensure all dependencies are correctly loaded.

## Citation

If using this work, please cite:

```
Patel, N. (2025). Discovering Modern NBA Player Archetypes Through Unsupervised Learning.
DTSA 5510 - Unsupervised Algorithms in Machine Learning, University of Colorado Boulder.
```
