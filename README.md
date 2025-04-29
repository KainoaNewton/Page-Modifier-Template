# Page Modifier Template

## 🚀 Customize with Cursor AI Assistant

To start developing with Cursor, simply say:

```
Help me customize the Page Modifier extension
```

Cursor will prompt:

- Which website(s) to modify
- Extension name
- Description & purpose
- CSS or DOM edits you need
- Any user interactions (clicks, dismissals)
- Permissions, icons, version

Then Cursor will update:

- `manifest.json` (name, description, permissions, popup)
- `popup.html` & `popup.js` (feature toggles UI and logic)
- `main.js` (feature code with storage checks)

After changes, reload the extension:

- Chrome/Edge: `chrome://extensions/` → Reload
- Firefox: `about:debugging#/runtime/this-firefox` → Reload

---

## ✏️ Edit Manually

- **Clone or copy** this folder.
- **Load** in your browser:
  - Chrome/Edge: `chrome://extensions/` → Load unpacked
  - Firefox: `about:debugging#/runtime/this-firefox` → Load Temporary Add-on
- **Toggle** features in the popup UI.
- **Add or modify** feature behavior in `main.js`, using storage checks:
  ```js
  chrome.storage.sync.get('feature_id', ({ feature_id }) => {
  	if (feature_id) {
  		// your PageModifier calls here
  	}
  });
  ```
- **Use helpers**:
  - `PageModifier.injectCSS(cssString)`
  - `PageModifier.addElement()/removeElement()`
  - `PageModifier.onElementReady()/onClick()`
- **Package & publish**:
  - Update `manifest.json` (name, version, description, permissions)
  - Zip files and upload to web stores

---

Enjoy customizing your page modifier! 🎉
