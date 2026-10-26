# ICRA workshop website — editing and publishing guide

A static, responsive website made with HTML and CSS. No installation, JavaScript, accounts, paid theme, or build process is needed to view it locally. All workshop facts are placeholders; nothing in this template confirms acceptance, affiliation, people, dates, or policies.

## 1. Open your website

Unzip the download first. Open `index.html` in your browser. Keep `styles.css` in the same folder. You can preview it without an internet connection; fonts and artwork are included through browser fonts and CSS.

Files:

- `index.html`: all visible content and page structure.
- `styles.css`: colors, typography, layout, and mobile styles.
- `.nojekyll`: empty file for publishing plain static files on GitHub Pages. Keep it; it may be hidden by your file browser.
- `README.md`: this guide; it is not displayed on the workshop homepage.

## 2. Edit the content

Open `index.html` in a plain-text editor such as VS Code or Notepad. Search for `EDIT:` to find editing notes and `TBA` to find unknown details. Edit the words between HTML tags; preserve the surrounding tags. Save, then refresh your browser.

Example: change `<h3>Speaker TBA</h3>` to `<h3>Confirmed speaker name</h3>` only after participation is confirmed. Keep unconfirmed information labeled TBA. Do not use a word processor to edit HTML.

| Content | Where to edit |
| --- | --- |
| Browser title and search description | `<title>` and `<meta name="description">` near the top |
| Workshop title, year, status, and summary | Hero section, beginning at `id="home"` |
| Date, venue, format | The list with `class="container facts"` |
| Abstract, objectives, audience | `id="about"` |
| Research topics | List in `id="topics"`; add or remove `<li>` items |
| Speakers | Articles in `id="speakers"`; duplicate a whole article to add someone |
| CFP, deadlines, review and publication policies | `id="cfp"` |
| Program | Table rows in `id="program"`; duplicate a whole `<tr>...</tr>` row |
| Organizers | Articles in `id="organizers"` |
| Contact | Section with `class="section container contact"` |
| Repeated workshop name/status | Footer at the end of the file |

When submissions open, replace `<span class="status-label">Submission portal TBA</span>` with a real link: `<a class="button" href="https://YOUR-CONFIRMED-PORTAL">Submit a paper</a>`. Replace the entire example URL before publishing. Update the nearby sentence saying the call is not open.

For contact, replace the contact paragraph with a link using a real address: `<a href="mailto:YOUR-CONFIRMED-EMAIL">Contact the organizers</a>`. These examples are editing instructions, not active links in the template.

To add a photo, place it in an `images` folder and replace a speaker's portrait placeholder with `<img class="portrait" src="images/speaker.jpg" alt="Confirmed speaker name">`. Add `.person img.portrait { width:100%; object-fit:cover; }` to the CSS. Use photos with permission. Keep file names simple and match capitalization exactly.

Change the color variables at the beginning of `styles.css` to personalize the design. Keep strong text/background contrast. The abstract orbit artwork is decorative CSS, so it needs no image download or attribution.

## 3. Review before publishing

- Review every TBA and keep it until the information is confirmed.
- Keep the proposal-status notice until acceptance is confirmed; revise status wording consistently across the page after confirmation.
- Check CFP page limits, deadlines, time zone, review procedure, archival policy, and registration requirements against your actual workshop arrangements.
- Open the page at desktop width and a narrow phone-sized width. Check all navigation links and any links you add.
- Use Tab to move through links and confirm the visible focus indicator.
- Publish only material you intend to make public. GitHub Pages is a public website.

## 4. Publish with GitHub Pages — browser-only route

1. Sign in to GitHub. Create a new repository named, for example, `icra-workshop`. Choose **Public** for the straightforward GitHub Free route. Initialize it with a README so a default branch exists. Do not enter any confidential proposal material.
2. In the repository's **Code** tab, choose **Add file → Upload files**. Upload the contents of the website folder, including `index.html`, `styles.css`, and this README. Commit the upload to `main`. If GitHub asks about replacing its starter README, use this guide as the repository README.
3. Check that `index.html` is directly at the top level beside `styles.css`. Do not upload the containing `icra-workshop` folder as a nested folder.
4. If `.nojekyll` was omitted because it was hidden, choose **Add file → Create new file**, enter `.nojekyll` as the filename, leave its content empty, and commit it.
5. Open **Settings → Pages** in the repository.
6. Under **Build and deployment**, set **Source** to **Deploy from a branch**. Choose **main** and **/(root)**, then **Save**. If you used another default branch, select that branch instead.
7. Wait for deployment. Open the repository's **Actions** tab to see whether the Pages deployment succeeded. Return to **Settings → Pages** and follow the published site link.
8. A project repository typically appears at `https://YOUR-USERNAME.github.io/icra-workshop/`. Use the exact URL GitHub displays, particularly for organization accounts or custom domains.

GitHub's current instructions and plan availability: [Creating a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site). Branch and folder settings: [Configuring a publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site). Checked October 19, 2026.

## 5. Update the live website

Open `index.html` in your GitHub repository, choose its edit button, change the content, and commit. GitHub republishes changes from the selected publishing branch. For bigger edits, modify your local copy, preview it, and upload the changed files again. Edit `styles.css` the same way for visual changes. Keep your local copy in sync with online edits.

## Troubleshooting

- **404 after publishing:** check the deployment result in Actions and confirm Pages uses the correct branch and `/(root)`. Confirm lowercase `index.html` exists at the top level. Allow the deployment to finish before reloading the exact Pages URL.
- **Page loads without styling:** confirm `styles.css` is next to `index.html`, with identical spelling and capitalization. Keep the stylesheet link as `href="styles.css"`; a leading slash would cause problems on project URLs.
- **Old content still shows:** check that your edit was committed to the publishing branch, wait for deployment, then perform a hard refresh.
- **No Pages option or deployment blocked:** check repository permissions, account plan, and organization policies. An owner may need to enable Pages.
- **Images are missing:** upload the images too and use relative paths such as `images/speaker.jpg`, with matching capitalization.

## Verification notes

The supplied files were checked for matching local resources, valid internal anchor targets, required content sections, and placeholder status. Responsive breakpoints, keyboard focus styles, a skip link, semantic landmarks, and a labeled schedule table are included. A rendered browser/device audit has not been performed; preview before publication. No website has been deployed on your behalf.
