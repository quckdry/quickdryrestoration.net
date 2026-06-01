# QuickDry Restoration LLC Website

Static GitHub Pages site for `quickdryrestoration.net`.

## Deploy To GitHub Pages

1. Put these files at the root of the GitHub Pages repository.
2. In GitHub, open Settings -> Pages.
3. Set the source to the repository root on the publishing branch.
4. Confirm the custom domain is `quickdryrestoration.net`.
5. Confirm the live phone number and email before launch.

## Contact Details

Current phone number:

```text
(760) 332-4841
```

Current `tel:` link value:

```text
tel:+17603324841
```

To change the phone number later, run both replacements from the repository root:

```bash
perl -pi -e 's/\\(760\\) 897-9616/(760) 123-4567/g' index.html */index.html README.md
perl -pi -e 's/tel:\\+17603324841/tel:+17601234567/g; s/"telephone": "\\+17603324841"/"telephone": "+17601234567"/g' index.html */index.html
```

Current email:

```text
management@quickdryrestorationllc.biz
```

To change it later:

```bash
perl -pi -e 's/management@quickdryrestorationllc\\.biz/new-email@example.com/g' index.html */index.html
```

## Project Structure

- `index.html`: homepage
- `styles.css`: shared styles
- `assets/images/`: generated technician-led photography, WebP plus JPEG fallbacks
- `assets/logo/`: supplied QuickDry wide wordmark and supporting logo files
- `assets/favicons/`: favicon set derived from the QuickDry droplet mark
- `homeowners/`, `property-managers/`, `insurance-adjusters/`, `plumbing-partners/`: noindex audience stubs
- city directories: noindex stubs for future city landing pages
- `ALT_TEXT.md`: consolidated image alt text
- `NOTES.md`: decisions and interpretations
- `AUDIT.md`: approved audit of the previous website

## Do Not Publish As Final Until

- The phone number and email are confirmed as launch-ready.
- City pages are expanded with local content and are set to index.
- Audience pages are expanded with real content or left noindex.
- Any future testimonials, awards, carrier relationships, or response metrics are added only after they are real and documented.
