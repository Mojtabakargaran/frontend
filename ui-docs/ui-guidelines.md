# UI Guidelines

## Typography

### Font Family
- Primary: `Inter` (system fallback: `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto`)
- Monospace: `"JetBrains Mono", Consolas, monospace`

### Text Hierarchy
- **Display**: `text-4xl md:text-5xl` (36-48px) - Hero sections
- **Heading 1**: `text-3xl md:text-4xl` (30-36px) - Page titles
- **Heading 2**: `text-2xl md:text-3xl` (24-30px) - Section headers
- **Heading 3**: `text-xl md:text-2xl` (20-24px) - Subsections
- **Body Large**: `text-lg` (18px) - Important content
- **Body**: `text-base` (16px) - Default text
- **Body Small**: `text-sm` (14px) - Secondary information
- **Caption**: `text-xs` (12px) - Labels, metadata

### Font Weights
- Light: `font-light` (300)
- Regular: `font-normal` (400)
- Medium: `font-medium` (500)
- Semibold: `font-semibold` (600)
- Bold: `font-bold` (700)

## Layout

### Container & Spacing
- **Max Width**: `max-w-7xl` (1280px) for main content
- **Responsive Padding**: `px-4 sm:px-6 lg:px-8`
- **Section Spacing**: `py-12 md:py-16 lg:py-20`
- **Content Spacing**: `space-y-6 md:space-y-8`

### Grid System
- **Columns**: Use CSS Grid with `grid-cols-1 md:grid-cols-2 lg:grid-cols-3`
- **Gaps**: `gap-4 md:gap-6 lg:gap-8`
- **Form Layout**: `grid-cols-1 md:grid-cols-2` for form fields

### Breakpoints (Tailwind defaults)
- **sm**: 640px
- **md**: 768px
- **lg**: 1024px
- **xl**: 1280px
- **2xl**: 1536px

## Color Usage

### Semantic Colors
- **Primary Actions**: Use `primary-600` for buttons, links
- **Secondary Actions**: Use `secondary-400` with `text-gray-800`
- **Success**: `emerald-500` for confirmations, success states
- **Warning**: `amber-500` for warnings, pending states
- **Error**: `red-500` for errors, destructive actions
- **Info**: `blue-500` for informational messages

### Text Colors
- **Primary Text**: `text-gray-900`
- **Secondary Text**: `text-gray-600`
- **Muted Text**: `text-gray-500`
- **Placeholder**: `text-gray-400`
- **Disabled**: `text-gray-300`

### Background Usage
- **Page Background**: `bg-background`
- **Card Background**: `bg-white`
- **Input Background**: `bg-white` with `border-gray-300`
- **Hover States**: `hover:bg-gray-50`
- **Active States**: `bg-primary-50`

## Interaction Rules

### Hover Effects
- **Buttons**: Scale `hover:scale-105` or background color change
- **Cards**: Elevation increase `hover:shadow-lg`
- **Links**: Underline `hover:underline` or color change

### Focus States
- **All Interactive Elements**: `focus:outline-none focus:ring-2 focus:ring-primary-500 focus:ring-offset-2`
- **Form Fields**: `focus:border-primary-500 focus:ring-primary-500`

### Transitions
- **Default**: `transition-colors duration-200`
- **Transform**: `transition-transform duration-200`
- **Shadow**: `transition-shadow duration-200`

### Loading States
- **Buttons**: Show spinner with `disabled` state
- **Forms**: Disable all fields during submission
- **Data**: Use skeleton loaders for content areas

## Accessibility

### ARIA Requirements
- Form fields must have proper labels and descriptions
- Interactive elements need appropriate ARIA roles
- Error states require `aria-invalid` and `aria-describedby`

### Keyboard Navigation
- Tab order must be logical and complete
- All interactive elements must be keyboard accessible
- Modal dialogs must trap focus

### Color Contrast
- Text must meet WCAG AA standards (4.5:1 ratio)
- Interactive elements need 3:1 contrast ratio
- Never rely solely on color to convey information

## Responsive Design

### Mobile-First Approach
- Design for mobile (`320px+`) first
- Progressive enhancement for larger screens
- Touch targets minimum `44x44px`

### Content Strategy
- Prioritize critical information on mobile
- Use collapsible sections for secondary content
- Implement responsive navigation patterns

### Performance
- Optimize images with Next.js Image component
- Lazy load non-critical content
- Minimize layout shifts (CLS)

## RTL Support

### Layout Considerations
- Use logical properties (`ms-*` instead of `ml-*`)
- Flip layouts automatically with `dir="rtl"`
- Icons and images may need mirroring

### Text Direction
- Apply `dir` attribute at component level
- Use `text-start` instead of `text-left`
- Consider reading patterns in RTL languages
