---
name: lesson-summarizer
description: |
  Summarizes educational lessons in beginner-friendly language and extracts main points for exam preparation.
  This skill should be used when students need to understand complex lessons, prepare for exams, or review course material quickly.
allowed-tools: Read, Grep, Glob
---

# Lesson Summarizer

Transform educational content into beginner-friendly summaries and exam-ready study guides.

## What This Skill Does

- **Summarizes lessons** with clear explanations using analogies and simple language
- **Extracts exam points** as concise, high-priority bullet points
- **Works with any subject** (math, science, history, language, etc.)
- **Supports multiple formats** (text files, PDFs, markdown, articles)

## What This Skill Does NOT Do

- Replace reading the original material
- Create practice tests (only extracts likely exam concepts)
- Provide personalized tutoring or feedback
- Memorize or index lessons for later retrieval

---

## Before Implementation

Gather context to ensure successful implementation:

| Source | Gather |
|--------|--------|
| **Lesson Content** | Read the full lesson/article to understand scope, complexity, and topics |
| **Student Level** | Infer from lesson content (e.g., "AP Biology" = college prep, "algebra" = high school) or confirm directly |
| **Subject Domain** | Identify the subject area to apply appropriate terminology and examples |
| **Conversation Context** | Check if user already mentioned their education level, exam date, or specific topics to focus on |

---

## Required Clarifications

Before proceeding with summarization, confirm these essential details:

1. **Is the lesson content available?**
   - Can the user provide the full text, upload a file, or should I wait?
   - Note: Partial content or outlines work but produce less comprehensive summaries

2. **What's the target education level?**
   - Try to infer from lesson topic first (e.g., "photosynthesis" might suggest high school biology)
   - Ask only if unclear: "Is this for high school, college, or self-study?"

## Optional Clarifications

If relevant and not already mentioned in conversation:

3. **Specific exam focus** (if the user didn't already mention which topics matter most)
4. **Summary length preference** (longer/shorter than default 300-500 words)
5. **Learning goal** (exam prep, conceptual understanding, quick review)

---

## How to Use This Skill

### Invoke the skill:
```
/lesson-summarizer <path-to-lesson-file>
```

Or provide the lesson content directly in your message.

### Output Specification

The skill delivers three core sections:

1. **Beginner-Friendly Summary** (~300-500 words)
   - Clear heading introducing the topic and its relevance
   - Explanation using everyday analogies
   - Breakdown of complex ideas into simpler pieces
   - Simple vocabulary (technical terms defined as introduced)
   - ASCII diagrams if helpful for visualization
   - Real-world examples or scenarios
   - 1/4 to 1/3 the length of the full lesson for quick review

2. **Exam-Ready Key Points** (bullet list, 5-15 points)
   - Numbered or bulleted key concepts
   - Concise definitions or explanations (1-3 sentences each)
   - Listed in priority order (most important/frequently tested first)
   - Include definitions, formulas, dates, processes, relationships, and common misconceptions
   - Format: bold terms, clear explanations, memory tips for difficult items

3. **Summary Section** (best practices included below)
   - Recap of key concepts (2-5 bullet points)
   - Learning objectives met
   - Main takeaways for long-term retention
   - Connections to broader course context
   - Common pitfalls and misconceptions to avoid

---

## Summarization Workflow

### Step 1: Understand the Lesson
- Read the entire lesson carefully
- Identify the main topic and learning objectives
- Note the complexity level
- Find connections between concepts

### Step 2: Create the Beginner-Friendly Summary
- **Start with context**: What is this lesson about and why does it matter?
- **Use analogies**: Compare to familiar real-world examples
- **Explain terminology**: Define technical terms as you introduce them
- **Break into sections**: Organize by subtopic or logical flow
- **Add examples**: Include concrete examples or scenarios
- **Visual aids**: Use ASCII diagrams for processes, structures, or relationships
- **Keep language simple**: Avoid jargon; use "is like" instead of "analogous to"

### Step 3: Extract Exam Key Points
- **Identify core concepts**: What must students know for exams?
- **Scan for definitions**: Key terms, dates, formulas, processes
- **Spot cause-and-effect**: Relationships and dependencies
- **Find common patterns**: Themes that repeat across the lesson
- **List in priority order**: Most important/frequently tested concepts first
- **Keep concise**: 1-3 sentences per bullet point

### Step 4: Create the Summary Section
- **Recap key concepts**: 2-5 most important ideas from the lesson
- **Confirm learning objectives**: What students can now understand or do
- **Extract takeaways**: Ideas for long-term retention, not just exam prep
- **Show connections**: How this fits into broader course/topic context
- **Highlight common mistakes**: "Don't confuse X with Y" statements
- **Format for quick review**: Concise, scannable format (bullets, short paragraphs)

### Step 5: Format for Learning
- Use formatting for clarity (bold for terms, code blocks for equations)
- Group related concepts together
- Add "memory tips" for hard-to-remember items
- Note any tricky concepts or common misconceptions

---

## Example Workflow

**Input**: Article about the water cycle
**Step 1 Output**: Identified 4 stages (evaporation, condensation, precipitation, collection)
**Step 2 Output**: Summary with water→cloud→rain analogy, simple language
**Step 3 Output**: 8 key exam points (definition of evaporation, examples, energy involved, etc.)
**Step 4 Output**: Formatted with bold terms, diagram of cycle, memory tip for condensation

---

## Summarization Techniques

### Analogies
Connect unfamiliar to familiar:
- "Mitochondria are like power plants in a factory (the cell)"
- "Photosynthesis is like plants eating sunlight"

### Simple Language Rules
- Use "is" instead of "constitutes"
- Use "makes" instead of "generates"
- Use "needs" instead of "requires"
- Explain "why" before "how"

### Structure for Understanding
```
What is it?
  ↓
Why does it matter?
  ↓
How does it work?
  ↓
Examples (real-world or in context)
```

### Visual Organization
- Use headers and subheaders
- Bullet points for lists
- Short paragraphs (2-3 sentences max)
- ASCII diagrams for processes/structures

---

## Exam Points Extraction Rules

### What to Include
✓ Definitions and terminology
✓ Key dates, numbers, or formulas
✓ Cause-and-effect relationships
✓ Main processes or stages
✓ Common misconceptions to avoid
✓ Frequently tested concepts

### What to Skip
✗ Extra examples beyond one per point
✗ Author's personal opinions
✗ Introductory phrases ("It is worth noting...")
✗ Redundant information

### Priority Ordering
1. **High priority**: Central topics, definitions, essential processes
2. **Medium priority**: Important details, supporting concepts
3. **Low priority**: Extended examples, historical context, nice-to-know facts

---

## Handling Different Input Scenarios

### Complete Lesson Text
**Best case**: Full lesson content provided (300-3000 words)
- Produces comprehensive, accurate summary and exam points
- Proceed with all steps of workflow

### Incomplete Input (Outline, Abstract, or Partial Text)
**What to do**: Acknowledge limitations and deliver best-effort summary
- Summarize available content clearly
- Note what information is missing that could affect exam prep
- Ask user: "Would you like to share the full lesson for a more comprehensive summary?"
- Example: "You've provided an outline. I can summarize these points, but a full lesson would help identify additional exam-likely concepts."

### Very Short Lessons (< 200 words)
**What to do**: Adjust expectations
- Produce proportionally shorter summary (100-150 words)
- Extract 3-6 key points (instead of default 5-15)
- Ensure quality isn't sacrificed—still include analogies and clarity

### Highly Specialized Topics
**What to do**: Verify accuracy and show domain limitations
- Be transparent: "This is advanced [domain] content; I'll summarize but verify key technical points"
- Use terminology from the source material
- Extract concepts accurately but note if analogies might oversimplify

### Conflicting Information in Source
**What to do**: Flag discrepancies
- Note where sources conflict: "The lesson states X, but also mentions Y (which contradicts). I've prioritized the primary explanation."
- If unable to reconcile, present both viewpoints in exam points

---

## Special Cases by Subject

### Math/Science Lessons
- Include key formulas (highlighted)
- Explain what variables mean
- Show how formulas are applied
- Add step-by-step example walkthrough

### History/Literature Lessons
- Explain cause-and-effect chains
- Highlight key figures, dates, and events
- Note different perspectives
- Extract lessons/significance

### Language Lessons
- Define grammar concepts with clear examples
- Show sentence patterns (before/after)
- Highlight exception rules
- Include pronunciation or etymology if relevant

---

## Output Format Template

Deliver summaries in this structure for consistency:

```markdown
## [Topic Name]: [Engaging Subtitle]

[Beginner-friendly summary with:
- Opening context explaining what and why
- Analogies and everyday comparisons
- Breakdown into logical sections
- ASCII diagram(s) if helpful
- Real-world examples
- Concluding insight]

### Exam-Ready Key Points

1. **[Concept Name]**: [Clear definition/explanation, 1-3 sentences]
2. **[Concept Name]**: [Clear definition/explanation, 1-3 sentences]
...

(Ordered by priority: most important/testable first)

### Summary & Takeaways

**Key Concepts Recap**
- [Main idea 1]
- [Main idea 2]
- [Main idea 3]

**What You've Learned**
- [Learning objective 1]
- [Learning objective 2]

**How This Fits In**
- Connection to [broader topic/course]
- Links to prerequisite/follow-up concepts

**Common Pitfalls to Avoid**
- Don't confuse [concept A] with [concept B]
- Remember that [common misconception] is incorrect
```

---

## Quality Checklist

Before delivering the summary:
- [ ] Summary uses simple, clear language (define technical terms as introduced)
- [ ] At least one analogy or real-world comparison included
- [ ] Summary structure follows: What is it → Why does it matter → How does it work → Examples
- [ ] ASCII diagrams aid understanding (if complex concepts warrant visual aid)
- [ ] Exam points are concise (1-3 sentences each)
- [ ] Exam points are in priority order (high-priority first)
- [ ] No critical information is missed
- [ ] Examples are relevant and clear
- [ ] Memory tips included for hard-to-remember items
- [ ] Common misconceptions noted in exam points (if applicable)

### Summary Section Quality Checks
- [ ] Key concepts recap is 2-5 bullets (not exhaustive)
- [ ] Learning objectives clearly state what student can now do/understand
- [ ] Connections to broader course/topic are explained
- [ ] Common pitfalls section identifies 1-2 misconceptions to avoid
- [ ] Summary length allows quick review (1/4 to 1/3 of original lesson)
- [ ] Formatting is scannable (bullets, short paragraphs, bold terms)

---

## Important Notes on Curriculum & Standards

- **Math and Science**: Curricula standards update periodically (AP, IB, national standards). If studying material from previous years, verify that exam points align with current curriculum.
- **History**: Historiography changes; note if your lesson reflects current historical consensus or older perspectives.
- **Language learning**: Grammar rules and vocabulary can vary by dialect or standard. Clarify which English variant (American, British, etc.) or which language standard applies.

---

## Memory Tips & Mnemonics

For difficult concepts, create memory devices:

**Acronyms**: "PEMDAS" for order of operations, "BODMAS" in UK
**Rhymes**: "In 1492, Columbus sailed the ocean blue"
**Vivid imagery**: Link concepts to mental images (DNA as a twisted ladder)
**Story chains**: Connect concepts in a narrative (water cycle as journey)
**Position method**: Visualize information in specific locations

Include subject-specific memory tips in exam points where concepts are commonly forgotten.

---

## Tips for Better Results

1. **Provide complete lesson**: Paste full text or upload document for most comprehensive results
2. **Specify subject/level**: Mention "high school biology" or "college physics" for appropriate complexity
3. **Highlight focal areas**: If certain topics matter more for your exam, mention them explicitly
4. **Ask for adjustments**: Request more/fewer exam points, simpler/deeper explanations, or emphasis on specific topics
5. **Use for active learning**: Read the summary, then test yourself on the exam points before the actual test
6. **Request follow-ups**: Ask for "practice question concepts" or "common misconceptions to avoid" for deeper prep
7. **Verify against your exam**: Cross-check extracted points against your exam format and emphasis (some exams weight topics differently)

---

## Summary Section Best Practices

The summary section is critical for long-term learning and quick review:

### What to Include
✓ **Key concepts recap** (2-5 bullets distilling the main ideas)
✓ **Learning objectives** (what students can now do or understand)
✓ **Main takeaways** (ideas to remember beyond exam prep)
✓ **Connections** (how this fits into the broader course/topic)
✓ **Common pitfalls** (1-2 misconceptions to avoid, phrased as "don't confuse")
✓ **Visual organization** (bullets, bold terms, short paragraphs)

### Length & Scannability
- Keep summary 1/4 to 1/3 the length of the original lesson
- Students should grasp it in 2-3 minutes of reading
- Use clear formatting: headers, bullets, short paragraphs
- Avoid jargon; define technical terms if used

### Real-World Context
- Explain why this topic matters beyond the exam
- Link to prerequisite concepts students should understand
- Note follow-up topics that build on this foundation
- Use concrete examples when applicable
