---
layout: page
title: Research highlights
---


1. _[Automated methods for reaction discovery](#auto)_
2. _[Tools to analyze reaction networks](#amktools)_
3. _[Generalization of TSSCDS to study vdW complexes](#vdw)_
4. _[Energy transfer models in gas-surface collisions](#etransfer)_
5. _[Rare-event acceleration](#axd)_
6. _[Fitting PESs](#pes)_
7. _[Vibrational angular momentum in MD simulations](#vam)_



### 1. Automated methods for reaction discovery<a name="auto"></a>

Over the last years we have been involved in the development of automated methods to discover complex reaction mechanisms. The methods are based on the use of molecular dynamics simulations, Heuristics and Graph Theory. The procedure has been applied to different systems and an open-source program is available: [![GitHub - AutoMeKin](https://img.shields.io/badge/GitHub-AutoMeKin-blue?logo=github)](https://github.com/emartineznunez/AutoMeKin/)

<p align="center">
   <img src="https://raw.githubusercontent.com/emartineznunez/emartineznunez.github.io/master/assets/img/bbfs.jpg" alt="alt text" width="600">
</p>
Example system showing the BBFS criterion, used in AutoMeKin to pindown the location of transition-state guess structures. Blue vectors correspond to the velocity vectors of the specific atom. Solid lines link neighboring atoms and the dashed lines indicate nonneighboring ones. At time step t, the maximum distance between i1 and its neighbors i2, i3 is smaller than the minimum distance, d, to non-neighbors k;  red dashed line. At time step t', the distance d$\scriptstyle{(}$i1,k2$\scriptstyle{)}$ becomes smaller than the distance d$\scriptstyle{(}$i1,i3$\scriptstyle{)}$, indicating the possibility of a TS in the vicinity.

{: .box-warning}
The program and the underpinning methods are described in [this publication](https://onlinelibrary.wiley.com/doi/full/10.1002/jcc.26734). AutoMeKin mostly relies on the MD-based method developed under the name [TSSCDS](https://onlinelibrary.wiley.com/doi/abs/10.1002/jcc.23790).



### 2. Tools to analyze reaction networks<a name="amktools"></a>

The level of detail attained in the computational description of reaction mechanisms can be vastly improved through tools for automated chemical space exploration, particularly for systems of small to medium size.  In this spirit, the new Python library [![GitHub - amk_tools](https://img.shields.io/badge/GitHub-amk_tools-blue?logo=github)](https://github.com/dgarayr/amk_tools/) has been designed to read and manipulate complex reaction networks, greatly simplifying their overall analysis. The package provides interactive dashboards featuring visualizations of the network, the three-dimensional molecular structures and vibrational normal modes of all chemical species, and the corresponding energy profiles for selected pathways. 

<p align="center">
   <img src="https://raw.githubusercontent.com/emartineznunez/emartineznunez.github.io/master/bokeh_plot.png" alt="alt text" width="600">
</p>

{: .box-warning}
Further details in the original [publication](https://pubs.acs.org/doi/full/10.1021/acsphyschemau.1c00051). This is a collaborative work with Diego Garay-Ruiz, Moises Álvarez-Moreno, Carles Bo, from ICIQ.



### 3. Generalization of TSSCDS to study vdW complexes<a name="vdw"></a>

We present a generalization of the transition state search using chemical dynamics simulations, TSSCDS, methodology, which allows the topographical characterization of intermolecular potential energy surfaces, IPES, for non-covalently bound complexes, vdW-TSSCDS. Starting from a single random input geometry, we show that vdW-TSSCDS is able to globally and automatically locate stationary points of an IPES, even in limiting cases such as extremely flat regions or nontrivial topologies, _e.g._, bifurcation points. The basic idea is the expression of the connectivity matrix in block structure, where diagonal blocks correspond to the isolated fragments and off-diagonal blocks provide the intermolecular connectivity. To this end, we introduce a new definition of bound or not, in a non-covalent sense, utilizing an extra set of van der Waals distances, which encompasses all kinds of non-covalent distances.

<p align="center">
   <img src="https://raw.githubusercontent.com/emartineznunez/emartineznunez.github.io/master/assets/img/vdW.jpg" alt="alt text" width="600">
</p>

{: .box-warning}
This work is a collaboration with Dani Peláez and this research group and this is the original [work](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.26008)



### 4. Energy transfer models in gas-surface collisions<a name="etransfer"></a>

An energy transfer model has been developed for gas-surface collisions. The model relies on simple gas-phase scattering models. When energy transfer is analyzed in the limit of high incident energies, the following results are found:

1. The percent of energy transfer to vibration and rotation of light diatomic projectiles decreases as the projectile’s mass increases, while this transfer is almost independent of the mass for heavier projectiles.

2. For small projectiles, less than 10 atoms, transfer to vibration increases as a function of the projectile’s size.

3. However, for larger projectiles, the percent transfer to vibration is nearly constant, a result that can be attributed to a mass effect and also to the fact that only a reduced subset of “effective” vibrational dof is being activated in the collisions

The MD results can be very well fitted to an equation that accounts for the adiabatic, low-energy, and impulsive, high-energy, regimes:

$
\langle \Delta E \rangle=\langle \Delta E^{ad} \rangle+\langle \Delta E^{imp} \rangle=\langle \Delta E_0 \rangle+a\exp \left(\frac{-b}{\sqrt{E}}\right)+cd^2\mathrm{csch}^2\left(\frac{d}{\sqrt{E}}\right)
$   

with $\langle \Delta E_0 \rangle$, $a$, $b$, $c$ and $d$ being adjustable parameters.

<p align="center">
   <img src="https://raw.githubusercontent.com/emartineznunez/emartineznunez.github.io/master/assets/img/etransfer.jpeg" alt="alt text" width="400">
</p>

{: .box-warning}
You can consult the full details in [this publication](https://pubs.acs.org/doi/10.1021/jp4117134) 



### 5. Rare-event acceleration<a name="axd"></a>

The approach is based on introducing constraints which lock trajectories in a region of the phase space close to the dividing surface with volume $\scriptstyle{\Gamma_1}$ , which separates reactants and products. This results in substantial, _i.e._, up to more than 2 orders of magnitude, speeding up of the trajectory simulation. Actual microcanonical rates $\scriptstyle{k(E)}$ are calculated by introducing a correction factor equal to the fraction of the phase volume which is allowed by the constraints. The constraints can be more complex than previously used boosting potentials. The approach has its origin in Intramolecular Dynamics Diffusion Theory, which shows that the majority of nonstatistical effects are localized near the transition state. 

$
k(E)=k^{biased}(E)\frac{\Gamma_1}{\Gamma}
$   


{: .box-warning}
The method was developed by Dmitry Shalashilin and myself and is described in [this paper](https://pubs.acs.org/doi/10.1021/ct060042z)



### 6. Fitting PESs<a name="pes"></a>

We developed a software package based on a genetic algorithm that fits an analytic function to a given set of data points. The code, called GAFit, was also interfaced with the CHARMM and MOPAC programs in order to facilitate force field parameterizations and fittings of specific reaction parameters for semiempirical Hamiltonians. The present tool may be applied to a wide range of fitting problems, though it has been especially designed to significantly reduce the hard work involved in the development of potential energy surfaces for complex systems. For this purpose, it has been equipped with several programs to help the user in the preparation of the input files. We showcase the application of the computational tool to several chemical-relevant problems: force-field parameterization, with emphasis on nonbonded energy terms or intermolecular potentials, derivation of SRP for semiempirical Hamiltonians, and fittings of generic analytical functions.

<p align="center">
   <img src="https://raw.githubusercontent.com/emartineznunez/emartineznunez.github.io/master/assets/img/gafit.jpg" alt="alt text" width="600">
</p>

{: .box-warning}
This is a collaborative work with Saulo Vázquez and Roberto Rodríguez-Fernández, Francisco Pereira and Jorge Marques. Here is the [publication](https://www.sciencedirect.com/science/article/abs/pii/S0010465517300607)

### 7. Vibrational angular momentum in MD simulations<a name="vam"></a>

Linear molecules with degenerate bending modes have states, which may be represented by the quantum numbers $\scriptstyle{N}$ and $\scriptstyle{L}$. The former gives the total energy for these modes and the latter identifies their vibrational angular momentum $\scriptstyle{j_z}$. In this work, the classical mechanical analog of the $\scriptstyle{N,L}$-quantum states is reviewed, and an algorithm is presented for selecting initial conditions for these states in MD simulations. 

<p align="center">
   <img src="https://raw.githubusercontent.com/emartineznunez/emartineznunez.github.io/master/assets/img/vam.jpeg" alt="alt text" width="600">
</p>
Plots of motion in the XY plane for an O-atom of CO<sub>2</sub> prepared in different L states. Plots are given for states with and without vibrational angular momentum zpe.

{: .box-warning}
This is a collaborative work with Upakarasamy Lourderaj and the late Bill Hase. Here is the [publication](https://pubs.acs.org/doi/full/10.1021/jp073317v#)

