# College Result Analytics

Browser-based tool that reads the XI Standard **Tabulation Register PDF** and shows:

- Total, passed and failed students, pass percentage
- Class-wise count: Distinction, First Class, Second Class, Pass Class, Failed (Promoted)
- Division-wise and subject-wise analysis
- Searchable student list with CSV download

The PDF is read entirely in the browser. Nothing is uploaded to any server.

## Run locally

Open `index.html` in Chrome or Edge (internet needed once to load the PDF library from cdnjs), then choose the register PDF.

## Publish on GitHub Pages

1. Create a **private** repository named `college-result-analytics` and upload these files.
2. Go to Settings, then Pages, choose branch `main` and folder `/ (root)`, and save.
3. Open the Pages link GitHub shows. (Free accounts need a public repo for Pages; the app contains no student data, so this is safe.)

## How results are decided

- The register’s remark column is used: PASS with `I WITH DISTINCTION`, `I`, `II`, `III` maps to Distinction, First Class, Second Class, Pass Class. `PROMOTED` maps to Failed (Promoted).
- Percentage is the register total out of 600 (English, Urdu, Physics, Chemistry, Biology, Maths).
- A subject counts as failed when Avg (/2) is below 35 or the student is absent (AB).
- Students with no recognisable remark are listed under "Need review".

## Backup and store

- **Backup (download file):** saves the analysed results as a `.json` file. Open it again with Choose file to restore, with no PDF needed.
- **Store in this browser:** keeps the results on this device and opens them automatically next time. Use Remove stored copy on shared computers.

## Privacy

Never commit student PDFs, Excel, CSV or backup `.json` files. The included `.gitignore` blocks them.

## Next steps (planned)

Firebase login and Firestore storage, Excel/CSV import, merit lists, and PWA install on Android.
