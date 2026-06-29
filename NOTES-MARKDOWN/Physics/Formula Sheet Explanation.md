This is stuff that I don't remember or additional information about the formula sheet.


# Mechanics

## Motion equations

### No time motion equation

Sometimes a problem won't give us the time, and if we don't need to compute it, we can use this formula to avoid it completely:

$$\Large v^2=v^2_0+2a(x−x_0)$$

---

## Work-Energy Theorem

$$\Large W_{\text{net}}=\Delta K$$

- $W_{\text{net}}$ is the total work done by all forces.
- $\Delta K$ is the change in kinetic energy of the object.

Work changes the kinetic energy of an object 1:1. 
Work is the energy that flows into and out of an object's motion.

### Work-Energy with Potential energy

We have another version that breaks down the work into multiple components. 
This formula adds potential energy (*energy stored in the system due to position*).

$$\Large K_i + U_i + W_{\text{nc}} = K_f + U_f$$

Where $U=-\int F_c\cdot ds$, but usually we have:
- $U_\text{gravity} = mgh$
- $U_{\text{spring}}= \frac{1}{2}kx^2$

---

## Friction

We use the:
- **dynamic friction coefficient** ($\mu_k$) when the object moves.
- **static friction coefficient** ($\mu_s$) when the problem asks if an object will move, or what's the force required to move it.


### Low velocity drag

Drag happens when a very small object (or an object moving at slow speeds) moves through a liquid or a gas (*marbe falling in oil, dust particle in the air*).

$$\Large F_d=-bv$$
where $b$ is the drag coefficient (based on the size/shape of the object and the fluid's viscosity) and $v$ is the velocity of the object.

> [!hint]
> We have a negative sign in front because the drag force acts in the opposite direction of the velocity vector.


### High velocity drag

$$\Large F_d=-cv^2$$

Happens when we have high speeds (*cars on the highway, skydivers falling, airplanes flying, or baseballs moving through the air*).

---

## Momentum

**"Mass in motion"** or how hard it is to stop a moving object.

$$\Large p = mv$$

### Impulse

Change in momentum:

$$\Large J=\Delta p = F\cdot \Delta t$$

> [!hint]
> ![[Pasted image 20260604163555.png]]

---

## Circular motion

### Centripetal acceleration

An acceleration that always points to the center of the circle. It's given by the force that keeps the object in trajectory (a rope or something).

$$\Large a_c = \frac{v^2}{r}$$

Where $v$ is the tangential speed, and $r$ is the radius of the circle.

### Centripetal force

Of course a force is given by $m\cdot a$, so if we add mass, we get the centripetal force:

$$\Large F_c=\frac{mv^2}{r}$$

Which is still pointed towards the center of the circle.

---

# Harmonic motion
## Mass-Spring SHM

### Angular frequency
$$\Large w = \sqrt{\frac{k}{m}}$$

Instead of imagining a spring going in 1D, imagine a mass moving in a circle.
The projection on the horizontal diameter is the actual spring, while we abstract using a circle for formulae and calculations.

> [!hint]
> The angular frequency measure how many radians per second the mass goes along the abstract circle.


### Total energy stored in the oscillating system

$$\Large E=\frac{1}{2}kA^2$$

## Pendulum

### Period (one swing of a pendulum)

![[Pasted image 20260608165626.png]]

- $L$ is the **length of the rope**.
- $g$ is the gravitational acceleration


## Traveling wave

Imagine a string that vibrates, thus creating waves.
This formula describes the exact positions of every piece of the vibrating string, at each point in time.

![[Pasted image 20260609111726.png]]

- $x$ is the horizontal position along the string.
- $t$ is the instant at which we want to measure.
- $y$ is the vertical position of the string, at position $x$ and insant $t$.


> [!hint]
> The curve changes shape with each instant of time.
> ![[Pasted image 20260609111928.png]]


### Scaling factor k

![[Pasted image 20260609113313.png]]

This is just a stretch factor for the x axis, determined by the wave length $\lambda$.

### Velocity of wave

![[Pasted image 20260609114117.png]]

---

# Thermodynamics
## Thermal Expansion

Objects can expand when heated up.

### 1D (length expansion)

$$\Large \Delta L = \alpha L_0 \Delta T$$

- $\Delta L$ is the change in length
- $\alpha$ is the coefficient of linear expansion
- $L_0$ is the initial length
- $\Delta T$ is the change in temperature

### 3D (volume expansion)

$$\Large \Delta V = \beta V_0 \Delta T$$

- $\Delta V$ is the change in volume
- $\beta$ is the coefficient of volume expansion
- $\Delta T$ is the change in temperature


## Heat

$$\Large Q=mc\Delta T$$
We use this formula with the mass almost exclusively for solids and liquids. We switch to moles when we are using gases.

---

# Electric fields

## Coulomb Force

![[Pasted image 20260615122118.png]]
![[Pasted image 20260615122153.png]]


## Electric field

Force experienced at any point in space from an hypotetical test-charge, given a $q$ charge.

![[Pasted image 20260615122401.png]]


## Electric Potential

It's the energy required to move a +1 Coulomb charge from an hypotetical infinitely distant starting point (no electric field influences) to that point.

$$\Large V=k_e\frac{q}{r}$$

> [!hint]
> You can picture this as if it was the height of the field. Each point of the "scalar" field has a potential, and for example positive charges find it more difficult to climb to higher potentials, rather than going where potential is less.
> 
> ![[Pasted image 20260615184717.png]]
> ![[Pasted image 20260616124402.png]]

> [!note] What if we have **multiple charges**?
> ![[Pasted image 20260615185032.png]]


### Line integral

When we want to compute the energy it takes for a charge to move through an electric field, we use this line integral:

#### We don't give a shit about this for now


## Electric potential energy

![[Pasted image 20260616124459.png]]
![[Pasted image 20260616124443.png]]

---
# Magnetism

A positive charge generates an electric field like a sphere:

![[Pasted image 20260616233200.png]]

Due to special relativity, when an object moves through space, the space gets compressed along the axis of movement.
So if our charge moves, the electric field gets squashed, and the electric field gets more dense along the "equator":

![[Pasted image 20260616233410.png]]

So basically the field, being more dense at the equator, pushes with greater force, and this force is what we call a magnetic field. This only works with moving charges for some reason, but it's like this.

## Magnetic force

$$\Large F=qv\;×\;B=qvB\sin\theta$$

![[Pasted image 20260618120322.png]]

Theta is the angle between the direction of motion and the magnetic field vector.

### Magnetic orbits

When a particle gets caught in a magnetic field, it moves in circular motion.

![[Pasted image 20260618121132.png]]

This is the formula for the radius of the orbit:

![[Pasted image 20260618121511.png]]

and this is the formula for the period of the orbit:

![[Pasted image 20260618121533.png]]

> [!hint]
> ![[Pasted image 20260618121424.png]]

---

# Maxwell Equations

## Gauss's Law

$$\Large\oint \vec{E} \cdot d\vec{A} = \frac{Q_{enc}}{\varepsilon_0}$$

If you trap a charge in a complex shape, the amount of flux that passes through the walls doesn't depend on the shape or on the distribution of charges. But just on the charge amount.

Total Flux strictly depends on _how much_ charge is trapped inside, completely ignoring _where_ or _how_ it is distributed.

> [!hint]
> ![[Pasted image 20260618123828.png]]

> [!example]
> ![[Pasted image 20260618125856.png]]
> ![[Pasted image 20260618125839.png]]


## Gauss's Law for Magnetism

$$\Large \oint \vec{B} \cdot d\vec{A} = 0$$

Magnetic monopoles don't exist. 
Unlike electric charges which can exist as an isolated proton or electron, magnetic poles _always_ come in North/South pairs.

> [!hint]
> Because of this, magnetic field lines never truly "start" or "end." Instead, they form endless, unbroken closed loops (traveling North to South on the outside, and South back to North on the inside).


If you try to get the magnetic flux through a closed surface, it will always be 0, because the field lines always come back to the negative dipole.

![[Pasted image 20260618125222.png]]


## Faraday’s Law of Induction

A _changing_ magnetic field creates an electric current.

If you just sit a magnet next to a loop of wire, absolutely nothing happens.
But the exact second you start **moving** that magnet, the electrons start being pushed through the wire.


> [!tldr]
> - **Electric Fields** are created by **any charge**, whether it is sitting still or moving.
> - **Magnetic Fields** are created **ONLY by moving charges** (currents).
>   
> ![[Pasted image 20260618130424.png]]

![[Pasted image 20260619215320.png]]

---

# Important stuff about electromagnetism

## Coil

A magnetic field that is generated from a current (in a wire) looks like this:

![[Pasted image 20260618140934.png]]

If we start to fold the wire into a coil, we get superposition of magnetic field lines:

![[Pasted image 20260618141017.png]]

Resulting in a "unified" magnetic field that acts like a bar magnet:

![[Pasted image 20260618140844.png]]

## What is current

Wires are grids of fixed atoms (positive charges) with free electrons inside. 
Only the electrons (negative charges) move in a wire, displacing the electrons close to them.

> [!hint]
> In a solid metal like copper, the atoms basically "donate" their outermost electron to the group.
