---
up: "[[Demand Theory]]"
created: 2024-11-10
modified: 2024-11-10
tags:
  - microeconomics
---


>[!definition] Afriat Inequalities
>There exist positive numbers $(u_{k}, \lambda_{k})_{k\in K}$ that satisfy the Afriat Inequalities, 
> $$
> u_{k}\leq u_{l} + \lambda_{l}p_{l}(y_{k} - y_{l})
>$$

#Type/definition
## Overview

### Motivation 
An alternative approach to studying data is to ask whether there is any "nice" function which is consistent with the data being observed. We consider here the case where there may be multiple optimal elements from a choice set, and we observe only one of them. We take advantage of monotonicity (or local non-satiation). We define $y\succ^{R}y'$ where $y\in x(p,w)$ by $y'\cdot p <w$. Recall that, under non-satiation, $y \in x(p,w)$ and $y'\cdot p<w \implies y\succ^{R}y'$ but the converse does not hold. 
### Related Concepts
- [[Generalized Axiom of Revealed Preference]]: 

> [!definition] 
> The generalized axiom of revealed preference (GARP) is satisfied by a collection of data $(y_{k}, p_{k})_{k\in K}$ iff $\forall k, k',\ y_{k}\succeq^{IR}y_{k'} \implies \neg(y_{k'}\succ^{"R"}y_{k})$

> [!proposition] 
> Let $(y_{k}, p_{k})_{k\in K}$ be a finite collection of consumption data. The following are equivalent: 
> 1) There exists a locally non-satiated continuous, concave utility function that rationalizes the data, ie. maximizing this $u$ leads to a demand function $x(\cdot)$ such that $x(p_{k}, p_{k}\cdot y_{k}) = y_{k}$
> 2) The data satisfy GARP 
> 3) There exists a locally non-satiated quasiconcave utility function that rationalizes the data, ie. maximizing this $u$ leads to a demand function $x(\cdot)$ such that $x(p_{k}, p_{k}\cdot y_{k}) = y_{k}$. 
> 4) There exists positive numbers $(u_{k}, \lambda_{k})_{k\in K}$ that satisfy the Afriat inequalities

- Note that this implies that with finite data we cannot distinguish between quasiconcavity and concavity of $u$. Thus, there is a sense in which assuming concavity is $w$.$l$.$o$.$g$. - it can never be refuted without refuting the existence of any monotonic utility maximizing behavior. 


### Examples:
- Example: [[ ]] (Link to an example if available)
- Example: Insert example within the file 
- Table for items with tag example and up points to this file 



---

## Extensions 

- Connection to [[Production Theory]]
	- Note that with production, we are maximizing profit with output, $q_{j}$, instead of utility. Further, the input demands serve as our y's and the input prices in place of $p$. 
	- Shows that Afriat Inequalities can be extended to a large range of optimization problems with finite data. 

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

