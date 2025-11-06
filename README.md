# Flight Performance Analysis using GraphFrames and Databricks

[![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)](https://databricks.com/)
[![Apache Spark](https://img.shields.io/badge/Apache_Spark-E25A1C?style=for-the-badge&logo=apache-spark&logoColor=white)](https://spark.apache.org/)
[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![GraphFrames](https://img.shields.io/badge/GraphFrames-4285F4?style=for-the-badge&logo=apache&logoColor=white)](https://graphframes.github.io/)

## 📋 Overview

A graph-based analytics solution leveraging **GraphFrames** and **Databricks** to analyze flight performance data with over 1 million records. This project transforms traditional tabular flight data into graph structures, enabling advanced network analysis, airport ranking, and delay pattern discovery that would be difficult with conventional SQL queries.

## 🎯 Project Impact

- **Graph-Based Insights**: Unlock complex relationship patterns between airports and flight routes
- **Performance Optimization**: Identify critical delay patterns and bottleneck airports
- **Network Analysis**: Discover hub airports, popular routes, and transfer cities using PageRank
- **Predictive Intelligence**: Determine high-risk routes for delays and optimize scheduling
- **Scalable Processing**: Handle millions of flight records efficiently using Spark's distributed computing

## 🏗️ Architecture
<img width="620" height="268" alt="image" src="https://github.com/user-attachments/assets/317372ed-8ee3-450e-8997-507c3de7ee54" />

```
CSV Data Source → DBFS Storage (Raw/Parquet) → Spark SQL Processing
                                                        ↓
                                            GraphFrames Creation
                                                        ↓
                                Graph Analytics & Visualization
                                    (PageRank, Motif Finding, BFS)
```

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| **Language** | Python |
| **Framework** | PySpark |
| **Platform** | Databricks |
| **Graph Library** | GraphFrames |
| **Processing Engine** | Apache Spark |
| **Storage** | DBFS (Databricks File System) |
| **Format** | CSV, Parquet |

## ✨ Key Features

### GraphFrames Capabilities
- 🔍 **Motif Finding** - Discover complex flight patterns and connections
- 📊 **PageRank Algorithm** - Rank airports by importance and connectivity
- 🔄 **Triangle Count** - Identify closely connected airport clusters
- 🛤️ **Breadth-First Search** - Find shortest paths between cities
- 🎯 **Subgraph Queries** - Filter and analyze specific route segments

### Analysis Features
- ✅ **Delay Analysis** - On-time vs delayed flight statistics
- 🏆 **Airport Ranking** - Most connected and busiest airports
- 🌐 **Route Optimization** - Popular routes and transfer hubs
- 📈 **Performance Metrics** - Delay trends by origin and destination
- 🔗 **Network Relationships** - Complex multi-hop connection patterns

## 📊 Dataset

**Size**: 1,048,576 flight records

**Parameters**:
- Date - Flight date
- Delay - Departure delay in minutes
- Distance - Flight distance in miles
- Origin - Origin airport code
- Destination - Destination airport code

## 🔬 Analysis Questions Answered

1. **Basic Metrics**
   - Total number of airports and trips
   - Longest delay in the dataset
   - Delayed vs on-time/early flight distribution

2. **Delay Patterns**
   - Flights from SFO most likely to have significant delays
   - Destinations with highest delay tendencies
   - Seattle (SEA) departures with significant delays

3. **Network Analysis**
   - Airport importance ranking (PageRank)
   - Most popular flight routes
   - Top transfer cities
   - Relationship patterns through motif finding

## 🚀 Quick Start

### Prerequisites
- Databricks Account ([Community Edition](https://databricks.com/try-databricks) or Paid)
- Basic knowledge of Python and Spark
- Understanding of graph theory concepts (helpful but not required)

### Setup Steps

1. **Login to Databricks**
   - Access your Databricks workspace
   - Navigate to the workspace home

2. **Create Cluster**
   ```
   Cluster Configuration:
   - Runtime: Latest Spark version (3.x+)
   - Worker Type: Standard_DS3_v2 (or similar)
   - Min Workers: 2
   - Max Workers: 4
   ```

3. **Install GraphFrames Library**
   ```
   Compute → Select Cluster → Libraries → Install New
   Maven Coordinates: graphframes:graphframes:0.8.2-spark3.2-s_2.12
   ```

4. **Upload Data Files**
   ```
   DBFS Path Structure:
   /FileStore/tables/raw/
   ├── airport_codes_na.txt
   └── departuredelays.csv
   ```

5. **Import & Run Notebook**
   - Import the provided notebook
   - Attach to your cluster
   - Execute cells sequentially

## 📁 Project Structure

```
FileStore/
└── tables/
    └── raw/
        ├── airport_codes_na.txt      # Airport metadata
        └── departuredelays.csv        # Flight delay records
```

## 🔄 Workflow

1. **Data Ingestion** - Load CSV files into Spark DataFrames
2. **Data Preparation** - Clean and transform data for graph structure
3. **Graph Creation** - Build GraphFrame with vertices (airports) and edges (flights)
4. **Analysis Execution**
   - Run PageRank for airport importance
   - Execute motif finding for pattern discovery
   - Perform BFS for shortest paths
   - Calculate delay statistics and aggregations
5. **Visualization** - Display results and insights

## 🎓 Key Concepts

### Graph Components
- **Vertices** - Airports (nodes in the network)
- **Edges** - Flights (connections between airports)
- **Directed vs Undirected** - Flight routes have direction (origin → destination)

### Algorithms Used
- **PageRank** - Measures airport importance based on incoming connections
- **Triangle Count** - Identifies tightly connected airport groups
- **Motif Finding** - Discovers specific patterns (e.g., A→B→C→A cycles)
- **Breadth-First Search** - Finds shortest route between two cities

## 📚 Learn More

### Official Documentation
- [GraphFrames User Guide](https://graphframes.github.io/graphframes/docs/_site/user-guide.html)
- [Databricks Documentation](https://docs.databricks.com/)
- [PySpark API Reference](https://spark.apache.org/docs/latest/api/python/)
- [Apache Spark GraphX](https://spark.apache.org/docs/latest/graphx-programming-guide.html)

### Tutorials & Resources
- [Graph Analytics with Spark](https://spark.apache.org/docs/latest/graphx-programming-guide.html)
- [PageRank Algorithm Explained](https://en.wikipedia.org/wiki/PageRank)
- [Databricks GraphFrames Examples](https://docs.databricks.com/spark/latest/graph-analysis/graphframes/graph-analysis-tutorial.html)

### Related Topics
- Network Analysis
- Social Network Graphs
- Recommendation Systems
- Route Optimization

## 💡 Use Cases

### Aviation Industry
- Flight delay prediction
- Route optimization
- Hub airport identification
- Scheduling improvements

### Similar Applications
- Social network analysis
- Recommendation engines
- Fraud detection networks
- Supply chain optimization
- Traffic flow analysis

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report issues
- Suggest improvements
- Submit pull requests
- Share your analysis insights

## 📝 License

This project is licensed under the MIT License.

## 🙏 Acknowledgments

- Built on Databricks platform
- Powered by Apache Spark and GraphFrames
- Inspired by network analysis and graph theory principles

---

**Note**: When working with Databricks Community Edition, remember that clusters automatically terminate after 2 hours of inactivity. Always save your work and export notebooks regularly.
