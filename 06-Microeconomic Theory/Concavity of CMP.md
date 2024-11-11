---
aliases: 
up: "[[Cost Minimization]]"
created: 2024-11-10
modified: 2024-11-10
tags:
  - microeconomics
  - Type/assumption
---


>[!assumption] $c$ is concave in $w$

## Overview

### Motivation 
The concavity of the cost function in input prices $w$ is a fundamental property that reflects the firm's ability to substitute between inputs as their relative prices change. This property ensures that cost-minimizing behavior is well-defined. This means that as input prices change, the cost functions graph will curve downward when viewed from above in the input price space. 

### Related Concepts
- [[CMP FOC]]: First-order conditions for cost minimization
- [[Shephard's Lemma]]: Relationship between cost minimization and input demand; related to the derivatives of the cost function. The partial derivative of the cost function with respect to an input price gives the cost-minimizing demand for that input.
- [[Definiteness of the CMP]]: Connected to second-order properties



## Implications

### Related Notions:
- [[Substitution Effect]]: As the price of one input increases, the firm can substitute towards cheaper inputs. This ability to adjust input combinations helps mitigate the impact of price increases on total costs. 
- **Optimization**: The cost function represents the minimum cost of producing a given output at given input prices. As prices change, firms optimize their input mix, leading to a cost increase that is less than proportional to the price increase. 
- **Continuity:** Because $c(w,q)$ is concave in $w$, it is also continuous in $w$ 

---


## Remarks

- **_Remark._** While $c$ is concave in input prices $w$, it is typically convex in output, $q$. This convexity in $q$ implies that marginal costs are generally non-decreasing in output, which is consistent with the [[Law of Diminishing Returns]]. 
  
### Further Reading
- [[ ]] (Link to other notes or literature on the topic)

## References
- Source or textbook chapter: 

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

