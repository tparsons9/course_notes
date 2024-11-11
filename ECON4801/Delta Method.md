---
creation date: 2024-11-07 16:43
modification date: Thu 7th November 2024 16:43:33
up: 
references:
  - "[[Convergence in Distribution]]"
  - "[[Taylor's Theorem]]"
tags:
---

> [!proposition] Delta Method
> Let $\{ X_{n} \}$ be a sequence of random $k$-vectors such that $a_{n}(X_{n}-b)\xrightarrow{d}W$ for some constants $\{ a_{n} \}$ and $b$. Let $g:\mathbb{R}^{k}\mapsto\mathbb{R}^{m}$ be differentiable in an open neighborhood of $b$, with derivative $Dg(b)$ at $b$. Then, 
> $$
>a_{n}(g(X_{n})-g(b))\xrightarrow{d}Dg(b)W
>$$

`\begin{proof}`
	By [[Taylor's Theorem]], 
	$$
	g(X_{n})-g(b) = Dg(b)(X_{n}-b) + o_{p}(\lvert \lvert X_{n} - b \rvert  \rvert _{2})
	$$
	so, 
	$$
	a_{n}(g(X_{n})-g(b)) = Dg(b)a_{n}(X_{n}-b) + o_{p}(\lvert \lvert a_{n}(X_{n}-b) \rvert  \rvert _{2})
	$$
	Since $a_{n}(X_{n}-b)\xrightarrow{d}W$, 
	$$
	o_{p}(\lvert \lvert a_{n}(X_{n}-b) \rvert  \rvert _{2}) = o_{p}(O_{p}(1)) = o_{p}(1)
	$$
	and $Dg(b)a_{n}(X_{n}-b)\xrightarrow{d}Dg(b)W$ by [[Slutsky Theorem]]. Hence, 
	$$
	a_{n}(g(X_{n})-g(b)) = Dg(b)a_{n}(X_{n}-b) + o_{p}(1)\xrightarrow{d}Dg(b)W
	$$
`\end{proof}`
> [!proposition] Second-order Delta Method
> Let $\{ X_{n} \}$ be a sequence of random $k$ - vectors such that $a_{n}(X_{n}-b)\xrightarrow{d}W$ for some constants $\{ a_{n} \}$ and $b$, let $g:\mathbb{R}^{k}\mapsto \mathbb{R}$ be twice differentiable in an open neighborhood of $b$, with derivatives $\nabla g(b) = 0$ and $\nabla^{2}g(b)$ at $b$. Then, 
> $$
> a_{n}^{2}(g(X_{n})-g(b))\xrightarrow{d} \frac{1}{2}W^{\top}\nabla^{2}g(b)W
>$$

`\begin{proof}`
	Since $\nabla g(b) = 0$, we have, 
	$$
	g(X_{n})-g(b) = \frac{1}{2}(X_{n}-b)^{\top}\nabla^{2}g(b)(X_{n}-b) + o_{p}(\lvert \lvert X_{n}-b \rvert  \rvert _{2}^{2})
	$$
	so, 
	$$
	\begin{align}
	a_{n}^{2}(g(X_{n})-g(b))  & \\
	= &  \frac{1}{2}[a_{n}(X_{n}-b)]^\top \nabla^{2}g(b)[a_{n}(X_{n} - b)] + o_{p}(\lvert \lvert a_{n}(X_{n}-b) \rvert  \rvert _{2}^{2})
	\end{align}
	$$
	Since $a_{n}(X_{n}-b)\xrightarrow{d} W$, 
	$$
	o_{p}(\lvert \lvert a_{n}(X_{n}-b) \rvert  \rvert _{2}^{2})= o_{p}(O_{p}(1)^{2}) = o_{p}(O_{p}(1)) = o_{p}(1)
	$$
	and 
	$$
	\frac{1}{2}[a_{n}(X_{n}-b)]^{\top}\nabla^{2}g(b)[a_{n}(X_{n}-b)]\xrightarrow{d} \frac{1}{2}W^{\top}\nabla^{2}g(b)W
	$$
	by Slutsky's Theorem. Hence, 
	$$
	\begin{align}
	a_{n}^{2}(g(X_{n})-g(b))  & = \frac{1}{2}[a_{n}(X_{n} - b)]^{\top}\nabla^{2}g(b)[a_{n}(X_{n}-b)] + o_{p}(1) \\
	 & \xrightarrow{d} \frac{1}{2}W^{\top}\nabla^{2}g(b)W
	\end{align}
	$$
`\end{proof}`
# Motivation

The Delta Method is a powerful tool in probability theory and statistics that allows us to approximate the distribution of a function of a random variable. It provides a way to derive the asymptotic distribution of a function of a random variable based on the asymptotic distribution of the random variable itself. The Delta Method is particularly useful in deriving the asymptotic distribution of sample statistics and estimators, making it a key tool in statistical inference.



## Examples

```dataviewjs
const currentPage = dv.current().file.name.replace(/\.md$/, '');

// Initialize an array to hold pages that reference the current page
let examplePages = [];

// Function to escape special regex characters in the page name
function escapeRegExp(string) {
    return string.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
}

// Create a regex pattern to match [[Current Page]] links
const linkPattern = new RegExp(`\\[\\[${escapeRegExp(currentPage)}\\]\\]`, 'g');

// Get all pages with #example tag
const exampleFiles = dv.pages('#example').file;

// Iterate over tagged files
for (let file of exampleFiles) {
    // Skip the current file
    if (file.path === dv.current().file.path) continue;

    // Get the raw content of the file
    let content = await dv.io.load(file.path);

    // Check if the current page is referenced
    if (linkPattern.test(content)) {
        examplePages.push(file.link);
    }
}

// Display the results
if (examplePages.length > 0) {
    dv.header(3, "Referenced in Examples");
    dv.list(examplePages);
} else {
    dv.header(3, "Referenced in Examples");
    dv.paragraph("No references found in example pages.");
}
```
## Remarks

Notice that we did not require $Dg(b)$ to be nonsingular (or even nonzero), nor did we require $Dg$ to be continuous at $b$. Although $W$ will be normally distributed in the vast majority of applications (by [[Central Limit Theorem]]), that is not required either. 

Suppose instead that we have a sequence $\{ b_{n} \}$ of $k$ - vectors such that $a_{n}(X_{n}-b_{n})\xrightarrow{d}W$, and that $b_{n}\to b$. Add the assumption that $Dg$ is continuous at $b$. Then $Dg(b_{n})= Dg(b) + o(1)$, so the proof still goes through. 

#### Second-order Delta Method 
Although the first-order delta method is valid when $Dg(b) = 0$, it isn't very helpful in that case. Unless $g$ is a constant function, $g(X_{n})$ is still going to be random, so we'd like our approximating distribution to be nondegenerate. The remedy is provided by the 2nd order DM. 

#### Relationship to [[Modes of Convergence]]
Combining the first and second order delta methods, we get, 
$$
a_{n}(g(X_{n})-g(b))\xrightarrow{p} 0\text{ and }\ a_{n}^{2}(g(X_{n})-g(b))\xrightarrow{d} \frac{1}{2}W^{\top}\nabla^{2}g(b)W
$$

# Links 

## Proved by: 
- [[Continuous Mapping Theorem]]
- [[Levy's Continuity Theorem]]
- [[Taylor's Theorem]]

## Proves: 
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

