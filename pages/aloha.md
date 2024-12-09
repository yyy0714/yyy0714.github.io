---
layout: default
title: ALOHA
permalink: /aloha
---

## Poisson Distribution

Suppose an event occurs $G$ times per second **on average**, if the occurance of the events follows the Poisson distribution, then the probability of the event occurs $k$ times per second is

$$
P(x = k) = \frac{G^k e^{-G}}{k!}
$$

## Pure ALOHA

In Pure ALOHA, transmission can happen any time.

Consider the following extreme case for collision:
- **A** transmits at time $T$ and it takes $t$ to reach **B**.
- **B** transmits right before $T + t$ and it also takes $t$ to reach **A**. 

Hence, **A** will not sense the collision after $T + 2t$. 

In Pure ALOHA, the probability of having a successful transmission is equivalent to the probability of having no additional transmissions during the $2t$ interval.

Suppose there are $G$ additional transmissions during time interval $t$ and this follows the Poisson distribution, then
- There are $2G$ additional transmissions on average during any $2t$ time interval.
- The probability of having $k$ additional transmission during any $2t$ time interval is $P(x = k) = \frac{2G^k e^{-2G}}{k!}$

Hence, the probability of having a successful transmission is

$$
P(x = 0) = \frac{2G^0 e^{-2G}}{0!} = e^{-2G}
$$

The above equation indicates that $G e^{-2G}$ transmissions are successful during any $t$ time interval and the maximum number of transmissions during any $t$ time interval is $1$.

Hence, the efficiency of Pure ALOHA is

$$
\eta = \frac{T_{\rm PA}}{T_{\rm max}} = G e^{-2G}
$$

and $\eta_{\rm max} = 18.4 \%$ when $G = 0.5$

## Time Slotted ALOHA

In Time Slotted ALOHA, transmissions can only happen during the start of each time slot. This elminates the extreme case mentioned in Pure ALOHA.

In Time Slotted ALOHA, the probability of having a successful transmission is equivalent to the probability of having no additional transmissions during the $t$ interval.

The probability of having a successful transmission is

$$
P(x = 0) = \frac{G^0 e^{-G}}{0!} = e^{-G}
$$

The efficiency of Time Slotted ALOHA is

$$
\eta = \frac{T_{\rm TSA}}{T_{\rm max}} = G e^{-G}
$$

and $\eta_{\rm max} = 36.8 \%$ when $G = 0.5$

The efficiency is $2\times$ better than that of Pure ALOHA!
