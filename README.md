# HumanDrive static website

Upload the contents of this folder to the GitHub Pages published directory.

- `/` → `index.html`
- `/privacy/` → `privacy/index.html`
- `/contact/` → `contact/index.html`

Privacy policy text is copied without edits from `../publication/privacy-translations/source-ko.txt` and the seven `privacy-*.txt` translations (updated 2026-10-24). Existing language selection is shared via localStorage. Default language is English.


## Structure and privacy policy

This is a static website with no package manager or build step. Each page contains its own styles and scripts. `privacy/index.html` embeds all eight policies in `POLICY_TEXT`; `renderPolicy()` assigns the selected text to `#policy-raw.textContent` and CSS preserves line breaks. Keep the source wording, effective date, URLs, and trailing newlines intact when synchronizing. The site brand remains HumanDrive, while the policy itself uses the source name HardDrive for Humans.

Language selection accepts `?lang=`, then the shared `humandrive_lang` localStorage value, and defaults to English. Supported policy keys are `ko`, `en`, `de`, `es`, `ja`, `zh-Hans`, `pt-BR`, and `fr`.

Verification on 2026-10-24: all eight embedded and rendered policies exactly matched their source files (logical LF newlines), including eight sections, three deletion list items and nine URLs. Node VM execution of the actual policy script checked language changes, URL and saved-language initialization, English fallback and unavailable localStorage. All three pages passed JavaScript syntax checks. Markup, styles, rendering logic, home/contact pages and CNAME were preserved. No browser layout check or deployment was performed.
