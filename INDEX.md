# Design System Index

> ⚠️ **AI Instructions:** Before implementing any UI, consult this index first.
> Do NOT guess component usage. Navigate to the relevant `.md` file and read it fully before writing code.

## How to Use This System

1. **Identify the pattern** — What is the user trying to achieve?
2. **Check the decision tree** below — Find the right component category
3. **Read the component's `.md` file** — Understand usage, props, and best practices
4. **Only then write code** — Use the documented patterns

---

## Quick Decision Trees

### User needs to take an action
```
Action type?
├── Primary page action → Button (components/ui/button/button.md)
├── Secondary/supporting action → Button secondary variant
├── Icon only → IconButton (components/ui/icon-button/icon-button.md)
├── Navigation that looks like action → LinkButton
├── Multiple related actions → ButtonGroup
├── Contextual/right-click → ContextMenu
└── Destructive action → Button destructive + confirmation flow
```

### User needs to see feedback
```
Feedback type?
├── Success/error message (temporary) → Toast (components/ui/toast/toast.md)
├── Inline form validation → FormField error state
├── System-wide status → Banner
├── Loading (known progress) → Progress
├── Loading (unknown duration) → Spinner
├── Content loading → Skeleton
└── Empty state → EmptyState
```

### User needs to input data
```
Input type?
├── Short text → Input (components/ui/input/input.md)
├── Long text → Textarea
├── Selection from options
│   ├── 2-5 visible options → RadioGroup / SegmentedControl
│   ├── 5+ options (single select) → Select
│   ├── 5+ options (searchable) → Combobox
│   └── Multiple selections → MultiSelect / Checkbox group
├── Boolean toggle
│   ├── In a form → Checkbox
│   └── Settings/preferences → Switch
├── Date/time → DatePicker
├── File upload → FileUpload
└── Rich content → RichTextEditor
```

### User needs to see content
```
Content type?
├── Grouped related information → Card (components/ui/card/card.md)
├── List of similar items → List
├── Structured data comparison → Table
├── Hierarchical/nested data → Tree / Accordion
├── User/entity representation → Avatar
├── Status indicator → Badge
├── Category/label → Tag
├── No content available → EmptyState
└── Data visualization → Chart components
```

### User needs an overlay/interruption
```
Interruption level?
├── Must decide before continuing → Modal (components/ui/modal/modal.md)
├── Supplementary panel (can coexist) → Sheet (components/ui/sheet/sheet.md)
├── Quick info on hover → Tooltip
├── Interactive anchored UI → Popover
├── Action menu from trigger → DropdownMenu
├── Right-click menu → ContextMenu
└── Search/command interface → CommandPalette
```

---

## Component Registry

> **AI Instruction:** This is your lookup table. Find the component, then READ its `.md` file before using.

### Primitives (Low-level building blocks)
| Component | Path | One-liner |
|-----------|------|-----------|
| Button | `components/ui/button/button.md` | Actions and triggers |
| Input | `components/ui/input/input.md` | Single-line text entry |
| Textarea | `components/ui/textarea/textarea.md` | Multi-line text entry |
| Select | `components/ui/select/select.md` | Choose from dropdown |
| Checkbox | `components/ui/checkbox/checkbox.md` | Toggle boolean or multi-select |
| Radio | `components/ui/radio/radio.md` | Single choice from few options |
| Switch | `components/ui/switch/switch.md` | On/off toggle for settings |
| Slider | `components/ui/slider/slider.md` | Range/value selection |

### Layout (Structure and spacing)
| Component | Path | One-liner |
|-----------|------|-----------|
| Card | `components/ui/card/card.md` | Contained content group |
| Stack | `components/ui/stack/stack.md` | Vertical/horizontal flex spacing |
| Grid | `components/ui/grid/grid.md` | 2D responsive layouts |
| Divider | `components/ui/divider/divider.md` | Visual separation |
| Container | `components/ui/container/container.md` | Max-width wrapper |

### Feedback (Status and responses)
| Component | Path | One-liner |
|-----------|------|-----------|
| Toast | `components/ui/toast/toast.md` | Temporary notifications |
| Banner | `components/ui/banner/banner.md` | Persistent system messages |
| Progress | `components/ui/progress/progress.md` | Determinate loading |
| Spinner | `components/ui/spinner/spinner.md` | Indeterminate loading |
| Skeleton | `components/ui/skeleton/skeleton.md` | Content placeholder |

### Overlays (Layered UI)
| Component | Path | One-liner |
|-----------|------|-----------|
| Modal | `components/ui/modal/modal.md` | Blocking dialog |
| Sheet | `components/ui/sheet/sheet.md` | Slide-in panel |
| Popover | `components/ui/popover/popover.md` | Anchored floating UI |
| Tooltip | `components/ui/tooltip/tooltip.md` | Hover hints |
| DropdownMenu | `components/ui/dropdown-menu/dropdown-menu.md` | Action menu |
| ContextMenu | `components/ui/context-menu/context-menu.md` | Right-click menu |
| CommandPalette | `components/ui/command-palette/command-palette.md` | Keyboard-first search |

### Data Display (Showing information)
| Component | Path | One-liner |
|-----------|------|-----------|
| Table | `components/ui/table/table.md` | Structured data rows |
| List | `components/ui/list/list.md` | Vertical item collection |
| Avatar | `components/ui/avatar/avatar.md` | User/entity image |
| Badge | `components/ui/badge/badge.md` | Status indicators |
| Tag | `components/ui/tag/tag.md` | Labels and categories |

### Navigation (Moving around)
| Component | Path | One-liner |
|-----------|------|-----------|
| Tabs | `components/ui/tabs/tabs.md` | Content sections |
| Breadcrumb | `components/ui/breadcrumb/breadcrumb.md` | Location hierarchy |
| Pagination | `components/ui/pagination/pagination.md` | Page navigation |
| Sidebar | `components/ui/sidebar/sidebar.md` | App navigation |

### Composite (High-level patterns)
| Component | Path | One-liner |
|-----------|------|-----------|
| FormField | `components/ui/form-field/form-field.md` | Label + Input + Error |
| SearchInput | `components/ui/search-input/search-input.md` | Search with icon |
| EmptyState | `components/ui/empty-state/empty-state.md` | No content placeholder |
| ConfirmDialog | `components/ui/confirm-dialog/confirm-dialog.md` | Pre-built confirmation |
| DataTable | `components/ui/data-table/data-table.md` | Table with sorting/filtering |

---

## Common Patterns

> **AI Instruction:** For these recurring scenarios, follow the documented pattern exactly.

| Pattern | Guide | Components Used |
|---------|-------|-----------------|
| Form with validation | `patterns/forms.md` | FormField, Button, Toast |
| Deletion confirmation | `patterns/deletion.md` | Modal, Button, Toast |
| List with actions | `patterns/list-actions.md` | List, DropdownMenu, Modal |
| Settings page | `patterns/settings.md` | Tabs, FormField, Switch |
| Empty + loading states | `patterns/async-states.md` | Skeleton, EmptyState, Spinner |
| Search experience | `patterns/search.md` | SearchInput, CommandPalette, List |

---

## Animation Presets

Quick reference — details in `foundations/motion.md`

| Preset | Duration | Easing | Use for |
|--------|----------|--------|---------|
| `instant` | 100ms | ease-out | Micro-feedback (hover, active) |
| `fast` | 150ms | ease-out | Small transitions, toggles |
| `normal` | 200ms | ease-out | Most UI transitions |
| `smooth` | 300ms | cubic-bezier(0.16, 1, 0.3, 1) | Overlays, modals entering |
| `slow` | 500ms | ease-in-out | Page transitions |

---

## AI Checklist Before Writing UI Code

- [ ] Did I identify the core user need?
- [ ] Did I check the decision tree above?
- [ ] Did I READ the component's `.md` file?
- [ ] Am I using the right component (not a similar-looking one)?
- [ ] Did I follow the composition pattern in the docs?
- [ ] Did I check "When NOT to use" section?
- [ ] Am I handling edge cases mentioned in the docs?

---

## Folder Structure

```
your-repo/
├── DESIGN_SYSTEM.md          ← You are here (AI reads this FIRST)
├── .cursorrules              ← Cursor AI instructions
├── .claude/
│   └── rules.md              ← Claude AI instructions
├── foundations/
│   ├── colors.md
│   ├── typography.md
│   ├── spacing.md
│   └── motion.md             ← Animation philosophy
├── patterns/
│   ├── forms.md
│   ├── deletion.md
│   ├── async-states.md
│   └── ...
└── components/
    └── ui/
        ├── _component.template.md  ← Template for new components
        ├── button/
        │   ├── button.tsx
        │   └── button.md     ← Full component docs
        ├── modal/
        │   ├── modal.tsx
        │   └── modal.md
        └── ...
```

---

## How This Saves Context Window

| Layer | Size | When AI Reads |
|-------|------|---------------|
| `DESIGN_SYSTEM.md` | ~3-4KB | Always (it's the entry point) |
| Component `.md` | ~2-3KB each | Only when that component is needed |
| `patterns/*.md` | ~1-2KB each | Only for specific patterns |

**Without this system:** AI might load 50KB+ of docs upfront
**With this system:** AI loads ~5KB index + ~3KB per component needed = much leaner

---

## Pro Tips for AI Tools

### 1. Add to `.cursorrules` or Claude rules:
```
Before implementing any UI component, ALWAYS read DESIGN_SYSTEM.md first.
Then navigate to and read the specific component's .md file before writing code.
Never guess component APIs — always reference the documentation.
```

### 2. Use file references in prompts:
```
Build a delete confirmation using the pattern in @patterns/deletion.md 
and components from @components/ui/modal/modal.md
```

### 3. Keep the index updated
When you add components, add them to the registry table and relevant decision trees.