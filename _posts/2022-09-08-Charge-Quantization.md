---
layout: post
title:  "A crash course on modern physics: I. Charge quantization"
date:   2022-09-08 22:20:00 -0300
categories: physics modern-physics quantum-physics quantization
---

# A crash course on modern physics: I. Charge quantization and electron discovery

This is the first of a series of posts which will introduce, in a very brief
way, the fundamentals of modern physics. These posts are intended for
undergraduate students which are already familiar with classical physics.
Hopefully, these posts may help some student out there, or simply curious
people out there. Today's post are based mainly on the following books:

- [Tipler, Llewellyn - Física Moderna](https://www.amazon.com/Fisica-Moderna-Paul-Tipler/dp/852162607X/ref=sr_1_1?crid=3PGILPA51SRIO&keywords=Tipler+F%C3%ADsica+Moderna&qid=1662838963&sprefix=tipler+f%C3%ADsica+moderna%2Caps%2C348&sr=8-1)
- [Thornton, Rex - Modern Physics for Scientists and Engineers](https://www.amazon.com/Modern-Physics-Scientists-Engineers-4th/dp/1133103723)
- [Serway, Madison, Moses, Moyer - Modern Physics](https://www.amazon.com/Physics-International-Raymond-Madison-Clement/dp/B010WFFPU2)

The idea that the world around us is made of discrete "things" is not new.
On ancient greece, Democritus and his master Leucippus advocated the atomic
idea, that is, that matter was made of indivisible blocks. The idea was
revisited during Renascence by Pierre Gassendi and Robert Hooke who proposed
that matter was made of small indestructible solids. But the idea only gained
traction with Dalton's "billiard ball" atomic model. Dalton's idea of atoms
of the same element being identical, and different elements possessing atoms
of different properties (such as mass), helped to explain the proportions in
chemical reactions. Avogadro's law further cemented this concept. This was
the general knowledge at the end of XIX century.

## 1. Charge quantization: Thomson and Milikan experiments

The idea of quantization of charge started soon after Dalton's model, wit
Faraday. He discovered that to generate one mole of a cation (an ion that, now we know, lost one
electron), the same amount of charge $F$ was necessary, regardless of the
substance. Once Avogadro's number was determined, the charge of a cation could
be determined by
$$
e = F/N_A\,.
$$
Albeit Avogadro's number could not be reliably determined, the above relation
already showed the quantization of electric charge. But solely from this
experiment was impossible to infer any information of what was carrying
the charge.

### 1.1 Cathodic rays and Thomsom's experiment for electron's discovery

Curiously, Faraday was also the responsible for the observation of an phenomena
that eventually led to the discovery of the electron. He was interested in the
discharge of electrical current through gases. To this end, an apparatus called
"discharge tube" was used. It consisted of placing two metal plates inside a
partially evacuated tube, with the metal plates connected to the poles of a
battery (see schematic [here](http://chemed.chem.purdue.edu/genchem/history/faraday.html#:~:text=The%20Discovery%20of%20the%20Electron%20(Michael%20Faraday)&text=The%20tube%20was%20filled%20with,the%20gas%20began%20to%20glow.)).
The gas could be slowly pumped out of the tube. Faraday noticed around 1830
that a small arc of light formed near the cathode (the metal piece connected to
the negative pole of the battery).

Later, in 1858, Julius Plücker showed that this glow originated from the movement of
electric charges by approaching a magnet close to the tube. By the Lorentz
force law
$$
\begin{align}
\vec{F} = q \vec{v} \times \vec{B}\,,
\end{align}
$$
any charge moving in an electromagnetic field should be deflected. And indeed,
when he approached the magnet to the discharge tube, the glow position changed.

It is important to notice that it was not clear that these were some sort of
ray. [This photo](https://en.wikipedia.org/wiki/Cathode_ray#/media/File:Glow_discharge_regions.jpg)
or maybe [this video](https://youtu.be/4KC8iBINhAA?t=264) may help understanding
why: at the pressures achieved at the time, only a glow was visible. This come
to change in 1869 when Johann Hittorf. To understand his discovery, we need to
cite one detail of the discharge tubes that were ommited for simplicity above.

In a discharge tube, near the cathode, there is a region where no glow is
visible. When the pressure inside the tube is reduced, this region without glow
increases. However Plücker was able to show that if he reduced the pressure
enough, he could observe fluorescence phenomena in the glass wall of the tube.
Hittorf, which was a student of Plücker, managed to show that he could cast
shadows in this fluorescence and that by considering an "L" shaped tube, the
fluorescence only happened in the arm of the cathode. With
this, it showed that there were "cathodic rays" traveling inside the
discharge tube (see [here](https://www.encyclopedia.com/science/dictionaries-thesauruses-pictures-and-press-releases/hittorf-johann-wilhelm)
for details on Hittorf's work).

The final development on cathode-ray tubes was by William Crookes in 1879. He
confirmed Plücker's and Hittorf's discovery as well as determined the direction
of travel of the rays. Perhaps one of its most
famous experiment is one where he inserted a Maltese cross inside the tube
and show it casting a shadow in the fluorescence in the opposite side. Since
the shadow is bigger than the object inserted, it served as evidence that the
rays were traveling from cathode to anode direction. Now, by inserting a known
magnetic field transverse to the ray's travel direction, it could use Lorentz
law tro determine the charge of the cathode ray, which, as we know today,
is negative.

### 1.2 Thomsom's experiment and the charge-mass ratio of the electron

Study of cathodic rays led to the discovery of X-rays by Wilhelm Röntgen. But
for our discussion, J.J. Thomsom was the one able to show that cathode rays
were massive negatively charged particles. His apparatus was very similar to the
ones from Crookes, Hittorf and Plücker. He used a cathode-ray tube with an
aperture just after the cathode to collimate the rays. The rays then traversed
a region where an electric and magnetic fields where placed transverse to each
other and to the cathode ray direction, as shown in the
figure sketched below. The deflection angle $\theta$ could be measured in a fluorescent
screen at the other end of the tube.

![Thomsom's experiment](/assets/thomsom_experiment.png)

Let us consider the deflection when the magnetic field is turned off. It will be
given by $\tan \theta = v_y/v_x$. Under the hypothesis that cathodic rays are
massive particles of mass $m$ and charge $e$, the force which acts upon it
will be $\vec{F} = e E \hat{y}$. The resulting acceleration is then
$\vec{a} = \frac{e}{m}E$ and one can find the value for $v_y$ as
$$
v_y = \frac{e}{m} E t
$$
where $t$ is the time the particles takes to transverse the region between the
charged plates.

The expression above alone can give us important hints. If we look at the sketch
above, $E < 0$. Hence, a positive value of $v_y$ (or a positive deflection
angle) implies that $e < 0$ (because $m,\, t > 0$). Thus, by simply observing
the deflection angle, Thomsom was able to confirm that cathodic rays were
negatively charged. Also, the presence of the mass $m$ in the denominator also
indicated a particle-like behavior. But he could not determine yet the electric charge
and the mass of these particles.

The introduction of the magnetic field comes as a way to determine the time $t$
the particle stays under the influence of the electric field. It is placed in
a direction and strength as to be opposite to the electrical force. We can use
this to shift the unknown quantity from the time to the initial velocity by
using $t = l/v_x$.

Since $\vec{B} = B \hat{z}$, the force on the particle will be initially
$\vec{F}= - e v_x B\vec{y}$. This force will be constant because we adjusted the
magnetic and electric field as to obtain a net force on the particle equals
to zero, that is $eE - e v_x B = 0$. Since $E$ and $B$ are known, it is
possible to measure the particle velocity and then the time it takes to travel
between the plates.

To summarize, we have so far that
<center>
$\begin{align}
v_y = v_x \tan \theta & = \frac{e}{m} \frac{E l}{v_x}\,, \\
v_x & = \frac{E}{B}\,.
\end{align}$
</center>
Hence, by simply solving this system, Thomsom could obtain an expression to
the charge-mass ratio of the cathode-ray's particle in terms solely of
his measurable quantities (deflection angle, size of the capacitor plaques
generating the electric field and the electric and magnetic fields.)
<center>
$\begin{align}
\frac{e}{m} & = \frac{E}{B^2}\frac{\tan \theta}{l}.
\end{align}$
</center>

As a last ingredient, a well known result from electromagnetism is that the
electric field produced between the plates of a plane capacitor is
approximately constant and given by $E = V/d$, where $V$ is the potential
difference $V$ between the plates and $d$ is the distance between them. These.
two variables are easier to measure then the electric field. Thus one can
replace $E$ by these quantities. The magnetic field could be generated by a
[Helmholtz coil](https://en.wikipedia.org/wiki/Helmholtz_coil), which produces,
to a good approximation, an uniform field on the neighborhood of its center and
has an analytical expression to the generated field in terms of the radius of
the coils, the number of loops on them and the electrical current generating
the field.

The value obtained for $e/m$ by Thompson was of the order of $10^11$ C/kg.
Faraday in his electrolysis experiment made estimations for ratios of $e/m$.
The values could change according the kind of substance where being
experimented (today we know that this is because some substance may give up
more than one electron), but was always of the order of $10^8$ C/kg.
Thomsom's particles were 1000 lighter. Also, the ratio was independent of the
kind of gas in the discharge tube.

This discovery led to a reformulation on the way matter was understood. Faraday
particles in the electrolysis experiment surely were atoms. And these atoms
seemed to transfer charge between them in a mechanism that was unknown at the
time. On another end, Thomsom had found a light particle and showed that it
could carry charge. It become very tempting to part away with the idea of an
indivisible atom and embed these new particles - which we know today as the
electron - in the atom. To balance the charge, the bulk of the atom, would be
positively charged. The analogy Thomsom proposed was of a plum pudding, with
the electrons being the 'plums' inside the positively charged 'pudding'. The
potential difference between anode and cathode would then be ripping the electrons
from the atoms, generating a stream of them which was being observed as
the cathode rays.

## 1.2 Milikan and the electronic charge

Despite the efforts of Thomsom, the individual charge of an electron was not
measured yet. There was not a direct measurement of a minimal unit of charge.
This would remove, without a doubt, the quantization of electric charge.

Millikan was the one that managed to devise a way to measure the electric charge
of the electron. His apparatus is sketched below. Oil was pulverized through a
small nozzle. Friction with the nozzle would charge the droplets, which then
felt between two capacitor plates through a small hole on the upper plate.
By performing the experiment in a dark room and illuminating the particles,
he could then track the motion of the particle with a telescope. By adjusting
the value of the electric field, one is able to equilibrate the droplet.
Considering the mass of the droplet to be $m$ and it to be carrying a charge q,
the equilibrium condition (neglecting the buoyance of air, since the droplet is
much denser than the air), we can isolate the charge q as
$$
q = \frac{m g}{E}\,,
$$
where $E$ is the equilibrium field in which the the charge is equilibrated.

![Milikan's experiment](/assets/milikan_experiment.png)

It remained to estimate the mass of the droplet. The most obvious way is by
measuring the droplet radius and using the oil density to obtain
$$
m = \frac{4}{3}\rho \pi r^3\,.
$$
But a direct measurement of the droplet radius is very difficult and error
prone. Instead, by turning off the electric field, the droplet would be under a friction force
given by Stoke's Law $\vec{F} = -6 \pi \eta r \vec{v}$. The equation of motion
of the droplet is then
$$
\frac{dv}{dt} = - \frac{b} v - g\,,
$$
where 
$$
\alpha = \frac{9 \eta}{2\rho r^2}\,.
$$
This is a first order non-homogeneous equation. The solution for the
homogeneous equation can easily be found to be of the form
$v(t) = A \exp(-\alpha t)$. An inhomogeneous solution can be found
considering the net force into the droplet being zero. In this situation, the
particle reaches a velocity given $v_f = -g/\alpha$. For large enough times, the
transient velocity given by the homogeneous term can be neglect and the droplet
travels at velocity $v_f$, called transient velocity. By measuring this
transient velocity, Milikan was able to determine the particle radius as being
$$
r = \sqrt{\frac{9\eta v}{2 \rho g}}
$$

With the droplet radius estimated, it is then easy to compute its mass and find
its charge. He also noticed that, sometimes the particles abruptly changed
behavior. He attributed this behavior to the particle gaining one unit of charge
from background radiation. This was confirmed by approximating a source of
radiation and noticing the frequency of these changes increased. The fact that
the change was abrupt instead of smooth further pointed out to the quantization
of charge.

To obtain the value of the charge of the electron, Milikan made a histogram
of the observed charges. After thousands of measurements, he could determine
that the histogram had peaks which repeated at regular intervals. Each peak
corresponded top droplets with $q = -n e$, where $n$ was the peak number. In
this fashion, he could measure the charge $e$.

This picture stood until the decade of 1970's. By this time, the atomic model
had evolved from Thomsom's model to the modern picture given by quantum
mechanics, existence of antiparticles where established and a plethora of
unstable particles which were sensitive to the strong nuclear force was
discovered. This "particle zoo" was organized in a "periodic table" of
particles which received the name "The Eightfold Way". And the same way the
periodic table was a consequence of the substructure of the atom, The Eightfold
Way led to the proposition that these particles, including the proton - which
has a single positive charge - also should be composed of more elementary
particles which were named quarks. Moreover, the quarks should have electric
charge $\pm e/3$ or $\pm 2 e/3$. Going into all the details of the evidence for
quarks existence of quarks is out of scope (and a post entirely dedicated to it
is a nice idea). But suffice to say that, except for very few skeptics, the
community widely accepts the idea and the model is successful in predicting a
number of phenomena.

It is important to point out that the quarks existence does not completely
invalidates Milikan's point. First, because one can simply say that the
true quanta of charge should be $e/3$. But more important: quarks are always
tightly bound together and it is impossible, so far as it is known, to observe
an isolated quark. This phenomena is called confinement and is the reason a few
scientists are skeptic from its material existence. Furthermore, they form
bound states in ways that the net charge always have a multiple of the charge
of the electron. This is the reason why Milikan could not find a smaller charge
and why, for all purposes outside particle physics, the minimal electric charge 
is the one of the electron.
