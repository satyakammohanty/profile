# Satyakam Mohanty Profile

This repository contains a Hugo-based personal profile site. It is a static website built with the Ananke theme and customized with a single-page portfolio layout, custom styling, and data-driven content.

This is a static Hugo site, not a server-backed application. Hugo reads the config in hugo.toml, combines the theme in themes/ananke, and applies the local overrides in layouts/home.html, layouts/_partials/site-header.html, layouts/_partials/site-footer.html, and assets/ananke/css/profile.css. The page content comes from data/profile.toml, and Hugo turns all of that into static HTML/CSS in public.

## What’s In The Site

The homepage is structured into these sections:

- Hero / intro
- Impact at a glance
- Work experience
- Skills and expertise
- Certifications
- Education
- Contact
- Additional section links

The visible content is mostly driven from [profile_sm/data/profile.toml](profile_sm/data/profile.toml), while the page layout and styling are handled by local template overrides.

## Key Files

- [profile_sm/hugo.toml](profile_sm/hugo.toml) sets the site title, base URL, theme, navigation menu, and custom CSS.
- [profile_sm/data/profile.toml](profile_sm/data/profile.toml) stores the homepage content.
- [profile_sm/layouts/home.html](profile_sm/layouts/home.html) renders the one-page layout.
- [profile_sm/layouts/_partials/site-header.html](profile_sm/layouts/_partials/site-header.html) overrides the header and navigation.
- [profile_sm/layouts/_partials/site-footer.html](profile_sm/layouts/_partials/site-footer.html) overrides the footer.
- [profile_sm/assets/ananke/css/profile.css](profile_sm/assets/ananke/css/profile.css) contains the custom visual design.
- [profile_sm/themes/ananke](profile_sm/themes/ananke) is the base Hugo theme used by the site.

## Build And Run

Run these commands from the [profile_sm](profile_sm) directory:

```bash
hugo server
```

This starts the local development server with live reload, usually at `http://localhost:1313/`.

To generate the production site:

```bash
hugo
```

That writes the generated static files to [sm/public](sm/public).


Use Hugo’s `--destination` flag when building production output:

```bash
cd sm
hugo --destination ../docs
```

Or, with the short form:

```bash
cd sm
hugo -d ../docs
```

That makes Hugo write the generated site to the folder you specify instead of the default `public/`. The path is relative to the folder where you run the command, so if you run it from `sm`, `../docs` would put the output beside that folder.

```bash
cd sm
hugo --destination ../docs --baseURL https://satyakammohanty.github.io/
```

To run a local server in Python 3, open your terminal or command prompt, navigate to your target folder, and run `python -m http.server`.This instantly hosts the contents of your current directory. You can access it in your web browser at `http://localhost:8000`

```bash
cd ..
cd profile
cd docs
python -m http.server
```


## Build And Deploy (Github)

To build the site for production and publish it from the GitHub Pages-ready output folder:

```bash
cd sm
hugo --destination ../docs --baseURL https://satyakammohanty.github.io/
```

This generates the static site into [docs](docs), which is the folder used for deployment.

To preview the built output locally:

```bash
cd docs
python -m http.server 8000
```

Then open `http://localhost:8000/` in your browser.

To deploy:

1. Commit the changes in the repository.
2. Push the repository to GitHub.
3. Make sure GitHub Pages is configured to serve files from [docs](docs).

## Customization Notes

- Update the text, links, and section content in [profile_sm/data/profile.toml](profile_sm/data/profile.toml).
- Adjust the site title and navigation in [profile_sm/hugo.toml](profile_sm/hugo.toml).
- Tweak colors, spacing, typography, and layout in [profile_sm/assets/ananke/css/profile.css](profile_sm/assets/ananke/css/profile.css).
- If you want to replace the placeholder values, update the email, phone, LinkedIn URL, and resume link in the data file.

## Notes

This project is intentionally static. Hugo compiles the templates and data into HTML/CSS, so there is no backend server or application runtime beyond the local Hugo development server.









<!-- cd sm
git submodule add https://github.com/<owner>/<theme-repo>.git themes/<theme-name>

nomad-tech -->