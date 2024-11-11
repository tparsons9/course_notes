---
aliases: 
up: "[[Cost Minimization]]"
created: 2024-11-10
modified: 2024-11-10
tags:
  - microeconomics
  - Type/assumption
---


>[!assumption] Convexity of Conditional Factor Demands
>If $f$ is (strictly) quasiconcave, so that the upper contour set $\{ z\geq 0: f(z)\geq q \}$ is (strictly) convex, then $z$ is a (singleton) convex set

## Overview
The convexity of conditional factor demands is a key property in production theory that relates to the cost minimization problem. It ensures that the optimal input choices form a convex set when producing a given output level.

### Motivation 
- Ensures well-behaved optimization in cost minimization problems
- Provides theoretical foundation for input substitution
- Critical for establishing uniqueness of cost-minimizing input combinations

### Related Concepts
- [[Shephard's Lemma]]
- [[CMP FOC]]
- [[Definiteness of the CMP]]




## Implications
1. If input prices are linear, the cost minimization problem has a unique solution
2. The cost function is well-defined and continuous
3. Factor demands respond smoothly to price changes

### Related Notions:
- [[Quasiconcavity]]



---

## Visual/Graphical Representation
- Sketch or Graph (Use Latex or attach an image if relevant): 

## Remarks
- Ensures smooth substitution between inputs as relative prices change
- Links to the convexity properties of isoquants
  
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

