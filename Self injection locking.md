- Wildi, T. _et al._ “Phase-stabilised self-injection-locked microcomb.” _Nat. Commun._ **12**, 235 (2021): Demonstrates full phase stabilization of a microcomb using self-injection locking, achieving independent control of comb offset and spacing​
    
    [arxiv.org](https://arxiv.org/html/2401.10160v1#:~:text=Through%20the%20principle%20of%20self,over%20100%C2%A0kHz%20and%20permit%20phase)
    
    ​
    
    [pmc.ncbi.nlm.nih.gov](https://pmc.ncbi.nlm.nih.gov/articles/PMC7801488/#:~:text=35,This%20soliton%20state%20provides)
    
    .
    
- Voloshin, A. S. _et al._ “Dynamics of soliton self-injection locking in optical microresonators.” _Nat. Commun._ **12**, 235 (2021): Shows that SIL of the pump laser relaxes laser requirements and enables soliton generation with previously inaccessible detunings​
    
    [pmc.ncbi.nlm.nih.gov](https://pmc.ncbi.nlm.nih.gov/articles/PMC7801488/#:~:text=telecommunications%20to%20astronomy,significantly%20modifies%20the%20laser%20diode)
    
    ​
    
    [pmc.ncbi.nlm.nih.gov](https://pmc.ncbi.nlm.nih.gov/articles/PMC7801488/#:~:text=locked%20to%20the%20microresonator,kHz%20frequency%20offset%2C%20that%20is)
    
    .
    
- Hillbrand, J. _et al._ “Coherent injection locking of quantum cascade laser frequency combs.” _Nature Photonics_ **13**, 101–108 (2019): Injection-locks a QCL comb’s repetition rate to an RF reference, proving the comb spectrum can be fully phase-locked and stabilizing comb operation​
    
    [arxiv.org](https://arxiv.org/abs/1808.06636#:~:text=platform%20for%20on,comb)
    
    .
    
- Wu, J. _et al._ “Self-Injection Locked and Phase Offset-Free Micromechanical Frequency Combs.” _Phys. Rev. Lett._ **134**, 107201 (2025): Reports a self-injection-locked mechanical comb with greatly improved comb spacing stability and phase noise, and with zero phase offset between comb lines​
    
    [journals.aps.org](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.134.107201#:~:text=to%20decade,injection%20locking%20and%20zero)
    
    .
    
- Shen, B. _et al._ “Integrated low-noise frequency comb source using self-injection locked DFB laser and microresonator soliton.” _Nature_ **582**, 365–369 (2020): Achieves a narrow-linewidth soliton microcomb by self-injection locking a chip-scale laser to a Si$_3$N$_4$ resonator, highlighting SIL’s role in low-noise comb generation​
    
    [pmc.ncbi.nlm.nih.gov](https://pmc.ncbi.nlm.nih.gov/articles/PMC7801488/#:~:text=locked%20to%20the%20microresonator,kHz%20frequency%20offset%2C%20that%20is)
    

should analyse with Adler equation--- it seems like a linear phase relation that

$\frac{1}{2 \pi} \cdot \frac{d \phi(t)}{d t}=\Delta \nu-\frac{\nu_0}{2 Q} \cdot \frac{E_1}{E_0} \cdot \sin \phi(t)$
- $\phi(t)$ ：注入信号与自由振荡器之间的相位差；
- $\Delta \nu=\nu_0-\nu_1$ ：自由振荡器与注入信号之间的频率差；
- $Q$ ：微腔的品质因数；
- $E_0 / E_1$ ：自由振荡模式与＂注入信号＂的场强比（本质是 comb 各簇之间的相互作用强度）；
好像起码要在一个线宽里面才能