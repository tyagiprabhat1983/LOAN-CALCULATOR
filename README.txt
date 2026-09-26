LOAN CALCULATOR - OFFLINE PWA

This package contains the supplied Loan Calculator & Repayment Analyzer converted into an installable PWA structure.

It has NO CDN script dependencies. PDF export uses the browser's native Print/Save-as-PDF function. Excel export creates an Excel-compatible .xls file directly in JavaScript.

Files: index.html, manifest.webmanifest, sw.js, icon-192.png, icon-512.png.

INSTALL ON ANDROID:
A service worker/PWA must initially be served over HTTPS (or localhost); Android Chrome does not allow service workers from a file:// URL. Open the app from an HTTPS static host, choose Chrome menu > Install app/Add to Home screen, and let it finish caching. After installation, the app can run offline from the home-screen icon.

CHANGES IN THIS VERSION:
- Fixed PDF export: the schedule/analysis table no longer gets clipped when using
  Print > Save as PDF, because the on-screen scroll box (max-height + overflow) is
  now unclipped and all app UI (nav, buttons, input forms) is hidden specifically
  for print, via a dedicated @media print stylesheet. A clean title/date header is
  also added to the printed page. No CDN or library dependency was added; it still
  uses the browser's own native Print/Save-as-PDF feature.
- Fixed Excel export: it previously saved an HTML table with a .xls extension,
  which many Android apps (Excel, WPS, Sheets) refuse to open correctly or show
  as empty because the file content doesn't match a real Excel format. It now
  generates a genuine .xlsx (Office Open XML) file, built directly in JavaScript
  with no external library, so it opens correctly everywhere. Opening/Closing
  balance columns (and Interest/Principal where mathematically safe) are real
  Excel formulas chained row-to-row, plus SUM() totals — not just static values.
- Added icons to each Home screen menu card.
