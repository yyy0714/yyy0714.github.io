---
layout: default
title: MOSFET
permalink: /mosfet
---

## Threshold Voltage $V_{\rm t}$

**Threshold voltage** is the value of gate-source voltage ($v_{\rm GS}$) at which a sufficient number of mobile electrons accumulate in the channel region to form a conducting channel.

---

## Overdrive Voltage $v_{\rm ov}$

**Overdrive voltage** is defined as

$$
v_{\rm ov} \equiv v_{\rm GS} - V_{\rm t}
$$

---

## Oxide Capacitance $C_{\rm ox}$

**Oxide capacitance** is the capacitance of the parallel-plate capacitor **per unit area**.

$$
C_{\rm ox} = \frac{\epsilon_{\rm ox}}{t_{\rm ox}}
$$

Where
- $\epsilon_{\rm ox}$ is the oxide permittivity, $\rm F/m$
- $t_{\rm ox}$ is the oxide thickness, $\rm m$

---

## Channel charge $Q$

$$
\begin{equation}
    Q = C_{\rm ox} \cdot W \cdot L \cdot v_{\rm ov}
    \label{eq:channel-charge}
\end{equation}
$$

Where
- $W$ is the channel width, $\rm m$
- $L$ is the channel length, $\rm m$

---

## Assumptions

For the following sections, a few assumptions are made:
- **Enhancement-type *n*-channel MOSFET** is used.
- Source and base are connected to the gound ($v_{\rm S} = v_{\rm B} = 0$).
- $v_{\rm GS}$ is held constant and $v_{\rm GS} > V_{\rm t}$.
- $v_{\rm DS}$ is positive, so electrons flow from source to drain.
- **Channel-length modulation** is ignored when $v_{\rm DS}$ is small and medium.

---

## Channel Current $i_{\rm D}$

### Linear Region: Small $v_{\rm DS}$

Since $v_{\rm DS}$ is small, we can assume that the voltage between the gate and various points along the channel is uniform and equal to $v_{\rm GS}$.

According to Coloumb's law, the magnitude of **electric field $\mathbf{E}$** across the channel is

$$
|\mathbf{E}| = \frac{v_{\rm DS}}{L}
$$

According to Ohm's law, the magnitude of **drift velocity $\boldsymbol{\nu}$** of the channel electrons towards the drain is

$$
\begin{equation}
    |\boldsymbol{\nu}| = \mu_{\rm n} |\mathbf{E}|
    \label{eq:channel-electron-velocity}
\end{equation}
$$

Where
- $\mu_{\rm n}$ is the electron mobility, $\rm m^2/(V \cdot s)$

By the definition of current (charge per unit time)

$$
i_{\rm D} = |\boldsymbol{\nu}| \cdot \frac{Q}{L}
$$

According to equation \eqref{eq:channel-charge} and equation \eqref{eq:channel-electron-velocity}

$$
\boxed{
    i_{\rm D} =
    \mu_{\rm n} \cdot 
    C_{\rm ox} \cdot 
    \frac{W}{L} \cdot 
    v_{\rm ov} \cdot 
    v_{\rm DS} 
}
$$
        
Observe that $i_{\rm D}$ is linearly dependent on $v_{\rm DS}$, thus the MOSFET is operating like a resistor with resistance

$$
r_{\rm DS} = \frac{1}{\mu_{\rm n} \cdot C_{\rm ox} \cdot \frac{W}{L} \cdot v_{\rm ov}}
$$

### Quadratic Region: Medium $v_{\rm DS}$

As $v_{\rm DS}$ increases, we can no longer assume that the voltage between the gate and various points along the channel is uniform and equal to $v_{\rm GS}$. Instead, the voltage of interest near the source now is $v_{\rm GS} - v_{\rm DS}$.

$$
\boxed{
    i_{\rm D} = 
    \mu_{\rm n} \cdot 
    C_{\rm ox} \cdot 
    \frac{W}{L} \cdot 
    \left( v_{\rm ov} - \frac{1}{2} v_{\rm DS} \right) \cdot 
    v_{\rm DS}
}
$$

### Saturation Region: Large $v_{\rm DS}$
When $v_{\rm DS} \geq v_{\rm ov}$, the channel is **pinched off**. Further increasing $v_{\rm DS}$ would cause **channel-length modulation**.

$$
\boxed{
    i_{\rm D} = 
    \frac{1}{2} \cdot
    \mu_{\rm n} \cdot 
    C_{\rm ox} \cdot 
    \frac{W}{L} \cdot 
    v_{\rm ov}^2 \cdot
    (1 + \lambda \cdot v_{\rm DS})
}
$$

Where
- $\lambda$ is the channel-length modulation coefficient, $\rm V^{-1}$

---

## Velocity Saturation
