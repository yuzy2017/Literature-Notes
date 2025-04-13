### 🔍 What problem does this paper address?
-Generate Combs in short wavelength range limited by large material dispersion and loss
-Use Pockels effect couple infrade and near visible
-22% conversion efficiency from pulse pumped laser to near visible comb but not phase locked
strong chi2 coupling
-tune the visible comb by more than one FSR robustly. by dispersive wave
可以强调“近可见波段是传统Kerr梳难以覆盖的区域”，本工作**拓展了可集成光梳的波段范围**。
### 🧪 What are the key methods or experimental techniques?
- Experimental setup / materials used
- Mode dispersion parameters:
   - IR: \( d_1 = 727\,\text{GHz},\ d_2 = 140\,\text{MHz} \)
   - VIS: \( D_1 = 703.7\,\text{GHz},\ D_2 = 43\,\text{MHz} \)
   - χ(2) coupling strength: \( g^{(2)} = 0.08\,\text{MHz} \)

series of rings. shifting the radius of each ring, the resonance shifted by 9nm each.
- AlN resonator eight rings are cascaded using one set of bus waveguides
- ![[Pasted image 20250328202757.png]]
- Theoretical model (if any)
- Couple mode equation in the supplimentary 
- ![[Pasted image 20250328202833.png]]

### 📈 What are the main results?
- What does the paper demonstrate?
dispersive wave caused by visble and infrade phase matching.  And the position could be shifed by wg width when dispersive wave near pump efficiency increase
- Cherenkov radiation ≠ SHG dispersive wave，它是由 **χ(2)耦合构成的 hybrid mode 对 comb 产生共振增强**，类似高阶色散引发的 DW，但这里机制不同。
    
- 所以可以写成：

- The Cherenkov-like radiation is a dispersive wave caused by phase matching between the IR comb line and a hybridized VIS-IR mode, **not** traditional SHG.

- Any key figures (Fig. X) to note
-![[Pasted image 20250328204344.png]]

![[Pasted image 20250328204447.png]]
### 🌟 What is novel or interesting about this work?
- Technical innovations
Theory frame work about explain DW with DOS
identify the infrade and near visble hybridization by the chi2 effects from resonance thermal shifts
- “Theory framework explain DW with DOS” 是一个特别好的总结点，别的总结一般只说“observed DW”，你能从理论角度说出来很专业；
    
- 你提到 thermal shift 识别 hybridization，也说明你注意到他们在频率 domain 做 tuning 的巧妙方法。
    

💡**建议细化比较**：

- 再补一句“以往做 visible comb 要外部倍频、或者弱 intracavity SHG，而本文靠 χ(2)-χ(3) 强耦合实现”会更完整。
- Compared to prior work, what’s new?
different tuning method by tuning the width of the wg change phase matching not by tune the pump

### 📌 Connections to Gong Zheng’s PhD thesis
- Which chapter does this relate to?
not his work
- Is this part of a larger research trajectory?
build the theory back ground towards pockles comb on AlN

### 💡 My thoughts & extensions
- Can I use this technique/idea?
-Learn the theory frame work and combine thermal and photorefractive components inside.
compare with the LLE method
- How could I adapt this concept to my experiment or simulation?
- Yes may be we can learn the multiplixing method?
- 
- What are my questions after reading?
- The chrenkov radiation is the DW of the SHG?
- Could implement a simplified modal-expansion + thermal detuning model to test whether DW can appear in my SHG simulation.
- Try extracting the DOS structure from QuTiP simulated hybrid-mode Hamiltonian?




## 🌈 Cherenkov-like Radiation 与 Hybrid Mode 的关系整理

### 🧠 核心结论：
> **Cherenkov-like radiation 出现在 near-visible 波段，是因为某个 IR comb line 与 hybrid mode 的频率共振对齐，导致 DOS 增强，从而产生频谱尖峰。**

---

### 🔗 逻辑链梳理：

#### 1️⃣ 什么是 Hybrid Mode？
- 在 AlN 微环中，由于强 χ(2) 非线性（Pockels 效应），红外模 \( a_j \) 和可见模 \( b_j \) 被强耦合起来。
- 二者形成两个 **混合模式（hybrid modes）**，分别记作 \( A_j, B_j \)，是以下线性组合：
$A_j = \alpha_j a_j + \beta_j b_j,\quad B_j = \alpha'_j a_j + \beta'_j b_j$

- 每个 hybrid mode 有自己新的本征频率，记为 \( \lambda_j^\pm \)，其解析表达式为：

$\lambda_j^\pm = \frac{1}{2}(\chi^a_j + \chi^b_j \pm \sqrt{(\chi^a_j - \chi^b_j)^2 + 4G_j^2})$

其中 \( \chi^{a,b}_j \) 为 detuning + loss，\( G_j \) 是 χ(2) 耦合强度。

---

#### 2️⃣ 什么是 DOS（Density of States）？
- 描述某一频率是否与某个模式频率共振增强的程度；
- 近似可用 Lorentzian 表示：

\[
\text{DOS}_j(\omega) \propto \frac{1}{(\omega - \omega_j)^2 + \kappa_j^2}
\]

- 在本文中，**DOS 是基于上述 hybrid mode 的本征频率 \( \lambda^\pm_j \)** 计算出来的。

---

#### 3️⃣ 为什么 near-visible 会出现 Cherenkov-like radiation？
- IR comb 是 Kerr 效应在 IR 波段产生的，其频率分布为：

\[
f_n = f_0 + n \cdot \text{FSR}
\]

- 当某一个 comb line 的频率刚好等于一个 hybrid mode 的频率（尤其是以可见光为主成分的 hybrid mode）：

\[
f_n^{\text{comb}} \approx \lambda_j^\pm
\]

→ **DOS 增强** → 光谱中该点能量急剧上升 → 出现“Cherenkov-like radiation”。

---

#### 4️⃣ 图示说明（参考 Fig. 2b）：
- 图中绿虚线表示 \( D_{\text{int}} = 0 \) 的位置；
- 该点即为 comb line 与 hybrid mode 共振的频率；
- 可视为 **非线性光学版本的 Cherenkov radiation（色散波）**。

---

### ✅ 小结：
| 概念 | 含义 |
|------|------|
| Hybrid mode | 红外 + 可见光模式通过 χ(2) 强耦合混合出的新模式 |
| DOS | 基于 hybrid mode 频率计算，衡量 comb line 是否落在共振点上 |
| Cherenkov-like radiation | 来自 comb line 与 hybrid mode 的频率对齐共振增强 |
| 可调性 | 改变波导宽度可调节 hybrid mode 的频率，从而调控 radiation 位置 |

---

