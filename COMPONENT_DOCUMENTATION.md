# Tools Wonder - Component Documentation

## Overview

This document provides comprehensive documentation for all UI components, design patterns, and reusable elements used throughout the Tools Wonder platform. Each component is documented with its structure, styling, behavior, and usage examples.

## Table of Contents

1. [Design System](#design-system)
2. [Layout Components](#layout-components)
3. [Form Components](#form-components)
4. [Interactive Components](#interactive-components)
5. [Utility Components](#utility-components)
6. [Styling Guidelines](#styling-guidelines)
7. [Responsive Patterns](#responsive-patterns)
8. [Accessibility Features](#accessibility-features)

---

## Design System

### Color Palette

```css
:root {
    /* Primary Colors */
    --primary-color: #007bff;      /* Main brand blue */
    --primary-hover: #0056b3;     /* Darker blue for hover states */
    --primary-light: #e9f5ff;     /* Light blue for backgrounds */
    
    /* Secondary Colors */
    --secondary-color: #ffffff;    /* White */
    --background-color: #f8f9fa;   /* Light gray background */
    --border-color: #e5e7eb;      /* Light gray borders */
    
    /* Text Colors */
    --text-primary: #1f2937;      /* Dark gray for headings */
    --text-secondary: #4b5563;    /* Medium gray for body text */
    --text-muted: #6b7280;        /* Light gray for captions */
    
    /* Status Colors */
    --success-color: #10b981;     /* Green for success states */
    --warning-color: #f59e0b;     /* Orange for warnings */
    --error-color: #ef4444;       /* Red for errors */
    --info-color: #3b82f6;        /* Blue for information */
}
```

### Typography Scale

```css
/* Font Families */
--font-primary: 'Inter', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
--font-mono: 'Monaco', 'Menlo', 'Ubuntu Mono', monospace;

/* Font Sizes */
--text-xs: 0.75rem;     /* 12px */
--text-sm: 0.875rem;    /* 14px */
--text-base: 1rem;      /* 16px */
--text-lg: 1.125rem;    /* 18px */
--text-xl: 1.25rem;     /* 20px */
--text-2xl: 1.5rem;     /* 24px */
--text-3xl: 1.875rem;   /* 30px */
--text-4xl: 2.25rem;    /* 36px */

/* Font Weights */
--font-normal: 400;
--font-medium: 500;
--font-semibold: 600;
--font-bold: 700;
```

### Spacing System

```css
/* Spacing Scale (based on 0.25rem = 4px) */
--space-1: 0.25rem;     /* 4px */
--space-2: 0.5rem;      /* 8px */
--space-3: 0.75rem;     /* 12px */
--space-4: 1rem;        /* 16px */
--space-5: 1.25rem;     /* 20px */
--space-6: 1.5rem;      /* 24px */
--space-8: 2rem;        /* 32px */
--space-10: 2.5rem;     /* 40px */
--space-12: 3rem;       /* 48px */
--space-16: 4rem;       /* 64px */
```

---

## Layout Components

### 1. Container Component

**Purpose**: Provides consistent page width and centering across all tools.

```css
.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 var(--space-4);
}

/* Responsive variations */
@media (max-width: 768px) {
    .container {
        padding: 0 var(--space-3);
    }
}
```

**Usage**:
```html
<div class="container">
    <!-- Tool content goes here -->
</div>
```

### 2. Tool Container Component

**Purpose**: Main wrapper for individual tool interfaces.

```css
.tool-container {
    background: var(--secondary-color);
    border-radius: 15px;
    box-shadow: 0 0 20px rgba(0,0,0,0.1);
    padding: var(--space-8);
    margin: var(--space-4);
    max-width: 800px;
    width: 90%;
}

@media (max-width: 480px) {
    .tool-container {
        padding: var(--space-4);
        margin: var(--space-2);
        border-radius: 10px;
    }
}
```

**Usage**:
```html
<div class="tool-container">
    <h1 class="tool-header">Tool Name</h1>
    <!-- Tool content -->
</div>
```

### 3. Grid Layout Component

**Purpose**: Responsive grid system for tool cards and content layout.

```css
.tool-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: var(--space-6);
    margin-top: var(--space-6);
}

@media (max-width: 768px) {
    .tool-grid {
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
        gap: var(--space-4);
    }
}

@media (max-width: 480px) {
    .tool-grid {
        grid-template-columns: 1fr;
    }
}
```

### 4. Section Component

**Purpose**: Organizes content into logical sections with consistent spacing.

```css
.tool-section {
    padding: var(--space-12) 0;
    border-bottom: 1px solid var(--border-color);
}

.tool-section:last-child {
    border-bottom: none;
}

.section-heading {
    font-size: var(--text-2xl);
    font-weight: var(--font-semibold);
    color: var(--text-primary);
    margin-bottom: var(--space-2);
    display: flex;
    align-items: center;
    gap: var(--space-2);
}

.section-subheading {
    color: var(--text-secondary);
    margin-bottom: var(--space-8);
    font-size: var(--text-lg);
}
```

---

## Form Components

### 1. Input Component

**Purpose**: Standardized text input fields across all tools.

```css
.form-input {
    width: 100%;
    padding: var(--space-3) var(--space-4);
    border: 2px solid var(--border-color);
    border-radius: 8px;
    font-size: var(--text-base);
    font-family: var(--font-primary);
    transition: border-color 0.3s ease, box-shadow 0.3s ease;
    background-color: var(--secondary-color);
}

.form-input:focus {
    outline: none;
    border-color: var(--primary-color);
    box-shadow: 0 0 0 3px rgba(0, 123, 255, 0.1);
}

.form-input:disabled {
    background-color: var(--background-color);
    cursor: not-allowed;
    opacity: 0.6;
}

/* Input variants */
.form-input--error {
    border-color: var(--error-color);
}

.form-input--success {
    border-color: var(--success-color);
}
```

**Usage**:
```html
<input type="text" class="form-input" placeholder="Enter text here">
<input type="email" class="form-input form-input--error" placeholder="Email address">
```

### 2. Textarea Component

**Purpose**: Multi-line text input for longer content.

```css
.form-textarea {
    width: 100%;
    min-height: 150px;
    padding: var(--space-4);
    border: 2px solid var(--border-color);
    border-radius: 8px;
    font-family: var(--font-primary);
    font-size: var(--text-base);
    resize: vertical;
    transition: border-color 0.3s ease;
}

.form-textarea:focus {
    outline: none;
    border-color: var(--primary-color);
    box-shadow: 0 0 0 3px rgba(0, 123, 255, 0.1);
}
```

### 3. Select Component

**Purpose**: Dropdown selection input.

```css
.form-select {
    width: 100%;
    padding: var(--space-3) var(--space-4);
    border: 2px solid var(--border-color);
    border-radius: 8px;
    font-size: var(--text-base);
    background-color: var(--secondary-color);
    cursor: pointer;
    appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' fill='none' viewBox='0 0 20 20'%3E%3Cpath stroke='%236b7280' stroke-linecap='round' stroke-linejoin='round' stroke-width='1.5' d='M6 8l4 4 4-4'/%3E%3C/svg%3E");
    background-position: right var(--space-3) center;
    background-repeat: no-repeat;
    background-size: 1.5em 1.5em;
    padding-right: var(--space-10);
}

.form-select:focus {
    outline: none;
    border-color: var(--primary-color);
}
```

### 4. File Input Component

**Purpose**: Styled file upload input with drag and drop support.

```css
.file-input-wrapper {
    position: relative;
    display: inline-block;
    width: 100%;
}

.file-input {
    position: absolute;
    opacity: 0;
    width: 100%;
    height: 100%;
    cursor: pointer;
}

.file-input-label {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-height: 200px;
    border: 2px dashed var(--border-color);
    border-radius: 12px;
    background-color: var(--background-color);
    cursor: pointer;
    transition: all 0.3s ease;
    text-align: center;
    padding: var(--space-8);
}

.file-input-label:hover,
.file-input-label.drag-over {
    border-color: var(--primary-color);
    background-color: var(--primary-light);
}

.file-input-icon {
    font-size: 3rem;
    color: var(--primary-color);
    margin-bottom: var(--space-4);
}

.file-input-text {
    font-size: var(--text-lg);
    font-weight: var(--font-medium);
    color: var(--text-primary);
    margin-bottom: var(--space-2);
}

.file-input-subtext {
    font-size: var(--text-sm);
    color: var(--text-muted);
}
```

**Usage**:
```html
<div class="file-input-wrapper">
    <input type="file" id="fileInput" class="file-input" accept="image/*">
    <label for="fileInput" class="file-input-label">
        <i class="fas fa-cloud-upload-alt file-input-icon"></i>
        <span class="file-input-text">Choose File or Drag & Drop</span>
        <span class="file-input-subtext">Supports JPG, PNG, WEBP up to 10MB</span>
    </label>
</div>
```

### 5. Range Slider Component

**Purpose**: Slider input for numeric values with visual feedback.

```css
.range-slider {
    width: 100%;
    margin: var(--space-4) 0;
}

.range-input {
    width: 100%;
    height: 6px;
    border-radius: 3px;
    background: var(--border-color);
    outline: none;
    appearance: none;
}

.range-input::-webkit-slider-thumb {
    appearance: none;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    background: var(--primary-color);
    cursor: pointer;
    box-shadow: 0 2px 4px rgba(0,0,0,0.2);
}

.range-input::-moz-range-thumb {
    width: 20px;
    height: 20px;
    border-radius: 50%;
    background: var(--primary-color);
    cursor: pointer;
    border: none;
    box-shadow: 0 2px 4px rgba(0,0,0,0.2);
}

.range-label {
    display: flex;
    justify-content: space-between;
    font-size: var(--text-sm);
    color: var(--text-muted);
    margin-top: var(--space-2);
}
```

---

## Interactive Components

### 1. Button Component

**Purpose**: Primary interactive element with multiple variants and states.

```css
.btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: var(--space-3) var(--space-6);
    border: none;
    border-radius: 8px;
    font-size: var(--text-base);
    font-weight: var(--font-medium);
    font-family: var(--font-primary);
    cursor: pointer;
    transition: all 0.3s ease;
    text-decoration: none;
    gap: var(--space-2);
    min-height: 44px; /* Touch-friendly minimum */
}

/* Button Variants */
.btn--primary {
    background-color: var(--primary-color);
    color: var(--secondary-color);
}

.btn--primary:hover:not(:disabled) {
    background-color: var(--primary-hover);
    transform: translateY(-1px);
    box-shadow: 0 4px 8px rgba(0, 123, 255, 0.3);
}

.btn--secondary {
    background-color: var(--primary-light);
    color: var(--primary-color);
    border: 1px solid var(--primary-color);
}

.btn--secondary:hover:not(:disabled) {
    background-color: var(--primary-color);
    color: var(--secondary-color);
}

.btn--outline {
    background-color: transparent;
    color: var(--primary-color);
    border: 2px solid var(--primary-color);
}

.btn--outline:hover:not(:disabled) {
    background-color: var(--primary-color);
    color: var(--secondary-color);
}

.btn--danger {
    background-color: var(--error-color);
    color: var(--secondary-color);
}

.btn--success {
    background-color: var(--success-color);
    color: var(--secondary-color);
}

/* Button Sizes */
.btn--small {
    padding: var(--space-2) var(--space-4);
    font-size: var(--text-sm);
    min-height: 36px;
}

.btn--large {
    padding: var(--space-4) var(--space-8);
    font-size: var(--text-lg);
    min-height: 52px;
}

/* Button States */
.btn:disabled {
    opacity: 0.6;
    cursor: not-allowed;
    transform: none;
}

.btn--loading {
    position: relative;
    color: transparent;
}

.btn--loading::after {
    content: '';
    position: absolute;
    width: 16px;
    height: 16px;
    top: 50%;
    left: 50%;
    margin-left: -8px;
    margin-top: -8px;
    border: 2px solid transparent;
    border-top-color: currentColor;
    border-radius: 50%;
    animation: spin 1s linear infinite;
}

@keyframes spin {
    to {
        transform: rotate(360deg);
    }
}
```

**Usage**:
```html
<button class="btn btn--primary">Primary Button</button>
<button class="btn btn--secondary btn--small">Small Secondary</button>
<button class="btn btn--outline btn--loading">Loading...</button>
<button class="btn btn--danger" disabled>Disabled</button>
```

### 2. Button Group Component

**Purpose**: Groups related buttons together with consistent spacing.

```css
.btn-group {
    display: flex;
    flex-wrap: wrap;
    gap: var(--space-3);
    margin: var(--space-4) 0;
}

.btn-group--grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
    gap: var(--space-2);
}

@media (max-width: 480px) {
    .btn-group {
        flex-direction: column;
    }
    
    .btn-group--grid {
        grid-template-columns: 1fr 1fr;
    }
}
```

### 3. Tool Card Component

**Purpose**: Interactive card for displaying tool information and navigation.

```css
.tool-card {
    background-color: var(--secondary-color);
    border-radius: 12px;
    padding: var(--space-6);
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.07), 
                0 2px 4px -2px rgba(0, 0, 0, 0.05);
    transition: all 0.3s ease;
    display: flex;
    flex-direction: column;
    height: 100%;
    cursor: pointer;
    border: 1px solid transparent;
}

.tool-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 
                0 4px 6px -4px rgba(0, 0, 0, 0.05);
    border-color: var(--primary-color);
}

.tool-card-icon {
    font-size: 2.5rem;
    color: var(--primary-color);
    margin-bottom: var(--space-4);
    text-align: center;
}

.tool-card-title {
    font-size: var(--text-xl);
    font-weight: var(--font-semibold);
    color: var(--text-primary);
    margin-bottom: var(--space-2);
    text-align: center;
}

.tool-card-description {
    font-size: var(--text-base);
    color: var(--text-secondary);
    flex-grow: 1;
    margin-bottom: var(--space-4);
    text-align: center;
    line-height: 1.5;
}

.tool-card-button {
    background-color: var(--primary-light);
    color: var(--primary-color);
    padding: var(--space-3) var(--space-4);
    border-radius: 8px;
    font-weight: var(--font-medium);
    text-align: center;
    text-decoration: none;
    transition: all 0.3s ease;
    border: 1px solid transparent;
}

.tool-card-button:hover {
    background-color: var(--primary-color);
    color: var(--secondary-color);
    transform: translateY(-1px);
}
```

### 4. Tab Component

**Purpose**: Navigation between different sections or modes within a tool.

```css
.tab-container {
    margin-bottom: var(--space-6);
}

.tab-list {
    display: flex;
    border-bottom: 2px solid var(--border-color);
    margin-bottom: var(--space-6);
    overflow-x: auto;
}

.tab-button {
    background: none;
    border: none;
    padding: var(--space-4) var(--space-6);
    font-size: var(--text-base);
    font-weight: var(--font-medium);
    color: var(--text-secondary);
    cursor: pointer;
    border-bottom: 2px solid transparent;
    transition: all 0.3s ease;
    white-space: nowrap;
}

.tab-button:hover {
    color: var(--primary-color);
}

.tab-button.active {
    color: var(--primary-color);
    border-bottom-color: var(--primary-color);
}

.tab-content {
    display: none;
}

.tab-content.active {
    display: block;
    animation: fadeIn 0.3s ease;
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(10px); }
    to { opacity: 1; transform: translateY(0); }
}
```

### 5. Modal Component

**Purpose**: Overlay dialogs for confirmations, settings, or additional content.

```css
.modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1000;
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
}

.modal-overlay.active {
    opacity: 1;
    visibility: visible;
}

.modal {
    background-color: var(--secondary-color);
    border-radius: 12px;
    max-width: 500px;
    width: 90%;
    max-height: 90vh;
    overflow-y: auto;
    box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
    transform: scale(0.95) translateY(20px);
    transition: all 0.3s ease;
}

.modal-overlay.active .modal {
    transform: scale(1) translateY(0);
}

.modal-header {
    padding: var(--space-6) var(--space-6) var(--space-4);
    border-bottom: 1px solid var(--border-color);
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.modal-title {
    font-size: var(--text-xl);
    font-weight: var(--font-semibold);
    color: var(--text-primary);
}

.modal-close {
    background: none;
    border: none;
    font-size: var(--text-xl);
    color: var(--text-muted);
    cursor: pointer;
    padding: var(--space-2);
    border-radius: 4px;
    transition: color 0.3s ease;
}

.modal-close:hover {
    color: var(--text-primary);
}

.modal-body {
    padding: var(--space-6);
}

.modal-footer {
    padding: var(--space-4) var(--space-6) var(--space-6);
    border-top: 1px solid var(--border-color);
    display: flex;
    gap: var(--space-3);
    justify-content: flex-end;
}
```

---

## Utility Components

### 1. Loading Spinner Component

**Purpose**: Visual feedback for loading states.

```css
.spinner {
    display: inline-block;
    width: 20px;
    height: 20px;
    border: 2px solid var(--border-color);
    border-radius: 50%;
    border-top-color: var(--primary-color);
    animation: spin 1s linear infinite;
}

.spinner--large {
    width: 40px;
    height: 40px;
    border-width: 4px;
}

.spinner--small {
    width: 16px;
    height: 16px;
    border-width: 1px;
}

@keyframes spin {
    to {
        transform: rotate(360deg);
    }
}
```

### 2. Progress Bar Component

**Purpose**: Shows progress for file uploads and processing.

```css
.progress-bar {
    width: 100%;
    height: 8px;
    background-color: var(--border-color);
    border-radius: 4px;
    overflow: hidden;
    margin: var(--space-4) 0;
}

.progress-fill {
    height: 100%;
    background-color: var(--primary-color);
    border-radius: 4px;
    transition: width 0.3s ease;
    width: 0%;
}

.progress-text {
    font-size: var(--text-sm);
    color: var(--text-muted);
    text-align: center;
    margin-top: var(--space-2);
}
```

### 3. Notification/Toast Component

**Purpose**: Temporary messages for user feedback.

```css
.notification {
    position: fixed;
    top: var(--space-4);
    right: var(--space-4);
    background-color: var(--secondary-color);
    border-radius: 8px;
    padding: var(--space-4) var(--space-6);
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
    border-left: 4px solid var(--primary-color);
    z-index: 1000;
    max-width: 400px;
    transform: translateX(100%);
    transition: transform 0.3s ease;
}

.notification.show {
    transform: translateX(0);
}

.notification--success {
    border-left-color: var(--success-color);
}

.notification--error {
    border-left-color: var(--error-color);
}

.notification--warning {
    border-left-color: var(--warning-color);
}

.notification-title {
    font-weight: var(--font-semibold);
    color: var(--text-primary);
    margin-bottom: var(--space-1);
}

.notification-message {
    color: var(--text-secondary);
    font-size: var(--text-sm);
}
```

### 4. Tooltip Component

**Purpose**: Contextual help and information on hover.

```css
.tooltip {
    position: relative;
    display: inline-block;
}

.tooltip-content {
    visibility: hidden;
    opacity: 0;
    position: absolute;
    bottom: 125%;
    left: 50%;
    transform: translateX(-50%);
    background-color: var(--text-primary);
    color: var(--secondary-color);
    padding: var(--space-2) var(--space-3);
    border-radius: 6px;
    font-size: var(--text-sm);
    white-space: nowrap;
    z-index: 1000;
    transition: all 0.3s ease;
}

.tooltip-content::after {
    content: '';
    position: absolute;
    top: 100%;
    left: 50%;
    margin-left: -5px;
    border-width: 5px;
    border-style: solid;
    border-color: var(--text-primary) transparent transparent transparent;
}

.tooltip:hover .tooltip-content {
    visibility: visible;
    opacity: 1;
    transform: translateX(-50%) translateY(-5px);
}
```

### 5. Badge Component

**Purpose**: Small status indicators and labels.

```css
.badge {
    display: inline-flex;
    align-items: center;
    padding: var(--space-1) var(--space-2);
    font-size: var(--text-xs);
    font-weight: var(--font-medium);
    border-radius: 12px;
    text-transform: uppercase;
    letter-spacing: 0.025em;
}

.badge--primary {
    background-color: var(--primary-light);
    color: var(--primary-color);
}

.badge--success {
    background-color: #d1fae5;
    color: var(--success-color);
}

.badge--warning {
    background-color: #fef3c7;
    color: var(--warning-color);
}

.badge--error {
    background-color: #fee2e2;
    color: var(--error-color);
}

.badge--gray {
    background-color: var(--background-color);
    color: var(--text-muted);
}
```

---

## Styling Guidelines

### 1. CSS Custom Properties Usage

All components use CSS custom properties for consistent theming:

```css
/* Always use custom properties for colors */
.my-component {
    color: var(--text-primary);           /* ✅ Good */
    background-color: var(--primary-color); /* ✅ Good */
    /* color: #1f2937; */                   /* ❌ Avoid */
}

/* Use custom properties for spacing */
.my-component {
    padding: var(--space-4);              /* ✅ Good */
    margin: var(--space-2) var(--space-4); /* ✅ Good */
    /* padding: 16px; */                    /* ❌ Avoid */
}
```

### 2. BEM Naming Convention

Follow BEM (Block Element Modifier) naming for CSS classes:

```css
/* Block */
.tool-card { }

/* Element */
.tool-card__header { }
.tool-card__body { }
.tool-card__footer { }

/* Modifier */
.tool-card--featured { }
.tool-card--small { }
.tool-card__header--centered { }
```

### 3. Component State Classes

Use consistent state class naming:

```css
/* State classes */
.component.is-active { }
.component.is-disabled { }
.component.is-loading { }
.component.is-error { }
.component.is-success { }

/* Avoid */
.component.active { }
.component.disabled { }
```

### 4. Responsive Design Patterns

Use consistent breakpoints and mobile-first approach:

```css
/* Mobile first - base styles for mobile */
.component {
    font-size: var(--text-base);
    padding: var(--space-4);
}

/* Tablet and up */
@media (min-width: 768px) {
    .component {
        font-size: var(--text-lg);
        padding: var(--space-6);
    }
}

/* Desktop and up */
@media (min-width: 1024px) {
    .component {
        font-size: var(--text-xl);
        padding: var(--space-8);
    }
}
```

---

## Responsive Patterns

### 1. Breakpoint System

```css
/* Breakpoint variables */
:root {
    --breakpoint-sm: 640px;
    --breakpoint-md: 768px;
    --breakpoint-lg: 1024px;
    --breakpoint-xl: 1280px;
}

/* Usage */
@media (min-width: 768px) { /* md */ }
@media (min-width: 1024px) { /* lg */ }
```

### 2. Responsive Typography

```css
.responsive-text {
    font-size: clamp(1rem, 2.5vw, 1.5rem);
    line-height: 1.5;
}

.heading-responsive {
    font-size: clamp(1.5rem, 4vw, 2.5rem);
    line-height: 1.2;
}
```

### 3. Container Queries (Future-proofing)

```css
.tool-container {
    container-type: inline-size;
}

@container (min-width: 400px) {
    .tool-content {
        display: grid;
        grid-template-columns: 1fr 1fr;
    }
}
```

---

## Accessibility Features

### 1. Focus Management

```css
/* Focus styles for keyboard navigation */
.focusable:focus {
    outline: 2px solid var(--primary-color);
    outline-offset: 2px;
}

/* Remove default outline and add custom */
button:focus,
input:focus,
select:focus,
textarea:focus {
    outline: none;
    box-shadow: 0 0 0 3px rgba(0, 123, 255, 0.3);
}
```

### 2. Screen Reader Support

```css
/* Screen reader only text */
.sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
}

/* Show on focus for skip links */
.sr-only:focus {
    position: static;
    width: auto;
    height: auto;
    padding: var(--space-2) var(--space-4);
    margin: 0;
    overflow: visible;
    clip: auto;
    white-space: normal;
}
```

### 3. Color Contrast

Ensure all color combinations meet WCAG AA standards:

```css
/* High contrast mode support */
@media (prefers-contrast: high) {
    .component {
        border-width: 2px;
        border-color: currentColor;
    }
}

/* Reduced motion support */
@media (prefers-reduced-motion: reduce) {
    * {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
    }
}
```

### 4. ARIA Attributes

```html
<!-- Button states -->
<button aria-pressed="false" aria-describedby="help-text">Toggle</button>

<!-- Form labels -->
<label for="email-input">Email Address</label>
<input id="email-input" type="email" aria-required="true" aria-invalid="false">

<!-- Live regions for dynamic content -->
<div aria-live="polite" id="status-message"></div>

<!-- Modal dialog -->
<div role="dialog" aria-labelledby="modal-title" aria-describedby="modal-description">
    <h2 id="modal-title">Modal Title</h2>
    <p id="modal-description">Modal content...</p>
</div>
```

---

## Performance Considerations

### 1. CSS Optimization

```css
/* Use efficient selectors */
.tool-card { }                    /* ✅ Good - class selector */
#specific-element { }             /* ✅ Good - ID selector */
.parent .child { }                /* ✅ Good - descendant */
.parent > .child { }              /* ✅ Good - direct child */

/* Avoid inefficient selectors */
* { }                             /* ❌ Avoid - universal */
[attribute="value"] { }           /* ❌ Avoid - complex attribute */
.class1.class2.class3 { }         /* ❌ Avoid - multiple classes */
```

### 2. Animation Performance

```css
/* Use transform and opacity for animations */
.animated-element {
    transform: translateX(0);
    opacity: 1;
    transition: transform 0.3s ease, opacity 0.3s ease;
}

.animated-element.hidden {
    transform: translateX(-100%);
    opacity: 0;
}

/* Enable hardware acceleration */
.gpu-accelerated {
    will-change: transform;
    transform: translateZ(0);
}
```

### 3. Critical CSS

Inline critical CSS for above-the-fold content:

```html
<style>
/* Critical styles for initial page load */
.container { max-width: 1200px; margin: 0 auto; }
.tool-header { font-size: 2rem; color: #1f2937; }
</style>
```

---

## Browser Support

### Supported Browsers
- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

### Progressive Enhancement

```css
/* Base styles for all browsers */
.feature {
    background-color: var(--primary-color);
}

/* Enhanced styles for modern browsers */
@supports (display: grid) {
    .feature {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    }
}

@supports (backdrop-filter: blur(10px)) {
    .modal-overlay {
        backdrop-filter: blur(10px);
    }
}
```

---

## Component Testing

### Visual Testing Checklist

- [ ] Component renders correctly on all supported browsers
- [ ] Responsive behavior works on mobile, tablet, and desktop
- [ ] Dark mode compatibility (if applicable)
- [ ] High contrast mode support
- [ ] RTL language support (if applicable)
- [ ] Print styles (if applicable)

### Accessibility Testing

- [ ] Keyboard navigation works properly
- [ ] Screen reader compatibility
- [ ] Color contrast meets WCAG AA standards
- [ ] Focus indicators are visible
- [ ] ARIA attributes are properly implemented

### Performance Testing

- [ ] CSS file size is optimized
- [ ] Animations are smooth (60fps)
- [ ] No layout shifts during component loading
- [ ] Images are properly optimized
- [ ] Critical CSS is inlined

---

*This documentation is regularly updated. Last updated: December 2024*