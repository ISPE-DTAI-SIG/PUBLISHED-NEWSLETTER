# Updating the newsletter

This guide is for SIG editors and incoming secretaries. You can use ChatGPT or Claude to update the newsletter without connecting your AI account to GitHub or installing software. You need GitHub write access to this repository to publish; otherwise, send the reviewed HTML file to a repository maintainer.

## 1. Download the current issue

1. Open [index.html in GitHub](https://github.com/ISPE-DTAI-SIG/PUBLISHED-NEWSLETTER/blob/main/index.html).
2. Use **Download raw file** to save the HTML file to your computer.
3. Keep an untouched backup and work on a copy.

Use the HTML file, rather than a PDF or copied webpage text, so the existing layout and embedded images are available to your AI tool.

## 2. Ask ChatGPT or Claude to update it

Attach the downloaded HTML file and paste the approved content into your AI conversation. A repository link alone may not give the tool access to the file; attaching the file is the simplest approach.

Copy this prompt:

> Update the attached ISPE DTAI SIG newsletter HTML using the content below.
>
> Preserve the existing layout, styling, and embedded images. Keep the result self-contained, with no new external image or stylesheet dependencies. Update the issue title, quarter, year, date, and relevant sections, including the browser page title and any print headings. Use only the supplied content; flag missing information rather than inventing it. Do not carry forward outdated announcements or deadlines without flagging them for review. Remove any draft instructions from the final issue.
>
> Return a complete, self-contained HTML file that I can download and open in a browser, plus a brief list of changes and anything that still needs review. Do not publish anything.
>
> New newsletter content:
> [Paste approved content here]

Review the returned change list. If changes are needed, ask the tool to revise the same file and return the complete updated HTML again. If it cannot provide a downloadable file, request the full HTML and save it as a plain-text file with an `.html` extension.

## 3. Review the file locally

Double-click the returned HTML file to open it in a browser. Before publishing, check:

- The issue title, quarter, year, and publication date are correct.
- Names, summaries, meeting times, time zones, and deadlines match the approved content.
- Old announcements and draft notes have been removed or deliberately retained.
- Images appear, text fits, and sections are readable at both wide and narrow browser widths.
- Each link opens the intended destination.
- Print preview looks reasonable if readers will save a PDF.
- Any questions raised by the AI have been resolved and the content has the usual SIG approval.

AI-generated revisions still need an editor’s review. Keep the approved HTML file for the publishing steps below.

## 4. Publish the approved issue in GitHub

Publish the archive first, then update the homepage. Keep all existing issue folders.

### Add a permanent archived copy

1. Choose a new issue folder using the existing convention: for example, `q4-2026` for Q4 2026. Do not reuse an earlier issue’s folder.
2. On your computer, create that folder and place a copy of the approved HTML inside it named exactly `index.html`.
3. Open the [repository](https://github.com/ISPE-DTAI-SIG/PUBLISHED-NEWSLETTER), select **Add file → Upload files**, and drag the entire new folder into the upload area.
4. Confirm that GitHub shows the path as, for example, `q4-2026/index.html`. Commit the upload with a message such as “Publish Q4 2026 newsletter archive.”

### Update the latest-issue homepage

1. Make a second copy of the same approved HTML named exactly `index.html`, outside the issue folder on your computer.
2. From the repository’s top level, select **Add file → Upload files** and upload this file. This replaces the root `index.html`.
3. Commit with a message such as “Update homepage to Q4 2026 newsletter.”
4. Edit [README.md](https://github.com/ISPE-DTAI-SIG/PUBLISHED-NEWSLETTER/blob/main/README.md) using GitHub’s pencil button. Add the new archive link to the live-site list and update the current-issue description in the structure section. Preserve links to earlier issues. Commit the change.

For Q4 2026, the archive address would be:

https://ispe-dtai-sig.github.io/PUBLISHED-NEWSLETTER/q4-2026/

The latest-issue address stays the same:

https://ispe-dtai-sig.github.io/PUBLISHED-NEWSLETTER/

If GitHub requires a branch and pull request, follow that process and have a maintainer merge it before checking publication.

## 5. Confirm publication

GitHub Pages publishes automatically after changes reach `main`. Allow a few minutes, then:

1. Open the latest-issue address and confirm it shows the new issue. Refresh the page if it still shows the previous issue.
2. Open the new archive link and confirm it shows the same approved issue.
3. Open an older archive link and confirm it still works.
4. Share the permanent archive link when referring to a specific issue; the homepage changes with each publication.

## If something goes wrong

- **No upload or edit option:** ask a repository maintainer for write access or send them the reviewed HTML file.
- **Broken layout or missing images:** return to the saved original and ask the AI to preserve the embedded images and existing styling, then review again.
- **Wrong content published:** use GitHub’s file history to recover the previous HTML, or ask a maintainer to restore it.
- **Page not updating or an archive returns 404:** confirm that the file is named `index.html` and the folder matches the link exactly. Ask a maintainer to check the Pages deployment if it remains broken.

Maintainer note: GitHub Pages should publish from the `main` branch and the repository root (`/`), where `index.html` lives. Do not switch the source to `/docs` unless the site files are intentionally moved there. Website addresses must include the current repository name, `PUBLISHED-NEWSLETTER`.
