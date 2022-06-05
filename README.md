# Data Visualization [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/tzaffi/dataviz/master)

Some Data Visualization Examples - all bindered 

## `FlowSankey` 

Show funnels using Plotly's Sankey Plot.

![image](https://user-images.githubusercontent.com/291133/82733970-a5b88a80-9ce5-11ea-9902-145caade8fdf.png)

## `TraceAggregator`

Aggregate flows to produce inputs for `FlowSankey`. EG:

```python
import random
from random import sample

romantic_stages = ["meet", "dislike", "like", "hate", "love", "break up", "polyamourous"]

traces = []
for i in range(1000):
    traces.append(romantic_stages[0:1] \
            + [romantic_stages[i] for i in sorted(sample([1, 2, 3, 4, 5, 6], random.randint(0, 6)))])
            
ta = TraceAggregator(traces)
fsk = FlowSankey(*ta.agg(), title_text="Romantic Life")
fsk.build()

```

produces something like:

![image](https://user-images.githubusercontent.com/291133/82744037-4ab48100-9d41-11ea-876d-b6a6ab922040.png)

## Scatter Plots

<img width="973" alt="image" src="https://user-images.githubusercontent.com/291133/172035180-89e81704-0f69-4f48-87b5-c9c273d08994.png">

