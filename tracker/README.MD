In high resolution spectrometry, the main challenge is to separate a beam of near-identical mass particles into several beams each composed of only one mass and hence one single particle type, thus ensuring "purity" of each beam for ensuing relevant experiments.
As an example, a optical setup (made of multipoles, beam drifting tubes, magnet separators) able to separate particles with mass M1=100 and M2=100.0001 (i.e. a $\delta$ = 0.0001) respectively would exhibit a corresponding resolution R = 1 / $\delta$ = 10 000.

Particle beam transport modelling software (i.e. SIMION, CosyScript ...) commonly show beam trajectories, track beam transformation including higher order effects owing to real-world optics challenges at user-selected locations along the optical setup, but do not provide a visually-clear insight on the separation ability of the optical setup for different particle mass beams. 

> beamline layout and corresponding beam trajectory modelling (modelled in CosyScript).
![layoutoptic2](https://user-images.githubusercontent.com/126000617/220473800-5e5050ef-093c-494b-91ca-4d4fc37dbc20.png)


This gap is filled with this project Octave code, as it shows whether, and if so how well, a multimass particle beam can be separated into single mass smaller beams. Using the beam transformation data (i.e. transfer matrices) recorded across the optical setup, this Octave routine projects and displays a set of different beams at the several transfer matrix locations.       
A beam is composed of N particles, each characterized by its size x (e.g mm) and angle orientation a (e.g. mrad) in the horizontal plane, and size y and angle b in the vertical plane respectively. 

> beam initial definition plotted in both horizontal and vertical planes.
![beamstart](https://user-images.githubusercontent.com/126000617/220470657-c73feaa1-bce4-4610-9f18-399615f7f661.png)


Each particle is then input to the location-relevant transfer matrix to calculate the parameters of the corresponding projected particle in both planes. Applying this operation to all particles of a set of beams with nearly identical mass, projected beams can be plotted to assess how well the optical setup performs in terms of separation ability.

The routine includes :
+ generating a beam of N particles within the boundaries of the beam size,
+ calculating projected particles using the transfer matrix file provided by the beam transport modelling software,
+ creating and adequately parametrizing a histogram associated to the particle spatial distribution,
+ setting and plotting beam particles.
