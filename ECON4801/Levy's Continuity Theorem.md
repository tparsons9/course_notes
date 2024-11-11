---
creation date: 2024-11-07 14:34
modification date: Thu 7th November 2024 14:34:01
up: "[[Characteristic Functions]]"
references:
  - "[[Continuous Mapping Theorem]]"
  - "[[Central Limit Theorem]]"
  - "[[Convergence in Distribution]]"
  - Continuous Mapping Theorem
tags:
---

> [!theorem] Lévy's Continuity Theorem
> Let $\{ \mu_{n} \}$ and $\mu$ be probability measures on $(\mathbb{R}^{n},\ \mathcal{B})$. Then $\mu_{n}\Rightarrow \mu$ if and only if $\phi_{\mu_{n}}\to\phi_{\mu}$ pointwise

^a1e133


# Motivation
The theorem shows that any results we prove about characteristic functions, including convergence results, translates directly into results about probability measures (and vice versa). When we face a difficult question about probability measures, we will often translate it into a question about characteristic functions, find the answer, and then translate it back into probability-measure space. 

## Examples
### Example 1: Convergence of Binomial to Poisson Distribution

Consider a sequence of binomial distributions with parameters $n$ and $p$, where $n \to \infty$ and $p \to 0$ such that $np = \lambda$ remains constant. Lévy's Continuity Theorem can be used to show that the binomial distribution converges to a Poisson distribution.
**Proof Sketch:**

1. **Characteristic Function of Binomial:** Derive the characteristic function of the binomial distribution.

2. **Limit of Characteristic Functions:** Show that as $n \to \infty$ and $p \to 0$, the characteristic function converges to that of the Poisson distribution.

3. **Apply Lévy's Continuity Theorem:** Conclude the convergence of the binomial distribution to the Poisson distribution.

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

- **Analytical Convenience:** Characteristic functions transform convolution (sums of independent random variables) into multiplication, simplifying the analysis of convergence.

- **Uniqueness:** Lévy's Continuity Theorem ensures that a probability measure is uniquely determined by its characteristic function, provided certain conditions are met.

- **Symmetry with Inversion Theorem:** Just as the Fourier inversion theorem allows recovery of a function from its Fourier transform, Lévy's Continuity Theorem allows recovery of a probability measure from its characteristic function.

- **Requirements:** The theorem requires pointwise convergence of characteristic functions and ensures that the limiting characteristic function corresponds to a valid probability measure (continuity at the origin).



# Links 

## Proves: 

```dataviewjs 

const currentPage = dv.current().file.name.replace(/\.md$/, '');

// Initialize an array to hold pages that reference the current page within proofs
let referencingPages = [];

// Function to escape special regex characters in the page name
function escapeRegExp(string) {
    return string.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
}
const linkPattern = new RegExp(`\\[\\[${escapeRegExp(currentPage)}[\\^\\w\\#]*\\]\\]`, 'g');
 
//const linkPattern = new RegExp(`\\[\\[${escapeRegExp(currentPage)}\\]\\]`, 'g');

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

