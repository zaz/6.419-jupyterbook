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

# Written Report – 6.419x Module 5

<div class="author"><b>Name:</b> username</div>

```{code-cell}
:tags: ["remove-input"]
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import matplotlib.colors as colors

# data loading and function definitons go here
```

## Problem 2

*(3 points): Provides an explanation of how the correlation was computed.*

**Solution:**


<br>

*(5 points): A map with the two points with correlations marked.*

**Solution:**


<br>

*(2 points): Provides a convincing commentary on why the two marked locations could be correlated.*

**Solution:**


<br>

### Problem 3.a

*(3 points): Provides an explanation of the simulation algorithm, with equations for the evolution of the particle trajectory.*

**Solution:**


<br>

*(2 points):* The end point of each particle is marked by the red dot at the end of its trail.

**Solution:**


<br>

*(3 points):* The two intermediate times (33, 66) are marked by another two red dots in the middle of the particle's trail.

**Solution:**


<br>

*(2 points):* The initial state of the simulation is marked by the end of the trail that has no red dot.

**Solution:**


<br>

### Problem 3.b

**Solution:**


<br>

*(3 points):* **Note: Each plot above shows 3 plots in 1:** 120hrs is marked by the red dot at the end of the particle trail. 72 and 48 are makred by succesive red dots along the particle trail. The starting position for the particle is the end of the particle trail with no dot.

**Solution:**


<br>

*(3 points):* The 3 3-in-1 plots show drift for $\sigma = 10, 20, 30$, respectively.

**Solution:**


<br>

*(4 points):* If search can be initiated immediately, search activities should be concentrated around the area the plane landed. If search takes longer, it should be conducted in the area the debris is forecasted to have drifted to. A good starting point if search is delayed could be [107, 357], the average of my 3 calculations based on feasible standard deviations and $10,000$-point Monte-Carlo simulations, although this could be refined if we have prior information about the standard deviation.

**Solution:**


<br>

### Problem 4

*(1 point)* We will use the squared exponential function because it has nice properties such as smoothness and ease of computation using the kernel method.

**Solution:**


<br>

*(1 point)* The parameters of the kernel function are the standard deviation, $\sigma$, and the lengthscale, $\ell$.

**Solution:**


<br>

*(1 point)* The search space we will use for $\sigma$ is $\{10, 20, 30\}$ because that is a reasonable range of error for an aircraft not equipped with ADS-B GPS or ELT GPS (more modern-equipped aircraft transmit their GPS coordinates and will be exactly locatable, rendering our models mostly moot). The search space we will use for $\ell$ is $\{0.1, 0.5, 1, 5\}$

**Solution:**


<br>

*(1 point)* We will use 50 folds for cross validation.

**Solution:**


<br>

### Problem 6.a

*(2 points):* The end point of each particle at 300 days is marked by the red dot at the end of its trail.

**Solution:**


<br>

*(2 points):* Two intermediate times (100, 200) days are marked by another two red dots in the middle of the particle's trail.

**Solution:**


<br>

*(2 points):* The initial state of the simulation is marked by the end of the trail that has no red dot.

**Solution:**


<br>

*(5 points):* The top plot is for $\sigma = 10$ and the bottom plot is for $\sigma = 20$. There is naturally more variability in the places driftwood ends up with greater variance in the start position, but the general areas are roughly the same and correspond to areas of land that are concave.

**Solution:**


<br>

*(2 points):* Observation stations should be set up on land where the tendrils shown intersect land, namely: San Vicente, Puerto Galera and Barbaza.

**Solution:**


<br>

*(2 points):* Observation stations should be set up on the ocean near the crash site, left of it, and upwards of it on the map shown. Areas marked by shading.

**Solution:**


<br>

### Problem 6.b



*(2 points):* The end point of each particle at 300 days is marked by the red dot at the end of its trail.

*(2 points):* Two intermediate times (100, 200) days are marked by another two red dots in the middle of the particle's trail.

*(2 points):* The initial state of the simulation is marked by the end of the trail that has no red dot. You can visually check that none of these trails are on land.

*(4 points):* The 3 monitoring stations should be placed at Sibuco, Dagupan (on the Lingayen Guld at the top), and Lahad Datu.

*(4 points):* These are the locations with the largest clusters of washed-up particles.

<br>

## Date Cleaning & Boilerplate Code

To replicate my results, the following code must be run before any code above.

### Data Cleaning

Save CSV data in a Numpy compressed array format for easy (and faster) access:

```
import numpy as np
import pandas as pd

# Ocean Flow [x,y flow rate][time][x][y]
OF = np.empty(shape=(2, 100, 555, 504))

for t in range(100):
    OF[0, t] = pd.read_csv(f"OceanFlow/{t+1}u.csv", header=None).T
    OF[1, t] = pd.read_csv(f"OceanFlow/{t+1}v.csv", header=None).T

mask = pd.read_csv(f"OceanFlow/mask.csv", header=None).T.iloc[:,::-1]

np.savez_compressed("OceanFlow.npz", OF=OF, mask=mask)
```

The above only needs to be run once to clean the data; after that, the below must be run in every session before evaluating code snippets above:

### Imports, Functions, and Definitions

```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import matplotlib.colors as colors

# data loading and function definitons go here
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
