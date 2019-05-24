# Molecules Explorer

## Release Notes
### Recent changes
#### Version 0.1 - July 16, 2016
* Initial release of Molecules Explorer.

## Introduction
The primary goal of the molecular explorer is to report the atomic structure of molecules,
found using quantum chemistry computational methods. Further quantities of interest,
including the electron affinity (EA) and ionization potential (IP), are also reported.

## Manual
* [Molecular Glossary of Terms](/user-guide/molecular_terms)

## Calculations
The methodology used to compute the atomic structure is a standard quantum chemical
approach. This involves solving Schrodinger’s equation using both a linear combination of
atomic orbitals (LCAO) with a relevant functional to address the question of the
potential. The LCAO were implemented with the use of the 6-31+* Pople basis [^2] and the
hybrid-functional B3LYP was used [^3].

## Properties
the electron affinity (EA) and ionization potential (IP) are given by
$$EA = -\delta G_red(sol)/nF$$
$$IP = -\delta G_ox(sol)/nF$$

![Free energy cycle](img/molecules-explorer/free_energy_cycle.png)
*Figure 2: Free energy cycle for computing the oxidation/reduction potential. R denotes the molecule of interest.*

According to the above thermodynamic cycle in Fig. 1,
$delta G_ox(sol)$ and $\delta G_red(sol)$ can be calculated from the Gibbs free
energy change of gas phase:

$$\delta G_ox(sol)=\delta G_ox(gas)+\delta G_solv(R^+)-delta G_solv(R)$$
$$\delta G_red(sol)=\delta G_red(gas)+\delta G_solv(R^-)-delta G_solv(R)$$

The reported IP/EA are the adiabatic IP/EA[^1], which optimizes the geometry at different charge states (cation, anion, neutral), which emphasizes high-fidelity results.

## Using the Computational Molecular Explorer
In order to search the database for the molecule in question, four methods can be employed.

1. Elements : returns any entry that includes the queried elements
2. Formula : returns any entry that satisfies a permutation of the queried atoms (e.g.
   H2O1, H2O, HOH, OHH all return water)
3. InChi (The IUPAC International Chemical Identifier): uses “bond connectivity,
   tautomeric information, isotope information, stereochemistry, and electronic charge
   information.” (See [InChI
   Wikipedia](https://en.wikipedia.org/wiki/International_Chemical_Identifier)) This may
   be the most precise way of searching for a molecule but perhaps the most complicated.
4. Chem Doodle: allows drawing of the chemical structure to query for the database entry
   (currently not supported on Firefox)

## References
[^1]: S. P. Ong , G. Ceder , Electrochim. Acta , 55 , 3804 (2010)
[^2]: Ditchfield, R., Hehre, W.J. & Pople, J.A. J. Chem. Phys. 54, 724 (1971)
[^3]: Becke, A.D. Phys. Rev. A. 38, 3098 (1988)
