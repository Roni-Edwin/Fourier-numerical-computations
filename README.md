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


The second notebook, Updated_Upper_bounds_for_wd.ipynb, contains code for certifying the supremum 
```math
\sup_{r>0}\left|\sum_{j=1}^Nc_j\mathopen{}\left(\kappa_d(rs_j)-s_j^{-d}\kappa_d(r/s_j)\right)\mathclose{}-\kappa_d(r)\right|
```
for candidates $c \in \mathbb{R}^{N_d}$, $s \in (0,\infty)^{N_d}$, dimensions $d$, read from a .py file. For given $c,s,d$, we naively bound the supremum of 
```math
    \mathcal{I}_d(c,s,r)\coloneqq \sum_{j=1}^Nc_j\mathopen{}\left(\kappa_d(rs_j)-s_j^{-d}\kappa_d(r/s_j)\right)\mathclose{}-\kappa_d(r),
```
 over $r >0$ naively by first bounding the tail, so $r>R$ using decay estimates for the Bessel functions. We then taking a mesh $r_0=0<r_1<\cdots< r_n=R$. On each interval $[r_i,r_{i+1}]$, we write
```math
   D(t)\coloneqq H((1-t)r_i+tr_{i+1})-((1-t)H(r_i)+tH(r_{i+1}))
```
 and expanding about a stationary point $t_0$, 
 ```math
   \left| D(t)-D(t_0)\right|=\left|\int_{t_0}^tD'(s)\textup{d}s\right|=\left|\int_{t_0}^t\,\int_{t_0}^{s} D''(u)\textup{d}u\textup{d}s\right|\le \sup_{ [0,1]}|D''|=\left[\frac{s^2}{2}-t_0s\right]_{t_0}^t
```
giving
```math
   \left| D(t)-D(t_0)\right|\le \mathopen{}\left(\frac{t^2}{2}-t_0t+\frac{t_0^2}{2}\right)\mathclose{}\sup_{ [0,1]}|D''|=\frac{(t-t_0)^2(r_{i+1}-r_i)^2}{2}\cdot \sup_{r \in [r_i,r_{i+1}]}|H''(r)|.
```
 Choosing the endpoint closer to $t_0$, so $|t-t_0|\le 1/2$ then implies 
 ```math
     \sup_{r \in [r_i,r_{i+1}]}|H(r)|\le \max(|H(r_i)|,|H(r_{i+1}|)+\frac{(r_{i+1}-r_i)^2}{8}\sup_{r \in [r_i,r_{i+1}]}|H''(r)|.
```
 Combining this with the tail bound gives us the upper bound for the relevant supremum.

 For the second derivative of $\kappa_d$, Recall that
```math
\kappa_d(r)
=\Gamma\left(\frac d2\right)(\pi r)^{-\nu}J_\nu(2\pi r),
\qquad \nu=\frac d2-1.
```
The Bessel differentiation identity
```math
\frac{d}{dz}\left(z^{-\nu}J_\nu(z)\right)
=-z^{-\nu}J_{\nu+1}(z)
```
gives, for $r>0$,
```math
\kappa_d'(r)
=-2\pi\Gamma\left(\frac d2\right)
(\pi r)^{-\nu}J_{\nu+1}(2\pi r).
```
Using
```math
\kappa_{d+2}(r)
=\Gamma\left(\frac d2+1\right)
(\pi r)^{-\nu-1}J_{\nu+1}(2\pi r),
\qquad
\Gamma\left(\frac d2+1\right)
=\frac d2\Gamma\left(\frac d2\right),
```
we obtain
```math
\kappa_d'(r)
=-\frac{4\pi^2r}{d}\kappa_{d+2}(r).
```
Differentiating once more,
```math
\begin{aligned}
\kappa_d''(r)
&=-\frac{4\pi^2}{d}\kappa_{d+2}(r)
  -\frac{4\pi^2r}{d}\kappa_{d+2}'(r)\\
&=-\frac{4\pi^2}{d}\kappa_{d+2}(r)
  +\frac{16\pi^4r^2}{d(d+2)}\kappa_{d+4}(r).
\end{aligned}
```

Thus
```math
\boxed{
\kappa_d''(r)
=-\frac{4\pi^2}{d}\kappa_{d+2}(r)
+\frac{16\pi^4r^2}{d(d+2)}\kappa_{d+4}(r).
}
```

The identity extends to $r=0$ by continuity. Since
$\kappa_m(0)=1$, it gives
```math
\kappa_d''(0)=-\frac{4\pi^2}{d}.
```



