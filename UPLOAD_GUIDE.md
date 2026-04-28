# How to Add a New Report

## Files in this repo

```
index.html                          ← landing page (edit this each time)
1_nepal-hospitality-service-design.html
2_tech-reformation-report.html
3_global-tech-nepal-audit.html
4_entrepreneur-blueprint.html
UPLOAD_GUIDE.md                     ← this file
```

---

## Steps

### 1. Name your file

Use this format — number prefix, then a short slug:

```
5_your-report-title.html
```

The number must be the next in sequence. Current last number: **4**

---

### 2. Place the file in this folder

Drop the `.html` file into:

```
/home/bijaybk/Projects/aetonet/research-and-findings/
```

---

### 3. Add a card to index.html

Open `index.html` and find the `<main>` section. Copy the block below and paste it **after the last `</a>` tag**, before `</main>`.

Update the three highlighted values:

```html
<a class="report-card" href="5_your-report-title.html">
  <div class="report-number">5</div>
  <div class="report-meta">
    <h2>Full Title of Your Report</h2>
    <span>Report Type</span>
  </div>
  <div class="arrow">&#8594;</div>
</a>
```

| Placeholder | Replace with |
|---|---|
| `5_your-report-title.html` | exact filename of your new file |
| `5` (in report-number div) | the report number |
| `Full Title of Your Report` | the display title shown on the card |
| `Report Type` | one of: Field Report / Audit / Blueprint / Analysis |

---

### 4. Commit and push

Run these commands in the terminal from this folder:

```bash
git add 5_your-report-title.html index.html
git commit -m "Add report 5: Your Report Title"
git push
```

GitHub Pages will update automatically within ~60 seconds.

---

## Quick checklist

- [ ] File is named `N_slug.html` with the correct next number
- [ ] File is placed in this folder
- [ ] Card added to `index.html` with matching filename, number, title, and type
- [ ] Both files staged: `git add <new-file>.html index.html`
- [ ] Committed and pushed

---

## Current report count: 5
Next file should start with: **6_**
