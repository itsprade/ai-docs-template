# Index Update Rules

> ⚠️ **AI Instructions:** When a new component is created, you MUST update all locations listed below.
> Do NOT skip any section. Follow the format exactly as shown in existing entries.

---

## When to Use This File

Reference this file when:
- Creating a new component
- Renaming an existing component
- Deleting a component
- Changing a component's category
- Adding a new pattern

---

## Checklist: New Component

When adding a new component, update these files in order:

- [ ] 1. Create component `.md` file
- [ ] 2. Update `DESIGN_SYSTEM.md` — Component Registry
- [ ] 3. Update `DESIGN_SYSTEM.md` — Decision Tree (if applicable)
- [ ] 4. Update `DESIGN_SYSTEM.md` — Common Patterns (if applicable)
- [ ] 5. Update related component docs — Related Components table

---

## 1. Create Component Documentation

**Location:** `components/ui/[component-name]/[component-name].md`

**Action:** Copy `_component.template.md` and fill in all sections.

**Required sections:**
- Mental Model
- When to Use
- When NOT to Use
- Anatomy
- Props
- Usage examples
- Behavior & Animation
- Accessibility
- Edge Cases
- Related Components

---

## 2. Update Component Registry

**Location:** `DESIGN_SYSTEM.md` → Component Registry section

**Action:** Add a new row to the appropriate category table.

**Format:**
```markdown
| ComponentName | `components/ui/component-name/component-name.md` | One-liner description |
```

**Categories:**
- Primitives — Low-level building blocks (Button, Input, Select)
- Layout — Structure and spacing (Card, Stack, Grid)
- Feedback — Status and responses (Toast, Banner, Spinner)
- Overlays — Layered UI (Modal, Sheet, Popover)
- Data Display — Showing information (Table, List, Avatar)
- Navigation — Moving around (Tabs, Breadcrumb, Sidebar)
- Composite — High-level patterns (FormField, DataTable)

**Example — Adding a new "Chip" component to Primitives:**

Before:
```markdown
### Primitives
| Component | Path | One-liner |
|-----------|------|-----------|
| Button | `components/ui/button/button.md` | Actions and triggers |
| Input | `components/ui/input/input.md` | Single-line text entry |
```

After:
```markdown
### Primitives
| Component | Path | One-liner |
|-----------|------|-----------|
| Button | `components/ui/button/button.md` | Actions and triggers |
| Chip | `components/ui/chip/chip.md` | Compact interactive element |
| Input | `components/ui/input/input.md` | Single-line text entry |
```

**Rules:**
- Keep alphabetical order within each category
- One-liner should be 3-6 words
- Path must match actual file location

---

## 3. Update Decision Trees

**Location:** `DESIGN_SYSTEM.md` → Quick Decision Trees section

**Action:** Add the component to relevant decision tree(s).

**When to add:**
- Component serves a distinct user need
- Component is an alternative to existing options
- Users might be confused about when to use it

**Format:**
```
├── Scenario description → ComponentName (path/to/component.md)
```

**Example — Adding "Chip" to the action decision tree:**

Before:
```markdown
### User needs to take an action
```
Action type?
├── Primary page action → Button
├── Icon only → IconButton
└── Navigation that looks like action → LinkButton
```
```

After:
```markdown
### User needs to take an action
```
Action type?
├── Primary page action → Button
├── Icon only → IconButton
├── Compact toggleable action → Chip (components/ui/chip/chip.md)
└── Navigation that looks like action → LinkButton
```
```

**Rules:**
- Add to ALL relevant decision trees
- Include the file path for new/less common components
- Place in logical order (most common first, or alphabetical)

---

## 4. Update Common Patterns

**Location:** `DESIGN_SYSTEM.md` → Common Patterns section

**Action:** Add or update pattern entries if the component is used in common patterns.

**When to add:**
- Component is essential to a recurring pattern
- New pattern emerges from component usage

**Format:**
```markdown
| Pattern Name | `patterns/pattern-name.md` | Component1, Component2, NewComponent |
```

**Example — Adding "Chip" to filter pattern:**

Before:
```markdown
| Pattern | Guide | Components Used |
|---------|-------|-----------------|
| Form with validation | `patterns/forms.md` | FormField, Button, Toast |
```

After:
```markdown
| Pattern | Guide | Components Used |
|---------|-------|-----------------|
| Form with validation | `patterns/forms.md` | FormField, Button, Toast |
| Filter interface | `patterns/filters.md` | Chip, Select, Button |
```

---

## 5. Update Related Components

**Location:** Other component `.md` files → Related Components section

**Action:** Add the new component to related components' docs.

**When to add:**
- New component is an alternative to existing component
- New component is commonly used with existing component
- Users might confuse the two

**Format:**
```markdown
| Instead of... | Use... | When... |
|---------------|--------|---------|
| ThisComponent | `NewComponent` | Scenario when new component is better |
```

**Example — Updating Button.md to reference Chip:**

Add to `components/ui/button/button.md` → Related Components:
```markdown
| Instead of... | Use... | When... |
|---------------|--------|---------|
| Button | `Chip` | Compact, toggleable selections |
```

Add to `components/ui/chip/chip.md` → Related Components:
```markdown
| Instead of... | Use... | When... |
|---------------|--------|---------|
| Chip | `Button` | Primary actions, form submissions |
```

**Components to check:**
- Direct alternatives (similar function)
- Common companions (often used together)
- Parent/child relationships (one contains the other)

---

## Quick Reference: What to Update

| Adding... | Update these files |
|-----------|-------------------|
| New primitive component | Registry (Primitives), Decision tree, Related components |
| New layout component | Registry (Layout), Related components |
| New feedback component | Registry (Feedback), Feedback decision tree, Related components |
| New overlay component | Registry (Overlays), Overlay decision tree, Related components |
| New data display component | Registry (Data Display), Content decision tree, Related components |
| New navigation component | Registry (Navigation), Related components |
| New composite component | Registry (Composite), Relevant decision trees, Common patterns, Related components |
| New pattern | Common Patterns table, Create pattern `.md` file |

---

## Validation Checklist

After making updates, verify:

- [ ] Component appears in Component Registry
- [ ] Component is in correct category
- [ ] Path in registry matches actual file location
- [ ] Added to relevant decision tree(s)
- [ ] Related components updated (both directions)
- [ ] Alphabetical order maintained in registry
- [ ] One-liner is concise and clear
- [ ] All links/paths are correct

---

## Example: Full Update Flow

**Scenario:** Adding a new `Chip` component

### Step 1: Create documentation
```
components/ui/chip/chip.md  ← Copy from _component.template.md and fill in
```

### Step 2: Update registry in DESIGN_SYSTEM.md
```markdown
### Primitives
| Chip | `components/ui/chip/chip.md` | Compact interactive element |
```

### Step 3: Update decision tree in DESIGN_SYSTEM.md
```markdown
### User needs to take an action
├── Compact toggleable action → Chip (components/ui/chip/chip.md)

### User needs to input data
├── Selection from options
│   ├── Toggleable visual selections → Chip (components/ui/chip/chip.md)
```

### Step 4: Update common patterns (if applicable)
```markdown
| Filter interface | `patterns/filters.md` | Chip, Select, Button |
```

### Step 5: Update related component docs

In `button/button.md`:
```markdown
| Button | `Chip` | Compact, toggleable selections |
```

In `tag/tag.md`:
```markdown
| Tag | `Chip` | When element needs to be interactive/dismissible |
```

In `chip/chip.md`:
```markdown
| Chip | `Button` | Primary actions, form submissions |
| Chip | `Tag` | Non-interactive labels |
```

---

## Removing a Component

When deleting a component:

1. [ ] Remove from Component Registry
2. [ ] Remove from Decision Trees
3. [ ] Remove from Common Patterns
4. [ ] Update Related Components in other docs
5. [ ] Delete the component's `.md` file
6. [ ] Search for any other references in docs

---

## Renaming a Component

When renaming a component:

1. [ ] Rename the `.md` file and folder
2. [ ] Update Component Registry (name and path)
3. [ ] Update Decision Trees
4. [ ] Update Common Patterns
5. [ ] Update Related Components in all docs
6. [ ] Search and replace old name in all docs