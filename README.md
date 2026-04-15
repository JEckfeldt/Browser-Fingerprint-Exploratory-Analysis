# Browser Fingerprint Analysis (User-Agent Exploration)

This project explores **user-agent strings** to understand browser/software usage patterns and measure similarity between them.

## Overview

- Analyzed frequency of user-agent strings  
- Visualized top entries across:
  - All software  
  - Browsers  
  - Applications  
  - Bots  
- Measured similarity using:
  - **Levenshtein similarity** (edit distance)  
  - **Jaccard similarity** (token overlap)  

## Dataset

`user_agents.csv` includes:
- `user_agent` — full string  
- `simple_software_string` — simplified label  
- `software_type` — browser / application / bot  
- `times_seen` — frequency  

## Methods

### Levenshtein Similarity
```
similarity = 1 - (edit_distance / max_length)
```

### Jaccard Similarity
- Split strings into tokens  
- Compare overlap between sets  

```
similarity = |intersection| / |union|
```

## Key Takeaways

- A small number of user-agents dominate the dataset  
- Browser strings are highly repetitive (shared prefixes like "Mozilla/5.0")  
- Bots and applications show more structural variation  
- Jaccard similarity better captures meaningful differences than raw edit distance  

## Tech Stack

- R  
- dplyr  
- ggplot2  
- stringdist  
- scales  

## How to Run

1. Install dependencies:
```
install.packages(c("dplyr", "ggplot2", "scales", "stringdist"))
```

2. Place `user_agents.csv` in the project folder  

3. Run the script to generate plots and similarity metrics  

## Future Work

- Clustering similar user-agents  
- Device/browser classification  
- Integration with fingerprinting data  
