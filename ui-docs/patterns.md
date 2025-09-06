# UI Patterns

## Authentication Layout

### Public Registration Layout
```typescript
structure: {
  container: "min-h-screen bg-background",
  wrapper: "flex min-h-screen",
  content: "flex flex-1 flex-col justify-center px-4 py-12 sm:px-6 lg:px-8",
  card: "mx-auto w-full max-w-md",
  header: "mb-8 text-center",
  form: "space-y-6",
  footer: "mt-8 text-center"
}
```

### Layout Structure
- **Header**: Logo, title, subtitle
- **Main**: Registration form in centered card
- **Footer**: Links to terms, privacy, support
- **Language Toggle**: Top-right corner
- **Background**: Subtle gradient or pattern

### Responsive Behavior
- Mobile: Full-width form with padding
- Desktop: Fixed-width centered card
- Maintain vertical rhythm across breakpoints

## Form Patterns

### Multi-Step Form
```typescript
structure: {
  progress: "mb-8",
  step: "space-y-6",
  navigation: "flex justify-between mt-8"
}
```

### Progress Indicator
- Step numbers with connecting lines
- Completed, current, and upcoming states
- Clickable for navigation (if validation allows)

### Field Groups
```typescript
sections: {
  personal: "Personal Information",
  hospital: "Hospital Details",
  security: "Security Settings"
}
```

### Field Layout
- **Single Column**: Mobile and narrow forms
- **Two Column**: Desktop forms with related fields grouped
- **Full Width**: Textareas, selects with many options

### Validation Pattern
- **Real-time**: Email format, password strength
- **On Blur**: Field completeness, uniqueness checks
- **On Submit**: Complete form validation
- **Server Errors**: Map to specific fields when possible

### Error Display Hierarchy
1. **Field-level**: Inline below input
2. **Section-level**: Above field group
3. **Form-level**: Top of form
4. **Page-level**: Toast notifications

## Data Display Patterns

### Table Pattern
```typescript
structure: {
  container: "overflow-hidden bg-white shadow ring-1 ring-black ring-opacity-5 md:rounded-lg",
  table: "min-w-full divide-y divide-gray-300",
  header: "bg-gray-50",
  body: "divide-y divide-gray-200 bg-white"
}
```

### Table Features
- **Sorting**: Clickable headers with indicators
- **Filtering**: Search input above table
- **Pagination**: Below table with page info
- **Loading**: Skeleton rows maintain layout
- **Empty State**: Centered message with action

### Card Grid Pattern
```typescript
structure: {
  container: "grid grid-cols-1 gap-6 sm:grid-cols-2 lg:grid-cols-3",
  card: "overflow-hidden bg-white shadow rounded-lg hover:shadow-lg transition-shadow",
  image: "aspect-video bg-gray-200",
  content: "p-6",
  actions: "px-6 py-3 bg-gray-50 border-t"
}
```

## Navigation Patterns

### Primary Navigation
```typescript
structure: {
  container: "bg-white shadow",
  wrapper: "mx-auto max-w-7xl px-4 sm:px-6 lg:px-8",
  nav: "flex justify-between h-16",
  menu: "hidden md:flex space-x-8",
  mobile: "md:hidden"
}
```

### Navigation States
- **Active**: Highlighted with primary color
- **Hover**: Subtle background change
- **Focus**: Visible outline for keyboard users
- **Disabled**: Grayed out, not clickable

### Breadcrumb Pattern
```typescript
structure: {
  container: "flex items-center space-x-2 text-sm text-gray-500",
  separator: "text-gray-300",
  current: "text-gray-900 font-medium"
}
```

## Modal Patterns

### Confirmation Modal
```typescript
structure: {
  content: "text-center",
  icon: "mb-4 text-4xl",
  title: "text-lg font-semibold mb-2",
  description: "text-gray-600 mb-6",
  actions: "flex justify-center space-x-3"
}
```

### Form Modal
```typescript
structure: {
  header: "pb-4 border-b",
  content: "py-6 space-y-4",
  footer: "pt-4 border-t flex justify-end space-x-3"
}
```

### Modal Sizes by Use Case
- **Confirmation**: Small (`sm:max-w-sm`)
- **Form**: Medium (`sm:max-w-lg`)
- **Details**: Large (`sm:max-w-2xl`)
- **Image/Content**: Extra Large (`sm:max-w-4xl`)

## Loading Patterns

### Page Loading
```typescript
structure: {
  container: "min-h-screen flex items-center justify-center",
  spinner: "text-primary-600",
  message: "mt-4 text-gray-600"
}
```

### Content Loading
- **Skeleton**: Match content structure
- **Spinner**: For shorter waits
- **Progress**: For deterministic operations

### Form Submission
- **Button Loading**: Spinner replaces text
- **Form Disabled**: All fields become read-only
- **Overlay**: Prevent interaction during submission

## Error Patterns

### Error Boundaries
```typescript
structure: {
  container: "min-h-screen flex items-center justify-center",
  content: "text-center max-w-md mx-auto",
  icon: "text-6xl text-red-500 mb-4",
  title: "text-xl font-semibold mb-2",
  description: "text-gray-600 mb-6",
  actions: "space-x-3"
}
```

### Error States
- **404**: Page not found with navigation
- **500**: Server error with retry option
- **Network**: Connection issues with retry
- **Permission**: Access denied with contact info

## Success Patterns

### Registration Success
```typescript
structure: {
  container: "text-center",
  icon: "text-6xl text-green-500 mb-4",
  title: "text-2xl font-semibold mb-2",
  description: "text-gray-600 mb-6",
  nextSteps: "bg-green-50 p-4 rounded-lg mb-6",
  actions: "space-x-3"
}
```

### Inline Success
- **Toast**: Brief confirmation
- **Banner**: Persistent confirmation
- **Checkmark**: Visual confirmation in UI

## Responsive Patterns

### Mobile-First Approach
```typescript
breakpoints: {
  mobile: "Stack vertically, full-width components",
  tablet: "Two-column layouts, larger touch targets",
  desktop: "Multi-column, hover states, keyboard shortcuts"
}
```

### Content Priority
- **Mobile**: Essential information only
- **Tablet**: Add secondary information
- **Desktop**: Full feature set with enhanced UX

### Touch Interactions
- **Minimum Size**: 44px for touch targets
- **Spacing**: Adequate space between interactive elements
- **Feedback**: Visual feedback for touch interactions

## Accessibility Patterns

### Screen Reader Support
- **Landmarks**: Proper semantic HTML
- **Headings**: Logical heading hierarchy
- **Labels**: All form inputs properly labeled
- **Descriptions**: Additional context where needed

### Keyboard Navigation
- **Tab Order**: Logical and complete
- **Focus Indicators**: Visible and high contrast
- **Shortcuts**: Common keyboard shortcuts supported
- **Escape Handlers**: Consistent escape behavior

### Color Accessibility
- **Contrast**: Meet WCAG AA standards
- **Color Independence**: Don't rely solely on color
- **Focus Indicators**: High contrast focus rings
- **Error States**: Multiple indicators (color + icon + text)

## RTL Support Patterns

### Layout Adaptation
```typescript
rtl: {
  flexDirection: "flex-row-reverse for RTL",
  textAlign: "text-start instead of text-left",
  margins: "me-4 instead of mr-4",
  icons: "Mirror directional icons"
}
```

### Content Considerations
- **Numbers**: Left-to-right even in RTL
- **Icons**: Mirror arrows, but not symbols
- **Images**: Consider cultural context
- **Forms**: Right-align labels in RTL
