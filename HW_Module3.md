---
jupytext:
  cell_metadata_filter: -all
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.14.1
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---

# Written Report – 6.419x Module 3

<div class="author"><b>Name:</b> username</div>

```{code-cell}
:tags: ["remove-input"]
import numpy as np
import pandas as pd
import networkx as nx
import statsmodels.api as sm
import matplotlib.pyplot as plt
import warnings
warnings.simplefilter(action='ignore', category=(FutureWarning, UserWarning))

# data loading/parsing goes here
```

## Problem 1.2

*c. (2 points): How does the time complexity of your solution involving matrix multiplication in part (a) compare to your friend's algorithm?*

**Solution:**


<br>

*d. (3 points): Bibliographic coupling and cocitation can both be taken as an indicator that papers deal with related material. However, they can in practice give noticeably different results. Why? Which measure is more appropriate as an indicator for similarity between papers?*

**Solution:**


<br>

## Problem 2.5

*c. (2 points): Observe the plot you made in Part (a) Question 1. The number of nodes increases sharply over the first few phases then levels out. Comment on what you think may be causing this effect. Based on your answer, should you adjust your conclusions in Part (b) Question 5?*

**Solution:**


<br>

*d. (5 points):  In the context of criminal networks, what would each of these metrics teach you about the importance of an actor's role in the traffic? In your own words, could you explain the limitations of degree centrality? In your opinion, which one would be most relevant to identify who is running the illegal activities of the group? Please justify.*

**Solution:**


<br>

*e. (3 points): In real life, the police need to effectively use all the information they have gathered, to identify who is responsible for running the illegal activities of the group. Armed with a qualitative understanding of the centrality metrics from Part (d) and the quantitative analysis from part Part (b) Question 5, integrate and interpret the information you have to identify which players were most central (or important) to the operation.*

**Solution:**


<br>

*f.2. (3 points):  The change in the network from Phase X to X+1 coincides with a major event that took place during the actual investigation. Identify the event and explain how the change in centrality rankings and visual patterns, observed in the network plots above, relates to said event.*

**Solution:**


<br>

*g. (4 points):  While centrality helps explain the evolution of every player's role individually, we need to explore the global trends and incidents in the story in order to understand the behavior of the criminal enterprise*

*Describe the coarse pattern(s) you observe as the network evolves through the phases. Does the network evolution reflect the background story?*

**Solution:**


<br>

*h. (2 points):  Are there other actors that play an important role but are not on the list of investigation (i.e., actors who are not among the 23 listed above) ? List them, and explain why they are important.*

**Solution:**


<br>

*i. (2 points):  What are the advantages of looking at the directed version vs. undirected version of the criminal network?*

**Solution:**


<br>

*j. (4 points):   Recall the definition of hubs and authorities. Compute the hub and authority score of each actor, and for each phase. Using this, what relevant observations can you make on how the relationship between **n1** and **n3** evolves over the phases. Can you make comparisons to your results in Part (g)?*

**Solution:**


<br>


## Problem 4



## Includes

The code below must be run before any code above.  You will also need to install `pygraphviz` and `pygraphviz-dev`.

```
import numpy as np
import pandas as pd
import networkx as nx
import statsmodels.api as sm
import matplotlib.pyplot as plt
import warnings
warnings.simplefilter(action='ignore', category=(FutureWarning, UserWarning))

# data loading/parsing goes here
```

## Citations

\[1] [Strassen, Volker (1969). "Gaussian Elimination is not Optimal". Numer. Math. 13 (4): 354–356. doi:10.1007/BF02165411. S2CID 121656251][1]

\[2] [Alman, Josh; Williams, Virginia Vassilevska (2020), "A Refined Laser Method and Faster Matrix Multiplication", 32nd Annual ACM-SIAM Symposium on Discrete Algorithms (SODA 2021), arXiv:2010.05846][2]

\[3] [Bachelier, L. (1900a), "Théorie de la spéculation" (PDF), Annales Scientifiques de l'École Normale Supérieure, vol. 3, no. 17, pp. 21–86][3]

\[4] [Henry Small, 1973. "Co-citation in the scientific literature: A new measure of the relationship between two documents" Archived 2012-12-02 at the Wayback Machine. Journal of the American Society for Information Science (JASIS), volume 24(4), pp. 265-269. doi = 10.1002/asi.4630240406][4]


 [1]: https://doi.org/10.1007%2FBF02165411
 [2]: https://arxiv.org/abs/2010.05846
 [3]: http://archive.numdam.org/article/ASENS_1900_3_17__21_0.pdf
 [4]: https://web.archive.org/web/20121202085010/http://polaris.gseis.ucla.edu/gleazer/296_readings/small.pdf
