---
layout: post
title:  "A crash course on modern physics: I. Charge quantization"
date:   2022-09-08 22:20:00 -0300
categories: physics modern-physics quantum-physics quantization
---

# A crash course on modern physics: I. Charge quantization

This is the first of a series of posts which will introduce, in a very brief 
way, the fundamentals of modern physics. These posts are intended for 
undergraduate students which are already familiar with classical physics.
Hopefully, these posts may help some student out there, or simply curious
people out there. Today's post are based mainly on the following books:
- [Tipler, Llewellyn - Física Moderna](https://www.amazon.com/Fisica-Moderna-Paul-Tipler/dp/852162607X/ref=sr_1_1?crid=3PGILPA51SRIO&keywords=Tipler+F%C3%ADsica+Moderna&qid=1662838963&sprefix=tipler+f%C3%ADsica+moderna%2Caps%2C348&sr=8-1)
- [Thornton, Rex - Modern Physics for Scientists and Engineers](https://www.amazon.com/Modern-Physics-Scientists-Engineers-4th/dp/1133103723)
- [Serway, Madison, Moses, Moyer - Modern Physics](https://www.amazon.com/Physics-International-Raymond-Madison-Clement/dp/B010WFFPU2)

<p style=padding:25px></p>


The idea that the world around us is made of discrete "things" is not new. 
On ancient greece, Democritus and his master Leucippus advocated the atomic 
idea, that is, that matter was made of indivisible blocks. The idea was 
revisited during Renascence by Pierre Gassendi and Robert Hooke who proposed
that matter was made of small indestructible solids. But the idea only gained 
traction with Dalton's "billiard ball" atomic model. Danton's idea of atoms
of the same element being identical, and different elements possessing atoms
of different properties (such as mass), helped to explain the proportions in
chemical reactions. Avogadro's law further cemented this concept. This was
the general knowledge at the end of XIX century.

## 1. Charge quantization: Thomson and Milikan experiments

The idea of quantization of charge started soon after, with Faraday. He found 
that to generate one mole of a cation (an ion that, now we know, lost one 
electron), the same amount of electricity $F$ was necessary, regardless of the
substance. Once Avogadro's number was determined, the charge of a cation could
be determined by
$$
e = F/N_A\,.
$$
Albeit Avogadro's number could not be reliably determined, the above relation
already pointed to the quantization of electric charge.

### 1.1 Thomsom's experiment and the charge mass ratio of electron
Curiously, Faraday was also the responsible for an observation of a phenomena
that eventually started the studies that allowed for electron's charge to be
eventually determined as the fundamental charge. He observed that placing two 
metal electrodes at either ends of a tube partially evacuated, an arc of light 
was visible leaving the cathode (negative electrode) towards the anode. The 
origin of this glow was unknown. Other scientists, such as Crookes, showed that 
by increasing the vacuum in the tube, the light was emitted only near the 
anode. Also, insertion of metal objects inside the tube caused shadows to 
appear. This showed that, whatever was causing the glow, it was traveling in a 
straight line, like a ray of light. Since these "rays" had origin in the 
cathode, they were called "cathodic rays".

Study of cathodic rays led to the discovery of X-rays by Wilhelm Röntgen. But 
for our discussion, J.J. Thomsom was the one able to show that cathode rays 
were massive negatively charged particles. The experiment had in one end of
an evacuated tube, the electrodes generating the cathodic ray. These rays
was collimated by an aperture and then traversed a region where electric and 
magnetic fields in a perpendicular configuration was present, as shown in the 
figure sketched below. The deflection angle could be measured in a fluorescent
screen at the other end of the tube.

![Thomsom's experiment](/assets/thomsom_experiment.png)

Let us consider the deflection when the magnetic field is turned off. It will be
given by $\tan \theta = v_y/v_x$. Under the hypothesis that cathodic rays are
massive particles of mass $m$ and charge $e$, the force which acts upon it
will be $\vec{F} = e E \hat{y}$. The resulting acceleration is then 
$\vec{a} = \frac{e}{m}E$ and one can find the value for $v_y$ as
$$
v_y = \frac{e}{m}\frac{E}{t}
$$
where $t$ is the time the particles takes to transverse the region between the
charged plates.

The expression above alone can give us important hints. If we look at the sketch
above, $E < 0$. Hence, a positive value of $v_y$ (or a positive deflection 
angle) implies that $e < 0$ (because $m,\, t > 0$). Thus, by simply observing
the deflection angle, Thomsom was able to prove that cathodic rays were 
negatively charged particles. But he could not determine yet the electric charge
and the mass of these particles.

The introduction of the magnetic field comes as a way to determine the time $t$
the particle stays under the influence of the electric field. Because the field
is perpendicular to the initial velocity, it will not modify it, and this time 
can be replaced by the initial velocity $v_x$ as $t = l/v_x$ and we shift the 
unknown quantity from the time to the initial velocity.

Since $\vec{B} = B \hat{z}$, the force on the particle will be initially
$\vec{F}= - e v_x B\vec{y}$. This force will be constant if we adjust the
magnetic and electric field as to obtain a net force on the particle equals
to zero, that is $eE - e v_x B = 0$. Since $E$ and $B$ are known, it was 
possible to measure the particle velocity and then the time it takes to travel
between the plates. With the deflection angle when the magnetic field is turned
off measured, it was possible to determine the charge mass ratio of the particle
emitted.

This discovery led to a reformulation on the way matter was understood. These 
negatively charged particle surely had to be present in the matter. On another
hand, atoms are electrically neutral. Thomsom parted away with the idea 
of an indivisible atom and suggested it to be an spherical "pudding" of positive
charge, with particles of negative charge - which are now called the electrons - incrusted
on it. The potential difference between the cathode and the anode was ripping electrons
from the atoms, generating a stream of them which was being observed as
the cathodic rays.

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
