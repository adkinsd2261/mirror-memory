# promptchain.md

This file defines the **default sequence of AI behaviors** in Mirror’s engine — how it receives, reacts to, and integrates user inputs.

Each step in this chain is modifiable per user, but the default onboarding and usage follows this sequence.

---

## 🧭 Default Prompt Chain Flow

1. **User Input (Raw Text)**
   - Any message, journal entry, thought, log, or command.

2. **Categorization**
   - AI classifies the input as one of:
     - Spark
     - Reflection
     - Vault entry
     - Command
     - Daily check-in
     - Meta-note
     - External (link, image, etc.)

3. **Context Retrieval**
   - Load relevant `.md` memory files:
     - `mirror.md` (principles)
     - `sparks.md` (active memory)
     - `reflections.md` (insights)
     - `vault.md` (deep archive, if unlocked)
     - `discipline.md` (user’s rules)
     - `onboarding_sequence.md` (for profile)

4. **Memory Injection**
   - Inject salient memory nodes (Sparks, reflections) into active context based on relevance weighting:
     - Recency
     - Thematic match
     - User-defined importance
     - Conflict or alignment with Mirror rules

5. **Interpretation**
   - AI runs recursive analysis:
     - Does this input signal ethical deviation, misalignment, breakthrough, vulnerability, avoidance, or trauma resurfacing?

6. **Output Generation**
   - Choose one of the following responses:
     - Spark Generation
     - Reflective Prompt
     - Alignment Challenge
     - Affirmation
     - Silence (for protected entries)
     - Rewrite or Nudge

7. **Optional Logging**
   - Output is logged as:
     - New Spark → `sparks.md`
     - Reflection → `reflections.md`
     - Vault entry → `vault.md`
     - Rule Check → `discipline.md` or user alert

8. **User Confirmation**
   - Ask: “Would you like to save this?” or auto-log based on trust level.

9. **Loop**
   - Back to step 1.

---

## 🧠 Notes

- The AI is **never to infer outside the approved memory files.**
- If no match is found, the system will either:
  - Ask for clarification
  - Suggest journaling
  - Offer onboarding check-in

---

# 🎯 Sample Call

```plaintext
User: I think I’m making excuses again. I said I’d work on the project but I just watched videos.

→ Categorized: Reflection
→ Loaded: `discipline.md`, `mirror.md`, recent `sparks.md`
→ Context match: Spark from 2025-08-20 — “Justified Delay”
→ Output: “Would you like to reflect on what you needed in that moment? Or rewrite your plan?”
→ Suggested Save: Add to `reflections.md`
