---
layout: article-toc
---
# Does my dev work need documentation?

## Part 1: Does this feature need documentation?

Q1. Is the feature user-facing (i.e., end users will interact with it directly)?  
- Yes → Needs documentation.  
- No → Go to Q2.

Q2. Does the feature change or affect functionality or users' existing ways of working or ?  
- Yes → Needs documentation.  
- No → Go to Q3.

Q3. Is the feature visible to external stakeholders (customers and partners?  
- Yes → Needs documentation.  
- No → Go to Q4.

Q4. Will internal teams (Support, Sales, or Customer Success) need to explain or troubleshoot this feature?  
- Yes → Needs documentation (internal or external).  
- No → Documentation not required (may only need internal release notes).

---

## Part 2: If documentation *is* needed, how high is the priority?

Q1. Is the feature part of a major release or a flagship functionality that will be marketed or announced publicly?  
- Yes → High priority.  
- No → Go to Q2.

Q2. Will users experience significant confusion or risk without documentation (e.g., complex UI, breaking changes, or required setup steps)?  
- Yes → High priority.  
- No → Go to Q3.

Q3. Is the feature critical for compliance, security, or user safety?  
- Yes → High priority.  
- No → Go to Q4.

Q4. Does the feature affect a niche audience or is it optional/non-core functionality?  
- Yes → Medium or low priority (depending on impact).  
- No → Medium priority.

---

### Example Output

| Feature Type | Documentation Needed? | Priority |
|---------------|-----------------------|-----------|
| New public API endpoint | Yes | High |
| Internal admin dashboard tool | Yes | Medium |
| UI color theme toggle | Yes | Low |
| Database indexing optimization | No | — |