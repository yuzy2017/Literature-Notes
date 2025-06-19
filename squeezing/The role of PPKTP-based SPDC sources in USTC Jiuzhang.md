
Photonic quantum computing is regarded as a promising pathway to realize quantum computational advantage, mainly owing to photons’ natural immunity to decoherence, high-speed transmission, and room-temperature operability. In the milestone Jiuzhang experiment, the University of Science and Technology of China (USTC) demonstrated quantum computational advantage using a photonic platform, notably leveraging squeezed light sources generated via spontaneous parametric down-conversion (SPDC) in periodically poled potassium titanyl phosphate (PPKTP) crystals. In this term paper, I focus on the hardware aspects of the PPKTP-based SPDC light source, which is a cornerstone of the Jiuzhang photonic quantum computing platform.

Achieving large-scale boson sampling, as in Jiuzhang, fundamentally depends on the ability to generate many indistinguishable, pure, and efficient nonclassical states of light. Among possible approaches, SPDC in PPKTP crystals stands out due to several hardware-level advantages:
- **Engineered Phase Matching**: Periodic poling allows for quasi-phase matching, which significantly improves the efficiency and spectral properties of the generated photon pairs. 
- **High Nonlinear Coefficient**: KTP has a relatively large χ^(2), making SPDC efficient at moderate pump powers. 
- **Thermal and Mechanical Robustness**: PPKTP crystals are less sensitive to temperature drifts than other nonlinear crystals (e.g., PPLN), aiding long-term stability.

In their device, each source consists of a PPKTP crystal placed on a thermoelectric cooler (TEC) for fine temperature control. They pump it with a pulsed laser which (~780 nm) is shaped and split into multiple beams, each focused onto an individual PPKTP crystal. Afterwards they place Dichroic mirrors and polarization compensation optics (e.g., KTP walk-off compensators) are used to separate the SPDC photons from the pump and control indistinguishability. Finally they Downconverted photons are spectrally filtered (e.g., with 12-nm filters) to increase spectral purity.

Under periodic poling, the crystal’s nonlinear domains are flipped with a regular period, enabling quasi-phase matching for SPDC. So that the pump photon is spontaneously converted into a pair of lower-energy photons (signal and idler) whose frequencies sum to that of the pump. Furthermore by temperature tuning and precise poling, the output photons can be made nearly frequency-uncorrelated (high purity) and degenerate.

With this high yield poling, they can operate 25 PPKTP crystals in parallel to produce 25 two-mode squeezed states(equivalent to 50 single-mode squeezed states). The average source purity measured is 0.938 which means a spectral purity reaching 0.99.

With this purity, it can compete with the quantum dot single-photon sources. As quantum dots offer deterministic emission, but have challenges in indistinguishability, spectral purity, and integration for many channels. 

### References
1. Han-Sen Zhong, Hui Wang, Yu-Hao Deng, et al., "Quantum computational advantage using photons," Science 370, 1460–1463 (2020). 
2. Supplemental Material, Science 370, 1460–1463 (2020). 
3. J. L. O'Brien, A. Furusawa, J. Vučković, "Photonic quantum technologies," Nature Photonics 687–695 (2009). 
4. [USTC Jiuzhang Official News](https://www.ustc.edu.cn/2020/1214/c17128a464960/page.htm) 
5. N. Quesada, J. M. Arrazola, "Gaussian boson sampling using squeezed states," Phys. Rev. A 98, 062322 (2018).
这里的引用文献和DTU的squeezer的引用文献是可以看的 就是他们是能够帮你了解squeezing还有xanadu的 proposal 可以帮你了解最新的进展