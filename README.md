# SURGE: Optimal Hedging under Transaction Costs

**Researcher:** Aditya Mishra, IIT Kanpur

**Program:** SURGE 

**Supervisor:** *Dr. Akash Anand*

**Duration:** *May 12, 2026 - July 12, 2026*

---

## Project Overview: Optimal Hedging under Transaction Costs

This repository documents a comprehensive numerical verification of the Hodges and Neuberger (1989) optimal hedging model. While the classical Black-Scholes framework relies on continuous, costless rebalancing, real-world markets impose proportional transaction costs that make perfect replication infinitely expensive. 

To resolve this, this project reformulates the hedging process as a stochastic optimal control problem, seeking a dynamic strategy that maximizes the expected exponential utility of terminal wealth. The result is a mathematically rigorous "no-trade region" that optimally balances hedging error against transaction costs.

This research bridges continuous-time financial mathematics with discrete numerical implementation, relying on three core pillars:

### 1. Theoretical & Mathematical Framework
* **Stochastic Calculus:** Foundations in measure-theoretic probability, martingales, and Itô's lemma.
* **Optimal Control:** Derivation of the Hamilton-Jacobi-Bellman (HJB) equation and the cash-independence factorization strictly unique to exponential utility.
* **Free-Boundary Problems:** Application of smooth-pasting conditions to analytically define the buy/sell boundaries.
* **The SDE-PDE Correspondence:** Unifying stochastic expectations and deterministic PDEs via the Feynman-Kac theorem and the Kolmogorov Backward Equation.

### 2. Computational Architecture
The project verifies the optimal strategy by ensuring agreement across three independent computational routes:
* **SDE Simulation:** Vectorized Euler-Maruyama schemes to simulate Geometric Brownian Motion and evaluate discrete delta/Leland heuristic hedging.
* **Discrete Dynamic Programming:** Backward induction on Cox-Ross-Rubinstein (CRR) binomial lattices to compute the no-trade boundaries without continuous-time machinery.
* **Finite-Difference Solvers:** Crank-Nicolson PDE solvers tailored for free-boundary parabolic PDEs.

### 3. Headline Reproductions
This repository successfully reproduces the core findings of the original Hodges-Neuberger paper:
* **Graph A:** Numerical computation of the no-trade region boundaries $(x_{-}, x_{+})$ as a function of the transaction cost rate.
* **Graph C:** Analytical extraction of the asymptotic boundary behavior via Newton's method on the reduced 1D system.
* **The Efficient Frontier:** Extensive Monte Carlo verification demonstrating that the extracted H&N strategy Pareto-dominates both naive continuous hedging and Leland's volatility adjustment.
---

## Setup & Installation

```bash
# Clone the repository
git clone https://github.com/adityam1shra/SURGE-Optimal-Hedging-under-transaction-costs.git
cd SURGE-Optimal-Hedging-under-transaction-costs

# Create and activate virtual environment
python3 -m venv surge_venv
source surge_venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```
---

## References

- Hodges & Neuberger (1989), “Optimal Replication of Contingent Claims
  Under Transactions Costs.”
- Shreve, Stochastic Calculus for Finance II (Springer, 2004)
- Higham (2001), “An algorithmic introduction to numerical simulation of
  stochastic differential equations,” SIAM Review 43(3)
- Wilmott, P. — *Paul Wilmott on Quantitative Finance*
- Cox, Ross, Rubinstein (1979), “Option pricing: a simplified approach.”
- Leland (1985), “Option pricing and replication with transactions costs,” J.
  Finance 40(5): 1283–1301
- Boyle & Emanuel (1980), “Discretely adjusted option hedges,” J. Financial
  Economics 8: 259–82.
- Fleming & Soner, Controlled Markov Processes and Viscosity Solutions
  (2nd ed.), Ch. 2–3.
- 
