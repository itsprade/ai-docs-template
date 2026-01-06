# ComponentName

> One-line description: What problem does this component solve? What is its purpose?

---

## Mental Model

Explain how to *think* about this component. What real-world concept does it map to? Use analogies if helpful. This helps AI understand the component's essence, not just its API.

**The [ComponentName] contract:**
- "What this component promises to the user..."
- "When this component appears, it means..."
- "The user should expect..."

---

## When to Use

✅ **Use [ComponentName] when:**
- Specific scenario where this component is the right choice
- Another scenario with clear criteria
- Another scenario explaining the use case
- Context that makes this component appropriate

---

## When NOT to Use

❌ **Don't use [ComponentName] when:**
- Scenario → use `AlternativeComponent` instead
- Scenario → use `AlternativeComponent` instead
- Scenario → use `AlternativeComponent` instead
- Scenario → consider a different approach entirely

**This section is critical for AI to avoid wrong component choices.**

---

## Decision: Choosing Variants

```
What's the context?
├── Context/scenario A → variant-a
├── Context/scenario B → variant-b
├── Context/scenario C → variant-c
└── Context/scenario D → variant-d
```

**Rule of thumb:** [Quick heuristic for choosing between variants]

---

## Anatomy

```
┌─────────────────────────────────────────┐
│                                         │
│   Visual ASCII diagram showing          │
│   the component's structure             │
│   and its parts                         │
│                                         │
└─────────────────────────────────────────┘
```

| Part | Purpose | Required |
|------|---------|----------|
| Part 1 | What this part does | Yes/No |
| Part 2 | What this part does | Yes/No |
| Part 3 | What this part does | Yes/No |
| Part 4 | What this part does | Yes/No |

---

## Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `variant` | `'primary'` \| `'secondary'` \| `'ghost'` | `'primary'` | Visual style variant |
| `size` | `'sm'` \| `'md'` \| `'lg'` | `'md'` | Size preset |
| `disabled` | `boolean` | `false` | Disables interaction |
| `prop4` | `string` | `—` | Description of prop |
| `prop5` | `() => void` | `—` | Callback description |

---

## Usage

### Basic Example

```tsx
import { ComponentName } from '@/components/ui/component-name'

<ComponentName>
  Basic content
</ComponentName>
```

### With Variants

```tsx
// Primary — main usage
<ComponentName variant="primary">...</ComponentName>

// Secondary — supporting usage
<ComponentName variant="secondary">...</ComponentName>

// Ghost — subtle usage
<ComponentName variant="ghost">...</ComponentName>
```

### With All Options

```tsx
<ComponentName
  variant="primary"
  size="lg"
  disabled={false}
  onClick={handleClick}
>
  Full example with all props
</ComponentName>
```

### Real-World Pattern

```tsx
// Show how this component is typically used in context
function RealWorldExample() {
  const [state, setState] = useState()
  
  return (
    <ComponentName>
      {/* Realistic content structure */}
    </ComponentName>
  )
}
```

---

## Behavior & Animation

### States

| State | Visual Change | Transition |
|-------|---------------|------------|
| Default | Base appearance | — |
| Hover | Describe change | 150ms ease-out |
| Active | Describe change | 100ms ease-out |
| Focus | Describe change | — |
| Disabled | Describe change | — |
| Loading | Describe change | — |

### Animation Specs

```tsx
// Framer Motion
<motion.div
  initial={{ opacity: 0, y: 10 }}
  animate={{ opacity: 1, y: 0 }}
  exit={{ opacity: 0, y: 10 }}
  transition={{ 
    duration: 0.2, 
    ease: [0.16, 1, 0.3, 1] 
  }}
/>
```

```css
/* CSS equivalent */
.component {
  transition: all 200ms ease-out;
}

.component:hover {
  /* hover styles */
}

.component:active {
  /* active styles */
}
```

---

## Content Guidelines

### [Part Name, e.g., Title/Label]

**Do:**
- Keep concise (X words or less)
- Use sentence case
- Be specific and actionable

**Don't:**
- Use vague language
- Use ALL CAPS
- End with punctuation (for short labels)

### [Another Part, e.g., Description/Body]

**Do:**
- Explain clearly
- Keep to X lines max

**Don't:**
- Use jargon
- Repeat the title

---

## Composition Patterns

### Pattern Name 1

```tsx
// Describe when to use this pattern
<ComponentName>
  <ComponentName.Part1>...</ComponentName.Part1>
  <ComponentName.Part2>...</ComponentName.Part2>
</ComponentName>
```

### Pattern Name 2

```tsx
// Describe when to use this pattern
<ComponentName>
  <OtherComponent />
  <AnotherComponent />
</ComponentName>
```

### Combined with [Other Component]

```tsx
// Show how this works with related components
<ParentComponent>
  <ComponentName>...</ComponentName>
</ParentComponent>
```

---

## Accessibility

- **Element:** What semantic HTML element is used
- **Role:** ARIA role if applicable
- **Keyboard:** Tab, Enter, Escape, Arrow key behaviors
- **Focus:** How focus is managed
- **Screen reader:** What gets announced
- **Minimum target:** Touch/click target size (44x44px)

---

## Edge Cases & Gotchas

⚠️ **Long content:** How to handle overflow, truncation
```tsx
// Code example if needed
```

⚠️ **Empty state:** What happens with no content

⚠️ **Loading state:** How to show loading

⚠️ **Error state:** How to handle errors

⚠️ **Mobile:** Responsive behavior considerations

⚠️ **[Specific gotcha]:** Description and solution

---

## Design Tokens

```css
/* Component-specific tokens */
--component-radius: var(--radius-md);
--component-padding: var(--space-4);
--component-gap: var(--space-2);

/* Size variants */
--component-height-sm: 32px;
--component-height-md: 40px;
--component-height-lg: 48px;

/* Colors */
--component-bg: var(--color-bg-primary);
--component-border: var(--color-border);
```

---

## Related Components

| Instead of... | Use... | When... |
|---------------|--------|---------|
| ComponentName | `Alternative1` | Scenario when alternative is better |
| ComponentName | `Alternative2` | Another scenario |
| ComponentName | `Alternative3` | Yet another scenario |

---

## Examples in the Wild

Reference implementations for inspiration:
- [Product/Site] — How they use this pattern
- [Product/Site] — Another good example