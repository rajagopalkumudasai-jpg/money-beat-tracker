MONEY & BEAT LEDGER — GitHub Pages Deployment

Default logic
-------------
Base Amount: ₹25,00,000
Money Paid: ₹1,00,000 per serial number (editable)
Initial rows: 25
First date: 20 May 2026, then the 20th of every following month
Beat Amount: entered manually

Calculations
------------
Net Amount = Base Amount - Beat Amount

Cumulative Beat:
- Starts with the current active carry + current Beat Amount.
- When Cumulative Beat reaches or exceeds ₹25,00,000, the completed ₹25L block is settled.
- Excess is carried to the next serial number.
Example:
Previous carry ₹24,00,000 + new Beat ₹3,00,000 = Cumulative Beat ₹27,00,000
=> 1 base cycle completed
=> Carry Forward ₹2,00,000
The next row starts with ₹2,00,000 carry before adding the next Beat Amount.

Series behavior
---------------
When all rows in the current series have Beat Amounts, the app asks:
1) Continue Same Series — adds another serial number and next monthly date
2) Start New Series — preserves the completed series, starts a fresh series with 25 rows and resets cumulative Beat

Storage
-------
All data auto-saves in browser localStorage on that device/browser.
Use Backup Data to download a JSON backup.
Clearing browser/site data can erase local records.

Excel
-----
Download Excel exports the CURRENT series as a real .xlsx workbook.
The app loads SheetJS from the official SheetJS CDN for browser Excel creation.

GitHub Pages hosting
--------------------
1. Create/open your GitHub repository.
2. Upload the EXTRACTED files:
   index.html
   manifest.json
   sw.js
3. Commit changes.
4. Repository Settings > Pages.
5. Build and deployment > Deploy from a branch.
6. Branch: main; Folder: /(root); Save.
7. Your live URL will be:
   https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/
8. After updating files later, commit them to the same repository.
9. If Chrome shows an older cached version, refresh once or clear site cache.

Mobile
------
On Android Chrome: open the live URL and use Add to Home screen / Install app when offered.
The amount fields use a numeric keyboard without spinner arrows and the page does not rebuild while typing.
