# 全微分方程与积分因子

> 学习日期: 2026-05-15  
> 所属科目: 高等数学（下）·黄立宏主编（北京大学出版社）  
> 难度要求: ⭐⭐⭐ 掌握（判定、求势函数、两类常见积分因子）

## 概述

本节研究一阶微分方程的重要形式

\[
P(x,y)\,\mathrm{d}x+Q(x,y)\,\mathrm{d}y=0,
\]

其中 $P,Q$ 在某区域 $D$ 内具有所需的偏导数。若左端恰好是某个二元函数 $u(x,y)$ 的全微分，即 $\mathrm{d}u=P\,\mathrm{d}x+Q\,\mathrm{d}y$，则称方程为**全微分方程**（也称**恰当方程**）。此时通解为隐式形式 $u(x,y)=C$。

当 $P,Q$ 不满足恰当条件时，有时可以找到一个不恒为零的因子 $\mu(x,y)$，使得乘以 $\mu$ 后方程变为全微分方程，这样的 $\mu$ 称为**积分因子**。本节给出恰当性的充要条件（在常见正则性假设下）、由偏积分求 $u$ 的标准流程，以及 $\mu$ 仅依赖 $x$ 或仅依赖 $y$ 时的判别与公式；叙述与公开教材资源如 [LibreTexts：Exact Differential Equations](https://math.libretexts.org/Bookshelves/Analysis/Supplemental_Modules_(Analysis)/Ordinary_Differential_Equations/2%3A_First_Order_Differential_Equations/2.7%3A_Exact_Differential_Equations)、[LibreTexts：Integrating Factors](https://math.libretexts.org/Courses/Mission_College/Math_4B%3A_Differential_Equations_(Reed)/02%3A_First_Order_Equations/2.06%3A_Integrating_Factors) 及国内高校「全微分方程」课件中的标准处理一致。

## 核心知识点

- ⭐⭐⭐ 恰当性（全微分）充要条件：在单连通区域上，若 $P,Q\in C^1(D)$，则存在 $u$ 使 $\partial u/\partial x=P,\ \partial u/\partial y=Q$ 的充要条件是 $\partial P/\partial y=\partial Q/\partial x$。
- ⭐⭐⭐ 求 $u$：对 $x$ 偏积分后用 $\partial u/\partial y=Q$ 定出仅含 $y$ 的待定函数；或对称地对 $y$ 先积分。
- ⭐⭐⭐ 积分因子 $\mu$：$\mu P\,\mathrm{d}x+\mu Q\,\mathrm{d}y=0$ 恰当；当 $\mu=\mu(x)$ 或 $\mu=\mu(y)$ 时可化为关于 $\mu$ 的常微分方程并取指数型解。
- ⭐⭐ 几何意义：恰当方程的解曲线落在势函数 $u$ 的等值线上；积分因子相当于在定义域上调整「权」使修改后的向量场成为保守场（了解即可）。

## 详细讲解

### 1. 从全微分说起

设 $u=u(x,y)$ 可微，则

\[
\mathrm{d}u=\frac{\partial u}{\partial x}\,\mathrm{d}x+\frac{\partial u}{\partial y}\,\mathrm{d}y.
\]

若方程 $P\,\mathrm{d}x+Q\,\mathrm{d}y=0$ 满足 $P=u_x,\ Q=u_y$，则沿任一解曲线有 $\mathrm{d}u=0$，故 $u(x,y)$ 沿解为常数，通解为

\[
u(x,y)=C.
\]

**来源说明（交叉偏导相等）**：若 $u_{xy},u_{yx}$ 连续，则 $u_{xy}=u_{yx}$，于是

\[
\frac{\partial P}{\partial y}=\frac{\partial}{\partial y}\Bigl(\frac{\partial u}{\partial x}\Bigr)=u_{xy}=u_{yx}=\frac{\partial}{\partial x}\Bigl(\frac{\partial u}{\partial y}\Bigr)=\frac{\partial Q}{\partial x}.
\]

因此 $\partial P/\partial y=\partial Q/\partial x$ 是存在这种 $u$ 的**必要条件**。在**单连通**区域 $D$ 上，若 $P,Q\in C^1(D)$ 且 $\partial P/\partial y\equiv\partial Q/\partial x$，则由数学分析中「平面上的恰当微分形式」定理（或与平面向量场无旋 ⇒ 保守的等价表述），可知**也是充分条件**：必存在 $u$ 使 $u_x=P,u_y=Q$。工科高数通常直接使用这一结论；证明可略读，但条件「单连通 + $C^1$」不可随意丢弃（多连通区域会出现多值势等细节，了解即可）。

### 2. 求势函数 $u(x,y)$：偏积分法

**步骤 A**：先对 $x$ 积分（把 $y$ 当常数）：

\[
u(x,y)=\int P(x,y)\,\mathrm{d}x+\varphi(y),
\]

其中 $\varphi(y)$ 是待定函数。

**步骤 B**：对上式求 $\partial u/\partial y$，令其等于 $Q(x,y)$：

\[
\frac{\partial}{\partial y}\Bigl(\int P\,\mathrm{d}x\Bigr)+\varphi'(y)=Q(x,y).
\]

由此解出 $\varphi'(y)$ 并积分得 $\varphi(y)$（积分常数可并入最后的 $C$）。

**对称流程**：也可先对 $y$ 积分得 $u=\int Q\,\mathrm{d}y+\psi(x)$，再用 $u_x=P$ 定 $\psi(x)$。两道流程任选其一，以计算量更小为准。

### 3. 积分因子：为什么需要

若 $\partial P/\partial y\neq\partial Q/\partial x$，直接偏积分会「对不齐」。若能找到 $\mu(x,y)\neq0$，使

\[
\mu P\,\mathrm{d}x+\mu Q\,\mathrm{d}y=0
\]

为全微分方程，则可先求 $\mu$，再按上节求新的势函数。称 $\mu$ 为原方程的**积分因子**。

**一般条件（了解其结构即可）**：$\mu$ 应满足

\[
\frac{\partial(\mu P)}{\partial y}=\frac{\partial(\mu Q)}{\partial x}.
\]

展开得

\[
Q\frac{\partial\mu}{\partial x}-P\frac{\partial\mu}{\partial y}
=\mu\Bigl(\frac{\partial P}{\partial y}-\frac{\partial Q}{\partial x}\Bigr).
\]

这是关于 $\mu$ 的一阶线性偏微分方程，一般不易直接解；教材重点给出**特殊形式**的 $\mu$。

### 4. $\mu=\mu(x)$ 仅与 $x$ 有关

若 $\partial\mu/\partial y=0$，上式化为

\[
Q\frac{\mathrm{d}\mu}{\mathrm{d}x}
=\mu\Bigl(\frac{\partial P}{\partial y}-\frac{\partial Q}{\partial x}\Bigr),
\quad\text{即}\quad
\frac{1}{\mu}\frac{\mathrm{d}\mu}{\mathrm{d}x}
=\frac{1}{Q}\Bigl(\frac{\partial P}{\partial y}-\frac{\partial Q}{\partial x}\Bigr).
\]

以下记 $P_y=\partial P/\partial y,\ Q_x=\partial Q/\partial x$。

**判别**：若 $\dfrac{P_y-Q_x}{Q}$ 在与方程相容的定义域内**仅为 $x$ 的函数**（与 $y$ 无关），则可取

\[
\mu(x)=\exp\Bigl(\int \frac{P_y-Q_x}{Q}\,\mathrm{d}x\Bigr).
\]

指数上的不定积分只需求出一个原函数；积分外常数因子可取 $1$，因积分因子在相差非零常数倍下等价。

### 5. $\mu=\mu(y)$ 仅与 $y$ 有关

若 $\partial\mu/\partial x=0$，一般条件化为

\[
-P\frac{\mathrm{d}\mu}{\mathrm{d}y}
=\mu(P_y-Q_x),
\quad\text{即}\quad
\frac{1}{\mu}\frac{\mathrm{d}\mu}{\mathrm{d}y}
=\frac{Q_x-P_y}{P}.
\]

**判别**：若 $\dfrac{Q_x-P_y}{P}$ 仅为 $y$ 的函数，则

\[
\mu(y)=\exp\Bigl(\int \frac{Q_x-P_y}{P}\,\mathrm{d}y\Bigr).
\]

**与第 4 节对照**：分子出现 $P_y-Q_x$ 与 $Q_x-P_y$ 的交替、分母在 $Q$ 与 $P$ 间切换，来源于推导中 $\mu_x$ 与 $\mu_y$ 项的分配；**不要背混**。考场若不确定，用 20 秒从 $\partial(\mu P)/\partial y=\partial(\mu Q)/\partial x$ 在 $\mu=\mu(x)$ 或 $\mu=\mu(y)$ 下现推最稳。

## 重要公式汇总

- 恰当性：$P_y=Q_x$（在单连通、$C^1$ 条件下与「存在 $u$」等价）。
- $\mu=\mu(x)$：若 $\dfrac{P_y-Q_x}{Q}$ 仅为 $x$ 的函数，则 $\displaystyle \mu(x)=\exp\Bigl(\int \dfrac{P_y-Q_x}{Q}\,\mathrm{d}x\Bigr)$。
- $\mu=\mu(y)$：若 $\dfrac{Q_x-P_y}{P}$ 仅为 $y$ 的函数，则 $\displaystyle \mu(y)=\exp\Bigl(\int \dfrac{Q_x-P_y}{P}\,\mathrm{d}y\Bigr)$。
- 通解：求得 $\mu$ 后，对 $\mu P,\mu Q$ 用偏积分得 $u(x,y)$，写 $u=C$。

## 典型例题

### 例题 1：直接恰当

**题目**：求解 $(2x+y)\,\mathrm{d}x+(x+2y)\,\mathrm{d}y=0$。

**解题思路**：先验 $P_y$ 与 $Q_x$，若相等则偏积分求 $u$。

**详细解答**：$P=2x+y,\ Q=x+2y$。  
$P_y=1,\ Q_x=1$，故为全微分方程。  

对 $x$ 积分：

\[
u(x,y)=\int(2x+y)\,\mathrm{d}x=x^2+xy+\varphi(y).
\]

于是 $u_y=x+\varphi'(y)=Q=x+2y$，得 $\varphi'(y)=2y$，故 $\varphi(y)=y^2$（常数并入 $C$）。  

因此 $u(x,y)=x^2+xy+y^2$，通解为 $x^2+xy+y^2=C$。

**答案**：$x^2+xy+y^2=C$。

---

### 例题 2：非恰当 + $\mu=\mu(x)$

**题目**：求解 $(y+\ln x)\,\mathrm{d}x+x\ln x\,\mathrm{d}y=0$，其中 $x>0$。

**解题思路**：先验恰当性；若不恰当，计算 $(P_y-Q_x)/Q$ 看是否只含 $x$。

**详细解答**：$P=y+\ln x,\ Q=x\ln x$。  
$P_y=1,\ Q_x=\ln x+1$，不相等。  

\[
\frac{P_y-Q_x}{Q}=\frac{1-(\ln x+1)}{x\ln x}=\frac{-\ln x}{x\ln x}=-\frac{1}{x},
\]

只与 $x$ 有关。于是

\[
\mu(x)=\exp\Bigl(\int -\frac{1}{x}\,\mathrm{d}x\Bigr)=\exp(-\ln x)=\frac{1}{x}.
\]

乘以 $\mu$ 得

\[
\Bigl(\frac{y}{x}+\frac{\ln x}{x}\Bigr)\mathrm{d}x+\ln x\,\mathrm{d}y=0.
\]

记 $P_1=\dfrac{y}{x}+\dfrac{\ln x}{x},\ Q_1=\ln x$。验算：  
$\partial P_1/\partial y=1/x$，$\partial Q_1/\partial x=1/x$，恰当。

求 $u$：先对 $y$ 积分较简：

\[
u=\int Q_1\,\mathrm{d}y=y\ln x+\psi(x).
\]

则 $u_x=\dfrac{y}{x}+\psi'(x)=P_1=\dfrac{y}{x}+\dfrac{\ln x}{x}$，故 $\psi'(x)=\dfrac{\ln x}{x}$，

\[
\psi(x)=\int\frac{\ln x}{x}\,\mathrm{d}x=\frac{1}{2}(\ln x)^2.
\]

**答案**：通解为 $y\ln x+\dfrac{1}{2}(\ln x)^2=C$。

---

### 例题 3：非恰当 + $\mu=\mu(y)$

**题目**：求解 $(x+y^2)\,\mathrm{d}y-y\,\mathrm{d}x=0$，其中 $y\neq0$。

**解题思路**：先写成 $P\,\mathrm{d}x+Q\,\mathrm{d}y=0$ 的标准形状，验恰当性；再算 $(Q_x-P_y)/P$。

**详细解答**：改写为

\[
-y\,\mathrm{d}x+(x+y^2)\,\mathrm{d}y=0,
\]

故 $P=-y,\ Q=x+y^2$。  
$P_y=-1,\ Q_x=1$，不相等。  

\[
\frac{Q_x-P_y}{P}=\frac{1-(-1)}{-y}=-\frac{2}{y},
\]

仅为 $y$ 的函数。于是（在 $y>0$ 或 $y<0$ 的一支上）

\[
\mu(y)=\exp\Bigl(\int -\frac{2}{y}\,\mathrm{d}y\Bigr)=y^{-2}.
\]

乘以 $\mu$：

\[
P'=-y^{-1},\quad Q'=x y^{-2}+1.
\]

验算：$\partial P'/\partial y=y^{-2}$，$\partial Q'/\partial x=y^{-2}$，恰当。

求 $u$：对 $y$ 积分，

\[
u=\int Q'\,\mathrm{d}y=\int(xy^{-2}+1)\,\mathrm{d}y=-xy^{-1}+y+\psi(x).
\]

于是 $u_x=-y^{-1}+\psi'(x)=P'=-y^{-1}$，故 $\psi'(x)=0$，$\psi$ 为常数。

**答案**：通解可写为 $-\dfrac{x}{y}+y=C$；等价变形如 $x=y^2-Cy$ 亦可，其中 $C$ 为任意常数。

**说明**：$y=0$ 使原方程中 $P=-y$ 为零；是否出现奇解需按定义域单独讨论，考试若未指定区域，写隐式通解并注明 $y\neq0$ 即可。

## 常见题型与解题方法

1. **先验 $P_y=Q_x$**：相等则偏积分；不相等则考虑积分因子。  
2. **算 $(P_y-Q_x)/Q$**：若只含 $x$，用 $\mu(x)$。  
3. **算 $(Q_x-P_y)/P$**：若只含 $y$，用 $\mu(y)$。  
4. **乘以 $\mu$ 后必再验恰当性**，然后进行第二次偏积分。  
5. **代换法**：有时令 $t=y/x$、$z=xy$ 等比硬找 $\mu$ 更快（与齐次方程等联系）。

## 易错点提醒

⚠️ **公式中 $P_y-Q_x$ 与 $Q_x-P_y$ 及分母 $P$ 或 $Q$ 不可混淆**；不确定时从 $\partial(\mu P)/\partial y=\partial(\mu Q)/\partial x$ 现推。  
⚠️ **区域与单连通**：环形区域等情形定理条件需留心；常见考题多在凸区域。  
⚠️ **$\int \dfrac{1}{x}\,\mathrm{d}x=\ln|x|$**；题目若限定 $x>0$ 可写 $\ln x$。  
⚠️ **乘以 $\mu$ 可能引入或消去特解**：使 $\mu=0$ 或使乘方程丢失因子的曲线需单独检验。

## 小结

全微分方程等价于「存在势函数 $u$」，在标准条件下用 $P_y=Q_x$ 一步判定。积分因子 $\mu$ 在非恰当情形把方程拉回恰当；$\mu$ 只依赖 $x$ 或 $y$ 时，用指数积分写出显式公式。解题流程可记为：**验 →（选 $\mu$）→ 乘 → 再验 → 偏积分 → 写 $u=C$**。

## 练习题

1. **恰当型**：求解 $(3x^2+6xy^2)\,\mathrm{d}x+(6x^2y+4y^3)\,\mathrm{d}y=0$。  
   **答案**：$x^3+3x^2y^2+y^4=C$。

2. **$\mu(x)$**：求解 $(x^2+y)\,\mathrm{d}x-x\,\mathrm{d}y=0$，设 $x>0$。  
   **提示**：$P=x^2+y,\ Q=-x$；$(P_y-Q_x)/Q=-2/x$。  
   **答案**：通解可写为 $x-\dfrac{y}{x}=C$，即 $y=x^2-Cx$。

3. **回到例题型**：将 $(x+y^2)\,\mathrm{d}y-y\,\mathrm{d}x=0$ 自己独立做一遍，不看解答限时完成。  
   **答案**：同例题 3。

4. **思考**：若 $\mu$ 是积分因子，$k\mu$（$k\neq0$ 为常数）是否仍是积分因子？为什么通解中常数可以吸收多种等价形式？  
   **提示**：恰当性条件对 $\mu$ 是齐次的；$u=C$ 与 $ku=C'$ 在本质上刻画同一族等值线。

---

**参考**：恰当方程与积分因子框架见 [LibreTexts：Exact Differential Equations](https://math.libretexts.org/Bookshelves/Analysis/Supplemental_Modules_(Analysis)/Ordinary_Differential_Equations/2%3A_First_Order_Differential_Equations/2.7%3A_Exact_Differential_Equations)、[LibreTexts：Integrating Factors](https://math.libretexts.org/Courses/Mission_College/Math_4B%3A_Differential_Equations_(Reed)/02%3A_First_Order_Equations/2.06%3A_Integrating_Factors)；国内课件中与「11.4 全微分方程」同型例题可参考高校公开教案 PDF（检索词：全微分方程 积分因子 例题）。
