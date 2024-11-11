---
aliases:
  - MRT
up: "[[Transformation Functions]]"
created: 2024-11-09
modified: 2024-11-09
tags:
  - microeconomics
  - Type/definition
related:
  - "[[Marginal Cost]]"
---


>[!definition] Marginal Rate of Transformation
>Let $F(\cdot)$ be a transformation function. If $F$ is differentiable, and if the production vector $\bar{y}$ satisfies $F(\bar{y}) = 0$, then for any commodities $j$ and $k$, the ratio, 
> $$
> \text{MRT}_{jk}(\bar{y}) = \frac{\partial F(\bar{y}) / \partial y_{j}}{\partial F(\bar{y}) / \partial y_{k}}
>$$
> is called the _marginal rate of transformation_ (MRT) of good $j$ for good $k$ at $\bar{y}$. 


## Overview

### Motivation 

The marginal rate of transformation is a measure of how much the (net) output of good $k$ can increase if the firm decreases the (net) output of good $j$ by one marginal unit. 

### Related Concepts
- [[Production Possibilities Frontier]]
- [[Marginal Rate of Technological Substitution]]



### Examples:
- Suppose an economy produces two goods: **Computers** ($l$) and **Books**($k$)
	- If $\text{MRT}_{lk} = 3$ then for the economy to produce one more unit of computers, the economy must reduce the production of **three books**, assuming resources are fully and efficiently utilized. 



---

## Visual/Graphical Representation
![[Pasted image 20241109122246.png]]


## Remarks

**_Remark._** With single-output production, when $F$ is differentiable, so is $f$, but the converse is false. 

If $f$ has a finite slope at $\hspace{0pt}0$ then the boundary of $Y$ has a kink at $\hspace{0pt}0$ and therefore $F$ cannot be differentiable. So assuming differentiability of $F$ at zero is a significant economic restriction resulting from the use of $Y$, rather than the use of $f$. However, except at $\hspace{0pt}0$ this issue does not arise, and we can easily extend the FOC to F's that are differentiable everywhere except at $\hspace{0pt}0$. 

---

**_Remark._** MRT is related to [[Production Possibilities Frontier]]

If $F(\bar{y})= 0$, we get, 
$$
\frac{ \partial F(\bar{y}) }{ \partial y_{k} } dy_{k} + \frac{ \partial F(\bar{y}) }{ \partial y_{j} } dy_{j} = 0
$$
and therefore the slope of the transformation frontier $\bar{y}$ is precisely $-\text{MRT}_{12}(\bar{y})$. 

--- 

#### _Remark._ Interpretation of MRT in case where $j$ and $k$ are two outputs

An alternative characterization of MRT is, 
$$
\operatorname{MRT}_{jk} = \frac{\text{Marginal Cost of }j}{\text{Marginal Cost of }k}
$$
or, as we showed above, as the slope of the PPF at a particular point, 
$$
\operatorname{MRT}_{jk}(\bar{y}) = - \frac{dy_{k}}{dy_{j}}
$$
For two outputs, we can think of this as the ratio between the loss of output and gain of output. 

--- 
#### _Remark._ Interpretation of MRT when $l$ is an input and $k$ is an output

$\text{MRT}_{lk}(\bar{y})$ for $l$ input and $k$ output is expressed as the measure of the **rate at which an input $l$ can be transformed into an additional unit of output $k$,** holding all other factors constant. Related to [[Marginal Productivity]]. 

For example, if the production function is $k = f(l)$, where $l$ is the labor hours and $k$ is the number of smartphones produced, suppose that the marginal product $\text{MP}_{l} = dy_{k} / dy_{l} = 10$ smartphones per labor hour. Then, 
$$
\text{MRT}_{lk}(\bar{y}) = \frac{1}{MP_{l}} = \frac{1}{10} = 0.1\text{ labor hours per smartphone}
$$

  
### Further Reading
- [[ ]] (Link to other notes or literature on the topic)

## References
- Source or textbook chapter: MWG Chapter $\hspace{0pt}5$, [[Production.pdf]]

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

