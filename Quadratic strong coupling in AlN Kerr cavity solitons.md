### 🔍 What problem does this paper address?
Pump from 1550nm in a mode phase matched AlN kerr comb cavity. In strong chi2 coupling
to form bright soliton we need balance between npm and $\eta$ to SH frequency
Previous works mostly focused on **weak quadratic coupling**; here they explore **strong χ(2) coupling** impact on Kerr soliton formation and SH comb efficiency in AlN
要和之前的工作对比

### 🧪 What are the key methods or experimental techniques?
- Experimental setup / materials used
- FSR 722GHz/700GHz; D2 70MHz (不算大 但是也不小)![[Pasted image 20250327141049.png]]
- ![[Pasted image 20250327141106.png]]
- Measure comb 
- 对了这里还有新的调phase matching的方法
- 5 AlN microrings with varying width (1.22–1.27 μm), same thickness/radius; only nPMn_{PM}nPM​ (phase matching offset) differs.
- Theoretical model (if any)
Simulation model same with the Pockels soliton one Coupled LLE including both χ(2) and χ(3) nonlinearities, modeling SHG/SFG and Kerr effect self-consistently.
- Key parameters or system
 $n_{pf}$  大概在9左右
 on chip pump power 540 mW very high
 slow tune 137MHz/s but in LN you need to be slower 50MHz/s
### 📈 What are the main results?
- What does the paper demonstrate?
Are the soliton spectrum vs $n_{pm}$ and the output power and spectrum
- - **Soliton success rate vs nPMn_{PM}nPM​**（Fig. 3）：|nPM| 越小，Psol 越低；
    
- **Conversion efficiency η\etaη vs nPMn_{PM}nPM​**（Fig. 2 & 4）：越靠近泵浦模，η 越高，但孤子更难稳定。

### 🌟 What is novel or interesting about this work?
- Technical innovations
- fast scan of the power to identify the soliton
Trade-off between soliton formation and SHG efficiency by tuning nPMn_{PM}nPM​; provides **design map** (Fig. 4) for different g(2) platforms (e.g., SiN, LN).
### 📌 Connections to Gong Zheng’s PhD thesis
- Which chapter does this relate to?
你写“extension of Pockels soliton”很好，但建议你之后再看 Gong Zheng 的 thesis 时：

- 找一下 LN 下用 780 nm pump 的那一章，对应的是“Pockels downconversion”；
    
- 本文是“反方向”：1550 nm → 775 nm，上转换，但两者模型是共通的。
- Is this part of a larger research trajectory?
- It is an extension of the pockels soliton in AlN

### 💡 My thoughts & extensions
- Can I use this technique/idea?
- When I pump comb I should care if I need large epsilon detune between FH and SH resonances
- How could I adapt this concept to my experiment or simulation?
-- - 如果是 LN，那 g(2) 很高，本文 Fig. 4(b) 中也提到在 LN 下你可能需要设置 |nPM| ≥ 6 才能稳定产生 soliton；
        
    - 这可能意味着你要设计更远离 pump 的 SH mode。
        
- **你是否考虑过 phase-matching bandwidth？**
    
    - 本文提到 phase matching 带宽约为 72 GHz，决定了可接受的 mode index 偏差；
        
    - 你可以反推自己实验结构的带宽，决定怎么设计 FSR 或 dispersion。
- What are my questions after reading?

   