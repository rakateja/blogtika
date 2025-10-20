# Reusable Custom Header

This Hugo site includes a reusable custom header that matches the TikaProcure marketing site design.

## Files Structure

```
layouts/
├── partials/
│   └── custom-header.html          # Reusable header partial
├── _default/
│   ├── baseof.html                 # Main layout using the header
│   └── page-example.html           # Example of using header in other pages
static/
└── css/
    └── custom-header.css           # Header styles
```

## Usage

### 1. In Layout Files

To include the header in any layout file:

```html
{{ partial "custom-header.html" . }}
```

### 2. Required CSS

Make sure to include the header CSS and Font Awesome:

```html
<!-- Font Awesome for icons -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">

<!-- Custom Header Styles -->
<link rel="stylesheet" href="{{ "css/custom-header.css" | relURL }}">
```

### 3. Complete Example

```html
<!DOCTYPE html>
<html lang="{{ site.Language.LanguageCode }}">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>{{ .Title }} | {{ .Site.Title }}</title>
    
    <!-- Font Awesome for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
    
    <!-- Custom Header Styles -->
    <link rel="stylesheet" href="{{ "css/custom-header.css" | relURL }}">
</head>
<body>
    {{ partial "custom-header.html" . }}
    
    <main>
        <!-- Your page content here -->
    </main>
</body>
</html>
```

## Features

- **Tika Logo**: Displays the official TikaProcure logo
- **Products Dropdown**: Hover-activated dropdown with product categories
- **Navigation Menu**: Dynamic menu from Hugo site configuration
- **Language Switcher**: Multi-language support
- **Responsive Design**: Mobile-optimized layout
- **Fixed Positioning**: Header stays at top when scrolling

## Customization

### Adding Menu Items

Add items to your `config.toml` or `config.yaml`:

```toml
[menu]
  [[menu.main]]
    name = "About"
    url = "/about"
  [[menu.main]]
    name = "Contact"
    url = "/contact"
```

### Modifying Styles

Edit `static/css/custom-header.css` to customize:
- Colors (CSS custom properties)
- Spacing and layout
- Typography
- Responsive breakpoints

### Adding New Dropdown Items

Edit `layouts/partials/custom-header.html` to modify the Products dropdown:

```html
<div class="dropdown-menu">
    <a href="#features" class="dropdown-item">Your New Product</a>
    <!-- Add more items here -->
</div>
```

## Browser Support

- Modern browsers (Chrome, Firefox, Safari, Edge)
- Mobile responsive design
- CSS Grid and Flexbox support required
