# alperentekin.com.tr

The personal academic website of Alperen Tekin. Plain HTML and CSS: no framework, no build step, no JavaScript. Nothing here needs updating to keep working.

## What is in this folder

| File | What it is |
|---|---|
| `index.html` | The whole site. Every word on the page lives here. |
| `alperen-tekin-cv.pdf` | The CV the site links to. |
| `assets/style.css` | The design. Colours and measurements are near the top. |
| `assets/fonts/` | The typeface, STIX Two Text, and its licence. |
| `assets/favicon.svg`, `favicon.png`, `apple-touch-icon.png` | The icon in browser tabs and on phone home screens. |
| `assets/share.png` | The image shown when the link is shared. |
| `404.html` | The page shown for a wrong address. |
| `CNAME` | Tells GitHub Pages which domain the site uses. |
| `_config.yml` | Keeps this README off the public site. |

## Editing

On GitHub, open `index.html`, click the pencil, change the text, and click **Commit changes**. The live site updates within a minute or two.

`index.html` is divided by comment banners: NAME AND ROLE, HOME, RESEARCH, TEACHING, CV, CONTACT. Find the banner, then the text.

**Add a paper or a publication.** Copy one block, from `<article class="entry">` to `</article>`, paste it where it belongs in the order, and change the text. Each block is a title, a grey line saying who and when, then a paragraph.

**Link a draft.** Upload the PDF into a folder named `papers` (Add file, Upload files). Under that paper in `index.html`, delete the two lines marked `REMOVE` and fill in the addresses. Delete the SSRN link if you do not need it.

**Add a presentation.** In the Presentations list, a year goes in `<dt>` and each talk of that year in its own `<dd>`.

**Replace the CV.** Upload the new PDF under exactly the same name, `alperen-tekin-cv.pdf`. It replaces the old one, and nothing else needs to change.

**Add profile links** (Google Scholar, ORCID, SSRN, LinkedIn). In the CONTACT section, delete the two lines marked `REMOVE`, replace the placeholder addresses with yours, and delete any line you do not use.

**Add a portrait.** Save a photo as `assets/portrait.jpg`, ideally 800 by 1000 pixels. In the NAME AND ROLE section, delete the two lines marked `REMOVE`.

**Keep the site light for everyone.** Visitors whose device is in dark mode currently get a dark version. To switch that off, open `assets/style.css`, delete the block that begins `@media (prefers-color-scheme: dark)`, and change `light dark` to `light` in `style.css` (once) and in `index.html` and `404.html` (once each).

**When your position changes,** update it in four places in `index.html`: the line under your name, the `<title>` and description near the top, the `og:description` just below them, and the block that begins `"@type": "Person"`. The year in the footer is the only other date to keep current.

## Putting it online

The site is hosted free on GitHub Pages; the domain, registered at Hostinger, points to it.

1. Create a GitHub account and a new **public** repository, for example `alperentekin-site`.
2. On the empty repository page, choose "uploading an existing file". Open this folder on your computer, select everything inside it, drag it in, and commit.
3. In the repository, open Settings, then Pages. Set Source to "Deploy from a branch", branch `main`, folder `/ (root)`, and save.
4. On the same page, the custom domain should already read `alperentekin.com.tr` (it comes from the `CNAME` file). If it does not, type it in and save.
5. At Hostinger, open the DNS records for the domain. Delete the existing `A` record for `@` and any `CNAME` record for `www`. Leave MX and TXT records alone. Add:

   | Type | Name | Points to |
   |---|---|---|
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |
   | CNAME | www | YOUR-USERNAME.github.io |

6. Back on the GitHub Pages settings page, wait until the DNS check passes (usually under an hour, occasionally a day), then tick **Enforce HTTPS**.

Confirm the four addresses against GitHub's own guide, "Managing a custom domain for your GitHub Pages site", before you enter them. The domain must be using Hostinger's nameservers for the records above to take effect; that is the default.

If you have Hostinger web hosting as well as the domain, you can skip GitHub: upload the contents of this folder to `public_html` and change no DNS records.

## Credits

Set in STIX Two Text, copyright the STIX Fonts Project Authors, used under the SIL Open Font License 1.1 (`assets/fonts/OFL.txt`).
