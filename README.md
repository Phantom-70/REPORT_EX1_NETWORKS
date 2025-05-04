# CS3205 Assignment 3 - Exercise 1 Report

## Analysis of Traceroute Data

### a) Total Trace Entries
- **Total trace entries:** 3902  
  _(Entries where router identities were not revealed or had invalid RTTs were ignored.)_

---

### b) Unique Router IPs and Statistics
- **Unique router IPs:** 189  
- **Statistics for each router:**  
  - Average RTT from source (Chennai) and standard deviation of RTT were computed.  
  - Data is available in `top_std_routers.csv`.  

#### Top 5 Routers with Highest RTT Standard Deviation:
| IP               | City      | Country Code | Avg RTT (ms) | Std Dev (ms) |
|------------------|-----------|--------------|--------------|--------------|
| 165.90.211.41    | Bamako    | ML           | 301.46       | 187.23       |
| 105.177.8.84     | Monrovia  | LR           | 249.51       | 71.68        |
| 193.251.251.219  | Ashburn   | US           | 20.01        | 50.62        |
| 195.177.8.80     | Modrovia  | LR           | 219.87       | 46.07        |
| 196.46.214.249   | Lusaka    | ZM           | 270.47       | 45.90        |

---

### c) World Map of Router Locations
- **Visualization:** `router_map.png`  
  - Routers (vertices) are plotted on a world map.  
  - Connections (edges) are color-coded by average latency (see colorbar).  
  - Routers within 50 km of each other are merged into a single vertex.  

---

### d) Latency vs. Distance Scatter Plot
- **Visualization:** `latency_distance_plot.png`  
  - **X-axis:** Physical distance (haversine) between routers.  
  - **Y-axis:** Latency of the edge.  
  - **Correlation coefficient:** 0.201  
  - **Linear regression:** \( y = 0.0027x + 11.9253 \)  

---

### e) Per-Packet Load Balancing
- **Total load-balanced hops observed:** 544  
- **Details:** Locations and ISPs for these hops are provided in `load_balanced_hops.csv`.  

---

### f) Most Common Routers Outside India
| IP               | City       | Country Code | ISP          | Occurrences |
|------------------|------------|--------------|--------------|-------------|
| 64.233.174.119   | Johannesburg | ZA          | Google LLC   | 3           |
| 192.178.251.164  | Mombasa    | KE          | Google LLC   | 3           |
| 192.178.251.144  | Mombasa    | KE          | Google LLC   | 3           |
| 192.178.251.110  | Mombasa    | KE          | Google LLC   | 3           |
| 108.170.234.255  | Mombasa    | KE          | Google LLC   | 3           |
| 192.178.251.100  | Mombasa    | KE          | Google LLC   | 3           |
| 192.178.97.114   | London     | GB          | Google LLC   | 2           |
| 72.14.238.165    | London     | GB          | Google LLC   | 2           |
| 192.178.97.188   | London     | GB          | Google LLC   | 2           |
| 192.178.97.48    | London     | GB          | Google LLC   | 2           |

**Key Observation:**  
Google LLC routers in **Mombasa (KE)** and **London (GB)** appear most frequently across paths to African destinations.

---

## Files Attached
1. `top_std_routers.csv` – Statistics for routers (avg RTT, std dev).  
2. `router_map.png` – World map visualization of routers and connections.  
3. `latency_distance_plot.png` – Scatter plot of latency vs. distance.  
4. `load_balanced_hops.csv` – Details of load-balanced hops.  

--- 

**Note:** For implementation details or additional data, refer to the Jupyter notebooks in the `ex1` folder.  
