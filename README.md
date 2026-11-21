# Fourier-numerical-computations
Contains code for bounds on the quantity
```math
w_d^{rad}\coloneqq \sup_{f \in \mathcal{H}^d_{rad}} \frac{\lVert f\rVert_{L^2}^2}{\lVert f\rVert_{L^1}\lVert \hat{f}\rVert_{L^1}},
```

where $\mathcal{H}_{rad}^d$
is the space of radial integrable functions such that 
```math
f,\hat{f} \in L^1(\mathbb{R}^d;\mathbb{R})
```

Upper_bound_wd_certified.ipynb, contains code for certifying the supremum 
```math
\sup_{r>0}\left|\sum_{j=1}^Nc_j\mathopen{}\left(\kappa_d(rs_j)-s_j^{-d}\kappa_d(r/s_j)\right)\mathclose{}-\kappa_d(r)\right|
```
for candidates $c \in \mathbb{R}^{N_d}$, $s \in (0,\infty)^{N_d}$, dimensions $d$, read from a SAVED_CANDIDATES.py file. For given $c,s,d$, we  bound the supremum of 
```math
    \mathcal{I}_d(c,s,r)\coloneqq \sum_{j=1}^Nc_j\mathopen{}\left(\kappa_d(rs_j)-s_j^{-d}\kappa_d(r/s_j)\right)\mathclose{}-\kappa_d(r),
```
 over $r >0$.

