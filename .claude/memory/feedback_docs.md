---
name: Keep docs in sync after feature changes
description: After significant UI or feature changes, proactively update README and check architecture diagram
type: feedback
---

After any significant feature change, always proactively:
1. Update the README Features section to reflect the new state
2. Check if the architecture diagram (architecture.html) needs updating — it covers data flow, not UI, so it only changes when storage or sync mechanisms change

**Why:** User had to ask explicitly after every change. This should be automatic.

**How to apply:** At the end of any session where features changed, update README and push it along with the feature commit. No need to ask.
