LN and BTO frequency response
device design to compensate the modulation dispersion

high frequency measurement (broadband) we have material any application
measurement method and optimization

1. **首次实现**对 LN 与 BTO 薄膜的 **介电常数与 Pockels 系数在100 MHz 到 330 GHz范围内的连续测量**；
    
2. **设计了专用相位移器**，集成在光子芯片中，用于宽带 EO 参数测量：
    
    - 利用高效、短长度、低损耗的 plasmonic-like 结构；
        
    - 避免了传统调制器中 RC 限制和速度失配问题；
        
3. 提出并验证了 **一个用于提取有效Pockels系数 reff 与介电常数的方法**，使用VNA反射测量（S11）与模拟拟合；
    
4. **发现：**
    
    - LN 的电光参数随频率变化极小（非常稳定）；
        
    - BTO 的 r₄₂ 和 εa 显著频率依赖，但 r₃₃ 和 εc 在 >1 GHz 范围内稳定；
        
5. **创新地证明：** 通过特定器件几何结构（例如增大电极-材料间隔），**可以消除 BTO 在高频下 r₄₂ 衰减造成的调制响应下降**。




## **四、创新点/贡献是什么？（What is new?）**

✅ **首次报道**：LN 与 BTO 的 Pockels 系数与介电常数从 MHz 到 330 GHz 的连续测量；

✅ **器件方法创新**：设计了一种高效、适用于超宽带电光表征的集成相位调制器结构；

✅ **首次实验证实**：

- BTO 的 r₄₂ 随频率显著下降，r₃₃ 相对稳定；
    
- εa 与 r₄₂ 的色散行为相关；
    
- 通过 Miller’s Rule 拟合 r₄₂ 的色散特性；
    
- 对器件结构做理论分析，解释为什么 **BTO 的 photonic 结构在高频仍能维持平坦调制响应**，而 plasmonic 结构会失真；
其实问题就是 怎么设计 会让 r42 更加稳定

✅ **对新材料发展具有指导性意义**，为下一代高速电光器件（>300 GHz）开发提供方法学框架。


## Monolithic Barium Titanate Modulators on Silicon-on-Insulator Substrates
RF sputtered BTO 3.17db/cm

LN approximate 0.25db/cm   **Wang et al., Nature 2018**: ≈ 0.27 dB/cm

quantum computing???
    SiN BTO 0.053db/cm 能否贴 如果给面试问一下研究重点？？？
    Possible for a CMOS compatable EO comb
    A manufacturable platform for photonic quantum computing
    ![[Pasted image 20250617153356.png]]
    ![[Pasted image 20250617153536.png]]
    ![[Pasted image 20250617153837.png]]
![[Pasted image 20250617155820.png]]

pulse 光通信友什么用
载波之间相干 就可以当成多载波激光阵列来跑DWDM， 同时保持了载波之间的严格的光学相位关系 支持QAM massively parallel more than 50TB.s on 179 individual carriers C and L bands (100GHz FSR) 如果EO comb也能这样子的话 就nb了

梳齿相干 那么 只用一个 comb teeth就可以对多路进行LO 补偿漂移

微波噪声在什么作用？

zhang mian photonic molecule 


# All-optical high-speed signal processing with silicon–organic hybrid slot waveguides

这个就是 异质集成的工作 然后 question is all optical switch 4mm long Si- organic hybrid wg
1e5 w-1/km 170Gb/s
全光开关 然后传统波导那个非线性效率低 掺杂可能有别的问题 好比说 free carrier absorption

slot contine electric field and polymer increase nonlinear coefficient
measure the third order by four wave mixing 

verify in a optical communication system

Nonlinear silicon photonics

chi1 chi3 
chi1 is free carrier 

chi3 different frequency involved as it mentioned in the article

he also talk about the speed not only related to the nonlinear process but also related to the structure and free carrier absorption? If it can operate for a long time???

then third order nonliearity application
1 super continuum
2THG
3 raman
4 fwm -- frequency conversion // amplification
5 demultiplexing
6 time frequency conversion
7 slot waveguide sensor

# Ultra-wideband MHz to THz plasmonic EO modulator
EO modulator not only for high speed communication but also can for the THz transceiver.
smaller pad provide for higher speed
design of the pad and design of the testing need to be checked in detail

# Measuring dielectric and electro-optic responses of thin films using plasmonic devices
用点 就是 希望在从 MHz 到 THz 范围里 测量 BTO的 epsilon 和 pockels coefficient
use plasmonic device
1 small so we can use lumped parameter to build the model
2 confine well so that results different from surrounding material (top down; bottom up; )

method
s11 get epsilon $C_{slot}$
sideband height get pockels coefficient V

result 
$\epsilon_{eff} = 30 (200MHz)$  18(67GHz)
$r_{eff}= 16pm/V$ 8pm/V(70GHz)
surface and gap affect the frequency responce very much

simple and effective


# 256 GBd Barium-Titanate-on-SiN Mach-Zehnder Modulator
![[Pasted image 20250619205259.png]]
how to improve the loss need to be checked  (2024)
the propagation loss is 0.5db/um could be better but the modulation seems cut at 110GHz 
transition 0.14db
3.5db photonic plasmonic conversion (this is too much) cannot be used in ring resonator
![[Pasted image 20250619205448.png]]

![[Pasted image 20250619205513.png]]
could change to without taper just use evanescent wave to modulatez


slow light loss still high 0.6dB/cm can you make plasmonic modulator of LN???

# Barium Titanate Racetrack Modulator on Silicon Nitride for 200 GBd Data Communication in the O-band
this structure there is no ring characterization just can be used

# PLD Epitaxial Thin-Film BaTiO3 on MgO − Dielectric and Electro-Optic Properties
## why
长膜的办法 PLD(pulse laser deposited)
higher quality than MOCVD cheaper than MBE

那 感觉 Joel Winiger 还是很猛的呀 天天在实验室 自己很chill
Tobias 也是很猛的呀 woc 感觉错过了 一个亿
measure the parameter with plasmonic devices
measure at higher frequency
## result
Pockels coefficient or the epsilon is constant upt to 67GHz
RF $\epsilon = 1100$  $r = 390 pm/V$ in the clamped regime
EO comb You only need to care about the desired modulate region

so if you learn analog circuits it could be used in both the modulator and the memristor.
## how
fab
design
measure

## so what
fill the gap of eo response of high speed thin film BTO
PLD cheap and high quality
domain to eo, growth to eo
