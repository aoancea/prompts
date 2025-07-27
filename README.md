# ✅ Prompt: End-to-End i18n Extraction, Translation, and Refactoring for Angular Using Transloco


You are working with an Angular codebase that uses the Transloco library for internationalization.

Your task is to:

1. Scan Angular HTML/Template code provided at the end of this prompt

2. Extract all static text content that is hardcoded and not already wrapped in a translation key (i.e., not already piped with | transloco).

3. For each such static text:
a. Create a corresponding translation key, following the format: Section_<PagePrefix>_<Description>. The page prefix can be User, Billing, Confirmation, etc.
b. Provide the English and Romanian translation for the string.
c. Create a json for ro and for en translations with the translation keys and their coresponding translations

4. Replace the hardcoded static string in the original Angular template with the corresponding translation key using the {{ 'key' | transloco }} syntax.

5. Finally, output:
a. Translations in both english (en) an romanian(ro) languages with their corresponding keys in json format
b. The updated html Angular template with all replacements done. Provide the whole html without any code missing

6. Do not skip any parts of the html content. Ensure all UI labels, headings, paragraph content, buttons, checkboxes, tooltips, and error messages are included.

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
- 🌍 Translation for both en an ro languages including keys and translations in json format
- ✅ The full HTML Angular component/template with all static text replaced. Output all code, even the one that remains the same. Here we need the full and only the full template, with nothing missing. I say again, nothing missing. Do not ask me if I want the output to be displayed, and do not prepare a .html file in which you put the output. Please output the full html directly in the first response



Below is the Angular HTML/Template code base:
