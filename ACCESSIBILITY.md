# Accessibility statement

Zelvyn is committed to making its API documentation usable by everyone,
including people who use assistive technology, keyboard-only navigation, or
reduced-motion and high-contrast settings.

## Our commitment

We aim to meet the **Web Content Accessibility Guidelines (WCAG) 2.2 Level AA**
for the public documentation and website. Accessibility is treated as a
correctness requirement, not an afterthought: a page that cannot be read or
operated by everyone is not finished.

## What we do

- Use semantic HTML headings, landmarks, lists, and tables so screen readers can
  navigate the structure.
- Keep a visible keyboard focus indicator and make every interactive control
  reachable and operable by keyboard.
- Maintain colour contrast for body text, controls, and focus states.
- Respect `prefers-reduced-motion` and avoid motion that is not essential.
- Give every image and icon a text alternative, or mark it decorative when it
  carries no meaning.
- Label form fields, associate error messages with their fields, and announce
  status changes.
- Provide code samples as selectable text with a visible copy control, not as
  images.
- Keep the documentation usable at 200% zoom and at narrow mobile widths.

## Supported environments

We test the current versions of:

- **Browsers:** Chrome, Firefox, Safari, and Edge.
- **Screen readers:** NVDA with Firefox, VoiceOver with Safari, and TalkBack on
  Android where available.
- **Input:** keyboard only, touch, and pointer.
- **Display:** default and high-contrast modes, 200% zoom, and reduced motion.

The API itself is consumed by HTTP clients and is not a visual interface. Its
accessibility surface is the documentation and the response contract described
in this handbook.

## Known limitations

- Some generated code samples are long and scroll horizontally on small
  screens. The copy control and text selection remain available, and no content
  is hidden.
- Syntax highlighting colours are decorative; code remains readable without
  colour.
- Third-party host status pages linked from the site may not meet the same
  standard. We link to them because the information is useful, and we report
  barriers we find.
- Older release notes and archived pages may not yet be fully remediated.

We review this list as issues are reported and fixed.

## Reporting a barrier

If something is not accessible to you, please tell us. Include the page, what
you were trying to do, the assistive technology or browser you used, and what
happened.

- Use the support form: <https://zelvyn.devs.surf/support> and choose
  **Something else**.
- Or open a documentation issue in this repository and describe the barrier.

We aim to acknowledge accessibility reports within **5 business days** and to
fix confirmed barriers as a priority.

## Feedback and enforcement

We welcome suggestions for improving accessibility. If you are not satisfied
with our response, say so in the same thread and ask for it to be escalated; we
will review the decision.
