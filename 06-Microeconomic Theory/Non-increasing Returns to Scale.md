---
aliases:
  - NIRTS
up: "[[Returns to Scale]]"
created: 2024-11-09
modified: 2024-11-09
tags:
  - microeconomics
  - Type/property
---


>[!assumption] NIRTS
> 1) The production function $f$ satisfies $f(\alpha x)\geq \alpha f(x),\ \forall \alpha \in [0,1]$ and for all $x$. 
> 2) Any feasible production can be proportionally shrunk (but not necessarily expanded): $y \in Y \implies \alpha y\in Y$ for $\alpha \in [0,1]$



## Overview

### Motivation 

**Non-increasing RTS (NIRTS)** occur when increasing all inputs by a certain proportion leads to an increase in output that is **less than or equal to** that proportion. 

Part (2) of the assumption articulates a fundamental property of production sets under **NIRTS**. It asserts that if a particular production plan $y$ is **achievable** within the production set $Y$, then any proportionally smaller version of that production plan is also achievable. 
### Related Concepts
[[ ]] (Use this to link to related concepts like Supply, Demand, Utility, etc.)

## Implications 
1) Implies the [[Possibility of Inaction]]
2) Production becomes **(weakly) less efficient** as the scale increases. Doubling inputs results in less than double the output. 
3) **Scalability**: The production set is closed under proportional reduction, meaning downsizing inputs and outputs maintains feasibility 
4) **Flexibility**: While scaling down is guaranteed, scaling up is *not necessarily feasible*. 

### Related Notions:
- [[Efficiency in Production]]: Efficiency (weakly) **decreases** with increased scale 

## Graphically 

![[Pasted image 20241109151304.png]]
In the figure above, the graph of (a) demonstrates NIRTS but in (b), NIRTS is violated. 

---

## Remarks

#### _Remark._ Equivalence of Statements for $Y = \{ (-z,q): q\leq f(z) \}$

`\begin{proof}`
$(1)\implies (2)$. Let $y = (-z,q) \in Y$. By definition of $Y$, we have $q \leq f(z)$. Let $\alpha \in [0,1]$ be arbitrary. We are given that $f(\alpha z)\geq \alpha f(z)$, WTS that $\alpha y \in Y$. Since $q \leq f(z)$, multiplying both sides by $\alpha$ which is non-negative preserves the inequality: $\alpha q \leq \alpha f(z)$. But $\alpha f(z)\leq f(\alpha z)$. So we have $\alpha q\leq f(\alpha z)$, therefore, $(-\alpha z, \alpha q) = y' \in Y$. 
$(2)\implies(1)$ We have, $\forall \alpha \in [0,1],\ \forall y \in Y$ that $\alpha y \in Y$. WTS that $f(\alpha z)\geq \alpha f(z)$. Let $y = (-z, f(z)) \in Y$. Then $\alpha y = (-\alpha z,\ \alpha f(z)) \in Y$. By definition of $Y$, for $\alpha y$ to be in $Y$, we need $\alpha f(z)\leq f(\alpha z)$. Therefore (2) follows by definition.
`\end{proof}`

---
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

---

**Next Steps:**
- [[ ]] (Link to the next note in your study flow.)
