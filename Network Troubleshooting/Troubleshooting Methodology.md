This  provides a structured, high-level **troubleshooting methodology** that can be applied to any network or IT problem. It follows a logical flow from problem identification to resolution and documentation, emphasizing the importance of testing theories, change control, and user verification.



---

### Troubleshooting Methodology Cheat Sheet

This guide outlines a repeatable process for identifying, diagnosing, resolving, and documenting network issues.

---

#### The Troubleshooting Flow (High Level)

| Phase | Description |
| :--- | :--- |
| **1. Identify the Problem** | Gather information, duplicate the issue, determine scope, and note what has changed. |
| **2. Establish a Theory** | Form a probable cause hypothesis (start with the obvious, simple possibilities). |
| **3. Test the Theory** | Verify the hypothesis (e.g., in a lab). If the theory is wrong, go back to step 2. |
| **4. Establish a Plan of Action** | Design the fix, including change control, rollback plans, and resource scheduling. |
| **5. Implement the Solution** | Apply the fix to the production environment (during an approved change window). |
| **6. Verify Full System Functionality** | Confirm with end users that the problem is resolved and that no new issues were introduced. |
| **7. Document the Findings** | Record the problem, the solution, and the steps taken for future reference. |

---

#### Phase 1: Identify the Problem

| Action | Details |
| :--- | :--- |
| **Gather information** | Talk to users; collect their observations. Review logs, metrics, and statistics from routers, switches, and servers. |
| **Duplicate the problem** | Reproduce the issue (if possible) to confirm you understand it correctly. |
| **Look for multiple symptoms** | Problems often have more than one symptom; identify all of them. |
| **Ask “What changed?”** | Has anything been changed recently (cables moved, devices powered off, configuration updates)? |
| **Scope the problem** | Is it one user, a department, or the entire network? Break large problems into smaller, manageable pieces. |
| **Build a lab** | If feasible, recreate the problem in a test environment to isolate the root cause safely. |

---

#### Phase 2 & 3: Establish and Test a Theory

| Action | Details |
| :--- | :--- |
| **Start with the obvious** | Check physical connections (cables, power), link lights, and simple configuration errors first. |
| **Choose an approach** | - **Top‑down** (start at OSI Layer 7 → Layer 1) – good for application issues. <br> - **Bottom‑up** (start at OSI Layer 1 → Layer 7) – good for new network installations. |
| **Use elimination** | If the problem occurs on both Windows and Linux, it’s not OS‑specific. Eliminate variables to narrow the cause. |
| **Test the hypothesis** | In a lab (or isolated environment), change one variable at a time. If the problem persists, the theory is wrong → go back and form a new theory. |

---

#### Phase 4: Establish a Plan of Action

| Action | Details |
| :--- | :--- |
| **Design the fix** | Specify exactly what changes will be made (configuration, hardware swap, cable replacement, etc.). |
| **Schedule change control** | Many organizations require a change window (off‑hours) for production changes. |
| **Prepare rollback plans** | Have **Plan A** (the change), **Plan B** (alternate approach), and a **rollback procedure** to revert to the previous state if something goes wrong. |

---

#### Phase 5: Implement the Solution

| Action | Details |
| :--- | :--- |
| **Execute during the change window** | Apply the approved fix to production. |
| **Separate teams (if applicable)** | In some organizations, the troubleshooting team identifies the fix, and the operations team implements it. |
| **Monitor during implementation** | Watch for unexpected side effects. |

---

#### Phase 6: Verify Full System Functionality

| Action | Details |
| :--- | :--- |
| **Test with users** | Have the people who originally reported the problem confirm that it is resolved. |
| **Check for regressions** | Ensure the fix did not break other functionality. |
| **Discuss prevention** | Talk with users about how to prevent the issue from recurring (training, monitoring, process changes). |

---

#### Phase 7: Document the Findings

| Action | Details |
| :--- | :--- |
| **Record the problem** | What was observed, when, and under what conditions. |
| **Record the solution** | Exactly what change was made to resolve the issue. |
| **Store in knowledge base** | Use a help desk database, wiki, or ticketing system so the information can be found later. |
| **Benefit** | Future troubleshooting (even a year later) can reference this documentation, saving time and effort. |

---

#### Summary Table: Troubleshooting Steps

| Step | Key Actions | Deliverable |
| :--- | :--- | :--- |
| **1. Identify the problem** | Talk to users, check logs, duplicate issue, note changes | Clear problem statement |
| **2. Establish a theory** | Start with obvious causes, use elimination | Probable cause hypothesis |
| **3. Test the theory** | Lab testing, change one variable | Confirmed (or refuted) theory |
| **4. Plan of action** | Design fix, rollback plan, change control | Approved implementation plan |
| **5. Implement** | Apply fix during change window | Fix deployed |
| **6. Verify functionality** | User confirmation, test for regressions | Problem resolved, system working |
| **7. Document** | Record problem, solution, and steps | Knowledge base entry |

---

#### Key Takeaways

| Takeaway | Explanation |
| :--- | :--- |
| **Always start with the obvious** | Check physical cables, power, and recent changes before diving into complex diagnostics. |
| **Duplicate the problem if you can** | Reproducing the issue helps confirm you understand it and makes testing fixes easier. |
| **Use a lab for safe testing** | Never test a theory directly on production unless there is no other option. |
| **Have a rollback plan** | Before making any production change, know how to revert to the previous state. |
| **Involve users in verification** | Only the user who experienced the problem can confirm that it is truly resolved. |
| **Document everything** | Future you (or your colleagues) will be grateful for clear documentation. |
