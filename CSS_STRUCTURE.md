# CSS Structure Documentation

## Overview
The CSS has been reorganized for better maintainability, removing duplicates and creating a clear hierarchy.

## File Structure

### 1. `css/base.css` - Foundation Styles
**Purpose**: Contains fonts, common elements, and base styles used across all pages
**Contents**:
- Vodafone font declarations (@font-face)
- Icon font (icomoon)
- Base reset and typography
- Common button styles (.modern-btn)
- Back button styles
- Common logo and page title styles
- Footer link styles
- Utility classes (.text-center, .hidden, etc.)
- Responsive image styles

### 2. `css/index.css` - Index Page Specific
**Purpose**: Styles specific to the main landing page (index.html)
**Contents**:
- Layout styles (body, container)
- Logo positioning
- Typography (title, subtitle with .title-large variant)
- QR section styles
- Main button and text button styles
- Desktop/mobile visibility controls
- Footer and icons
- Responsive breakpoints (768px, 480px, 900px)

### 3. `css/modal.css` - Modal Functionality
**Purpose**: All modal-related styles separated for clarity
**Contents**:
- Modal overlay and container
- Modal close button
- Modal content styling
- Steps and FAQ styling within modals
- Typography within modals
- Footer links within modals
- Responsive modal behavior
- Mobile/tablet modal hiding

### 4. Page-Specific CSS Files
**Cleaned up to remove duplicates**:
- `css/term-of-use.css` - Term of use page styles
- `css/privacy-policy.css` - Privacy policy page styles  
- `css/faq.css` - FAQ page styles
- `css/how-can-i-use.css` - How to use page styles
- `css/accordion.css` - Accordion component styles

### 5. `css/styles.css` - Legacy Bootstrap
**Status**: Contains Bootstrap and legacy styles
**Note**: This file is large (1059 lines) and contains Bootstrap framework. Consider whether all of it is needed.

## Implementation Order

### HTML Pages Should Load CSS In This Order:
```html
<link rel="stylesheet" href="css/base.css" />
<link rel="stylesheet" href="css/[page-specific].css" />
<link rel="stylesheet" href="css/modal.css" /> <!-- Only if page uses modals -->
```

### Example for index.html:
```html
<link rel="stylesheet" href="css/base.css" />
<link rel="stylesheet" href="css/index.css" />
<link rel="stylesheet" href="css/modal.css" />
```

## Benefits of New Structure

1. **No Duplicate Font Declarations**: All fonts declared once in base.css
2. **Clear Separation of Concerns**: Each file has a specific purpose
3. **Easier Maintenance**: Changes to common elements only need to be made in one place
4. **Better Performance**: Smaller, focused CSS files
5. **No Inline Styles**: All styles moved to external files
6. **Consistent Naming**: Clear, semantic class names
7. **Responsive Design**: Organized media queries

## Key Classes

### Visibility Controls
- `.desktop-only` - Show only on desktop (>900px)
- `.mobile-only` - Show only on mobile/tablet (≤900px)

### Typography
- `.title` - Standard title styling
- `.title-large` - Larger title variant (42px)
- `.page-title` - Common page title styling

### Buttons
- `.main-button` - Primary action buttons
- `.text-button` - Text-style buttons for mobile
- `.modern-btn` - Common button styling
- `.back-button` - Navigation back button

### Layout
- `.content-container` - Common container with max-width
- `.img-responsive` - Responsive images

## Migration Notes

1. **Removed from index.html**: ~200 lines of inline CSS
2. **Font Declarations**: Consolidated from 5 files to 1 (base.css)
3. **Modal Styles**: Separated into dedicated file
4. **Common Styles**: Moved to base.css for reuse

## Future Improvements

1. **Audit styles.css**: Determine if all Bootstrap components are needed
2. **CSS Variables**: Consider using CSS custom properties for colors and spacing
3. **Component Library**: Further organize into component-based CSS files
4. **Build Process**: Consider CSS preprocessing (Sass/Less) for variables and mixins

## Breakpoints

- **Mobile**: ≤480px
- **Tablet**: ≤768px  
- **Desktop/Modal**: >900px
- **Short Screens**: ≤700px height 