# SeaTurtle Website

Static landing page for SeaTurtle CLI.

## Local development

Because the site is plain static files, you can preview it with any simple local server.

Examples:

```bash
python3 -m http.server 4173
```

Then open <http://localhost:4173>.

## Deployment

The site is intended for Vercel.

Because this repo is plain static files, Vercel can deploy it without a build
step. Point the project at this repository and use the default static-site
behavior.
