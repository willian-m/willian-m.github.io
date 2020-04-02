---
layout: post
title:  "Overview of Milne coordinates (aka light-cone coordinates)"
date:   2020-03-20 19:09:00 -0300
categories: physics heavy-ion-collisions relativity light-cone-coordinates spatial-rapidity proper-time
---

# Overview of Milne coordinates (aka light-cone coordinates)

In relativistic heavy-ion collisions, it is usual to replace the 
usual coordinate system $(t,z,y,x)$ for the *Milne coordinates*. One of the 
reasons is that the relativistic hydrodynamic equations, which is commonly used
to model the system's evolution, may become simpler in this case.

My aim in this post is to give a feeling of how to interpret the Milne 
coordinates and summarize the main relations between them. First,  its 
definition is given as

<center>
$\begin{align}
\tau & = \sqrt{t^2 - z^2} \newline
\eta_s & = \frac{1}{2} \ln\left(\frac{t+z}{t-z}\right)\,.
\end{align}$
</center>

Throughout this post, I will ignore x and y coordinates because they suffer no
transformation. Thus, all computations will be restricted to the $(z,t)$/$(\tau,\eta_s)$
plane. I should also point out some sources which was invaluable for me:

- Text-book reference:  R. Vogt - Ultrarelativistic Heavy-Ion collisions: 
  Contains examples of the use of Milne coordinates (referred also as light-cone 
  variables) in hydrodynamic equations
- Relativity text-book: S. Weinberg - Gravity and Cosmology: For understanding 
  a bit more the relativity pieces
- [These lecture slides](https://www.physik.uni-bielefeld.de/~borghini/Teaching/Hydrodynamics15/06_09-slides.pdf) by N. Borghini, of U. Bielefeld


$\tau$ is called proper-time. Of course, this is not the usual proper-time 
relation of relativity, but it is closely related. Specifically, it is the
proper-time of a particle with constant velocity in the $z$ direction. 
$\eta_s$ is called spatial-rapidity, since its expression is the rapidity one
with momentum coordinates replaced by position.

One advantage of these coordinates is that it naturally restricts your 
positions inside the light cone. If $|z| > |t|$, then both the proper-time as 
the spatial-rapidity becomes complex numbers, which is outside of our domain.
For this reason, it is also called light-cone coordinates.

This feature hint us that we should interpret these coordinates in a 
space-time diagram. Constant proper-time sets an hyperbole inside the 
light-cone. Constant spatial-rapidity give us a line which is inside the 
light cone as well. Also, negative times are disallowed in these, since these 
would result in an negative argument of the logarithmic in the spatial-rapidity
definition. Thus, only the upper light-cone should be considered.

There is one more step that we should look when considering these coordinates.
Where is the $\tau$ and $\eta_s$ axis. To discover this, one sets $\tau = 0$ 
and obtain the equation $|t| = |z|$, i.e. the $\tau$ axis is exactly the 
light-cones emerging from the origin of the system. And $\eta_s = 0$ will lead
to $z = 0$. Thus the axis of $\eta_s$ coincides with the $z$ axis.

Finally, it is useful to know how to return to the usual coordinate system as 
well
<center>
$\begin{align}
t & = \tau \cosh \eta_s \newline
z & = \tau \sinh \eta_s\,.
\end{align}$
</center>

## Transformation matrix

Now that we have an intuition about the reference frame and now how to 
transform from and to these coordinates, it is time to transform tensors. 
This is be done by computing the matrix
$\Lambda_{\;\mu'}^\nu$, where the prime denotes the index in the Milne 
coordinates, i.e. $\mu = t,\,z$ and $\mu' = \tau,\eta_s$. The transformation 
matrix is defined as

<center>
$\begin{align}
\Lambda_{\;\mu'}^\nu = \frac{\partial x^\nu}{\partial x^{\mu'}} =
    \begin{pmatrix}
        \cosh \eta_s & \tau \sinh \eta_s \\
        \sinh \eta_s & \tau \cosh \eta_s
    \end{pmatrix}\,.
\end{align}$
</center>
$\Lambda_{\;\mu'}^\nu$ will give us how to change coordinates of a covariant 
tensor, i.e. $u_{\mu'} = u_\nu \Lambda_{\;\mu'}^\nu$. We have also the inverse 
transform

<center>
$\begin{align}
\Lambda_{\;\mu}^{\nu'} = \frac{\partial x^{\nu'}}{\partial x^\mu} =
    \begin{pmatrix}
        \frac{t}{\sqrt{t^2 - z^2}} & -\frac{z}{\sqrt{t^2 - z^2}} \\
        -\frac{z}{t^2-z^2} & \frac{t}{t^2-z^2}
    \end{pmatrix}\,.
\end{align}$
</center>

How about contravariant vectors? Well, we just use the inverse matrices! 
For instance,  $u^{\nu'} = \Lambda^{\nu'}_{\;\mu} u^\mu$ Of course,
we will have to write first the transformation matrix as function of $(\tau,\,\eta_s)$

<center>
$\begin{align}
\Lambda_{\;\mu}^{\nu'} = 
    \begin{pmatrix}
        \cosh\eta_s & -\sinh\eta_s \\
        -\frac{1}{\tau}\sinh\eta_s & \frac{1}{\tau}\cosh\eta_s
    \end{pmatrix}\,.
\end{align}$
</center>

Lastly, the verification that 
$\Lambda_{\;\rho'}^\nu \Lambda_{\;\mu}^{\rho'} = \delta^\nu_\mu$ provides a 
good consistency check.

## Metric in Milne coordinates

Another important ingredient when we are dealing with relativity is the metric.
Since the metric is a tensor itself, we can use the above matrices to convert 
the metric in cartesian coordinates to Milne ones. We define 
$\Lambda^{\nu'}_{\;\mu} \equiv (\Lambda^{-1})^{\nu'}\_{\;\mu}$ and the metric 
signature we will be using is $diag(-1,1)$. Let us start by converting the 
fully covariant metric

<center>
$\begin{align}
g_{\mu' \nu'} = \Lambda^\rho_{\;\mu'} \Lambda^\sigma_{\;\nu'}g_{\rho \sigma} = 
\Lambda^T g \Lambda = 
    \begin{pmatrix}
        -1 & 0 \\
        0 & \tau^2
    \end{pmatrix}\,.
\end{align}$
</center>

Now, the fully contravariant one

<center>
$\begin{align}
g^{\mu' \nu'}=\Lambda^{\mu'}_{\;\rho}\Lambda^{\nu'}_{\;\sigma}g^{\rho \sigma} = 
\Lambda^{-1} g (\Lambda^{-1})^T = 
    \begin{pmatrix}
        -1 & 0 \\
        0 & 1/\tau^2
    \end{pmatrix}\,.
\end{align}$
</center>

As a cross check, we have that
$g^{\mu' \nu'} g_{\mu' \nu'} = g^{\mu \nu} g_{\mu \nu} = 2$ as it should be.

## Derivatives

A derivative is nothing less than the subtraction of two quantities computed in
infinitesimally near points (normalized by the distance between them). If the 
way you measure things (which is given by
the metric) is independent of space, the derivative is computed as usual.
But when using Milne coordinates, this is not the case.
Thus, when comparing points, one must account that your "rule" changes with 
position. My aim is not to make a extensive derivation on *covariant* 
derivatives. The one interested can check a relativity book (e.g., S. Weinberg, 
Gravitation and Cosmology, 1972). It is enough to say that, for a fully 
contravariant tensor $T^{\mu \nu \kappa \dots}$, the derivative becomes

<center>
$\begin{align}
\nabla_\rho T^{\mu \nu \kappa \dots} = \partial_\rho T^{\mu \nu \kappa \dots} +
\Gamma^{\mu}_{\rho \lambda}T^{\lambda \nu \kappa \dots} + 
\Gamma^{\nu}_{\rho \lambda}T^{\mu \lambda \kappa \dots} +
\Gamma^{\kappa}_{\rho \lambda}T^{\mu \nu \lambda \dots} + \cdots
\end{align}$
</center>
and for a fully covariant tensor, we have

<center>
$\begin{align}
\nabla_\rho T_{\mu \nu \kappa \dots} = \partial_\rho T_{\mu \nu \kappa \dots} -
\Gamma^{\lambda}_{\mu \rho} T_{\lambda \nu \kappa \dots} -
\Gamma^{\lambda}_{\nu \rho} T_{\mu \lambda \kappa \dots} -
\Gamma^{\lambda}_{\kappa \rho} T_{\mu \nu \lambda \dots} - \cdots\;.
\end{align}$
</center>

$\Gamma^\lambda_{\mu \nu}$ is not a tensor and is called Christoffel symbol or
affine connection. It is the term that corrects the usual derivative
$\partial_\mu$. Although it is not its definition, I find that the easiest way
to compute it, once you have the metric, it is by using the relation

<center>
$\begin{align}
\Gamma^\lambda_{\mu \nu} = \frac{1}{2} g^{\lambda \kappa} 
( \partial_\mu g_{\kappa \nu} + \partial_\nu g_{\kappa \mu}
 - \partial_\kappa g_{\mu \nu})
\end{align}$
</center>

In the case of our metric, we must worry only with Christoffel symbols that 
contains the term $\partial_0 g_{1 1}$ appears (An index 0 means the $\tau$ 
direction and 1 means $\eta_s$ direction). Those are:

<center>
$\begin{align}
\Gamma^{0}_{1,\,1} = \tau \quad \quad \Gamma^{1}_{0,\,1}
                    = \Gamma^{1}_{1,\,0} = \frac{1}{\tau}
\end{align}$
</center>


All others will be 0. If we consider a contravariant vector derivative. We have

<center>
$\begin{align}
\nabla_\tau u^\tau & = \partial_\tau u^\tau \\
\nabla_\tau u^{\eta_s} & = \partial_\tau u^{\eta_s} + u^{\eta_s}/\tau\\
\nabla_{\eta_s} u^{\tau} & = \partial_{\eta_s} u^{\tau} + \tau u^{\eta_s}\\
\nabla_{\eta_s} u^{\eta_s} & = \partial_{\eta_s} u^{\eta_s} + u^{\tau}/\tau\,.
\end{align}$
</center>

And for covariant vectors

<center>
$\begin{align}
\nabla_\tau u_\tau          = \partial_\tau u_\tau \\
\nabla_\tau u_{\eta_s}      = \partial_\tau u_{\eta_s} - u_{\eta_s}/\tau\\
\nabla_{\eta_s} u_{\tau}    = \partial_{\eta_s} u_{\tau} - u_{\eta_s}/\tau\\
\nabla_{\eta_s} u_{\eta_s}  = \partial_{\eta_s} u_{\eta_s} - \tau u_{\tau}
\end{align}$
</center>

I hope that this helped the reader to gain intuition on the use of this metric.
Happy calculations :).