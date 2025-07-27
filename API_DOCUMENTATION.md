# Tools Wonder - Comprehensive API Documentation

## Overview

Tools Wonder is a comprehensive web-based utility platform offering 40+ tools across 6 categories: Image Tools, Document Tools, Calculator Tools, Text Tools, Web/Developer Tools, Color Tools, SEO & Marketing Tools, and Utility Tools. Each tool is implemented as a standalone HTML page with embedded CSS and JavaScript.

## Table of Contents

1. [Project Structure](#project-structure)
2. [Core Components](#core-components)
3. [Public APIs by Category](#public-apis-by-category)
4. [Common Patterns](#common-patterns)
5. [Usage Examples](#usage-examples)
6. [Integration Guide](#integration-guide)

## Project Structure

```
/
├── index.html                    # Main landing page with tool directory
├── README.md                     # Basic project description
├── [category]-[tool].html        # Individual tool pages
└── [Additional tool files...]
```

### Main Application Entry Point

**File**: `index.html`
**Purpose**: Central hub displaying all available tools with search functionality

#### Core Functions

```javascript
function filterTools()
```
- **Purpose**: Filters tool cards based on search input
- **Parameters**: None (reads from `#toolSearch` input)
- **Returns**: void
- **Usage**: Automatically called on search input changes

---

## Public APIs by Category

## 1. Image Tools

### 1.1 Image Converter (`image-converter.html`)

#### Public Functions

```javascript
// File input event handler
fileInput.addEventListener('change', function(e))
```
- **Purpose**: Handles image file selection
- **Parameters**: `e` (Event) - File input change event
- **Returns**: void

```javascript
// Quality adjustment
qualityRange.addEventListener('input', function())
```
- **Purpose**: Updates compression quality in real-time
- **Parameters**: None
- **Returns**: void

```javascript
// Image conversion
convertBtn.addEventListener('click', async function())
```
- **Purpose**: Converts image to selected format with quality settings
- **Parameters**: None
- **Returns**: Promise<void>

#### Supported Formats
- Input: JPG, PNG, WEBP, GIF, BMP
- Output: JPG, PNG, WEBP

#### Usage Example
```html
<input type="file" id="fileInput" accept="image/*">
<select id="formatSelect">
    <option value="jpeg">JPG</option>
    <option value="png">PNG</option>
    <option value="webp">WEBP</option>
</select>
<input type="range" id="qualityRange" min="0.1" max="1" step="0.1" value="0.8">
<button id="convertBtn">Convert Image</button>
```

### 1.2 Image Compressor (`image-compresser.html`)

#### Public Functions

```javascript
async function compressImage(file, quality)
```
- **Purpose**: Compresses image file while maintaining visual quality
- **Parameters**: 
  - `file` (File) - Image file to compress
  - `quality` (number) - Compression quality (0.1-1.0)
- **Returns**: Promise<Blob> - Compressed image blob

### 1.3 Image Resizer (`image-resize.html`)

#### Public Functions

```javascript
function resizeImage(width, height, maintainAspectRatio)
```
- **Purpose**: Resizes image to specified dimensions
- **Parameters**:
  - `width` (number) - Target width in pixels
  - `height` (number) - Target height in pixels
  - `maintainAspectRatio` (boolean) - Whether to maintain aspect ratio
- **Returns**: HTMLCanvasElement - Resized image canvas

### 1.4 Image Cropper (`image-croper.html`)

#### Public Functions

```javascript
function cropImage(x, y, width, height)
```
- **Purpose**: Crops image to specified rectangular area
- **Parameters**:
  - `x` (number) - X coordinate of crop area
  - `y` (number) - Y coordinate of crop area
  - `width` (number) - Width of crop area
  - `height` (number) - Height of crop area
- **Returns**: HTMLCanvasElement - Cropped image canvas

### 1.5 Image Rotator/Flipper (`Image-rodet.html`)

#### Public Functions

```javascript
function rotateImage(degrees)
```
- **Purpose**: Rotates image by specified degrees
- **Parameters**: `degrees` (number) - Rotation angle (90, 180, 270, -90)
- **Returns**: void

```javascript
function flipImage(direction)
```
- **Purpose**: Flips image horizontally or vertically
- **Parameters**: `direction` (string) - 'horizontal' or 'vertical'
- **Returns**: void

```javascript
function resetTransformations()
```
- **Purpose**: Resets all transformations to original image
- **Parameters**: None
- **Returns**: void

### 1.6 OCR - Image to Text (`ocr.html`)

#### Public Functions

```javascript
async function performOCR(imageFile)
```
- **Purpose**: Extracts text from image using OCR
- **Parameters**: `imageFile` (File) - Image file to process
- **Returns**: Promise<string> - Extracted text

---

## 2. Document Tools

### 2.1 PDF to Word Converter (`pdf-to-word.html`)

#### Public Functions

```javascript
function handleFileUpload(file, type)
```
- **Purpose**: Handles PDF or Word file uploads
- **Parameters**:
  - `file` (File) - Document file
  - `type` (string) - 'pdf' or 'word'
- **Returns**: void

```javascript
function setupDragDrop(dropArea, inputElement)
```
- **Purpose**: Sets up drag and drop functionality for file uploads
- **Parameters**:
  - `dropArea` (HTMLElement) - Drop zone element
  - `inputElement` (HTMLInputElement) - File input element
- **Returns**: void

### 2.2 PDF Compressor (`pdf-compresser.html`)

#### Public Functions

```javascript
function handleFile(file)
```
- **Purpose**: Processes PDF file for compression
- **Parameters**: `file` (File) - PDF file to compress
- **Returns**: void

```javascript
function formatFileSize(bytes)
```
- **Purpose**: Formats file size in human-readable format
- **Parameters**: `bytes` (number) - File size in bytes
- **Returns**: string - Formatted size (e.g., "2.5 MB")

```javascript
function calculateReduction(originalSize, compressedSize)
```
- **Purpose**: Calculates compression percentage
- **Parameters**:
  - `originalSize` (number) - Original file size
  - `compressedSize` (number) - Compressed file size
- **Returns**: number - Reduction percentage

### 2.3 Electronic Signature (`esigneture.html`)

#### Public Functions

```javascript
function startDrawing(e)
```
- **Purpose**: Initiates signature drawing
- **Parameters**: `e` (Event) - Mouse/touch event
- **Returns**: void

```javascript
function draw(e)
```
- **Purpose**: Draws signature stroke
- **Parameters**: `e` (Event) - Mouse/touch move event
- **Returns**: void

```javascript
function endDrawing()
```
- **Purpose**: Ends signature drawing
- **Parameters**: None
- **Returns**: void

```javascript
function clearSignature()
```
- **Purpose**: Clears the signature canvas
- **Parameters**: None
- **Returns**: void

---

## 3. Calculator Tools

### 3.1 Scientific Calculator (`scientific-calculator.html`)

#### Public Functions

```javascript
function addNumber(num)
```
- **Purpose**: Adds number to current calculation
- **Parameters**: `num` (string) - Number to add
- **Returns**: void

```javascript
function addOperation(op)
```
- **Purpose**: Adds mathematical operation
- **Parameters**: `op` (string) - Operation symbol (+, -, *, /, ^, sin, cos, etc.)
- **Returns**: void

```javascript
function calculate()
```
- **Purpose**: Evaluates the mathematical expression
- **Parameters**: None
- **Returns**: void

```javascript
function clearDisplay()
```
- **Purpose**: Clears calculator display and history
- **Parameters**: None
- **Returns**: void

```javascript
function factorial(n)
```
- **Purpose**: Calculates factorial of a number
- **Parameters**: `n` (number) - Number to calculate factorial for
- **Returns**: number - Factorial result

#### Supported Operations
- Basic: +, -, *, /, %
- Scientific: sin, cos, tan, log, ln, √, ^, π, e
- Advanced: factorial (!), parentheses, degree conversion

### 3.2 Age Calculator (`age-Calculator.html`)

#### Public Functions

```javascript
function calculateAge(birthDate)
```
- **Purpose**: Calculates age based on birth date
- **Parameters**: `birthDate` (Date) - Date of birth
- **Returns**: Object - Age breakdown (years, months, days)

### 3.3 BMI Calculator (`bmi-caculator.html`)

#### Public Functions

```javascript
function calculateBMI(weight, height, unit)
```
- **Purpose**: Calculates Body Mass Index
- **Parameters**:
  - `weight` (number) - Body weight
  - `height` (number) - Body height
  - `unit` (string) - 'metric' or 'imperial'
- **Returns**: Object - BMI value and category

### 3.4 Loan EMI Calculator (`loan.html`)

#### Public Functions

```javascript
function calculateEMI(principal, rate, tenure)
```
- **Purpose**: Calculates Equated Monthly Installment
- **Parameters**:
  - `principal` (number) - Loan amount
  - `rate` (number) - Interest rate per annum
  - `tenure` (number) - Loan tenure in months
- **Returns**: Object - EMI, total amount, total interest

### 3.5 Currency Converter (`curence.html`)

#### Public Functions

```javascript
async function convertCurrency(amount, fromCurrency, toCurrency)
```
- **Purpose**: Converts amount between currencies
- **Parameters**:
  - `amount` (number) - Amount to convert
  - `fromCurrency` (string) - Source currency code
  - `toCurrency` (string) - Target currency code
- **Returns**: Promise<number> - Converted amount

---

## 4. Text Tools

### 4.1 Text Case Converter (`text-case-change.html`)

#### Public Functions

```javascript
function convertCase(type)
```
- **Purpose**: Converts text case according to specified type
- **Parameters**: `type` (string) - Case type ('upper', 'lower', 'title', 'sentence', 'inverse', 'capitalize')
- **Returns**: void

#### Supported Case Types
- `'upper'`: UPPERCASE
- `'lower'`: lowercase
- `'title'`: Title Case
- `'sentence'`: Sentence case
- `'inverse'`: iNVERSE cASE
- `'capitalize'`: Capitalize Words

#### Usage Example
```javascript
// Convert text to uppercase
convertCase('upper');

// Convert text to title case
convertCase('title');
```

### 4.2 Word Counter (`word-counter.html`)

#### Public Functions

```javascript
function updateCount()
```
- **Purpose**: Updates word, character, and paragraph counts
- **Parameters**: None (reads from text input)
- **Returns**: void

```javascript
function generateChart(words, chars, charsNoSpace)
```
- **Purpose**: Generates visual chart of text statistics
- **Parameters**:
  - `words` (number) - Word count
  - `chars` (number) - Character count with spaces
  - `charsNoSpace` (number) - Character count without spaces
- **Returns**: void

### 4.3 Text Reverser (`text-revers.html`)

#### Public Functions

```javascript
function reverseText(mode)
```
- **Purpose**: Reverses text according to specified mode
- **Parameters**: `mode` (string) - Reverse mode ('characters', 'words', 'lines')
- **Returns**: void

### 4.4 Text Sorter (`text-sorter.html`)

#### Public Functions

```javascript
function sortText(order, type)
```
- **Purpose**: Sorts text lines
- **Parameters**:
  - `order` (string) - 'asc' or 'desc'
  - `type` (string) - 'alphabetical' or 'numerical'
- **Returns**: void

### 4.5 Text Encryptor/Decryptor (`text-encreptor.html`)

#### Public Functions

```javascript
function encryptText(text, method, key)
```
- **Purpose**: Encrypts text using specified method
- **Parameters**:
  - `text` (string) - Text to encrypt
  - `method` (string) - Encryption method
  - `key` (string) - Encryption key
- **Returns**: string - Encrypted text

```javascript
function decryptText(text, method, key)
```
- **Purpose**: Decrypts text using specified method
- **Parameters**:
  - `text` (string) - Text to decrypt
  - `method` (string) - Decryption method
  - `key` (string) - Decryption key
- **Returns**: string - Decrypted text

---

## 5. Web/Developer Tools

### 5.1 Color Picker & Converter (`colorpiker.html`)

#### Public Functions

```javascript
function hexToRgb(hex)
```
- **Purpose**: Converts HEX color to RGB
- **Parameters**: `hex` (string) - HEX color code
- **Returns**: Object - RGB values {r, g, b}

```javascript
function rgbToHex(r, g, b)
```
- **Purpose**: Converts RGB color to HEX
- **Parameters**:
  - `r` (number) - Red value (0-255)
  - `g` (number) - Green value (0-255)
  - `b` (number) - Blue value (0-255)
- **Returns**: string - HEX color code

```javascript
function updateColorPreview(color)
```
- **Purpose**: Updates color preview display
- **Parameters**: `color` (string) - Color value in any format
- **Returns**: void

### 5.2 JSON Formatter & Validator (`jonson.html`)

#### Public Functions

```javascript
function formatJSON(jsonString)
```
- **Purpose**: Formats and beautifies JSON string
- **Parameters**: `jsonString` (string) - Raw JSON string
- **Returns**: string - Formatted JSON

```javascript
function validateJSON(jsonString)
```
- **Purpose**: Validates JSON syntax
- **Parameters**: `jsonString` (string) - JSON string to validate
- **Returns**: Object - Validation result {valid: boolean, error: string}

### 5.3 Base64 Encoder/Decoder (`decoder.html`)

#### Public Functions

```javascript
function encodeBase64(text)
```
- **Purpose**: Encodes text to Base64
- **Parameters**: `text` (string) - Text to encode
- **Returns**: string - Base64 encoded string

```javascript
function decodeBase64(base64)
```
- **Purpose**: Decodes Base64 string to text
- **Parameters**: `base64` (string) - Base64 string to decode
- **Returns**: string - Decoded text

### 5.4 URL Encoder/Decoder (`url-encoder.html`)

#### Public Functions

```javascript
function encodeURL(url)
```
- **Purpose**: URL encodes a string
- **Parameters**: `url` (string) - String to encode
- **Returns**: string - URL encoded string

```javascript
function decodeURL(encodedUrl)
```
- **Purpose**: URL decodes a string
- **Parameters**: `encodedUrl` (string) - URL encoded string
- **Returns**: string - Decoded string

### 5.5 HTML Minifier (`html-minifire.html`)

#### Public Functions

```javascript
function minifyHTML(html)
```
- **Purpose**: Minifies HTML code
- **Parameters**: `html` (string) - HTML code to minify
- **Returns**: string - Minified HTML

```javascript
function minifyCSS(css)
```
- **Purpose**: Minifies CSS code
- **Parameters**: `css` (string) - CSS code to minify
- **Returns**: string - Minified CSS

```javascript
function minifyJS(js)
```
- **Purpose**: Minifies JavaScript code
- **Parameters**: `js` (string) - JavaScript code to minify
- **Returns**: string - Minified JavaScript

### 5.6 Regex Tester (`regestexter.html`)

#### Public Functions

```javascript
function testRegex(pattern, text, flags)
```
- **Purpose**: Tests regular expression against text
- **Parameters**:
  - `pattern` (string) - Regular expression pattern
  - `text` (string) - Text to test against
  - `flags` (string) - Regex flags (g, i, m, etc.)
- **Returns**: Object - Test results {matches: Array, isValid: boolean}

---

## 6. Color Tools

### 6.1 RGB to HEX Converter (`rgb-to-hex.html`)

#### Public Functions

```javascript
function hexToRgb(hex)
```
- **Purpose**: Converts HEX to RGB values
- **Parameters**: `hex` (string) - HEX color code
- **Returns**: Object - {r, g, b} values

```javascript
function rgbToHex(r, g, b)
```
- **Purpose**: Converts RGB to HEX
- **Parameters**: RGB values (0-255)
- **Returns**: string - HEX color code

### 6.2 Gradient Generator (`gradient.html`)

#### Public Functions

```javascript
function updateGradient()
```
- **Purpose**: Updates gradient preview based on current settings
- **Parameters**: None
- **Returns**: void

```javascript
function addColorStop()
```
- **Purpose**: Adds new color stop to gradient
- **Parameters**: None
- **Returns**: void

```javascript
function copyCSS()
```
- **Purpose**: Copies generated CSS gradient code to clipboard
- **Parameters**: None
- **Returns**: void

### 6.3 Palette Generator (`paletor.html`)

#### Public Functions

```javascript
function generatePalette()
```
- **Purpose**: Generates color palette based on base color
- **Parameters**: None (reads from color input)
- **Returns**: void

```javascript
function generateHarmonicColors(baseColor)
```
- **Purpose**: Generates harmonious colors from base color
- **Parameters**: `baseColor` (string) - Base color in HEX format
- **Returns**: Array<string> - Array of harmonic colors

```javascript
function hexToHSL(hex)
```
- **Purpose**: Converts HEX color to HSL
- **Parameters**: `hex` (string) - HEX color code
- **Returns**: Object - {h, s, l} values

```javascript
function HSLToHex(h, s, l)
```
- **Purpose**: Converts HSL to HEX color
- **Parameters**: HSL values
- **Returns**: string - HEX color code

### 6.4 Contrast Checker (`constrst.html`)

#### Public Functions

```javascript
function checkContrast(color1, color2)
```
- **Purpose**: Checks color contrast ratio for accessibility
- **Parameters**:
  - `color1` (string) - First color
  - `color2` (string) - Second color
- **Returns**: Object - Contrast ratio and WCAG compliance

---

## 7. Utility Tools

### 7.1 QR Code Generator (`qr-genaretor.html`)

#### Public Functions

```javascript
function generateQR()
```
- **Purpose**: Generates QR code from text input
- **Parameters**: None (reads from text input)
- **Returns**: void

```javascript
function startScan()
```
- **Purpose**: Starts QR code scanning using camera
- **Parameters**: None
- **Returns**: void

### 7.2 UUID Generator (`uddi.html`)

#### Public Functions

```javascript
function generateUUIDs()
```
- **Purpose**: Generates multiple UUIDs
- **Parameters**: None (reads count from input)
- **Returns**: void

```javascript
function copyToClipboard(text)
```
- **Purpose**: Copies text to clipboard
- **Parameters**: `text` (string) - Text to copy
- **Returns**: void

### 7.3 Unit Converter (`unit-convater.html`)

#### Public Functions

```javascript
function convertUnits(value, fromUnit, toUnit, category)
```
- **Purpose**: Converts between different units
- **Parameters**:
  - `value` (number) - Value to convert
  - `fromUnit` (string) - Source unit
  - `toUnit` (string) - Target unit
  - `category` (string) - Unit category (length, weight, etc.)
- **Returns**: number - Converted value

### 7.4 Time Zone Converter (`timezone-vonvater.html`)

#### Public Functions

```javascript
function convertTime()
```
- **Purpose**: Converts time between time zones
- **Parameters**: None (reads from form inputs)
- **Returns**: void

### 7.5 Random Generator (`randon-genaretor.html`)

#### Public Functions

```javascript
function generateRandomNumber(min, max)
```
- **Purpose**: Generates random number in range
- **Parameters**:
  - `min` (number) - Minimum value
  - `max` (number) - Maximum value
- **Returns**: number - Random number

```javascript
function generatePassword(length, options)
```
- **Purpose**: Generates secure password
- **Parameters**:
  - `length` (number) - Password length
  - `options` (Object) - Password options (uppercase, lowercase, numbers, symbols)
- **Returns**: string - Generated password

---

## Common Patterns

### File Download Pattern

Most tools implement a common download pattern using html2canvas:

```javascript
function downloadResult() {
    html2canvas(document.querySelector("#previewArea")).then(canvas => {
        const link = document.createElement('a');
        link.download = 'result.png';
        link.href = canvas.toDataURL('image/png', 0.8);
        link.click();
    });
}
```

### Copy to Clipboard Pattern

```javascript
function copyToClipboard(text) {
    navigator.clipboard.writeText(text).then(() => {
        showNotification('Copied to clipboard!');
    });
}
```

### File Input Handler Pattern

```javascript
fileInput.addEventListener('change', function(e) {
    const file = e.target.files[0];
    if (file) {
        const reader = new FileReader();
        reader.onload = function(event) {
            // Process file data
        };
        reader.readAsDataURL(file);
    }
});
```

### Notification System

```javascript
function showNotification(message) {
    // Create and show notification
    const notification = document.createElement('div');
    notification.textContent = message;
    notification.className = 'notification';
    document.body.appendChild(notification);
    
    setTimeout(() => {
        notification.remove();
    }, 3000);
}
```

---

## Usage Examples

### Basic Tool Usage

```html
<!-- Include tool in your page -->
<iframe src="text-case-change.html" width="100%" height="600px"></iframe>

<!-- Or embed specific functionality -->
<script>
// Convert text to uppercase
function convertTextToUpper(text) {
    return text.toUpperCase();
}
</script>
```

### Integration with External APIs

```javascript
// Example: Integrating currency converter with external API
async function getCurrencyRates() {
    const response = await fetch('https://api.exchangerate-api.com/v4/latest/USD');
    return await response.json();
}

// Use with currency converter
async function convertWithLiveRates(amount, from, to) {
    const rates = await getCurrencyRates();
    const rate = rates.rates[to] / rates.rates[from];
    return amount * rate;
}
```

### Custom Styling

```css
/* Override default tool styles */
.tool-container {
    --primary-color: #your-brand-color;
    --secondary-color: #your-secondary-color;
}

/* Responsive adjustments */
@media (max-width: 768px) {
    .tool-container {
        padding: 1rem;
    }
}
```

---

## Integration Guide

### Embedding Individual Tools

1. **Direct Embedding**: Use iframe to embed complete tools
2. **Function Extraction**: Extract specific functions for custom implementations
3. **API Integration**: Connect tools with external services

### Customization Options

1. **Styling**: Override CSS variables for brand consistency
2. **Functionality**: Modify JavaScript functions for specific requirements
3. **UI/UX**: Adapt interface elements to match your application

### Security Considerations

1. **Input Validation**: All user inputs should be validated
2. **File Processing**: Implement proper file type and size restrictions
3. **XSS Prevention**: Sanitize all user-generated content

### Performance Optimization

1. **Lazy Loading**: Load tools only when needed
2. **Code Splitting**: Separate common utilities from tool-specific code
3. **Caching**: Implement appropriate caching strategies

---

## Browser Compatibility

- **Modern Browsers**: Full support for Chrome 80+, Firefox 75+, Safari 13+, Edge 80+
- **Required APIs**: Canvas API, File API, Clipboard API, Web Workers (for some tools)
- **Fallbacks**: Graceful degradation for unsupported features

---

## Contributing

To add new tools or modify existing ones:

1. Follow the established HTML structure pattern
2. Use consistent CSS variable naming
3. Implement common function patterns (download, copy, etc.)
4. Add comprehensive error handling
5. Update this documentation with new APIs

---

## License

This project is open source. Please refer to the LICENSE file for details.

---

*Last Updated: December 2024*