
**作者**: Boqiang Shen  
**年份**: 2021  
**导师/课题组**: Vahala Group, Caltech

Optical frequency combs have a wide range of applications in science and technology, including but not limited to, time keeping [3, 4], optical frequency synthesis [5–9], spectroscopy [8, 10–14], ranging [15–18], astronomical calibration [19–25], and microwave generation [26–31].

---

## ✳️ 核心创新点总结

- Electro-optic comb 用于精密天文测速，并部署到实际望远镜系统中（Chapter 3）
- 可见波段孤子频率梳生成，扩展了工作波段（Chapter 4）
- 低功率操作下的孤子稳定性研究及 phase diagram 拓展（Chapter 5）
- 双向锁模孤子用于 Vernier 高分辨率频谱仪设计（Chapter 6）
- 集成式 turnkey 微梳系统无需隔离器与复杂反馈（Chapter 7）
- 在正常色散下的 dark soliton CMOS-ready comb（Chapter 8）

---

## 🧭 论文章节结构与亮点

### Chapter 2: Electro-optic Frequency Combs
- 2.1-2.3 EO comb 架构、补偿、整形
- 创新点：
  - 高频率电调梳成形稳定，易于集成
  - 为后续天文测速平台（Chapter 3）提供基础

#### 图 2.1:
- 图示了整个EO梳的系统结构
- **问题**：
  - 每个模块的作用是什么？
  - 这套结构与传统模式锁模激光器相比有什么优势？
  - 它能稳定到什么程度？（比如频率漂移、相位噪声）

---

### Chapter 3: EO comb in Astronomy (PARVI)
- 重点：将EO comb 应用到实际天文探测仪器
- 创新点：
  - 成功在帕洛玛望远镜部署EO LFC，实际用于系外行星探测

#### 图 3.1:
- 激光频率梳系统详细搭建图  
- **问题**：
  - 这个 setup 是否具备野外观测稳定性？
  - Rubidium clock 和参考气体怎么用于稳定频率？
  - 实验环境下误差有多小？

#### 图 3.3 & 3.4:
- Flattener 效果图与 GUI 控制界面
- **问题**：
  - spectral flattener 是如何实现均匀输出的？
  - 用户界面上的哪些控制与频梳操作相关？

---

### Chapter 4: Towards Visible Soliton Combs
- 利用工程设计使孤子扩展到可见波段（778nm）
- **创新点**：
  - 展示了目前最短波长的孤子频率梳（755-790nm）

#### 问题：
- 哪种几何设计使得可见波段孤子生成成为可能？
- 使用1064nm与778nm泵浦的差异与挑战？
- 如何解决模式交叉、色散变化的问题？

---

### Chapter 5: Low Power Soliton along Iso-Contours
- **亮点**：
  - 利用 iso-contour 描述孤子状态，提供稳定操作新图谱
  - 最低泵浦功率为 10.8 mW

#### 图 5.2:
- 实验 setup 和不同 detuning 下孤子光谱
- **问题**：
  - 哪些参量是 detuning？如何测量？
  - sech² 拟合精度如何？如何验证是真孤子？

#### 图 5.3:
- Pulse width 的 iso-contours
- **问题**：
  - 这些理论曲线是如何推导的？
  - 为何某些等值线实验与模拟不一致？

---

### Chapter 6: Vernier Spectrometer with CP Solitons
- **创新点**：
  - 使用一腔中双向孤子 comb 形成 Vernier 尺读频率，提升解析度
  - 可测 step-tuned, chirped, 多线谱源

#### 图 6.1:
- 实验 setup 与静态测量结果
- **问题**：
  - 两个 comb 如何 phase-lock？
  - 如何从 beatnote 中判定 comb order？

#### 图 6.3 & 6.4:
- 多线谱、相关函数测量、mode index 提取
- **问题**：
  - correlation 峰值如何对应 beat order？
  - 为什么可以做到 MHz 精度下的频率提取？

---

### Chapter 7: Turnkey Soliton Microcombs
- **亮点**：
  - 取消 isolator 和控制电路，实现即插即用
  - 系统封装进 butterfly 模块，便于大规模部署

#### 问题：
- 所谓“new operating point” 如何定义？有哪些参数窗口？
- 该系统在稳定性和控制性方面与传统差距如何？

---

### Chapter 8: Dark Soliton in Normal Dispersion SiN Platform
- **创新点**：
  - CMOS 工艺制备的正常色散平台也能产生锁模梳
  - 实现了 dark soliton 的自注入锁定与直接启动

#### 图 8.3:
- Dark comb 的形成与谱图
- **问题**：
  - 如何确定是 dark soliton？
  - 用什么方法控制 injection locking 启动过程？

---

## 📌 阅读笔记区

```markdown
### 📍 阅读位置:
- Chapter X, Page XX

### 🔍 内容概要:

### 🌟 技术细节亮点:

### 🧠 不理解的地方 / 提问:

### 🧪 后续可以尝试的研究角度:

