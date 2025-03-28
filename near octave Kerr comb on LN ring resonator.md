## 📄 [near octave Kerr comb on LN ring resonator]
**Authors**:  
**Journal / Year**:  
**Link**: [DOI or arXiv]  

---

### 🔍 What problem does this paper address?
realize broad band kerr comb by carefully design the waveguide geometry
suppressing Raman effects
study the geometry affects the DW

### 🧪 What are the key methods or experimental techniques?
- Experimental setup / materials used
- - **Platform**: z-cut LN microring (R = 60 µm, 560 nm thick, loaded Q not mentioned)
    ![[Pasted image 20250326162507.png]]
- **Key Components**:
    on chip pump 240mW, kappa_i = 190MHz, 
    experimental setup not mentioned
- Theoretical model (if any)
-Estamate the Raman threshold and Kerr threshold
- Key parameters or system
coupling rate interaction coefficient dispersion
### 📈 What are the main results?
- Successfully generated **single soliton comb** at 1550 with 4/5 Octave
    over the modes of interest, e should be made smaller than 2.2 i in order to have Rth > Sth (see Supplement 1 for a detailed calculation). In the experiment, e was adjusted by varying the coupling gap so that the microring exhibited e 1.3 i,
D2 very small = 2.6MHz
at this condition threshold first SRS/threshold kerr = 1.3
- directly scan from red detuned side
    
- Figures of interest:
    fig2 soliton 
     fig3 tuning of dispersive wave
     fig4 raman affects

### 🌟 What is novel or interesting about this work?
-broad band kerr comb on LN studied the DW how geometry will affect verify the theory model

### 📌 Connections to Gong Zheng’s PhD thesis
- Which chapter does this relate to?
- it is a natural extension of the AlN thermal controlling work. similar technique that can be used in the same area
- Is this part of a larger research trajectory?

### 💡 My thoughts & extensions
- - **Can I use this?**  
    Yes, we can use the structure to get good detune but they use TE in zcut its an old story
    
- **Adaptation?**  
    Replace traditional thermal-locking with this "photorefraction-locking" scheme at longer wavelengths.
    
- **New questions?**
    
    我想仿照这篇设计做一个可控 DW LN 微环，DW 的位置可以通过 waveguide 宽度线性调节，预期能对 2μm 区产生宽带覆盖，计划配合 dispersion map + Raman gain 图来确认。

## 一、结构很好，但可以强化**比较性与框架意识**

你已经用了“问题–方法–结果–亮点”的好模板，但还可以考虑在阅读过程中建立如下 **结构性对比思维**：

|要素|建议加入|
|---|---|
|✅ 所属技术框架|比如“热调控 → 光折边调控”的技术路径演进|
|✅ 与 AlN/Silicon 对比|为什么 Kerr comb 难做？材料性能 vs 腔设计|
|✅ 与其他 LN 梳子研究比较|与 Tang组其他 paper 比，它新在哪？光谱更宽？控制更稳？|
|✅ 与自己 setup 的兼容性|TE on z-cut 可能不适合你？能否复现 DW？工作波段不同？|

🌱 举个例子：

> 同样是抑制拉曼，这篇用 geometry 工程 + 弱化 Raman；  
> 而另一篇（你前面读的 bidirectional pump）靠的是结构扰动避开受激激发区；  
> → 两种方式异曲同工，但在热稳定性 vs 系统复杂度上有 trade-off。

---

## 🔍 二、模型分析上，可以加入“量纲估计”与“数值判断力”

你已经提到了 Raman threshold 与 Kerr threshold，这其实是一个进入“科研判断力”的好入口！

建议你尝试加一句类比或估算：

> “Raman threshold ~XX mW vs Kerr threshold ~XX mW → 说明在本结构中 Kerr 主导非线性演化，Raman 被压制。”

🌱 或者加一点延伸性问题：

- “如果换成 x-cut 或换为 TE1 模式，Raman 会不会被激活？”
    
- “该波导横向尺寸对 DW 的调控灵敏度是多少？对 fabrication error 是否 robust？”
    

这类问题哪怕你不立刻能回答，也能逐步训练你“结构-性能”之间的量化直觉。

---

## 🌟 三、亮点总结可以更突出“为什么这篇 work 成立”

你写的是“verify DW 模型”，很好，但建议再进一步归纳**它为什么能做到 near-octave**：

|层次|可加入内容|
|---|---|
|Geometry 优化|精准工程化 GVD，控制 DW 出现频率|
|模式选择|TE 模式在 z-cut 上 Raman 活跃度更低，便于 suppress|
|Thermal or photorefraction?|是靠 fast ramp（SSBM）穿过 instability，还是靠 passive drift 进入稳定 detuning？|

你可以总结为：

> “DW positioning relies on precise dispersion shaping; LN geometry and Raman suppression enable stable soliton propagation to long λ.”

---

## 🧪 四、个人思考部分可以更“场景化”一点

你已经提到了“我能不能用？”、“能不能加 MZI？”，这是很好的科研问题感。

建议你加上一些更“仿真/实验路径”的具体化思路：

- 如果我想用这个结构，我该建哪种 FEM 模型？
    
- 它的 waveguide cross section 是不是可以拿来直接跑 Lumerical dispersion analysis？
    
- 我该如何判断 DW 位置与 β₂/β₃ 有关？ → 做一张参数扫描图？
    

甚至可以设想你和导师开会时会怎么说：

> “我想仿照这篇设计做一个可控 DW LN 微环，DW 的位置可以通过 waveguide 宽度线性调节，预期能对 2μm 区产生宽带覆盖，计划配合 dispersion map + Raman gain 图来确认。”

—

## ✅ 总结你的当前状态 + 建议路径

|项目|你现在做得很好|建议提升点|
|---|---|---|
|阅读结构|完整、准确，覆盖全面|可以增强对比性 + 总结归类意识|
|专业理解|懂梳子机制、DW、Raman|可加强模型理解、数值直觉|
|主动提问|已有问题感|可转向“实验设计问题”、“参数假设问题”|
|连接自己系统|已有初步思路|可进一步拆成“实验/仿真可行性分析”|