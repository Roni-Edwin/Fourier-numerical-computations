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

In two parts: The first notebook, Lower_bound_for_wd.ipynb, contains code for certifying reported lower bounds for 
```math
\frac{\left|\left\langle f,g_d\right\rangle\right|^2}{\left\lVert \mathcal{P}_+f\right\rVert_{L^1}^2},
```
where $\mathcal{P}_+$ denotes Projection onto $+1$-eigenspace, for a candidate function $f\in \mathcal{S}(\mathbb{R}^d)$, of the form $f(x)=P(\pi |x|^2)e^{-\pi |x|^2}$ for a polynomial $P(x)$;


The second notebook, Verify_SAVED_CANDIDATES_explained.ipynb, contains code for certifying the supremum 
```math
\sup_{r>0}\left|\sum_{j=1}^Nc_j\mathopen{}\left(\kappa_d(rs_j)-s_j^{-d}\kappa_d(r/s_j)\right)\mathclose{}-\kappa_d(r)\right|
```
for candidates $c \in \mathbb{R}^{N_d}$, $s \in (0,\infty)^{N_d}$, dimensions $d$, read from a SAVED_CANDIDATES.py file. For given $c,s,d$, we naively bound the supremum of 
```math
    \mathcal{I}_d(c,s,r)\coloneqq \sum_{j=1}^Nc_j\mathopen{}\left(\kappa_d(rs_j)-s_j^{-d}\kappa_d(r/s_j)\right)\mathclose{}-\kappa_d(r),
```
 over $r >0$.

