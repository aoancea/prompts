# ✅ Prompt: End-to-End i18n Extraction, Translation, and Refactoring for Angular Using Transloco


You are working with an Angular codebase that uses the Transloco library for internationalization.

Your task is to:

1. Scan Angular HTML/Template code (especially in .html or inline templates inside .ts files).

2. Extract all static text content that is hardcoded and not already wrapped in a translation key (i.e., not already piped with | transloco).

3. For each such static text:
a. Create a corresponding translation key, following the format: BookTickets_<PagePrefix>_<Description>. The page prefix can be Event, Billing, Confirmation, etc.
b. Provide the English and Romanian translation for the string.
c. Add the new key-value pairs into two translation JSON objects: en.json and ro.json.

4. Replace the hardcoded static string in the original Angular template with the corresponding translation key using the {{ 'key' | transloco }} syntax.

5. Finally, output:
a. The updated Angular template with all replacements done.
b. The translation key table (Original Text → Key → English → Romanian).
c. The generated en.json and ro.json objects only for the new keys.

6. Do not skip any parts of the content—ensure all UI labels, headings, paragraph content, buttons, checkboxes, tooltips, and error messages are included.

7. If a dynamic value is included `like Participant {{ i + 1 }})`, keep the dynamic expression intact while wrapping the static part in the translation key.


Here are some examples:

Before:
```html
<mat-label>Nume</mat-label>
```
After:
```html
<mat-label>{{ 'Section_Feature_Name_Label' | transloco }}</mat-label>
```

Also handle sections like:
```html
<h3>Participant {{ i + 1 }} - {{ item.name }}</h3>
```
 Keep the expression and translate the static portion, as per example below:
```html
<h3>{{ 'Section_Feature_Participant_Label' | transloco }} {{ i + 1 }} - {{ item.name }}</h3>
```

Ensure complete coverage of:
- Button labels (e.g., "Buy now", "Download")
- Input labels (e.g., "Name", "Phone number")
- Headers (e.g., "Your Tickets", "Order complete")
- Confirmation messages
- Checkbox labels (e.g., "I participate in the human chain record")
- Tooltips and accessibility text (e.g., alt="Event")

Produce high-quality, natural translations into both English and Romanian.

The final output must include:
- ✅ A full Angular component/template with all static text replaced.
- 🌍 en.json and ro.json translation files (only for the new keys).
- 🧾 A table mapping: Original Text → Translation Key → English → Romanian.
