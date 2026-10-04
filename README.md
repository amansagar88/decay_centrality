# Decay Centrality Analysis

Python notebook for implementing and evaluating **Decay Centrality**
across four network datasets. It includes a custom BFS-based
implementation, a NetworkX-optimized implementation, top-10 node
rankings, presentation-oriented network visualizations, and correlation
comparisons with standard centrality measures.

## Notebook

[**Open the Jupyter Notebook on
GitHub**](https://github.com/amansagar88/decay_centrality/blob/main/decay_centrality%20.ipynb)

> This relative link opens the notebook directly when the README and
> notebook are in the same GitHub repository. If you rename the
> notebook, update the link accordingly.

## What's Included

-   Custom Decay Centrality using breadth-first search (BFS).
-   An alternative implementation using NetworkX shortest-path routines.
-   Top-10 node rankings for each dataset, exported as CSV files.
-   Network visualizations that emphasize higher-ranked nodes using node
    size and color.
-   Pearson, Spearman, and Kendall correlation analysis comparing Decay
    Centrality with Degree, Closeness, Betweenness, Eigenvector, and
    PageRank.
-   Export of combined correlation results to an Excel workbook.

## Datasets

The notebook loads four networks:

-   **Zachary's Karate Club** --- generated through NetworkX.
-   **Dolphins Social Network** --- `dolphins.gml`.
-   **US Political Books Network** --- `polbooks.gml`.
-   **Reachability Network** --- `reachability.txt`, loaded as a
    directed graph.

Place `dolphins.gml`, `polbooks.gml`, and `reachability.txt` in the
notebook's working directory before running it.

## Decay Centrality

For a node (u), the notebook calculates:

\[ C\_`\delta`{=tex}(u) =
`\sum`{=tex}\_{`\substack{v \in V,\;v \ne u\\ d(u,v)<\infty}`{=tex}}
`\delta`{=tex}\^{d(u,v)} \]

where (d(u,v)) is the shortest-path distance from (u) to a reachable
node (v), and (`\delta`{=tex}) is the decay factor. The notebook uses
(`\delta `{=tex}= 0.5) by default. Unreachable nodes do not contribute
to the sum.
