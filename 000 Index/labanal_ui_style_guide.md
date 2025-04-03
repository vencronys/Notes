
# Labanal UI Style Guide

## 1. Typography

### 1.1. Fonts
- **Primary Font**: *Roboto* (sans-serif)
  - Modern, clean, and highly legible.
- **Secondary Font**: *Open Sans* (sans-serif)
  - For body text, subheadings, and general content.

### 1.2. Font Sizes

| Element          | Font Size (px) | Font Weight   | Example Usage                        |
|------------------|----------------|---------------|--------------------------------------|
| **Heading 1**    | 32px           | Bold          | Main page titles, section headers    |
| **Heading 2**    | 24px           | Semi-Bold     | Sub-sections, page titles           |
| **Heading 3**    | 18px           | Semi-Bold     | Subheadings, smaller section titles |
| **Body Text**    | 14px           | Regular       | General content, descriptions       |
| **Small Text**   | 12px           | Regular       | Footnotes, legal disclaimers        |
| **Input Labels** | 14px           | Regular       | Form labels, field descriptions     |

### 1.3. Line Heights
- **Headings**: 1.2
- **Body Text**: 1.5
- **Input Fields**: 1.4

---

## 2. Colors

### 2.1. Color Definitions

| Color Name       | Hex Code   | Usage                       |
|------------------|------------|-----------------------------|
| **Primary Blue** | #1D4ED8    | Buttons, links, highlights  |
| **Primary Green**| #10B981    | Success messages, icons     |
| **Primary Red**  | #EF4444    | Error messages, alerts      |
| **Primary Gray** | #6B7280    | Text for secondary content  |
| **Light Gray**   | #F3F4F6    | Backgrounds, borders, form fields |
| **Dark Gray**    | #1F2937    | Text (headers, labels, primary text) |
| **White**        | #FFFFFF    | Backgrounds, buttons, icons    |
| **Black**        | #000000    | Text on light backgrounds, emphasis |

### 2.2. UI Specific Colors

| Color Name     | Hex Code   | Usage                       |
|----------------|------------|-----------------------------|
| **Success**    | #10B981    | Success messages, tooltips  |
| **Warning**    | #F59E0B    | Warning messages, icons     |
| **Error**      | #EF4444    | Error messages, form errors |

### 2.3. Button States

| Button State      | Background Color | Text Color    | Border Color     |
|-------------------|------------------|---------------|------------------|
| **Normal**        | Primary Blue     | White         | Primary Blue     |
| **Hover**         | #2563EB          | White         | #2563EB          |
| **Active/Pressed**| #1E40AF          | White         | #1E40AF          |
| **Disabled**      | #D1D5DB          | Dark Gray     | #D1D5DB          |

---

## 3. Buttons and Inputs

### 3.1. Button Styles

- **Default Button**:  
  - Background Color: *Primary Blue*  
  - Text Color: *White*
  - Border Radius: 8px
  - Padding: 12px 20px
  - Font Size: 14px
  - Font Weight: Bold
  - Box Shadow: 0 4px 6px rgba(0, 0, 0, 0.1)

- **Secondary Button**:
  - Background Color: *Light Gray*
  - Text Color: *Primary Blue*
  - Border Radius: 8px
  - Padding: 12px 20px
  - Font Size: 14px
  - Font Weight: Medium
  - Box Shadow: none

- **Outline Button**:  
  - Background Color: Transparent
  - Text Color: *Primary Blue*
  - Border Color: *Primary Blue*
  - Border Radius: 8px
  - Padding: 12px 20px
  - Font Size: 14px
  - Font Weight: Medium

### 3.2. Input Fields

- **Standard Input**:  
  - Background Color: *White*
  - Border: 1px solid *Primary Gray*
  - Border Radius: 4px
  - Padding: 10px 15px
  - Font Size: 14px
  - Font Weight: Regular

- **Focused Input**:  
  - Background Color: *White*
  - Border: 1px solid *Primary Blue*
  - Border Radius: 4px
  - Padding: 10px 15px
  - Font Size: 14px
  - Font Weight: Regular

- **Disabled Input**:  
  - Background Color: *Light Gray*
  - Border: 1px solid #D1D5DB
  - Text Color: #B1B1B1
  - Padding: 10px 15px

### 3.3. Error Messages
- **Background Color**: #FEE2E2 (Light Red)
- **Text Color**: #B91C1C (Red)
- **Padding**: 10px
- **Border Radius**: 4px

---

## 4. Form Design

### 4.1. Form Layout
- **Alignment**: Left-align labels and input fields.
- **Spacing**: 16px of space between input fields and 24px between form sections.
- **Form Width**: Limit the form width to 480px on mobile, 720px on desktop.
- **Label Alignment**: Place labels above the input field.

### 4.2. Form Validation
- **Inline Validation**: Show validation messages next to or below the corresponding field.
- **Success Color**: Use *Primary Green* for valid inputs.
- **Error Color**: Use *Primary Red* for invalid inputs.

---

## 5. Icons

### 5.1. Icon Set
- **FontAwesome** icons should be used for consistency.
- Icons should be 16px in size and have the same color as text (use *Primary Gray* for normal icons, *Primary Blue* for interactive icons).

### 5.2. Usage
- **Buttons**: Place icons at the left of text in buttons (e.g., trash, edit, search).
- **Inputs**: Use small icons to indicate action (e.g., clear input, show password).

---

## 6. Spacing and Layout

### 6.1. Margins and Padding

| Element          | Margin (px)  | Padding (px)   |
|------------------|--------------|----------------|
| **Sections**     | 24px         | 16px           |
| **Input Fields** | 8px          | 12px           |
| **Buttons**      | 12px         | 12px 20px      |
| **Form Labels**  | 8px          | 0px            |

### 6.2. Border Radius
- **Buttons**: 8px
- **Input Fields**: 4px
- **Card/Panel**: 12px

---

## 7. UI States

### 7.1. Loading States
- **Spinner**: Display a simple spinner with *Primary Blue* on loading.
- **Progress Bar**: Use *Primary Blue* for loading bars with a 4px height.

### 7.2. Empty States
- **Background Color**: *Light Gray*
- **Icon**: Use an icon indicating no data (e.g., empty list icon).
- **Text**: "No records found." or a contextual message.

---

## 8. Error and Success Handling

### 8.1. Error Alerts
- **Background Color**: #FEE2E2 (Light Red)
- **Text Color**: #B91C1C (Red)
- **Icon**: Use a warning icon (e.g., exclamation mark).
- **Text**: Brief description of the error.

### 8.2. Success Alerts
- **Background Color**: #D1F8E1 (Light Green)
- **Text Color**: #047857 (Dark Green)
- **Icon**: Use a checkmark icon.
- **Text**: Description of the success.

---

## 9. Conclusion

This style guide ensures a consistent and professional UI/UX across the Labanal project, focusing on clarity, accessibility, and efficiency. Following these standards will ensure that users can easily navigate and interact with the system, improving their experience.
