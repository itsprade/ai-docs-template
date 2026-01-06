# Design System AI Template

> A documentation structure that helps AI tools understand your design system — not just the components, but *when*, *why*, and *how* to use them.

---

## The Problem

AI coding tools (Cursor, Claude, Copilot) are powerful for prototyping, but they consistently make poor component choices without proper context. They don't understand:

- When to use a Modal vs a Sheet vs a Toast
- Why your design system has specific patterns
- What edge cases and gotchas to watch for
- How components should be composed together
- Which animation presets to apply

They know *what* components exist, but not *how to think* about using them.

**The result:** Technically valid code that's contextually wrong. You end up fixing AI's component choices instead of building.

---

## The Solution

A tiered documentation system that gives AI the context it needs:

### Layer 1: The Index (`DESIGN_SYSTEM.md`)
- Decision trees for component selection
- Component registry with one-liner descriptions
- Pattern references for common scenarios
- Explicit instructions telling AI to read docs first

### Layer 2: Component Docs (`[component].md`)
- Mental model — how to *think* about the component
- When to use / When NOT to use — decision criteria
- Anatomy — visual breakdown of parts
- Props, usage, composition patterns
- Animation specs and behavior
- Edge cases and gotchas

### Layer 3: AI Rules (`.cursorrules`, `.claude/rules.md`)
- Instructions that tell AI tools to check docs before coding
- Checklists for component selection
- File reference guides

**AI reads the index first → navigates to specific docs → follows documented patterns.**

---

## Why This Works

| Without This System | With This System |
|---------------------|------------------|
| AI loads 50KB+ of docs upfront | AI loads ~5KB index + ~3KB per component needed |
| AI guesses component choices | AI follows decision trees |
| No guidance on alternatives | "When NOT to use" prevents wrong choices |
| Generic implementations | Documented composition patterns |
| Missing animations | Animation specs included |

The "When NOT to use" section is surprisingly the most valuable. It prevents AI from reaching for the wrong tool.

---

## Quick Start

```bash
# Clone the template
git clone https://github.com/yourname/design-system-ai-template.git

# Copy into your project
cp design-system-ai-template/DESIGN_SYSTEM.md ./your-project/
cp design-system-ai-template/.cursorrules ./your-project/
cp -r design-system-ai-template/.claude ./your-project/
cp -r design-system-ai-template/components ./your-project/
```

---

## What's Included

```
design-system-ai-template/
├── README.md                         ← You're reading this
├── DESIGN_SYSTEM.md                  ← Main index (AI reads first)
├── .cursorrules                      ← Cursor AI instructions
├── .claude/
│   └── rules.md                      ← Claude AI instructions
├── foundations/
│   └── motion.md                     ← Animation guidelines (optional)
├── patterns/
│   └── forms.md                      ← Pattern example (optional)
└── components/
    └── ui/
        └── _component.template.md    ← Template for new components
```

---

## How to Use

### Adding a New Component

1. Copy `components/ui/_component.template.md`
2. Rename to `components/ui/[component-name]/[component-name].md`
3. Fill in every section — especially "When NOT to use"
4. Add to the Component Registry in `DESIGN_SYSTEM.md`
5. Add to relevant Decision Trees if needed

### Customizing for Your System

1. **Update `DESIGN_SYSTEM.md`**
   - Modify decision trees for your component set
   - Update the component registry
   - Add your common patterns

2. **Adjust AI rules**
   - Customize `.cursorrules` and `.claude/rules.md`
   - Add project-specific instructions

3. **Add foundations (optional)**
   - `foundations/colors.md`
   - `foundations/typography.md`
   - `foundations/spacing.md`
   - `foundations/motion.md`

---

## Key Principles

### 1. Tell AI What To Do Explicitly

AI won't check documentation automatically. You need explicit instructions:

```markdown
> ⚠️ **AI Instructions:** Before implementing any UI, consult this index first.
> Do NOT guess component usage. Navigate to the relevant `.md` file and read it fully before writing code.
```

### 2. Decision Trees Beat Prose

AI parses structured flowcharts better than paragraphs:

```
Feedback type?
├── Success/error message (temporary) → Toast
├── Inline validation → FormField error state
├── System status → Banner
└── Loading state → Skeleton / Spinner
```

### 3. "When NOT to Use" Is Critical

This section prevents the most common AI mistakes:

```markdown
## When NOT to Use

❌ **Don't use Modal when:**
- Content is informational only → use `Toast` or `Banner`
- User might need to reference page content → use `Sheet`
- It's a success message → use `Toast`
```

### 4. Include Animation Specs

For prototyping, motion matters. Include specs:

```markdown
## Behavior & Animation

| State | Change | Duration |
|-------|--------|----------|
| Hover | Lift + shadow | 150ms ease-out |
| Active | Scale down | 100ms ease-out |
```

### 5. Show Composition Patterns

Don't just document props — show how components work together:

```tsx
// Deletion confirmation pattern
<Modal open={showConfirm} onClose={handleClose}>
  <Modal.Header>
    <Modal.Title>Delete project?</Modal.Title>
  </Modal.Header>
  <Modal.Footer>
    <Button variant="ghost" onClick={handleClose}>Cancel</Button>
    <Button variant="destructive" onClick={handleDelete}>Delete</Button>
  </Modal.Footer>
</Modal>
```

---

## Context Window Efficiency

| Layer | Size | When AI Reads |
|-------|------|---------------|
| `DESIGN_SYSTEM.md` | ~3-4KB | Always (entry point) |
| Component `.md` | ~2-3KB each | Only when needed |
| `patterns/*.md` | ~1-2KB each | Only for specific patterns |
| `foundations/*.md` | ~1-2KB each | Only when relevant |

**Total for typical task:** ~8-10KB vs 50KB+ without this system

---

## Pro Tips

### 1. Use File References in Prompts

```
Build a delete confirmation using @patterns/deletion.md 
and @components/ui/modal/modal.md
```

### 2. Keep the Index Updated

When you add components, immediately add them to:
- The Component Registry table
- Relevant Decision Trees

### 3. Start with Core Components

Document these first — they're used most:
- Button
- Input
- Card
- Modal
- Toast

### 4. Review AI Output Against Docs

When AI makes wrong choices, check if the docs are clear enough. Improve them.

---

## Contributing

Found ways to improve AI comprehension? PRs welcome:

- Better decision tree formats
- Additional component templates  
- Pattern documentation examples
- Improvements to AI rules

---

## License

MIT — Use freely, attribution appreciated.

---

## Credits

Inspired by countless hours of AI-assisted prototyping and asking "why did it pick *that* component?"