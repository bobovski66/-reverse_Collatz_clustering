# Collatz Towers Analysis

## Overview
This repository contains an in-depth analysis of the Collatz map using **topological data analysis (TDA)**. The core idea is to investigate the **tower structures** formed by applying the Collatz transformation iteratively and analyzing their connections through **2-adic valuations**, **mod-3 classes**, and **KeplerMapper visualizations**.

## Problem Statement
The Collatz function is defined as:
$$
C(n) = \begin{cases}
    \frac{n}{2}, & n \equiv 0 \mod 2 \\
    3n+1, & n \equiv 1 \mod 2
\end{cases}
$$
Instead of analyzing the standard trajectory of numbers, we focus on the **reverse Collatz process**, examining the inverse map:
$C^{-1}(n) = \{2n, \frac{n-1}{3} \textrm{ if } n-1 \equiv 0 \mod 3 \}$
Each number **n** can be associated with a **tower structure**:
$C(n) = 2^{v_2(3n+1)} \cdot w$
where $v_2(3n+1)$ is the **2-adic valuation** of $3n+1$, and $w$ is an odd number.

By studying these towers, we analyze **how different numbers map to each other** and how their topological structures emerge.

## Methodology
1. **Dataset Generation**
   - Compute the 2-adic valuation \( v_2(3m+1) \) for numbers \( m \) in a given range.
   - Identify towers \( 2^k w \) and classify them by mod-3 classes.
   - Construct the **backward step graph**, where edges represent numbers mapping backward in the Collatz process.

2. **Topological Data Analysis (TDA) with KeplerMapper**
   - Apply **UMAP** for dimensionality reduction.
   - Construct **Mapper graphs** to visualize high-dimensional data.
   - Cluster nodes using **DBSCAN** to detect structural patterns.

3. **PCA & Clustering Analysis**
   - Perform **PCA** on Mapper graphs to analyze structural variation.
   - Use **K-Means clustering** to group similar graph structures.
   - Identify the **most and least clustered numbers** to detect potential attractors.

4. **Network Analysis**
   - Compute **degree centrality** and **betweenness centrality** to identify critical nodes.
   - Analyze mod-3 classes to determine their role in connectivity.
   - Visualize clustering properties to see how local connections form.

## Results & Visualizations
### **1️⃣ Backward Step Graph of Collatz Towers**
![Backward Step Graph](output22.png)
- Each node represents a number in the Collatz process, color-coded by mod-3 class.
- Directed edges indicate valid backward steps, revealing hierarchical structures.

### **2️⃣ PCA-Based Clustering of Collatz Mapper Graphs**
![PCA Clustering](output24.png)
- Principal Component Analysis (PCA) reveals how different Mapper graphs separate in feature space.
- Three distinct clusters emerge, corresponding to different levels of connectivity and structure.

### **3️⃣ Visualization of Most & Least Clustered Nodes in Collatz Backward Graph**
![Clustered Nodes](output25.png)
- **Red nodes**: Most clustered, forming highly connected hubs.
- **Blue nodes**: Least clustered, sparse and isolated numbers.

### **4️⃣ KeplerMapper Graph for d=7, n_neighbors=30**
![Mapper Graph](image.png)
- A complex topology emerges, showing distinct substructures in the Collatz backward graph.
- Nodes are connected based on their structural similarity after UMAP reduction.

**📌 Explore the interactive KeplerMapper visualizations here:**  
   ▶️ **[Collatz Mapper Interface](mapper_outputs/index.html)**

## Conclusion
- **Towers in the Collatz process exhibit structured connectivity**, influenced by **2-adic valuations and mod-3 residues**.
- **Higher-dimensional embeddings capture complex relationships**, while **PCA and clustering reveal distinct structural behaviors**.
- **Certain numbers act as attractors**, forming hubs in the backward graph, while others remain sparsely connected.

## How to Use This Repository
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/collatz-towers-analysis.git
   ```
2. Install dependencies:
   ```bash
   pip install numpy pandas matplotlib networkx umap-learn kmapper
   ```
3. Run the analysis notebooks to reproduce results.

🚀 This project uncovers hidden **topological structures in the Collatz process** using modern data science techniques!

