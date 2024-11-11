---
up: 
created: 2024-11-09 
modified: 2024-11-09
tags: microeconomics 
---


>[!assumption] No Free Lunch
> $y \in Y$ and $y\geq 0$ implies that $y = 0$



#Type/assumption
## Overview

### Motivation 

Essentially says that it is not possible to produce something from nothing. The restriction that $y\geq 0$ implies that there are no inputs $z$ in the production set. Geometrically, $Y \cap \mathbb{R}^{n}_{+}\subseteq \{ 0 \}$. 

In other words, there are always trade-offs when deciding how to allocate limited resources among various production activities. 

## Implications
- **Shape of the [[PPF]]**: The PPF is concave to the origin due to increasing opportunity costs. As production of one good increases, the opportunity cost of producing additional units of that good rises 
- **Shifts in the [[PPF]]:** 
	- Outward shift indicates economic growth, where more of both goods can be produced with increased resources or technological advancements 
	- Inward shift reflects a reduction in available resources or a decrease in production capabilities 
- **If the Production Set is closed**: No Free Lunch implies that **scaling down** production plans is always feasible. Closedness ensures that even as firms make infinitesimal adjustments to their production levels, they remain within the feasible set 

### Related Notions:
- [[ ]] (Link to related notions)



---

## Visual/Graphical Representation
![[Pasted image 20241109153326.png]]
(a) violates the No Free Lunch property, while (b) satisfies it. 

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

