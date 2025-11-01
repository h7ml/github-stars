---
project: overtype
stars: 3221
description: The markdown editor that's just a textarea https://overtype.dev
url: https://github.com/panphora/overtype
---

OverType
========

A lightweight markdown editor library with perfect WYSIWYG alignment using an invisible textarea overlay technique. Includes optional toolbar. ~85KB minified with all features.

Live Examples
-------------

🎮 **Try it out**: Interactive demos on overtype.dev

-   Basic Editor - Minimal setup with live preview
-   With Toolbar - Full formatting toolbar
-   Multiple Instances - Several editors on one page
-   View Modes - Preview synchronization
-   Themes - Light/dark theme switching
-   All Features - Complete markdown showcase

Features
--------

-   👻 **Invisible textarea overlay** - Transparent input layer overlaid on styled preview for seamless editing
-   🎨 **Global theming** - Solar (light) and Cave (dark) themes that apply to all instances
-   ⌨️ **Keyboard shortcuts** - Common markdown shortcuts (Cmd/Ctrl+B for bold, etc.)
-   📱 **Mobile optimized** - Responsive design with mobile-specific styles
-   🔄 **DOM persistence aware** - Recovers from existing DOM (perfect for HyperClay and similar platforms)
-   🚀 **Lightweight** - ~85KB minified
-   🎯 **Optional toolbar** - Clean, minimal toolbar with all essential formatting
-   ✨ **Smart shortcuts** - Keyboard shortcuts with selection preservation
-   📝 **Smart list continuation** - GitHub-style automatic list continuation on Enter
-   🔧 **Framework agnostic** - Works with React, Vue, vanilla JS, and more

How it works
------------

We overlap an invisible textarea on top of styled output, giving the illusion of editing styled text using a plain textarea.

Comparisons
-----------

Feature

OverType

HyperMD

Milkdown

TUI Editor

EasyMDE

**Size**

~85KB

364.02 KB

344.51 KB

560.99 KB

323.69 KB

**Dependencies**

Bundled

CodeMirror

ProseMirror + plugins

Multiple libs

CodeMirror

**Setup**

Single file

Complex config

Build step required

Complex config

Moderate

**Approach**

Invisible textarea

ContentEditable

ContentEditable

ContentEditable

CodeMirror

**Mobile**

Perfect native

Issues common

Issues common

Issues common

Limited

**Markdown syntax**

Visible

Hidden

Hidden

Toggle

Visible

**Advanced features**

Basic

Full

Full

Full

Moderate

**Best for**

Simple, fast, mobile

Full WYSIWYG

Modern frameworks

Enterprise apps

Classic editing

**Choose OverType when you need:**

-   Tiny bundle size (10x smaller than alternatives)
-   Zero dependencies - single file that works immediately
-   Perfect native browser features (undo/redo, mobile keyboards, spellcheck)
-   Dead-simple integration without build tools
-   Easy to understand, modify, and extend
-   Excellent mobile support with visible markdown syntax

**Choose other editors when you need:**

-   Full WYSIWYG with hidden markdown syntax
-   Advanced features like tables, diagrams, or collaborative editing
-   Rich plugin ecosystems
-   Enterprise features and extensive customization
-   Framework-specific integration (React, Vue, etc.)
-   Complex multi-layered architecture for deep customization

Installation
------------

### NPM

npm install overtype

### CDN

<script src\="https://unpkg.com/overtype/dist/overtype.min.js"\></script\>

Quick Start
-----------

// Create a single editor
const \[editor\] \= new OverType('#editor', {
  value: '# Hello World',
  theme: 'solar'
});

// Get/set content
editor.getValue();
editor.setValue('# New Content');

// Change theme
editor.setTheme('cave');

Usage
-----

### Basic Editor

<div id\="editor" style\="height: 400px;"\></div\>

<script\>
  const \[editor\] \= new OverType('#editor', {
    placeholder: 'Start typing markdown...',
    value: '# Welcome\\n\\nStart writing \*\*markdown\*\* here!',
    onChange: (value, instance) \=> {
      console.log('Content changed:', value);
    }
  });
</script\>

### Toolbar & View Modes

// Enable the toolbar with view mode switcher
const \[editor\] \= new OverType('#editor', {
  toolbar: true,  // Enables the toolbar
  value: '# Document\\n\\nSelect text and use the toolbar buttons!'
});

// Toolbar provides:
// - Bold, Italic formatting
// - Heading levels (H1, H2, H3)
// - Links, inline code, code blocks
// - Bullet and numbered lists
// - View mode switcher (eye icon dropdown)
// - All with keyboard shortcuts!

// Three view modes available via toolbar dropdown:
// 1. Normal Edit - Default WYSIWYG markdown editing
// 2. Plain Textarea - Shows raw markdown without preview overlay
// 3. Preview Mode - Read-only rendered preview with clickable links

// Programmatically switch modes:
editor.showPlainTextarea(true);   // Switch to plain textarea mode
editor.showPreviewMode(true);     // Switch to preview mode

### Keyboard Shortcuts

The toolbar and keyboard shortcuts work together seamlessly:

-   **Cmd/Ctrl + B** - Bold
-   **Cmd/Ctrl + I** - Italic
-   **Cmd/Ctrl + K** - Insert link
-   **Cmd/Ctrl + Shift + 7** - Numbered list
-   **Cmd/Ctrl + Shift + 8** - Bullet list

All shortcuts preserve text selection, allowing you to apply multiple formats quickly.

### Multiple Editors

// Initialize multiple editors at once
const editors \= OverType.init('.markdown-editor', {
  theme: 'cave',
  fontSize: '16px'
});

// Each editor is independent
editors.forEach((editor, index) \=> {
  editor.setValue(\`# Editor ${index + 1}\`);
});

### Form Integration

// Use with form validation
const \[editor\] \= new OverType('#message', {
  placeholder: 'Your message...',
  textareaProps: {
    required: true,
    maxLength: 500,
    name: 'message'
  }
});

// The textarea will work with native form validation
document.querySelector('form').addEventListener('submit', (e) \=> {
  const content \= editor.getValue();
  // Form will automatically validate required field
});

### Custom Theme

const \[editor\] \= new OverType('#editor', {
  theme: {
    name: 'my-theme',
    colors: {
      bgPrimary: '#faf0ca',
      bgSecondary: '#ffffff',
      text: '#0d3b66',
      h1: '#f95738',
      h2: '#ee964b',
      h3: '#3d8a51',
      strong: '#ee964b',
      em: '#f95738',
      link: '#0d3b66',
      code: '#0d3b66',
      codeBg: 'rgba(244, 211, 94, 0.2)',
      blockquote: '#5a7a9b',
      hr: '#5a7a9b',
      syntaxMarker: 'rgba(13, 59, 102, 0.52)',
      cursor: '#f95738',
      selection: 'rgba(244, 211, 94, 0.4)'
    }
  }
});

### Preview & HTML Export

Generate HTML previews or export the rendered content:

const \[editor\] \= new OverType('#editor', {
  value: '# Title\\n\\n\*\*Bold\*\* text with \[links\](https://example.com)'
});

// Get the raw markdown
const markdown \= editor.getValue();
// Returns: "# Title\\n\\n\*\*Bold\*\* text with \[links\](https://example.com)"

// Get rendered HTML with syntax markers (for debugging/inspection)
const html \= editor.getRenderedHTML();
// Returns HTML with <span class="syntax-marker"> elements visible

// Get clean HTML for export (no OverType-specific markup)
const cleanHTML \= editor.getRenderedHTML({ cleanHTML: true });
// Returns clean HTML suitable for saving/exporting

// Convenience method for clean HTML
const exportHTML \= editor.getCleanHTML();
// Same as getRenderedHTML({ cleanHTML: true })

// Get the current preview element's HTML (actual DOM content)
const previewHTML \= editor.getPreviewHTML();
// Returns exactly what's shown in the editor's preview layer

// Example: Export clean HTML to server
const htmlToSave \= editor.getCleanHTML();  // No syntax markers
// Example: Clone exact preview appearance
document.getElementById('clone').innerHTML \= editor.getPreviewHTML();

### Stats Bar

Enable a built-in stats bar that shows character, word, and line counts:

// Enable stats bar on initialization
const \[editor\] \= new OverType('#editor', {
  showStats: true
});

// Show or hide stats bar dynamically
editor.showStats(true);  // Show
editor.showStats(false); // Hide

// Custom stats format
const \[editor\] \= new OverType('#editor', {
  showStats: true,
  statsFormatter: (stats) \=> {
    // stats object contains: { chars, words, lines, line, column }
    return \`<span>${stats.chars} characters</span>
            <span>${stats.words} words</span>
            <span>${stats.lines} lines</span>
            <span>Line ${stats.line}, Col ${stats.column}</span>\`;
  }
});

The stats bar automatically adapts to your theme colors using CSS variables.

### React Component

function MarkdownEditor({ value, onChange }) {
  const ref \= useRef();
  const editorRef \= useRef();
  
  useEffect(() \=> {
    const \[instance\] \= OverType.init(ref.current, {
      value,
      onChange
    });
    editorRef.current \= instance;
    
    return () \=> editorRef.current?.destroy();
  }, \[\]);
  
  useEffect(() \=> {
    if (editorRef.current && value !== editorRef.current.getValue()) {
      editorRef.current.setValue(value);
    }
  }, \[value\]);
  
  return <div ref\={ref} style\={{ height: '400px' }} />;
}

API
---

### Constructor

new OverType(target, options)

**Parameters:**

-   `target` - Selector string, Element, NodeList, or Array of elements
-   `options` - Configuration object (see below)

**Returns:** Array of OverType instances (always an array, even for single element)

### Options

{
  // Typography
  fontSize: '14px',
  lineHeight: 1.6,
  fontFamily: 'monospace',
  padding: '16px',
  
  // Theme - 'solar', 'cave', or custom theme object
  theme: 'solar',
  
  // Custom colors (override theme colors)
  colors: {
    h1: '#e63946',
    h2: '#457b9d',
    // ... any color variable
  },
  
  // Mobile styles (applied at <= 640px)
  mobile: {
    fontSize: '16px',
    padding: '12px',
    lineHeight: 1.5
  },
  
  // Behavior
  autofocus: false,
  placeholder: 'Start typing...',
  value: '',
  
  // Auto-resize
  autoResize: false,      // Auto-expand height with content
  minHeight: '100px',     // Minimum height when autoResize is enabled
  maxHeight: null,        // Maximum height (null = unlimited)
  
  // Native textarea properties
  textareaProps: {
    required: true,
    maxLength: 500,
    name: 'content',
    // Any HTML textarea attribute
  },
  
  // Toolbar
  toolbar: false,         // Enable/disable toolbar with formatting buttons
  
  // Smart lists
  smartLists: true,       // Enable GitHub-style list continuation on Enter
  
  // Stats bar
  showStats: false,       // Enable/disable stats bar
  statsFormatter: (stats) \=> {  // Custom stats format
    return \`${stats.chars} chars | ${stats.words} words\`;
  },
  
  // Callbacks
  onChange: (value, instance) \=> {},
  onKeydown: (event, instance) \=> {}
}

### Instance Methods

// Get current markdown content
editor.getValue()

// Set markdown content
editor.setValue(markdown)

// Get rendered HTML of the current content
editor.getRenderedHTML()                    // With syntax markers (for debugging)
editor.getRenderedHTML({ cleanHTML: true }) // Clean HTML without OverType markup
editor.getCleanHTML()                       // Alias for getRenderedHTML({ cleanHTML: true })

// Get the current preview element's HTML
editor.getPreviewHTML()            // Actual DOM content from preview layer

// Change theme
editor.setTheme('cave')  // Built-in theme name
editor.setTheme(customThemeObject)  // Custom theme

// View modes
editor.showPlainTextarea(true)    // Switch to plain textarea mode
editor.showPlainTextarea(false)   // Switch back to normal mode
editor.showPreviewMode(true)      // Switch to preview mode
editor.showPreviewMode(false)     // Switch back to normal mode

// Focus/blur
editor.focus()
editor.blur()

// Show or hide stats bar
editor.showStats(true)   // Show stats
editor.showStats(false)  // Hide stats

// Check if initialized
editor.isInitialized()

// Re-initialize with new options
editor.reinit(options)

// Destroy the editor
editor.destroy()

### Static Methods

// Set global theme (affects all instances)
OverType.setTheme('cave')  // Built-in theme
OverType.setTheme(customTheme)  // Custom theme object
OverType.setTheme('solar', { h1: '#custom' })  // Override specific colors

// Initialize multiple editors (same as constructor)
OverType.init(target, options)

// Get instance from element
OverType.getInstance(element)

// Destroy all instances
OverType.destroyAll()

// Access themes
OverType.themes.solar
OverType.themes.cave

Keyboard Shortcuts
------------------

Shortcut

Action

Cmd/Ctrl + B

Toggle bold

Cmd/Ctrl + I

Toggle italic

Cmd/Ctrl + K

Wrap in code

Cmd/Ctrl + Shift + K

Insert link

Cmd/Ctrl + Shift + 7

Toggle numbered list

Cmd/Ctrl + Shift + 8

Toggle bullet list

Supported Markdown
------------------

-   **Headers** - `# H1`, `## H2`, `### H3`
-   **Bold** - `**text**` or `__text__`
-   **Italic** - `*text*` or `_text_`
-   **Code** - `` `inline code` ``
-   **Links** - `[text](url)`
-   **Lists** - `- item`, `* item`, `1. item`
-   **Blockquotes** - `> quote`
-   **Horizontal rule** - `---`, `***`, or `___`

Note: Markdown syntax remains visible but styled (e.g., `**bold**` shows with styled markers).

DOM Persistence & Re-initialization
-----------------------------------

OverType is designed to work with platforms that persist DOM across page loads (like HyperClay):

// Safe to call multiple times - will recover existing editors
OverType.init('.editor');

// The library will:
// 1. Check for existing OverType DOM structure
// 2. Recover content from existing textarea if found
// 3. Re-establish event bindings
// 4. Or create fresh editor if no existing DOM

Examples
--------

Check the `examples` folder for complete examples:

-   `basic.html` - Simple single editor
-   `multiple.html` - Multiple independent editors
-   `custom-theme.html` - Theme customization
-   `dynamic.html` - Dynamic creation/destruction

Limitations
-----------

Due to the transparent textarea overlay approach, OverType has some intentional design limitations:

### Images Not Supported

Images (`![alt](url)`) are not rendered. Variable-height images would break the character alignment between textarea and preview.

### Monospace Font Required

All text must use a monospace font to maintain alignment. Variable-width fonts would cause the textarea cursor position to drift from the visual text position.

### Fixed Font Size

All content must use the same font size. Different sizes for headers or other elements would break vertical alignment.

### Visible Markdown Syntax

All markdown formatting characters remain visible (e.g., `**bold**` shows the asterisks). This is intentional - hiding them would break the 1:1 character mapping.

### Links Require Modifier Key

Links are clickable with Cmd/Ctrl+Click only. Direct clicking would interfere with text editing since clicks need to position the cursor in the textarea.

These limitations are what enable OverType's core benefits: perfect native textarea behavior, tiny size, and zero complexity.

Development
-----------

# Install dependencies
npm install

# Development build with watch
npm run dev

# Production build
npm run build

# Run tests
npm test

# Check bundle size
npm run size

Browser Support
---------------

-   Chrome 62+
-   Firefox 78+
-   Safari 16+
-   Edge (Chromium)

Requires support for:

-   CSS Custom Properties
-   ES6 features
-   Lookbehind assertions in RegExp (for italic parsing)

Architecture
------------

OverType uses a unique invisible textarea overlay approach:

1.  **Two perfectly aligned layers:**
    
    -   Invisible textarea (top) - handles input and cursor
    -   Styled preview div (bottom) - shows formatted markdown
2.  **Character-perfect alignment:**
    
    -   Monospace font required
    -   No size changes in styling
    -   Syntax markers remain visible
3.  **Single source of truth:**
    
    -   Textarea content drives everything
    -   One-way data flow: textarea → parser → preview

Contributors
------------

Special thanks to:

-   Josh Doman - Fixed inline code formatting preservation (#6), improved code fence detection (#19)
-   kbhomes - Fixed text selection desynchronization during overscroll (#17)
-   merlinz01 - Initial TypeScript definitions implementation (#20)
-   Max Bernstein - Fixed typo in website (#11)
-   davidlazar - Suggested view mode feature for toggling overlay and preview modes (#24)

License
-------

MIT

Contributing
------------

Contributions are welcome! Please feel free to submit a Pull Request.

* * *

Built with the radical idea that sometimes dumb ideas work.

* * *

**Ready for another radical idea?**  
Let's remove every layer of the web application stack.

### Hyperclay

Hyperclay by @panphora allows you to make a web app in a single, portable, self-updating, vanilla HTML file. No frameworks, no build steps, no deployment pipelines. Just a single HTML file that persists its own state and can be edited live.

Think of it as a Google Document for interactive code, where the UI, logic, and data all live in one self-modifying file. Share apps instantly, edit them directly, use them offline.
