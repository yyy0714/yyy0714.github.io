---
layout: default
title: PN Junction
permalink: /pn-junction
---

## Drift Current $I_{\rm S}$

When an electric field $\mathbf{E}$ is applied across the semiconductor, for holes

$$
\begin{equation}
    \begin{split}
        \boldsymbol{\nu}_{\rm p} &= \mu_{\rm p} \cdot \mathbf{E} \\[2ex]
        \boldsymbol{\nu}_{\rm n} &= -\mu_{\rm n} \cdot \mathbf{E}
    \end{split}
    \label{drift-velocity}
\end{equation}
$$

Where
- $\boldsymbol{\nu}_{\rm p}$ is the hole drift velocity, $\rm m/s$
- $\boldsymbol{\nu}_{\rm n}$ is the electron drift velocity, $\rm m/s$
- $\mu_{\rm p}$ is the hole mobility, $\rm m^2/(V \cdot s)$
- $\mu_{\rm n}$ is the electron mobility, $\rm m^2/(V \cdot s)$

Note the minus sign in the case of electrons, since they move in the opposite direction of the electric field.

According to the definition of current (charge per unit time) and equation \eqref{drift-velocity}

$$
\begin{equation*}
    \begin{split}
        I_{\rm p} &= A \cdot q \cdot p \cdot \boldsymbol{\nu}_{\rm p} \\
                  &= A \cdot q \cdot p \cdot \mu_{\rm p} \cdot \mathbf{E} \\[2ex]
        I_{\rm n} &= -A \cdot q \cdot n \cdot \boldsymbol{\nu}_{\rm n} \\
                  &= A \cdot q \cdot n \cdot \mu_{\rm n} \cdot \mathbf{E}
    \end{split}
\end{equation*}
$$

Where
- $I_{\rm p}$ is the hole drift current
- $I_{\rm n}$ is the electron drift current
- $A$ is the cross-sectional area of the semiconductor, $\rm m^2$
- $q$ is the **magnitude** of electron charge, $\rm C$
- $p$ is the hole concentration, $\rm m^{-3}$
- $n$ is the electron concentration, $\rm m^{-3}$

The drift current is the sum of the hole and electron drift current

$$
\begin{equation}
    \begin{split}
        I_{\rm S} &= I_{\rm p} + I_{\rm n} \\
                  &= \boxed{A \cdot q \cdot (p \cdot \mu_{\rm p} + n \cdot \mu_{\rm n}) \cdot \mathbf{E}}
    \end{split}
    \label{drift-current}
\end{equation}
$$

According to the definition of current density (current per unit area) and equation \eqref{drift-current}

$$
\begin{align*}
    \mathbf{J}_{\rm S} &= \frac{I_{\rm S}}{A} \\
                       &= q \cdot (p \cdot \mu_{\rm p} + n \cdot \mu_{\rm n}) \cdot \mathbf{E}
\end{align*}
$$

Where
- $\mathbf{J}_{\rm S}$ is the drift current density, $\rm A/m^2$

---

## Diffusion Current $I_{\rm D}$

When there exists a concentration gradient for the charge carriers (either holes or electrons)

$$
\begin{equation}
    \mathbf{J}_{\rm D} = -q \cdot D_{\rm c} \cdot \frac{\mathrm{d} c(x)}{\mathrm{d} x}
    \label{diffusion-current-density}
\end{equation}
$$

where
- $\mathbf{J}_{\rm D}$ is the charge carrier diffusion current density, $\rm A/cm^2$
- $q$ is the **magnitude** of electron charge, $\rm C$
- $D_{\rm c}$ is charge carrier diffusivity, $\rm m^2/s$
- $c(x)$ is the charge carrier concentration at point $x$, $\rm m^{-3}$

By the definition of current and equation \eqref{diffusion-current-density}

$$
\begin{equation*}
    \begin{split}
        I_{\rm D} &= A \cdot \mathbf{J}_{\rm D} \\
                  &= \boxed{-A \cdot q \cdot D_{\rm c} \cdot \frac{\mathrm{d} c(x)}{\mathrm{d} x}}
    \end{split}
\end{equation*}
$$

---

## PN Junction without Applied Voltage

### Junction Built-in Voltage $V_0$

$$
V_0 = V_{\rm T} \ln \left( \frac{N_{\rm A} \cdot N_{\rm D}}{n_{\rm i}^2} \right)
$$

Where
- $V_{\rm T}$ is the thermal voltage, $\rm K$
- $N_{\rm A}$ is the hole concentration of the *p*-type material, $\rm m^{-3}$
- $N_{\rm D}$ is the electron concentration of the *n*-type material, $\rm m^{-3}$
- $n_{\rm i}$ is the intrinsic carrier concentration, $\rm m^{-3}$

### Depletion Region Width $W$

$$
W = \sqrt{ \frac{2 \epsilon_{\rm s}}{q} \cdot \left( \frac{1}{N_{\rm A}} + \frac{1}{N_{\rm D}} \right) \cdot V_0 }
$$

Where
- $\epsilon_{\rm s}$ is the electrical permittivity of silicon, $\rm F/cm$
- $q$ is the magnitude of electron charge, $\rm C$

### Depletion Region Charge $Q$

$$
Q = A \cdot \sqrt{ 2 \epsilon_{\rm s} \cdot q \left( \frac{N_{\rm A} \cdot N_{\rm D}}{N_{\rm A} + N_{\rm D}} \right) \cdot V_0 }
$$

---

## PN Junction with Applied Voltage
- Reverse-bias
    - No diffusion current, so only small current equal to drift current at terminals
    - Increased voltage barrier
    - Increased depletion region
    - Reverse breakdown: zener effect and avalanche effect (not gonna cover)
- Forward-bias
    - Diffusion current increases significantly, so noticeable current equal to $I_{\rm D} - I_{\rm S}$
    - Reduced voltage barrier
    - Reduced depletion region
    - Excess concentration of minority carrier on both sides
    - Diffusion length
    - Saturation current

