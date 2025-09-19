# Accessibility Issues in IndiaFOSS Blog Page

This document lists and explains the accessibility issues intentionally introduced into the IndiaFOSS blog page for accessibility testing and workshop purposes. The issues are categorized based on the **POUR** principles: **Perceivable, Operable, Understandable, and Robust**.

---

## 1. Missing `lang` Attribute on `<html>` Tag  
**Principle:** Perceivable  
- The root `<html>` element lacks a `lang` attribute.  
- Screen readers cannot determine the page language, leading to incorrect pronunciation or accent.  
- **Impact:** Reduced comprehension for assistive technology users.

---

## 2. Low Contrast Navigation Links  
**Principle:** Perceivable  
- Navigation links use muted colors (#6b7280 on #f3f4f6) with insufficient contrast.  
- Fails WCAG minimum contrast ratio (4.5:1 for normal text).  
- **Impact:** Users with low vision or color blindness may have trouble distinguishing links.

---

## 3. Image Without `alt` Attribute  
**Principle:** Perceivable  
- The main cover image has no `alt` attribute.  
- Screen readers skip the image without any description.  
- **Impact:** Loss of important visual context for non-sighted users.

---

## 4. Ambiguous Date Format  
**Principle:** Perceivable  
- Date shown as “09/19/25” without clear format or century.  
- Date formats differ internationally (e.g., MM/DD/YY vs DD/MM/YY).  
- **Impact:** Users may misinterpret the publication date.

---

## 5. Removed Focus Outlines on Interactive Elements  
**Principle:** Operable  
- CSS disables default focus outlines on links and buttons (`outline: none`).  
- Keyboard users lose visible focus indication.  
- **Impact:** Difficult keyboard navigation, reduced usability.

---

## 6. Clickable `<div>` Without Keyboard Support or ARIA Role  
**Principle:** Operable  
- Subscription box is a clickable `<div>` with `onclick` but no `tabindex`, `role="button"`, or keyboard event handlers.  
- **Impact:** Keyboard users cannot focus or activate this element.

---

## 7. `<span>` Used as a Button Without Role or Keyboard Support  
**Principle:** Operable  
- “Share” button implemented as a styled `<span>` without semantic meaning or keyboard support.  
- **Impact:** Screen readers and keyboard users cannot interact properly.

---

## 8. Form Inputs Without Associated Labels  
**Principle:** Perceivable & Understandable  
- Email input and submit button use placeholders only, no `<label>` elements.  
- Placeholders are not accessible substitutes for labels.  
- **Impact:** Screen reader users may not understand the form field purposes.

---

## 9. Heading Structure Skips `<h1>` Inside `<article>`  
**Principle:** Understandable  
- Article heading starts with `<h2>`, no `<h1>` present inside the article.  
- Disrupts heading hierarchy and navigation.  
- **Impact:** Screen reader users may get confused or lose content context.

---

## 10. Non-descriptive Link Text ("here")  
**Principle:** Understandable  
- Link text “here” does not describe link destination or purpose.  
- **Impact:** Screen reader and keyboard users cannot predict link function.

---

## 11. Decorative Images with Missing or Empty `alt` Attributes  
**Principle:** Perceivable  
- Decorative icon images have no or empty `alt` attributes.  
- Screen readers may announce meaningless content or skip images.  
- **Impact:** Confusion or loss of decorative context.

---

## 12. No Landmark Roles (`<main>`, `<footer>`)  
**Principle:** Robust  
- Missing semantic landmarks such as `<main>` or ARIA roles on footer.  
- **Impact:** Assistive tech users cannot quickly jump to key page sections.

---

## 13. Unlabeled Lists Without Descriptions or ARIA Labels  
**Principle:** Understandable  
- Lists (e.g., open source licenses) lack accessible names or context.  
- **Impact:** Users may not understand the purpose or content of lists.

---

## 14. Clickable Elements Missing Keyboard Event Listeners  
**Principle:** Operable  
- Clickable divs and spans react only to mouse clicks (`onclick`), not keyboard keys.  
- **Impact:** Keyboard-only users cannot activate these elements.

---

## 15. No Visible Focus Indicator for Keyboard Navigation  
**Principle:** Operable  
- Focus outlines are globally removed, making it hard to see focus state.  
- **Impact:** Keyboard users lose visual navigation cues.

---

## 16. No ARIA or Semantic Roles on Interactive Non-semantic Elements  
**Principle:** Robust  
- Interactive custom elements lack ARIA roles and states.  
- **Impact:** Assistive technologies cannot identify or communicate their purpose.

---

## 17. Lack of Error or Validation Feedback in Form  
**Principle:** Understandable  
- Form has no feedback messages or instructions.  
- **Impact:** Users may be confused about input errors or submission status.

---

## 18. Ambiguous Color Choices Causing Low Contrast in Text  
**Principle:** Perceivable  
- Body text uses medium gray (#555555, #4b5563) that may fail contrast guidelines.  
- **Impact:** Reduced readability for users with visual impairments.

---

## 19. Lack of Keyboard Focus on Form Fields and Buttons  
**Principle:** Operable  
- Inputs and buttons can be focused but have no visible focus styling due to removed outlines.  
- **Impact:** Keyboard users may lose track when filling out forms.

---

## 20. No Instructions for Using the Form or Subscription Widget  
**Principle:** Understandable  
- No guidance or instructions for interacting with form or subscription box.  
- **Impact:** Users may be unsure how to use these controls.

---

# Summary Table of Accessibility Issues

| Issue                                   | Principle           | User Impact                                    |
|----------------------------------------|---------------------|-----------------------------------------------|
| Missing `lang` attribute                | Perceivable         | Incorrect language for screen readers         |
| Low contrast nav links                  | Perceivable         | Hard to distinguish navigation links          |
| Image without alt                      | Perceivable         | Missing image description                       |
| Ambiguous date format                  | Perceivable         | Misinterpretation of date                       |
| Removed focus outlines                 | Operable            | No visible keyboard focus                       |
| Clickable div no keyboard/ARIA role   | Operable            | Keyboard users cannot activate                  |
| `<span>` used as button                | Operable            | Inaccessible interactive element                |
| Form inputs without labels             | Perceivable/Understandable | Confusing form experience                |
| Skipped heading levels                 | Understandable      | Difficult heading navigation                    |
| Non-descriptive link text              | Understandable      | Poor link context                               |
| Decorative images missing alt          | Perceivable         | Confusing screen reader output                  |
| Missing landmarks                     | Robust              | Hard to navigate landmarks                      |
| Unlabeled lists                      | Understandable      | Poor context for list content                   |
| No keyboard event listeners           | Operable            | Keyboard users cannot activate                   |
| No visible focus indicator            | Operable            | Keyboard users lose navigation cues             |
| No ARIA roles on custom controls      | Robust              | Assistive tech misidentifies elements           |
| No form validation or feedback        | Understandable      | Confusing form usage                            |
| Low contrast text colors              | Perceivable         | Reduced readability                            |
| Keyboard focus hard to see            | Operable            | Keyboard users lose focus                        |
| No instructions for widgets/forms     | Understandable      | User confusion                                 |

---

*Use this list to guide your accessibility testing and training exercises.*

