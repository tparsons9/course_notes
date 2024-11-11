---
aliases: 
creation date: 2024-11-07 17:39
modification date: Thu 7th November 2024 17:39:13
up: 
references: 
tags: 
---

> [!theorem] Chebychev's WLLN
> Let $\{ X_{n} \}$ be a sequence of uncorrelated random variables with, 
> $$
>\lim_{ n \to \infty } n^{-2}\sum_{i=1}^{n}\text{Var}(X_{i}) = 0
>$$
>Then $n^{-1}\sum_{i=1}^{n}(X_{i} - \mathbf{E}[X_{i}])\xrightarrow{p} 0$ as $n\to \infty$. 

`\begin{proof}`
Write, 
$$
S_{n}:= n^{-1}\sum_{i=1}^{n}(X_{i} - \mathbf{E}[X_{i}])
$$
we want to show that $S_{n}\xrightarrow{p} 0$. Observe, by uncorrelated-ness, 
$$
\text{Var}(S_{n}) = n^{-2}\text{Var}\left( \sum_{i=1}^{n}(X_{i} - \mathbf{E}[X_{i}]) \right) = n^{-2}\sum_{i=1}^{n}\text{Var}(X_{i})
$$
hence $\text{Var}(S_{n})\to0$ by the variance condition. By non-negativity and [[Chebychev's Inequality]], we have for any $\epsilon>0$ that, 
$$
0\leq P(\lvert S_{n} \rvert >\epsilon)\leq \text{Var}(S_{n}) / \epsilon^{2}
$$
Since the RHS converges to zero, it follows that $P(\lvert S_{n} \rvert > \epsilon)\to 0$ for ever $\epsilon>0$, ie. $S_{n}\xrightarrow{p} 0$. 
`\end{proof}`

# Motivation

## Properties
1. Only requires finite variance and uncorrelated random variables
2. Convergence rate depends on how fast the scaled sum of variances approaches zero
3. Does not require independence, only uncorrelatedness
4. Works for both identically and non-identically distributed random variables

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

1) Neither $\left\{  n^{-1}\sum_{i=1}^{n}X_{i}  \right\}$ nor $\left\{  n^{-1}\sum_{i=1}^{n}\mathbf{E}[X_{i}]  \right\}$ need converge to anything; they could be 'exploding' together for example 
2) The restriction on the variance implies that each variance is finite, hence that each mean exists and is finite. 
3) The variance condition can be weakened. 


# Links 

## Proved by: 
- [[Chebychev's Inequality]]

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

## Justifications:
- [[Chebychev's Inequality]] - Used crucially in the proof
- Existence of moments - The variance condition implies finite first and second moments
- Uncorrelatedness - Used to simplify the variance of the sum

## Specializations: 
1. For i.i.d. random variables with finite variance σ², the variance condition simplifies to:
$$
n^{-2}\sum\text{Var}(X_{i}) = n^{-2}n\sigma^{2} = \frac{\sigma^{2}}{n}\to 0
$$
1. For bounded random variables |Xᵢ| ≤ M, the variance is automatically bounded

## Generalizations: 

1. [[Kolmogorov's First SLLN]] - Removes uncorrelatedness assumption for independent variables
2. [[Ergodic Theorem]] - Generalizes to stationary ergodic processes
