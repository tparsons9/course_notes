---
creation date: 2024-11-07 17:53
modification date: Thu 7th November 2024 17:53:22
up: 
references: 
tags: 
---

> [!theorem] Kolmogorov's First SLLN
> Let $\{ X_{n} \}$ be a sequence of independent random variables with, 
> $$
>\sum_{i=1}^{n} \frac{\text{Var}(X_{i})}{i^{2}}< \infty
>$$
>Then $n^{-1}\sum_{i=1}^{n}(X_{i} - \mathbf{E}[X_{i}])\xrightarrow{a.s.}0$ as $n\to \infty$. 

`\begin{proof}`
	Write,
	$$
	S_{n}:= n^{-1}\sum_{i=1}^{n}(X_{i} - \mathbf{E}[X_{i}])
	$$
	We want to show that $S_{n}\xrightarrow{a.s.}0$. Fix $\epsilon>0$. Using [[Hájek-Rényi Inequality]] with $c_{i} = i^{-1}$, 
	$$
	\begin{align}
	\mathbf{P}\left( \max_{k\in [m,n]}|S_{k}|\geq \epsilon \right)  & = \mathbf{P}\left( \max_{k\in [m,n]}k^{-1}\left\lvert  \sum_{i=1}^{k}(X_{i} - \mathbf{E}[X_{i}])  \right\rvert \geq \epsilon  \right) \\
	 & \leq \frac{1}{\epsilon^{2}}\left( m^{-2}\sum_{i=1}^{m}\text{Var}(X_{i}) + \sum_{i=m+1}^{n}i^{-2}\text{Var}(X_{i}) \right)  
	\end{align}
	$$
	Taking $n\to \infty$ and using the fact that $\sum_{i=1}^{\infty}\text{Var}(X_{i}) / i^{2}$ converges, 
	$$
	\mathbf{P}(\max_{k\geq m}|S_{k}|\geq \epsilon)\leq \frac{1}{\epsilon^{2}}\left( m^{-2}\sum_{i=1}^{m}\text{Var}(X_{i}) + \sum_{i=m+1}^{\infty}i^{-2}\text{Var}(X_{i}) \right) 
	$$
	now taking $m\to \infty$, 
	$$
	\lim_{ m \to \infty } \mathbf{P}\left( \sup_{k\geq m}|S_{k}|\geq \epsilon \right)\leq \frac{1}{\epsilon^{2}}\left( \lim_{ m \to \infty } m^{-2}\sum_{i=1}^{m}\text{Var}(X_{i}) + \lim_{ m \to \infty } \sum_{i=m+1}^{\infty}i^{-2}\text{Var}(X_{i}) \right) 
	$$
	Since$\sum_{i=1}^{\infty}\text{Var}(X_{i}) / i^{2}$ exists and is finite, [[Kronecker's Lemma]] with $c_{i} = i^{2}$ yields, 
	$$
	\lim_{ m \to \infty } m^{-2}\sum_{i=1}^{m}\text{Var}(X_{i}) = \lim_{ m \to \infty } m^{-2}\sum_{i=1}^{m}i^{2} \frac{\text{Var}(X_{i})}{i^{2}} = 0
	$$
	For the second term, 
	$$
	\begin{align}
	\lim_{ m \to \infty } \sum_{i=m+1}^{\infty} \frac{\text{Var}(X_{i})}{i^{2}} & = \lim_{ m \to \infty } \left( \sum_{i=1}^{\infty} \frac{\text{Var}(X_{i})}{i^{2}} - \sum_{i=1}^{m} \frac{\text{Var}(X_{i})}{i^{2}} \right)  \\
	 & = \sum_{i=1}^{\infty} \frac{\text{Var}(X_{i})}{i^{2}} - \sum_{i=1}^{\infty} \frac{\text{Var}(X_{i})}{i^{2}} \\
	 & = 0 
	\end{align}
	$$
	Hence $\lim_{ m \to \infty }\mathbf{P}(\sup_{k\geq m}|S_{k}|\geq \epsilon)\leq 0$, and since probabilities are nonnegative, = $\hspace{0pt}0$. 
`\end{proof}`

# Motivation

This isn't used that often. 

## Properties
_Remove if not needed_ 

## Examples
_Either Link to new documents or provide an example here_ 
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

The Kolmogorov variance condition $\sum_{i=1}^{\infty}\text{Var}(X_{i}) / i^{2}<\infty$ implies the [[Chebychev's WLLN]] variance condition: 
$$
\lim_{ n \to \infty } n^{-2}\sum_{i=1}^{n}\text{Var}(X_{i}) = 0
$$


# Links 

## Proved by: 
_Statements in which `proof` depends crucially on_ 

## Proves: 
_What the `statement` is used to prove_

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

## Justifications:
_Proofs of implicit assumptions of object/notion in statement_

## Specializations: 
- [[Markov's SLLN]]

## Generalizations: 
_Statements and proofs of abstractions of `statement`_
