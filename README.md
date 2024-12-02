# tetrex_analysis
Experiments and Analyses done for publication of TetRex


## Contents

Variable k Analysis
1. `runtimes` was done with the cache (k5 regex 13 is slow) and has no complexity info
2. `runtimes_and_complex` was still done with cache but also contains complexity, index query count, and cache hit count
3. `runtimes_no_cache` was run without the cache (duh) and also has complexity info and index counts
4. `runtimes_and_info` was run without cache and also tracks complexity, index queries, pruneings, absorptions, and max pileups

