---
creation date: 2024-11-07 15:46
modification date: Thu 7th November 2024 15:46:19
up: "[[Modes of Convergence]]"
references: 
tags:
---
> [!theorem] Mann-Wald CMT
> Let $(S, \rho),\ (S', \rho')$ be metric spaces, let $\{ X_{n} \}$ and $X$ be random elements of $(S, \rho)$, and let $g: S\mapsto S'$ be measurable and continuous. Then, 
> 1) $X_{n}\xrightarrow{a.s.}X$ implies $g(X_{n})\xrightarrow{a.s.}g(X)$
> 2) $X_{n}\xrightarrow{p}X$ implies $g(X_{n})\xrightarrow{p}g(X)$
> 3) $X_{n}\xrightarrow{d}X$ implies $g(X_{n})\xrightarrow{d}g(X)$

`\begin{proof}`
	$(1)$ We know that there are measurable $\Omega',\ \Omega'' \subseteq \Omega$ such that $X_{n}(\omega)\to X(\omega),\ \forall\omega \in \Omega'$, $g$ is continuous at all $X(\omega)\text{ s.t. }\omega \in \Omega''$, and $P(\Omega')=P(\Omega'') = 1$. Firstly, $\Omega' \cap \Omega''$ is measurable with $P(\Omega' \cap \Omega'') = 1$, since, 
	$$
	P(\Omega' \cap \Omega'') = 1 - P((\Omega')^{c}\cup (\Omega'')^{c})\geq 1 - P((\Omega')^{c}) - P((\Omega'')^{c}) = 1
	$$
	Secondly, $g(X_{n}(\omega))\to g(X(\omega))$ at all $\omega \in \Omega' \cap \Omega''$. 
	$(2)$ we only show for constant $\alpha$. By continuity of $g$ at $\alpha$, for each $\epsilon>0$, there is a $\delta>0$ such that $\rho(X_{n}, \alpha)<\delta \implies \rho'(g(X_{n}), g(\alpha))< \epsilon$. So, 
	$$
	1\geq P(\rho'(g(X_{n}), g(\alpha))< \epsilon)\geq P(\rho(X_{n}, \alpha)<\delta)
	$$
	Since $X_{n}\xrightarrow{p}\alpha$, the RHS converges to $\hspace{0pt}1$ regardless of the choice of $\delta$. It follows that $P(\rho'(g(X_{n}), g(\alpha))<\epsilon)\to 1$ for each $\epsilon>0$. Ie. $g(X_{n})\xrightarrow{p}g(\alpha)$. 
	$(3)$. For $S = \mathbb{R}^{l},\ S' = \mathbb{R}^{m}$, fix $t \in \mathbb{R}^{l}$. We wish to show that $\phi_{g(X_{n})}(t)\to\phi_{g(X)}(t)$. We have, 
	$$
	\begin{align}
	\phi_{g(X_{n})}(t) & = \int _{\mathbb{R}^{l}}\exp(it^{T}g(y)) \, F_{X_{n}}(dy)  \\
	 & = \int _{\mathbb{R}^{l}}\cos(tg(y)) \, F_{X_{n}}(dy) + i \int _{\mathbb{R}^{l}}\sin(tg(y)) \, F_{X_{n}}(dy) \\
	  & \to \int _{\mathbb{R}^{l}}\cos(tg(y)) \, F_{X}(dy) + i\int _{\mathbb{R^{l}}} \sin(tg(y)) \, F_{X}(dy) \\
	  & = \int _{\mathbb{R}^{l}}\exp(itg(y)) \, F_{X}(dy) \\
	  & = \phi_{g(X)}(t)
	\end{align}
	$$
	where convergence follows by the [[Portmanteau Theorem]] since $y\mapsto \cos(tg(y))$ and $y\mapsto\sin(tg(y))$ are bounded and continuous mappings. Hence $g(X_{n})\xrightarrow{d}g(X)$ by [[Levy's Continuity Theorem]]. 
`\end{proof}`

# Motivation
The Continuous Mapping Theorem (CMT) is a fundamental result in probability theory that allows us to extend convergence results through continuous functions. It essentially states that continuous transformations preserve all major types of convergence (except mean square convergence).

## Properties
1. The theorem applies to any continuous function, not just linear mappings
2. The continuity requirement cannot be weakened in general
3. The theorem extends to vector-valued random variables and more general metric spaces
4. For almost sure convergence, the proof relies crucially on the fact that the intersection of two probability 1 sets has probability 1

## Examples
1. If Xn →p X, then:
   - X²n →p X² (g(x) = x²)
   - sin(Xn) →p sin(X) (g(x) = sin(x))
   - exp(Xn) →p exp(X) (g(x) = exp(x))

2. Central Limit Theorem + CMT:
   If √n(X̄n - μ) →d N(0,σ²), then:
   n(X̄n - μ)² →d σ²χ²(1) by applying g(x) = x²

## Remarks

- [[Mean Square Convergence]]
	- Is not preserved under arbitrary continuous mappings! 
	- We need something stronger, eg. $g$ linear. 

# Links 

## Proved by: 
- [[Portmanteau Theorem]]
- [[Levy's Continuity Theorem]]

## Proves:
- [[Slutsky Theorem]] (as a special case)
- [[Delta Method]] (when combined with Taylor expansion)

## Justifications:
- [[Measurability of Continuous Functions]]
- [[Almost Sure Convergence]]



```dataviewjs

const currentPage = dv.current().file.name.replace(/\.md$/, '');

// Initialize an array to hold pages that reference the current page within proofs
let referencingPages = [];

// Function to escape special regex characters in the page name
function escapeRegExp(string) {
    return string.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
}

// Create a regex pattern to match [[Current Page]] links
const linkPattern = new RegExp(`\\[\\[${escapeRegExp(currentPage)}\\]\\]`, 'g');

// Iterate over all Markdown files in the vault
for (let file of dv.pages().file) { // You can adjust the source if needed
    // Skip the current file
    if (file.path === dv.current().file.path) continue;

    // Get the raw content of the file
    let content = await dv.io.load(file.path);

    // Use a regex to find all proof environments
    const proofRegex = /\\begin\{proof\}([\s\S]*?)\\end\{proof\}/g;
    let match;

    // Search for the link within each proof environment
    while ((match = proofRegex.exec(content)) !== null) {
        let proofContent = match[1];
        if (linkPattern.test(proofContent)) {
            referencingPages.push(file.link);
            break; // Stop after finding the first reference in this file
        }
    }
}

// Display the results
if (referencingPages.length > 0) {
    dv.header(3, "Used to Prove");
    dv.list(referencingPages);
} else {
    dv.header(3, "Used to Prove");
    dv.paragraph("No references found within proofs.");
}
```
