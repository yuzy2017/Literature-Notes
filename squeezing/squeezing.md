from Toman's LN squeezing paper

# 什么是squeezed light？
- 定义、数学表达式
- 单模 vs 双模 squeezing

# 如何在腔中产生 squeezed light？
- 非线性过程（OPO）机制
- 关键参数：pump, nonlinear coefficient, loss, Q...

# Squeezing 的影响因素
- 增大pump → squeezing增加？
- 增大Q → 增加光与材料相互作用的时间？
- Internal vs external coupling 比例如何影响测量？

# 实验上的挑战与优化策略
- 热效应、光折变、Kerr等寄生非线性
- modal phase matching 的优势
- 设计中如何实现低loss与高耦合

# 数学表达式总结
- quadrature variance 推导
- squeezing 与 gain 的关系式
- ## 一、squeezed quadrature 的表达式（主公式）

论文第4章和附录B中推导的核心结果为：

V−(ω)=1−ηesc4⋅P/Pth(1+P/Pth)2+(ωSB/Γ~s)2V_-(\omega) = 1 - \frac{\eta_{\text{esc}}}{4} \cdot \frac{\sqrt{P/P_{\text{th}}}}{(1 + \sqrt{P/P_{\text{th}}})^2 + (\omega_{\text{SB}} / \tilde{\Gamma}_s)^2}V−​(ω)=1−4ηesc​​⋅(1+P/Pth​​)2+(ωSB​/Γ~s​)2P/Pth​​​ V+(ω)=1+ηesc4⋅P/Pth(1−P/Pth)2+(ωSB/Γ~s)2V_+(\omega) = 1 + \frac{\eta_{\text{esc}}}{4} \cdot \frac{\sqrt{P/P_{\text{th}}}}{(1 - \sqrt{P/P_{\text{th}}})^2 + (\omega_{\text{SB}} / \tilde{\Gamma}_s)^2}V+​(ω)=1+4ηesc​​⋅(1−P/Pth​​)2+(ωSB​/Γ~s​)2P/Pth​​​

其中：

- V−V_-V−​：squeezed quadrature variance
    
- V+V_+V+​：anti-squeezed quadrature variance
    
- ηesc\eta_{\text{esc}}ηesc​：escape efficiency（腔中能量耦合出腔的比例）
    
- PPP：pump power
    
- PthP_{\text{th}}Pth​：振荡阈值功率
    
- ωSB\omega_{\text{SB}}ωSB​：sideband frequency（测量频率偏移）
    
- Γ~s\tilde{\Gamma}_sΓ~s​：signal 模式的总衰减率
    

---

## 🧩 二、关键变量和它们的物理含义

|变量|含义|增大会怎样影响 squeezing？|
|---|---|---|
|PPP|pump 功率|提升 squeezing（小于阈值时）；超过 50% Pth 后效果趋于平缓|
|PthP_{\text{th}}Pth​|振荡阈值功率|越低越好；与非线性耦合强度 Λ\LambdaΛ 成反比|
|ηesc\eta_{\text{esc}}ηesc​|escape efficiency|越大越好，更多 squeezed 光能从 cavity 输出|
|ωSB\omega_{\text{SB}}ωSB​|测量频率偏移|离开中心频率时 squeezing 会下降|
|Γ~s\tilde{\Gamma}_sΓ~s​|腔衰减速率（与Q因子相关）|越小（高Q）越有利于 narrow-band squeezing|

特别地，pump power 的影响是非线性的——不是越高越好，而是在 **临近阈值**的时候 squeezing 最强。

---

## 🔁 三、这个公式是如何推导来的？

推导逻辑分成三步：

### 1. **非线性哈密顿量建模**（第4章）

对于 χ² 材料，使用如下 Hamiltonian（假设简并 OPO）：

HNL=−ℏΛ cp cs†cs†+H.c.H_{\text{NL}} = -\hbar \Lambda \, c_p \, c_s^\dagger c_s^\dagger + \text{H.c.}HNL​=−ℏΛcp​cs†​cs†​+H.c.

推导得到 Heisenberg 运动方程，考虑 pump undepleted（未耗尽）近似后得到平均场和 fluctuation 的演化公式。

---

### 2. **解算 quadrature variance**

将 fluctuation 的运动方程（线性化后）转换到频域，解出输出 quadrature operator：

Xout(ω)=Kx(ω)Xin+Kx,phXph+...X_{\text{out}}(\omega) = K_x(\omega) X_{\text{in}} + K_{x,ph} X_{\text{ph}} + ...Xout​(ω)=Kx​(ω)Xin​+Kx,ph​Xph​+...

再对其计算期望值得到：

⟨Xout†Xout⟩=V−(ω)\langle X_{\text{out}}^\dagger X_{\text{out}} \rangle = V_-(\omega)⟨Xout†​Xout​⟩=V−​(ω)

同理得到 V+(ω)V_+(\omega)V+​(ω)。完整推导在附录 B.5。

---

### 3. **引入损耗模型**

如果考虑 detector 和耦合等的 loss，整体 squeezing 会变差：

V−→ηoptV−+(1−ηopt)V_- \rightarrow \eta_{\text{opt}} V_- + (1 - \eta_{\text{opt}})V−​→ηopt​V−​+(1−ηopt​)

也就是说损耗会把 squeezed 态拉回 vacuum noise。

---

## 🧠 四、使用费曼学习法的建议

你可以整理笔记时设以下问题：

1. 什么是 quadrature？X 和 P 分别代表什么？
    
2. 为什么有 squeezing 和 anti-squeezing？它们怎么从 Hamiltonian 推导来？
    
3. 为什么有阈值功率？如何用非线性系数 Λ\LambdaΛ、信号损耗率 Γ~s\tilde{\Gamma}_sΓ~s​ 写出？
    
4. 怎么优化 squeezing？是选材料提高 χ(2)\chi^{(2)}χ(2) 吗？是减小 loss 吗？
