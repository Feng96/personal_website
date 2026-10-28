# Yinan Feng — Personal website

Academic and personal website at https://yinanfeng.com, built with Hugo and the Stack theme.

## Content

- `content/_index.md` and `layouts/index.html`: research-focused homepage.
- `content/projects/usbf/`: USBF dataset and software overview.
- `content/page/`: research, publications, CV, about, and contact pages.
- `content/research-notes/` and `content/life/`: separate collections for technical and personal posts.
- `static/files/`: downloadable CV and one-page resume.

Existing article URLs are preserved. Historical experiment posts retain their dated results; the USBF project page provides current release context.

## Build and publish

Use **Hugo extended 0.125.7** with Go installed:

```sh
hugo server
hugo --minify --gc
```

Netlify builds `master` and serves `public/` at the custom domain. The GitHub Actions workflow also builds and publishes the GitHub Pages branch. Changes pushed to `master` trigger deployment.

## Updates

Update `content/projects/usbf/index.md` when publishing a new data summary. Counts on the personal site are dated snapshots; the live viewer reads the current Source Cooperative manifest. Do not present inherited national baseline records as completed new refinement or experimental LoD2 models as a national product.

Code uses the repository MIT license. Research data, source imagery, and other attributed assets retain their own licenses.
