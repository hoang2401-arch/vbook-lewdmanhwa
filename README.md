# v8 – Chapter reader diagnostic fix

Changes:
- `chap.js` returns an **array of page image URLs** from `Response.success(pages)` instead of a string containing HTML image elements.
- Only starts headless browser when HTTP extraction returned no images.
- Logs `HTTP images=...` and `final images=... first=...` for debugging.

**This build has been syntax-tested and mock-tested, not verified running on a device or on all live chapters.**

To update GitHub: Replace root `plugin.json` and `lewdmanhwa/plugin.zip`. Refresh extension listing, upgrade to 8 and re-open a chapter.

If it still fails, please share the **exact vBook log for `LewdManhwa chap v8`**, including an error message, so we can tell extraction failure from image hotlink failure.
