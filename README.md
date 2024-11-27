# Mapping the Landscape of Generative AI Research through Web of Science

This project explores the research landscape of Generative AI by analyzing author keywords from papers sourced from the Web of Science (WoS) database for the year 2024. Using keyword co-occurrence networks, this project maps the conceptual framework of Generative AI research, identifies dominant themes, and analyzes emerging trends.

---

## Workflow

### Data Loading and Preprocessing

The dataset was sourced from the Web of Science (WoS) database, focusing on research papers about Generative AI published in 2024. The data was loaded into a Pandas DataFrame, unnecessary columns such as `ISSN` were removed, and null values were dropped to ensure data integrity. 

To facilitate keyword-level analysis, the `Author Keywords` column was split into individual keywords using the `string.split()` method. This was followed by converting all keywords to lowercase using a lambda function and `applymap()` to normalize the data and ensure consistency.

---

### Frequency Analysis

The frequency of each keyword was calculated using the `Counter` class from Python's `collections` module. Keywords were stacked into a single list, and their occurrences were counted. This analysis identified the most frequently used keywords, such as "artificial intelligence" and "chatgpt."

---

### Co-occurrence Network Creation

A co-occurrence network was constructed using `networkx.Graph()`. Each keyword served as a node, and an edge was added between nodes if the keywords co-occurred in the same row. The edges were weighted based on the frequency of co-occurrence, resulting in a comprehensive representation of the relationships between keywords.

- **Graph Statistics**:
  - **Nodes:** 2988
  - **Edges:** 16149

---

### Network Visualization

The co-occurrence network was visualized using `networkx` and `matplotlib`. To highlight the most significant connections, the top 60 nodes with the highest degrees (most connections) were selected for plotting. This visualization revealed key themes and relationships in the dataset, highlighting dominant research areas.

---

### Adjacency Matrix

The adjacency matrix of the graph was calculated to represent the connections between nodes numerically. This matrix was then converted to a dense DataFrame for better readability and further analysis.

---

## Key Insights

1. **Keyword Frequency Analysis**: Keywords like "artificial intelligence" and "chatgpt" were among the most frequently occurring, highlighting major research themes.
2. **Network Visualization**: The co-occurrence network revealed dominant nodes (keywords) and their connections, showing key clusters and relationships in Generative AI research.
3. **Emerging Trends**: The analysis provided insights into how keywords cluster together, indicating areas of active research and potential gaps.

---

## Tools and Technologies Used

- **Python Libraries**: `pandas`, `networkx`, `matplotlib`, `collections`
- **Data Source**: [Web of Science (WoS)](https://www.webofscience.com/)
- **Analysis Techniques**: Frequency distribution, graph-based network analysis, adjacency matrix calculation

---

## Future Work

1. Explore advanced graph-based algorithms for community detection to uncover deeper insights into research clusters.
2. Conduct temporal analysis to track changes in Generative AI research trends over time.
3. Integrate semantic analysis of keywords to better understand contextual relationships between terms.

---

This project combines natural language processing, graph theory, and data visualization to map the conceptual framework of Generative AI research. It offers valuable insights into the dominant themes and trends shaping the field.
