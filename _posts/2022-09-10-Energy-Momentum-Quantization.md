---
layout: post
title:  "A crash course on modern physics: II. Blackbody radiation"
date:   2022-11-02 21:17:00 -0300
categories: physics modern-physics quantum-physics blackbody
---

# A crash course on modern physics: II. Black-body radiation

***TODO: Update this intro***

On the [last post](/_posts/2022-09-08-Charge-Quantization.md), we saw how
the matter of quantization of charge was settled. It was not a discovery per-se.
But rather, a confirmation of a suspicion that was present since Faraday's 
experiments on electrolysis. On another hand, no one suspected that energy and 
momentum transferred in electromagnetic radiation was a discrete phenomena. Originally, 
I had written this post as a review of energy discretization. This inevitably 
pass through the topic of blackbody radiation, which is huge itself. Hence,
I will talk about it before proceeding to a post dedicated to the energy and
momentum discretization.

The books on which I based this post off are the same as in
the last post, but I list them bellow for completeness

- [Tipler, Llewellyn - Física Moderna](https://www.amazon.com/Fisica-Moderna-Paul-Tipler/dp/852162607X/ref=sr_1_1?crid=3PGILPA51SRIO&keywords=Tipler+F%C3%ADsica+Moderna&qid=1662838963&sprefix=tipler+f%C3%ADsica+moderna%2Caps%2C348&sr=8-1)
- [Thornton, Rex - Modern Physics for Scientists and Engineers](https://www.amazon.com/Modern-Physics-Scientists-Engineers-4th/dp/1133103723)
- [Serway, Madison, Moses, Moyer - Modern Physics](https://www.amazon.com/Physics-International-Raymond-Madison-Clement/dp/B010WFFPU2)

Additionally, Rayleigh-Jeans law as well as Planck's law derivation can be found
[here](https://edisciplinas.usp.br/pluginfile.php/48089/course/section/16461/qsp_chapter10-plank.pdf).

The final considerations regarding the modern derivation is partially original,
but the derivation based on Bose-Einstein derivation can be found [here](https://phys.libretexts.org/Bookshelves/Thermodynamics_and_Statistical_Mechanics/Book%3A_Thermodynamics_and_Statistical_Mechanics_(Nair)/08%3A_Quantum_Statistical_Mechanics/8.02%3A_Bose-Einstein_Distribution) and on Thorton's book.



## 1. Classical transfer of energy and momentum of electromagnetic radiation

One of the greatest successes of classical physics was the electromagnetic 
theory. It succeed not only on accurately describing electric and magnetic 
phenomena, but it predicted that light was a form of electromagnetic radiation.
It could also predict light speed in vacuum and other forms of electromagnetic
radiation such as radio waves.

From classical electromagnetism, the energy density associated to an 
electromagnetic field is
<center>
$\begin{align}
u = \frac{1}{2\mu_0}|\vec{B}|^2 + \frac{\varepsilon_0}{2} |\vec{E}|^2
\end{align}$
</center>

If we allow this energy density to change in time (because, e.g. the fields are
waves), we have that
<center>
$\begin{align}
\frac{\partial u}{\partial t} = \frac{1}{2\mu_0} \vec{B}\cdot\frac{\partial \vec{B}}{\partial t}
 + \frac{\varepsilon_0}{2} \vec{E} \cdot \frac{\partial \vec{E}}{\partial t}
\end{align}$
</center>

To simplify, let us consider the fields in vacuum $\rho = 0$  and $\vec{j} = 0$.
We employ Àmpere's law as well as Faraday's lasw and obtain
<center>
$\begin{align}
\frac{\partial u}{\partial t} = -\frac{1}{\mu_0} \vec{B}\cdot \vec{\nabla} \times \vec{E}
 + \varepsilon_0 \vec{E} \cdot \frac{\vec{\nabla} \times \vec{B}}{\mu_0 \varepsilon_0} = -\frac{1}{\mu_0} \vec{\nabla}\cdot\left( \vec{E} \times \vec{B}\right)
\end{align}$
</center>

This can be written in the form of a continuity equation
<center>
$\begin{align}
\frac{\partial u}{\partial t} + \vec{\nabla} \cdot \vec{S} = 0\,,
\end{align}$
</center>
where $\vec{S}$ is called the *Poynting vector*, defined as
<center>
$\begin{align}
\vec{S} \equiv \frac{1}{\mu_0} \vec{E} \times \vec{B}\,.
\end{align}$
</center>
It should be interpreted as the flux of energy density of the electromagnetic fields.

We are interested in the simplest of the cases of plane waves in
the vacuum, which are given 
by $\vec{E}(\vec{x},t) = \vec{E}_0 \cos\left(\vec{k}\cdot \vec{x} - \omega t \right)$ and $\vec{B}(\vec{x},t) = \vec{B}_0 \cos\left(\vec{k}\cdot \vec{x} - \omega t \right)$. By employing 
Ampere's Law, one obtain that the magnitude of the plane waves obey the simple 
relationship $\hat{k} \times \vec{E}_0 = c \vec{B}$, where $c$ is the 
light-speed in vacuum.

Thus, the mean energy density contained in one wave-length will be
<center>
$\begin{align}
\left\langle u \right \rangle 
= \frac{1}{\lambda}\int_0^\lambda u(\vec{x},t)\, dx 
= \frac{\varepsilon_0}{2} |\vec{E}_0|^2\,,
\end{align}$
</center>
and the mean flux of energy
<center>
$\begin{align}
\left\langle \vec{S} \right \rangle 
= \frac{1}{\lambda}\int_0^\lambda \vec{S}(\vec{x},t)\, dx 
= \frac{1}{2 c \mu_0} |\vec{E}_0|^2 \hat{k} 
=  c \left\langle u \right\rangle \vec{k}\,.
\end{align}$
</center>

The above gave rise to how energy was transferred classically: an object 
exposed to electromagnetic radiation would be absorbing energy in a continuous
fashion, as one could clearly see from the Poynting vector expressions above.
The amount of energy transferred would be determined by the light intensity 
$I \equiv c \langle u \rangle$, which, in principle, could be arbitrarily low.

## 2. The black body radiation

Since humans learned how to melt metals, we learned that "hot things glow". 
If we heat, let's say, iron, it will become first a dark red and, as we go
to higher temperatures going through orange, yellow until we reach blue tinted
white. The object being heated seems also to glow brighter the hotter it gets.
If we describe the above for a child, it most likely will ask: why does it 
happens? Why these colors? And why it glows brighter for hotter temperatures?
These were precisely some of the questions physicists were trying to address
at the end of XIX century.

Lets start with a thought experiment. We consider one object at a temperature 
$T$ in the vacuum inside a cavity that has a perfectly reflecting wall. Inside 
it, the cavity there is a complete vacuum and we will suppose there is no 
radiation initially inside it.
Hence, the surroundings of this object is at absolute zero (implying that such
initial condition is impossible to achieve in practice --- hence why this is a 
thought experiment). The zeroth law of thermodynamics says that heat should be
transferred from this object to its surrounding, until the temperatures get 
equalized. But since we are at a perfect vacuum, heat transfer cannot happen
via thermal conduction. The only way is through radiation of electromagnetic
radiation. Thus, all bodies must emit electromagnetic radiation. The frequency
they emit must depend on their temperature, as to explain why only "hot" objects
glows at visible light.

As the radiation bounces in the wall, it fills the cavity with radiation. Some 
of this radiation can be reabsorbed by the body inside the cavity. The body will
cooldown until a temperature $T_f$ where the rate in which it absorbs radiation
is the same as the emission rate. At this point we may say it is thermalized 
with the radiation around it.

By the above thought experiment, we can see that if a given temperature the body
is a good emitter, it must also be a good absorber. And in principle this could
depend on the details of the object in question. To simplify the study, it was
proposed the concept of an ideal black-body as an object that, when exposed to
electromagnetic radiation, it is capable of absorbing it entirely. A very good
realization of such idealized constructed is a cavity with a small hole  on it.
A light ray that enters the cavity through the hole is very unlikely to exit
through it again. Thus, this hole will be a nearly perfect absorber. And by the
discussion above, also a nearly ideal emitter. Notice that all of this holds 
regardless of the material of cavity, making it a great tool to study blackbody
radiation.

## 2.1 Rayleigh-Jeans and the ultraviolet catastrophe

In June of 1900 Lord Rayleigh used the classical electromagnetism theory to 
obtain an expression for the spectrum of light emitted by a blackbody. Later,
in 1905 (ironically, after the blackbody problem had already been solved by 
Planck, as we will show later), missing numerical factors were inserted by 
Sir James Jeans. We will briefly show the derivation of what came to be known
as the Rayleigh-Jeans formula.

The core idea is that radiation inside the cavity will bounce off its walls and
form standing waves. As in any reflection phenomena, nodes will happen in the 
reflection surface. For simplicity sake, let's assume a cubic cavity of side $L$.
If indeed a standing wave is formed inside the cavity, it will follow the shape
<center>
$\begin{align}
\vec{E} = 2 \vec{E}_0 \sin \left(\vec{k}\cdot\vec{x}\right) \sin\left(\omega t\right)\,.
\end{align}$
</center>

At the edges, $\vec{E} = 0$. One can show, by picking standing waves 
perpendicular to each face of the cavity, that only discrete modes can be 
traveling inside this cavity, given by
<center>
$\begin{align}
\vec{k} = \frac{2\pi}{L}\left(\mathcal{l}\hat{x} + m\hat{y} + n\hat{z}\right)\quad l,\, m,\, n \ge 0\,.
\end{align}$
</center>

Using the wave equation
<center>
$\begin{align}
\nabla^2 \vec{E} = \frac{1}{c^2} \frac{\partial^2\vec{E}}{\partial t^2}
\end{align}$
</center>
one can find the relation between the wave number $\vec{k}$ and frequency $\nu$
as
<center>
$\begin{align}
\left|\vec{k}\right|^2 = \frac{\pi^2}{L^2}\left(l^2+m^2+n^2\right) = \frac{4\pi^2}{c^2} \nu^2
\end{align}$
</center>

An experiment will not be able to detect light of a specific frequency, but rather
in a (hopefully small) frequency window $\delta\nu$ around the target frequency $\nu$.
Imagine that $\nu/\delta\nu \sim 10^{-3}$. For visible light, this implies 
$\delta\nu \sim 10^{11}$ Hz. Mean while, a typical cavity will have $L \sim 1$ m.
Hence, changing the standing wave mode by one unit will change the frequency by
something of the order of $c/L \sim 10^{8}$ Hz --- three orders of magnitude smaller than
the sensitivity we estimated. That is, the spacing between the modes is small
enough that is reasonable to treat the spectrum as a continuum of modes rather
than a continuum.

By treating the modes as a continuum, we can map the quantities $c l/2L$, $c m/2L$
and $c n/2L$ to variables $x$, $y$ and $z$ respectively. The dispersion relation
above can then be seen as just a change of variables $\nu = \sqrt{x^2 + y^2 + z^2}$.
To complete the change of variables, we introduce $\tan\phi = x/y$ and 
$\tan \theta = z/\sqrt{x^2+y^2}$. We obtain then exactly the kind of change of
variables from cartesian coordinates to spherical ones --- which we already know
the Jacobian! Hence, if know consider a small cube 
$dx\, dy\, dz = c^3/8L^3 dl\, dm\, dn$
in the coordinates of standing wave modes, in the frequency space this will be
given by $\nu^2 \sin \theta\; d\phi d\theta d\nu$.

We are interested in the number of modes $dN$ that are in the the frequency 
interval $d\nu$. This will then be given by 
<center>
$\begin{align}
dN = \int_{\rm All\, directions} dl\, dm\, dn 
= \frac{8 L^3}{c^3} \int_0^{\pi/2} \int_0^{\pi/2} \nu^2 \sin \theta\; d\phi d\theta d\nu
= \frac{4\pi L^3}{c^3} \nu^2 d\nu
\end{align}$
</center>

Electromagnetic radiation has two polarization modes, each one of these will have
the same density of modes $dN/d\nu$ as expressed above. Hence for purposes of
counting modes contributing for the energy density $u$, we must use twice the 
above value. The contribution $du$ to the total energy density given by 
frequencies in the range $[\nu,\,\nu+d\nu]$ is
<center>
$\begin{align}
du = \frac{\varepsilon_0}{2} \left|\vec{E}_0\right|^2 2 dN 
= \varepsilon_0 \left|\vec{E}_0\right|^2 \frac{4\pi L^3}{c^3}\nu^2\, d\nu\,.
\end{align}$
</center>
But equipartion of energy tell us that each degree of liberty must be associated
to a factor $kT$. That is, the energy density factor 
$\varepsilon_0 \left|\vec{E}_0\right|^2 L^3/2$ should be replaced with $kT$. Hence,
the energy density per frequency will be given by
<center>
$\begin{align}
\frac{du}{d\nu} = \frac{8\pi}{c^3} kT\, \nu^2\,.
\end{align}$
</center>

This expression predicts that the energy density inside the cavity grows with 
a cubic power of the frequency. Since, as far as is known, there is no such 
thing as the highest possible frequency, to obtain the total energy density
inside the cavity, one should integrate from zero to infinity. The result
diverges, which is a physical impossibility. The reason being that,
for high frequencies, typically those in ultra-violet, the above expression
fails to describe the spectrum measured experimentally.

The skeptical may say that we don't measure the cavity energy density, and
we should concern solely with what leaves the cavity through the small aperture.
Here one must remember that $\vec{S} = u c \hat{k}$. Since radiation is 
distributed is distributed in an uniform way, one should compute the 
average $\langle \vec{S} \cdot \hat{x} \rangle$, where $\hat{x}$ is the normal to the
small aperture. Thus, one gets
<center>
$\begin{align}
\langle \vec{S} \cdot \hat{x} \rangle 
= \frac{1}{4\pi}\int_0^\pi \int_{-\pi/2}^{\pi/2} u c \hat{k} \cdot \hat{x} \sin \theta\, d\varphi
\, d\theta
= \frac{u c}{4\pi} \int_0^\pi \int_{-\pi/2}^{\pi/2} \sin^2\theta cos \varphi d\varphi
\, d\theta = u\frac{ c}{4}
\end{align}$
</center>

Hence, the difference between $u$ and the energy flux through the aperture is
just a factor $c/4$. Hence, since no one was obliterated by ultraviolet light 
(as well as shorter wave-length radiation) coming out of a small aperture of 
a furnace, something is indeed wrong with Rayleigh-Jeans theory.

## 2.2 Wien Law's

Rayleigh surely was not the only one working on the blackbody problem. Wilhelm 
Wien was one scientist who managed to obtain a reasonable success on the 
description of the ultraviolet sector --- precisely where Rayleigh failed. He 
proposed, based on empirical observations, that the energy density should follow
<center>
$\begin{align}
u(\nu,\, T) = A \nu^3 e^{-\beta \nu/T}\,,
\end{align}$
</center>
where $A$ and $\beta$ are constants. The drawback of such proposal was that, in
the infrared region, Wien's description failed. Despite this, it present some 
successes.

First, if one tries to predict the wavelength of peak emission, one can do
<center>
$\begin{align}
\left.\frac{\partial u(\nu,\, T)}{\partial \nu}\right|_{\nu_{\rm max}} 
= \left. A \nu^2 \left(1 -\frac{\beta \nu}{T}\right) e^{-\beta \nu/T} \right|_{\nu_{\rm max}}& = 0 
&\Rightarrow& & \frac{1}{\beta} = \frac{\nu_{\rm max}}{T} = {\rm constant}\,,
\end{align}$
</center>
Using $\nu = c/\lambda$, one arrives at what come to be known as 
*Wien's displacement law*
<center>
$\begin{align}
\lambda_{\rm max} T = {\rm constant}
\end{align}$
</center>
This actually holds even after the complete blackbody spectra was understood and
has, to this day, applications both technological as scientific. By measuring
the spectra of stars, scientists can determine their temperature by determining
the wavelength where the spectrum peaks. The same can be used to determine the
temperature of a furnace in steel industry.

Another success case is the total flux (that is, power irradiated per 
unit of area) emitted by the blackbody. This can be obtained by integrating
$\langle \vec{S} \cdot \hat{x} \rangle$ over the entire spectra. Using 
integration by parts, one can notice that, for $\nu \ge 1$
<center>
$\begin{align}
\int_0^\infty A \nu^n e^{-\beta \nu/T} d\nu = n \frac{T}{\beta} \int_0^\infty A \nu^{n-1} e^{-\beta \nu/T}\, d\nu\,.
\end{align}$
</center>
By applying this formula recurrently, it is possible to write
<center>
$\begin{align}
\int_0^\infty \nu^n e^{-\beta \nu/T} d\nu = n! \left(\frac{T}{\beta}\right)^n \int_0^\infty A e^{-\beta \nu/T}\, d\nu = n! \left(\frac{T}{\beta}\right)^{n+1} A\, .
\end{align}$
</center>

Hence, it is possible to write 
<center>
$\begin{align}
F = \int_0^\infty \langle \vec{S} \cdot \hat{x} \rangle\, d\nu = \frac{3}{2}\frac{A c}{\beta^4} T^4 = \sigma T^4\,.
\end{align}$
</center>
This is known as the Stefan-Boltzmann law, that were derived some years 
previously. Of course, since at low wavelength Wien's expression underestimates
the actual expression, the value $3 A/2 A c$ actually underestimate the
value of Stefan-Boltzmann constant.

## 2.3 Planck's solution

So far, we have seen that by the end of XIX century the puzzle of blackbody 
radiation spectrum had two expressions that worked in two different regimes:
long wavelengths (Rayleigh-Jeans) and short wave lengths (Wien's exponential 
law). The situation is summarized in the figure below, where we show the 
blackbody spectrum for a blackbody at 1500 K, compared to Wien's exponential
law and Rayleigh-Jeans law. The dashed line denotes the wavelength of peak 
emission, as predicted by Wien. The careful reader will notice that, albeit 
it is indeed very close to the actual experimental maximum, it is not 
completely accurate --- which is not a surprise, given that Wien's exponential
law is not completely accurate.

![Blackbody spectrum compared to Wien's exponential law and Rayleigh-Jeans law](/assets/blackbody-spectrum-1500k.png)

The solution came by the end of 1900, when he proposed an expression for the
blackbody radiation. He knew Wien's law and had access of experimental data
that showed the linear dependency with temperature for low wavelength (there is
no indication he was aware of Rayleigh work). Based on this, he interpolated
the two regimes to obtain
<center>
$\begin{align}
u(\nu,\,T) = \frac{8\pi h \nu^3}{c^3}\left(\frac{1}{e^{h\nu/kT}-1}\right)\,,
\end{align}$
</center>
where $h$ came to be known as Planck constant. Later, he also proposed a 
theoretical explanation to it. I will not follow exactly his explanation, but
a simpler variation from it.

His initial proposal was to model the wall of the cavity as composed of many
small charged oscillators. Classically, these accelerated charges would
emit radiation with the same frequency of their oscillation and with intensity 
proportional to its amplitude. The oscillators amplitude would fall continuously
as it emit radiation. Here planck change the prescription and said 
that these oscillators could only have discrete energy levels given by
<center>
$\begin{align}
E(\nu) = n h \nu\,.
\end{align}$
</center>
Planck's idea was that, after the calculation was complete, he could take the 
limit $h\to0$ and recover the continuous energy spectrum of the oscillator. To
explain why the blackbody has a continuum spectrum, he proposed that each 
oscillator has its own frequency. The collections of the large amount of 
oscillators would give the impression of a continuous spectrum --- just like
the collections of atoms give us the impression of a continuous matter.

The amplitude of the oscillator does not reach zero because the wall also 
absorbs radiation. Therefore, it will reach a situation of thermal equilibrium
with the medium surrounding it. Since they reach a thermal equilibrium, the 
mean energy density on the oscillators in the wall should match the mean energy
in the radiation field, that is, the energy should be equally partitioned between
radiation and the cavity wall. Assuming the energy of the oscillators follow the
Boltzmann distribution, the mean energy will be given by
<center>
$\begin{align}
\langle \varepsilon \rangle = \frac{\sum_{n=0}^\infty n h \nu e^{-\frac{n h \nu}{kT}}}{\sum_{n=0}^\infty e^{-\frac{n h \nu}{kT}}}
= -\frac{1}{Z(\beta)} \frac{\partial Z(\beta)}{\partial \beta }\,,
\end{align}$
</center>
where $Z(\beta)$ is called the partition and is given by
<center>
$\begin{align}
Z(\beta) = \sum_{n=0}^\infty e^{-\beta n h \nu} = \frac{1}{1-e^{-\beta h \nu}}
\end{align}$
</center>
and $\beta = 1/kT$. Notice that in the above expression we used that this is
a sum of a geometric series. Hence, the mean energy will be given by
<center>
$\begin{align}
\langle \varepsilon \rangle = \left(1-e^{-\beta h \nu}\right)\cdot \frac{ h\nu\, e^{-\beta h\nu}}{\left(1-e^{-\beta h \nu}\right)^2}
= \frac{h\nu}{e^{\beta h \nu}-1}\,.
\end{align}$
</center>

We return to the Rayleigh derivation and remember that we replaced the energy 
density of each wave mode, given by 
$\varepsilon_0 \left|\vec{E}_0\right|^2 L^3/2$, was replaced with the wave with 
$kT$. But we have seen above the mean energy for each oscillator is not $kT$, 
but rather $h\nu/(e^{\beta h \nu}-1)$. Hence, we should use this last value to
replace it. One obtains
<center>
$\begin{align}
\frac{du}{d\nu} = \frac{8 \pi}{c^3} \frac{h\nu^3}{e^{\beta h \nu}-1}
\end{align}$
</center>
Notice this is exactly the same expression Planck found empirically. We cannot
take the limit $h\to0$, under the penalty of getting $du/d\nu = 0$, which would
implies the absurd conclusion of no emission. Rather, $h$ can be obtained from
a fit to the blackbody radiation spectra. The natural conclusion of this 
derivation was that electromagnetic radiation was emitted in discrete packs of 
energy, given by
<center>
$\begin{align}
E = h \nu
\end{align}$
</center>
These packs of energy is what we known today as the photon. Planck's solution
is usually shown as the seed for the reborn of the corpuscular theory of light,
which led to its wave-particle duality description and the born of quantum 
mechanics.

# 3. Modern view on the Planck's Law derivation.

---
> Disclaimer: This section is a more advanced and less self-contained. It requires
> the reader to be familiar with concepts of statistical physics which I did not
> covered yet (and I don't know if I will make a post about it.)

---

Albeit the derivation above get us to the right final expression and uses the
same hypothesis Planck assumed, we know today this path is not completely valid.
With today atomic models, we know that the oscillator in the walls of the cavity
are the electrons orbiting the atomic nuclei. We also know these electron's can
occupy only discrete energy levels. And indeed, when an electron is in an 
excited state and transitions to a lower state, it does so by emitting light 
with frequency $\nu = \Delta E/h$, where $\Delta E$ is the difference of energy
between the levels that is carried away by the radiation. The problem is, 
contrary to Planck's hypothesis that each oscillator had its own frequency $\nu$,
we actually have a discrete set of frequencies $\nu$ that all oscillators may
emit. The spectrum should not be continuum given the modern atomic theory and
Planck's hypothesis.

At the hearth of the issue is that Planck resorted to trying to explain the 
blackbody radiation by looking at the interaction of radiation with the cavity
wall. If this is indeed what happens, by changing the wall material we should
see different behaviors --- which goes against the initial supposition. 
Therefore a correct derivation should only be concerned with the radiation 
inside the cavity, since the cavity wall should not affect the blackbody 
spectra.

The way to correctly derive Planck's law is using using the wave-particle 
duality and the indistinguishably between particles: two concepts that were not 
developed yet fully developed in Planck's time and one can even argue that 
were developed because of his work.

Imagine that we have two photons, both in the same energy
state $E(\nu)$ and same polarization. In classical physics, one can "tag" one 
these particles and distinguish it from the other. Thus, if we permute the two 
particles, you obtain a different state. This does not happens for quantum 
particles. The two photons are indistinguishable and permuting them lead to the
same state.

Let us consider that for a given energy $E_\nu$, we have $g_E$ possible states. 
This number is due to the different polarizations of light plus the 
combination of all the possible standing wave modes that results in the same
frequency --- and by means of $E = h\nu$ the same energy. We want to be able
to predict the probability $P(n_E)$ of finding $n_E$ particles in this state.

We start by asking how many configurations this energy level can hold?
This is a combinatorial problem and solving it would be a lengthy process, 
making this lengthy post even longer. Hence, we will just state that the 
answer is given by
<center>
$\begin{align}
W_{E} = \frac{\left(n_E + g_E - 1\right)!}{n_E!(g_E-1)!}
\end{align}$
</center>

The total the system has can be obtained as $W = \prod_{E} W_E$. But not of all 
these states are likely to occur. We must employ the second law of 
thermodynamics, i.e. use the above expression to compute the system's entropy
in a given state and search the state that maximizes it. The entropy is given by
$S = k \ln W$. We will employ the Stirling approximation $\ln n! \cong n \ln n - n$
and obtain
<center>
$\begin{align}
\ln S = k \sum_E (n_E + g_E - 1)\ln((n_E + g_E - 1)) - n_E - g_E + 1 - n_E \ln n_E + n_E + \ln [(g_E-1)!]\,.
\end{align}$
</center>
However, when we perform such a sum, we are not considering any kind of 
constrain, when we should actually impose that the distribution of states should
be such as respect the total energy constraint $E_{\rm Tot} = \sum_E n_E E$ and
the total particle number $N = \sum_E n_E$ (this last requirement will be 
relaxed later, since photons can be emitted and absorbed). These two 
requirements are satisfied using Lagrange multipliers, i.e. adding the terms
$\alpha(N-\sum_E n_E) + \beta(E_{\rm Tot }\sum_E n_E E)$ to the expression above.

To find the maximum entropy, we derive the expression we obtained after taking into
account the lagrange multipliers with respect to $n_E$ and equate it to zero. The 
equation to solve will be
<center>
$\begin{align}
\sum_E \ln(n_E + g_E - 1) - \ln n_E  - \alpha -\beta E = 0\,.
\end{align}$
</center>

Each one of the terms of this sum must be zero. Isolating $n_E$, we will obtain
<center>
$\begin{align}
n_E = \frac{g_E}{e^{\beta_E E + \alpha} -1}\,,
\end{align}$
</center>
where we assumed $g_E \ll 1$ and hence $g_E -1 \cong g_E$. Particles that 
occupies states according to the distribution above are said to follow the
*Bose-Eintein* statistics and are called Bosons. For the special case of 
photons in the cavity, the number of photons are not conserved and we set 
$\alpha = 0$.

It remains to count the degeneracy number of the state with energy $E$. Since
$E = h \nu$, it is enough to repeat the counting of states with frequency 
between $\nu$ and $\nu+d\nu$ that were done in the Rayleigh-Jeans section, 
which results in $g_E = 8\pi L^3/c^3 \nu^2$. The total energy will be then be 
given by
<center>
$\begin{align}
\frac{dU(\nu)}{d\nu} = h\nu n_E = L^3\frac{8\pi h \nu^3}{c^3} \frac{1}{e^{\beta h\nu}-1}\,.
\end{align}$
</center>

One thing that was left implicit before is that the Lagrange multiplier 
$\beta$ is identified ad being $1/kT$. Another important point is that this is
the total energy inside the cavity, hence it is proportional to its volume
$V = L^3$. Hence the spectra of the energy density inside the cavity (and in
general of an ideal blackbody) will be
<center>
$\begin{align}
\frac{du(\nu)}{d\nu} = h\nu n_E = \frac{8\pi h \nu^3}{c^3} \frac{1}{e^{\frac{h\nu}{kT}}-1}\,,
\end{align}$
</center>
precisely what Planck derived. Notice that we did not dealt, in any moment, how
the particles interacted with the walls, but rather the only consideration we 
made here was how photons should fill the available states.


# 4. Final remarks

Just as review: we have shown how Rayleigh-Jeans derived a expression for the 
blackbody radiation that worked at low frequencies and how Wien then proposed
an expression purely based on experimental data that fitted the high frequency
regime. Planck managed to interpolate between these two regimes and, in an 
attempt to find a theoretical foundation to his expression, he proposed that 
light was emitted in packs of energies given by
<center>
$\begin{align}
E = h \nu\,.
\end{align}$
</center>

Even though his model of oscillators in the wall of the cavity was not accurate,
this is often pointed as the first known evidence of the quantum world. The 
existence of these "packs of energy" that we now call photons was later confirmed
from other experiments. This quantization of energy is the cornerstone of a 
series of developments that led to quantum mechanics as we know today.

There are a number of things that we could show know, that I will not do for
brevity sake. One can integrate $du/d\nu$ over the entire spectra to obtain
Stefan-Boltzmann law, this time, with the correct constant value. We can also
correctly predict the wavelength of peak emission as was done when we had only
Wien's law. Lastly, we can use the approximations $1/(e^x-1) \cong 1/x$ for 
low values of $x$ and $1/(e^x-1) \cong e^{-x}$ for large values of $x$ to show
that Planck's law reduces to Rayleigh-Jeans law and Wien's exponential law at
low and large wavelengths respectively.