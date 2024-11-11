---
aliases: 
up: "[[Production Function]]"
created: 2024-11-09
modified: 2024-11-09
tags:
  - microeconomics
  - Type/property
---


>[!assumption] $Y$ is convex and $f$ is concave


## Overview

### Motivation 

> [!definition] 
> A production set $Y$ is **convex** if, for any two production plans $y_{1}$ and $y_{2}$ in $Y$, any **convex combination** of these plans is also in $Y$: If $y_{1},y_{2} \in Y$ then $\alpha y_{1} + (1 - \alpha)y_{2} \in Y$ for all $\alpha \in [0,1]$. 

This implies that firms can combine different production plans to achieve new production levels. 

> [!definition] 
> A production function $f(z)$ is **concave** if, for any two input vectors $z_{1},z_{2}$ and for any $\alpha \in [0,1]$, $f(\alpha z_{1} + (1 - \alpha )z_{2}) \geq \alpha f(z_{1})+ (1- \alpha)f(z_{2})$

This property reflects [[Diminishing Marginal Returns]] to inputs and ensures that average productivity does not decrease as inputs are combined. 

Convexity captures the idea that "unbalanced" input combinations are not more productive than balanced ones. If production plans $y$ and $y'$ produce exactly the same amount of output but use different input combinations, then a production vector that uses a level of each input that is the average of the levels used in these two plans can do at least as well as either $y$ or $y'$. 
### Related Concepts
- [[Convex Functions]]
- [[Concave Functions]]

## Implications 

1) [[Duality Principle]]: Convexity allows for the formulation of dual problems (eg. [[Cost Minimization]] and [[Profit Maximization]]) that provide deeper insights into the firm's operational efficiencies and constraints 
2) [[Diminishing Marginal Returns]]: Concave production functions embody this principle, where each additional unit of input yields less additional output than the previous unit
3) **Optimal Production Decisions**: Concave $f$ enables firms to maximize profits and minimize costs efficiently, as the optimization problems become concave maximization or convex minimization problems with unique solutions 
4) [[Non-increasing Returns to Scale|NIRTS]]: If, in addition to convexity of $Y$, we have [[Possibility of Inaction]], then this implies that $Y$ has non-increasing returns. 
	- To see this, note that for any $\alpha \in [0,1]$, we can write $\alpha y = \alpha y + (1 - \alpha) \mathbf{0}$. Hence, if $y \in Y$ and $\mathbf{0}\in Y$, convexity implies that $\alpha y \in Y$. 
5) Concavity of $f$ implies quasiconcavity: averaging inputs is good. 

### Related Notions:
- [[ ]] (Link to related notions)



---

## Remarks

>[!remark] $f(x)$ concave $\implies$ $Y$ convex
>This is because the concavity of $f(x)$ ensures that linear combinations of feasible outputs remain feasible. 

>[!remark] Establishing Concavity of $f$
>Observe that if we have $f$ strictly increasing, strictly quasiconcave, [[CRTS]], and $f(0)=0$, then $f$ is concave. 

Convexity of $Y$ (concavity of f) is, in general, a more restrictive assumption than [[NIRTS]] in two senses: 
1) It is more restrictive in terms of each individual input. [[Returns to Scale]] is about how $f(\alpha x) / \alpha$ relates to $f(x)$. Consider the case of one-input and assume that $f(0)=0$. Then NIRTS requires that any line between the origin and a point on the function $(x,f(x))$ lies below the graph of the function. **Concavity** requires that the line between _any_ two points (not only $(0, f(0))$ and $(x,f(x))$, but also between $(\hat{x}, f(\hat{x}))$ and $(x, f(x))$) lies below the graph of the function. 
2) Concavity implying quasiconcavity has nothing to do with RTS, which only considers changes keeping the proportion of inputs fixed. 

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

