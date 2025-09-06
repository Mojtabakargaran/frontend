# UI Components

## Button

### Base Implementation
- Use `shadcn/ui` Button component as foundation
- Override with Tailwind classes for custom styling

### Variants
```typescript
variants: {
  variant: {
    primary: "bg-primary-600 text-white hover:bg-primary-700 focus:ring-primary-500",
    secondary: "bg-secondary-400 text-gray-800 hover:bg-secondary-500 focus:ring-secondary-400",
    outline: "border border-primary-600 text-primary-600 hover:bg-primary-50 focus:ring-primary-500",
    ghost: "text-primary-600 hover:bg-primary-50 focus:ring-primary-500",
    destructive: "bg-red-600 text-white hover:bg-red-700 focus:ring-red-500"
  },
  size: {
    sm: "h-8 px-3 text-sm",
    default: "h-10 px-4 text-base",
    lg: "h-12 px-6 text-lg",
    icon: "h-10 w-10"
  }
}
```

### States
- **Default**: Base variant styling
- **Hover**: Background color change + scale transform
- **Focus**: Ring outline with proper contrast
- **Disabled**: `opacity-50 cursor-not-allowed`
- **Loading**: Show spinner, maintain size, disable interaction

### Accessibility
- Proper ARIA labels for icon-only buttons
- Loading state announced to screen readers
- Keyboard focus management

## Input

### Base Implementation
- Use `shadcn/ui` Input component
- Consistent height across all input types

### Variants
```typescript
variants: {
  variant: {
    default: "border-gray-300 focus:border-primary-500 focus:ring-primary-500",
    error: "border-red-500 focus:border-red-500 focus:ring-red-500",
    success: "border-emerald-500 focus:border-emerald-500 focus:ring-emerald-500"
  },
  size: {
    sm: "h-8 px-3 text-sm",
    default: "h-10 px-3 text-base",
    lg: "h-12 px-4 text-lg"
  }
}
```

### Form Field Structure
```html
<div class="space-y-2">
  <label class="text-sm font-medium text-gray-700">
    Field Label <span class="text-red-500">*</span>
  </label>
  <input class="w-full" />
  <p class="text-xs text-gray-500">Helper text</p>
  <p class="text-xs text-red-600">Error message</p>
</div>
```

### States
- **Default**: Border and ring colors as defined
- **Focus**: Enhanced border and ring visibility
- **Error**: Red border + error message below
- **Disabled**: `bg-gray-50 cursor-not-allowed opacity-60`
- **Required**: Red asterisk in label

### Input Types
- **Text/Email/Password**: Standard input styling
- **Phone**: Include country code selector if needed
- **Select**: Use `shadcn/ui` Select component
- **Textarea**: Maintain consistent border styling
- **Checkbox/Radio**: Custom styling with focus rings

## Card

### Base Implementation
- Use `shadcn/ui` Card components
- White background with subtle shadow

### Structure
```typescript
<Card className="bg-white shadow-sm border border-gray-200">
  <CardHeader className="pb-4">
    <CardTitle>Title</CardTitle>
    <CardDescription>Optional description</CardDescription>
  </CardHeader>
  <CardContent className="pt-0">
    Content area
  </CardContent>
  <CardFooter className="pt-4 border-t border-gray-100">
    Actions
  </CardFooter>
</Card>
```

### Variants
```typescript
variants: {
  variant: {
    default: "bg-white shadow-sm border border-gray-200",
    elevated: "bg-white shadow-md border border-gray-200",
    outline: "bg-transparent border-2 border-gray-300",
    ghost: "bg-transparent border-none shadow-none"
  },
  padding: {
    none: "p-0",
    sm: "p-4",
    default: "p-6",
    lg: "p-8"
  }
}
```

### Interactive Cards
- **Hover**: `hover:shadow-lg transition-shadow duration-200`
- **Clickable**: `cursor-pointer hover:bg-gray-50`
- **Focus**: When used as button/link

## Modal

### Base Implementation
- Use `shadcn/ui` Dialog components
- Backdrop with blur effect
- Center positioning with responsive sizing

### Structure
```typescript
<Dialog>
  <DialogTrigger asChild>
    <Button>Open Modal</Button>
  </DialogTrigger>
  <DialogContent className="sm:max-w-lg">
    <DialogHeader>
      <DialogTitle>Modal Title</DialogTitle>
      <DialogDescription>Optional description</DialogDescription>
    </DialogHeader>
    <div className="py-4">
      Modal content
    </div>
    <DialogFooter>
      <Button variant="outline">Cancel</Button>
      <Button>Confirm</Button>
    </DialogFooter>
  </DialogContent>
</Dialog>
```

### Sizes
```typescript
sizes: {
  sm: "sm:max-w-sm",
  default: "sm:max-w-lg",
  lg: "sm:max-w-2xl",
  xl: "sm:max-w-4xl",
  full: "sm:max-w-[90vw]"
}
```

### Behavior
- **Backdrop Click**: Close modal (can be disabled)
- **Escape Key**: Close modal
- **Focus Trap**: Keep focus within modal
- **Scroll Lock**: Prevent body scroll when open
- **Animation**: Fade in/out with scale transform

### Accessibility
- Proper ARIA attributes for screen readers
- Focus management on open/close
- Announce modal opening to assistive technology

## Form Components

### Field Wrapper
```typescript
interface FieldProps {
  label: string;
  required?: boolean;
  error?: string;
  helper?: string;
  children: React.ReactNode;
}
```

### Validation States
- **Error**: Red border, red text, error icon
- **Success**: Green border, checkmark icon
- **Warning**: Amber border, warning icon
- **Loading**: Spinner indicator

### Error Display
- Inline errors below fields
- Form-level errors at top
- Toast notifications for submission errors

## Layout Components

### Container
```typescript
<div className="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
  Content
</div>
```

### Grid
```typescript
<div className="grid grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-3">
  Items
</div>
```

### Stack
```typescript
<div className="space-y-6">
  Items
</div>
```

### Flex
```typescript
<div className="flex items-center justify-between gap-4">
  Items
</div>
```

## Loading States

### Spinner
- Use consistent spinner across all loading states
- Size variants: `sm`, `default`, `lg`
- Color matches context (primary for buttons, gray for general)

### Skeleton
- Use for content loading states
- Match the approximate size of final content
- Animate with pulse effect

### Progress
- Use for file uploads, form submission
- Show percentage when deterministic
- Indeterminate for unknown duration

## Feedback Components

### Toast
- Use `shadcn/ui` Toast component
- Auto-dismiss after 5 seconds
- Manual dismiss option
- Stack multiple toasts

### Alert
- Inline feedback within page content
- Variants: `info`, `success`, `warning`, `error`
- Optional dismiss button
- Icon support
