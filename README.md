# Sweety Retail ERP

Included: offline-first Android-installable PWA shell; IndexedDB product catalog; barcode/SKU text search; product category, HSN and GST-rate fields; sales cart; stock reduction; printable basic invoice; purchase entry with stock increase; customer/supplier directory; expense register; date-filtered sales/expense summary; CSV export; JSON backup and restore.

Run for testing: `python -m http.server 8080` then open localhost:8080. PWA install requires HTTPS hosting: open URL in Android Chrome → menu → Install app/Add to Home screen.

Important: this is a working starter, not a certified production accounting system. GST rate fields are stored but statutory CGST/SGST/IGST calculations, e-invoice, e-way bills and return filing are not implemented. Party balances are opening balances only; ledger posting, payment settlement, sales/purchase returns, audit logs, user roles, camera barcode scanning and robust historical-cost profit accounting are not implemented. Verify tax treatment with an accountant before using invoices for statutory purposes. Cloud sync is NOT active; it requires a provisioned cloud project, authentication, database schema, row-level security, sync queue and conflict handling. No secret keys are embedded. Back up data regularly; browser data clearing may erase local records.


## PWA install notes
- Deploy the contents of this folder at the site root over HTTPS.
- Keep `manifest.json`, `sw.js`, `icons/`, `index.html`, `style.css`, and `app.js` together.
- Open the HTTPS site in Chrome on Android. After the first load, wait a few seconds and check Chrome menu for **Install app**. Chrome's wording can vary by version.
- The service worker caches the app shell for offline opening and checks for updated app files when online.
- Back up business data regularly from Settings. App-shell offline support does not replace data backups or cloud sync.
