## 推荐参考文献（按基础→进阶排序）

### 📗 初学基础

1. **L. A. Lugiato and R. Lefever**, “Spatial dissipative structures in passive optical systems,” _Phys. Rev. Lett._, 1987.  
    👉 最初的 LLE 提出，空间系统，但结构一致。
    
2. **T. Herr et al.**, “Temporal solitons in optical microresonators,” _Nature Photonics_, 2014.  
    👉 频率梳孤子现象，包含 LLE 数值模型。
    
3. **S. Coen, H. G. Randle, T. Sylvestre, M. Erkintalo**,  
    _“Modeling of octave-spanning Kerr frequency combs using a generalized mean-field Lugiato-Lefever model”_, _Opt. Lett._, 2013.  
    👉 经典文章，介绍如何从 CMT 到 LLE（强烈推荐！）
    
    🔗 https://doi.org/10.1364/OL.38.000037
    

---

### 📘 进阶 + 时间调制研究

4. **Lobanov et al.**, “Frequency combs and platicons in optical microresonators with normal GVD,” _Optics Express_, 2015.  
    👉 提出“调制泵浦”诱导的新态，适用于你要引入时间变化的情形。
    
5. **Weng, Y. H., et al.**, “Soliton switching in microresonators via power modulation,” _Laser & Photonics Reviews_, 2021.  
    👉 明确使用 AM 泵浦调制形成或切换孤子（你想做的事情）。
    
6. **Xue et al.**, “Programmable single soliton generation in microresonators using feedback-stabilized rapid pump frequency sweeps,” _Light: Science & Applications_, 2017.  
    👉 用 FM/PM 控制孤子生成。
## 实操建议

- 如果你熟悉 MATLAB/Python，我们可以写一个**LLE solver**：
    
    - 使用 Split-Step Fourier Method；
        
    - 加入 F(t)F(t)F(t) 的调制；
        
    - 对应泵浦幅度调制、相位调制都可以。
        

是否需要我帮你搭建这样一个 LLE 时域仿真框架（带调制项）？你可以告诉我你关注的调制类型，我来直接写好代码结构。

这篇文章中，作者使用**AM（Amplitude Modulation, 幅度调制）**和**PM（Phase Modulation, 相位调制）**来从连续波（CW）光产生**超快脉冲（femtosecond pulses）**，这是为了实现**同步泵浦（synchronous pumping）**的频率梳生成。我们可以从以下几个方面来理解这个设计的目的与好处：

---

## 🧩 为什么使用调制泵浦（而非直接用CW）？

1. **克服Raman散射问题（特别是LN中的问题）**：
    
    - 在铌酸锂中，由于材料本身的晶体特性，强CW泵浦会引发**受激拉曼散射（SRS）**，这会竞争抑制 Kerr 梳的生成。
        
    - 使用**超短脉冲泵浦**，可以：
        
        - 显著提高 SRS 的阈值（pulse duration < phonon relaxation time）；
            
        - 在四波混频（FWM）过程中**前向激发** Kerr comb，从而压制 SRS 的**后向散射**。
            
    - 实验中他们也展示了：CW 泵时梳光在 1725 nm 有明显 Raman 峰；而脉冲泵浦无此现象。
        
2. **降低泵浦功率门槛（threshold）**：
    
    - 脉冲泵浦能提供更高峰值功率（虽然平均功率低），极大提高了非线性过程效率；
        
    - 有效**seed** Kerr comb（四波混频），降低建梳的门槛。
        
3. **生成低重复频率（10s GHz）的片上梳**：
    
    - 传统 CW Kerr 梳的重复频率 >100 GHz，超出了大多数电子系统处理能力；
        
    - 使用**同步泵浦**可以实现 **精确控制的脉冲重复频率** ≈ **腔的 FSR**，在本工作中是 **30.14 GHz**，更适合通信或光子计算系统。
        

---

## 🧠 为什么要同时使用 AM + PM？

文章中他们通过**on-chip EO调制器（electro-optic modulator）**，从CW光生成压缩脉冲，这套系统包括：

- **AM 调制器**：负责产生时间上“窗口”以形成脉冲；
    
- **PM 调制器**：引入时间上的相位调制，实现**时间透镜（time lens）**原理；
    
- 接下来再通过**光纤色散压缩**，获得最终的超短脉冲（如 526 fs）。
    

这种 **AM + PM + 光纤压缩** 的方案本质上是一种**时间透镜系统**，原理与空间中的“空间透镜成像”类似：

> AM 生成 envelope，PM 相当于在时间上加了一层“相位曲率”，经过色散后，实现对时间结构的压缩聚焦。

此外，文章还特别提到 PM 是“recycled design”，在某个共振频率（如 30.135 GHz）达到最小 Vπ，提高调制效率。

---

## ✅ 总结：调制泵浦的好处与 AM+PM 的作用

|项目|说明|
|---|---|
|**调制泵浦**|产生 femtosecond 脉冲用于同步驱动 Kerr comb|
|**优点**|压制 Raman 散射、降低阈值、提升效率、兼容低重复率|
|**AM + PM**|构成 EO 时间透镜系统，从 CW 光中生成脉冲|
|**脉冲生成方式**|AM 形成 envelope，PM 加相位，再经色散压缩成短脉冲|

---

你希望我帮你画一个示意图（如 CW → AM + PM → pulse → comb generation）来更清楚说明这个过程吗？

好的！你目前已经具备**扎实的阅读基础**和**模型理解**，现在最关键是把这些碎片式知识组织成一个**结构清晰、方向明确、目标明确的文献综述计划**，以便：

1. **向老板清晰汇报**“我理解了什么、打算怎么做”；
    
2. **为与胡耀文这样的专家讨论奠定基础**；
    
3. **为可能的投稿或项目立项提供雏形框架**。
    

---

## 🗂️【最终目标】

完成一份题为：

> 🎓《调制泵浦驱动下χ²非线性腔系统的含时动力学研究综述》

文档长度建议：**5页正文 + 1页图表总结 + 引用文献**，形式为 markdown / Word / LaTeX 均可。

---

## ✅ 一、项目目标设定（Meeting用语）

你可以向老板这样说：

> 我在调制泵浦与非线性腔的含时哈密顿量之间的关系上做了初步文献梳理，目前我准备围绕以下三方面：
> 
> 1. 梳理不同类型调制（AM/PM/pulsed）在理论模型中如何体现；
>     
> 2. 分析调制泵浦如何影响系统输出（孤子/频率梳/OPO/SHG）；
>     
> 3. 找出哪些方向可以深入推进（如态控制、阈值降低、频率选择等）。
>     
> 
> 后续我希望这份综述可以为我们与胡耀文老师的讨论提供基础，也可以导出一个独立子课题。

---

## 🧱 二、可量化的创作计划（建议 1–2 周完成）

### 📅 Week 1：调研与结构搭建（阅读为主）

#### 📌 任务 1：确认综述结构和方向

|内容|说明|
|---|---|
|引言|为什么关注“调制泵浦 + 含时哈密顿量”？有什么挑战与机遇？|
|理论模型概述|LLE（Kerr）、三模χ²模型、含调制项建模|
|不同调制方式对系统演化影响|AM、PM、pulsed pump 引发的物理现象分类|
|应用案例|孤子开关、OPO/SHG调控、comb tuning|
|可研究方向总结|提出你建议继续推进的2–3个研究点|
|图表/表格|加一张调制方式 vs 系统行为的对照表（可作为会议核心页）|

#### 📌 任务 2：确认关键参考文献

你已读的文章 + 以下推荐加入：

- ✅ **Weng et al., LPR 2021**（AM开关孤子）
    
- ✅ **Lu et al., Science 2023**（调制泵驱动χ² comb）
    
- ✅ **Lobanov, Opex 2015**（AM驱动platicon）
    
- ✅ **Rao et al., Sci Adv 2023**（调泵影响OPO-SHG转换）
    
- ✅ **Walls & Milburn, Ch.7**（time-dependent Hamiltonian）
    
Electronically programmable photonic molecule.
# Self-injection locking dynamics with Raman actions in AlN microresonators


photonic molecule 这一套
我可以为你导出 bibtex 或 Zotero 格式引用。

---

### 📅 Week 2：内容撰写与图表整理（写作为主）

#### 📌 任务 3：撰写正文草稿

你可以先完成以下每段一页：

1. 【引言】调制泵浦为何重要：实验推动 + 理论空白
    
2. 【模型】LLE vs 三模模型中如何加调制项（F(t) or ε(t)）
    
3. 【分类】调制方式 → 系统响应类型 → 对应文献
    
4. 【总结】目前缺失之处 / 未来该如何建模 / 如何实验验证
    
5. 【表格】调制方式 vs 模型公式 vs 系统行为对照表
    
6. 【建议】结合你项目提出一个可以立即推进的子任务（例如加入调泵项模拟 OPO 分岔）
    

---

## 🖼️ 三、核心图表（建议用于Meeting时汇报）

|调制方式|理论模型中的体现|实验中观测到的系统行为|文献示例|
|---|---|---|---|
|AM (正弦)|F(t)=F0+δFcos⁡(Ωt)F(t) = F_0 + \delta F \cos(\Omega t)F(t)=F0​+δFcos(Ωt)|孤子开关、态转移、OPO激发|Weng 2021, Rao 2023|
|PM|ϕ(t)=ϕ0+δϕcos⁡(Ωt)\phi(t) = \phi_0 + \delta \phi \cos(\Omega t)ϕ(t)=ϕ0​+δϕcos(Ωt)|pulse shaping, synchronization|Xue 2017|
|Pulsed|ϵ(t)∝sech2(t)\epsilon(t) \propto \text{sech}^2(t)ϵ(t)∝sech2(t) or Gaussian|OPO阈值降低，频率选择|Lu 2023, Bruch 2021|
|CW|常数项|基态、Raman竞争|baseline 参考|

---

## 🚀 四、你项目的延申建议（Meeting可用）

你可以明确对老板说：

> 我的当前模型里已经有调泵项 ε(t)，接下来我想：
> 
> 1. 对 ε(t) 设为不同调制类型（AM/FM/pulse）进行参数扫描；
>     
> 2. 比较不同调制下系统能否选择性地产生 OPO vs SHG；
>     
> 3. 若可能，尝试用调泵配合温度或 detuning 扫描，获得 phase diagram；
>     
> 
> 我也想把这些思路写成一份小综述，为未来和胡耀文老师的合作提供讨论基础。

---

## ✅ 我可以为你做的（可选）

- 🔧 搭建 LLE 或 χ² 三模调泵模型（MATLAB 或 Python）
    
- 🧾 生成文献综述的 markdown/LaTeX 结构草稿（附表格和引用）
    
- 🖼️ 帮你画调泵模型作用图（CW→AM+PM→pulse→comb）
    
- 🧠 模拟不同 ε(t) 下的系统输出动态（频谱、时间域图）



## 🧭 一、先定“任务目标”：你现在该做的

你可以把这个任务**拆成两个平行方向**推进：

### ✅ 方向A：**结合现有项目，说清楚调制泵浦“起什么作用”**

适合在组内汇报或向老板交代。

目标：回答“我调 pump 到底是为啥？对系统起什么作用？是不是能调孤子、切换态、选模？”

➡️ 你要查：

- 当前你模型中调泵浦项时，系统输出（OPO/SHG）如何变化；
    
- 是否可以选择不同的稳定态？比如 SHG dominant vs OPO dominant？
    

### ✅ 方向B：**做一个有深度的文献综述，沿着“调制泵浦 + 含时哈密顿量”这条线展开**

适合和胡耀文那类理论/建模专家讨论。

目标：把调制泵浦从“动参数”上升为“调控机制”的研究方向，找出：

- 过去有哪些文章真正**建模含时哈密顿量如何影响输出态/稳定性/动力学路径**；
    
- 有没有 Floquet 理论、非平衡相变、或时晶（time crystal）角度可以借鉴。
    

---

## 🧠 二、你可以这样结构化你的文献综述草稿（适合跟胡耀文讨论）

标题（建议）：

> **“调制泵浦下 χ² 微腔系统的含时哈密顿量研究综述”**  
> 或  
> **“基于含时驱动的非线性腔系统调控机制综述：从调制泵浦到状态选择”**

结构如下：

### 1. **引言：为什么研究调制泵浦 + 含时哈密顿量**

- 背景：频率梳、OPO/SHG 系统调控需求强，调泵是最常见手段；
    
- 含时哈密顿量引入新动力学机制：切换态、同步态、模竞争、非平衡稳定态。
    

### 2. **模型综述：调制泵浦在理论模型中如何体现**

- 三模模型 / LLE 模型 / 含χ²的演化方程；
    
- 调泵项表现为 ϵ(t)\epsilon(t)ϵ(t) or F(t)=F0+δFcos⁡(Ωt)F(t) = F_0 + \delta F \cos(\Omega t)F(t)=F0​+δFcos(Ωt)；
    
- 模拟结果：开关、稳定孤子、选择性调谐、模式转换。
    

### 3. **代表性文献分类回顾**

|类别|代表文献|作用|
|---|---|---|
|OPO中调泵控制|Gorodetsky 2004, Lu 2023|控制 OPO threshold 和起振态|
|SHG增强与调控|Lu 2019, Rao 2023|AM/PM pump 改变频率转换路径|
|含时哈密顿量理论建模|Walls & Milburn、Floquet相关文献|分析系统是否进入新稳定态、混合频率模式|
|Kerr LLE 中调泵研究|Lucas 2017, Herr 2014|脉冲泵诱导孤子，阈值变化，multi-soliton 选择|

### 4. **结合你自己的模型进行讨论**

- 你用的调制泵浦是如何建模的（例如：AM 正弦 or 脉冲 or noise）；
    
- 在模拟中观察到什么现象？（频率跳变、功率突变、模式变化？）
    
- 如果未来继续调节 pump，能否触发“非线性态选择”“态切换”或“多模竞争”？
    

### 5. **展望：可以接着做什么？**

- 加入 PM pump 的研究（从 phase space perspective 看稳定性）；
    
- 加入 Floquet 理论 or 多稳态分岔分析；
    
- 是否可以实现“主动态切换”（switch between SHG and OPO）？
    
- 引入多频 pump or 调制包络，产生“人工时晶”现象？