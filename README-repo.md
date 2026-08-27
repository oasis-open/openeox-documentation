# openeox.org source code repository

This repository contains the source code for the website openeox.org
about the OpenEoX which is a standardized framework for Managing
End of Life and other Product Lifecycle Information.

The website itself is build with Hugo and styled using Bootstrap.

For more details about OpenEoX, refer to the
[OpenEoX Paper](https://docs.oasis-open.org/openeox/standardization-framework/openeox-standardization-framework-technical-report.pdf).

Also see [README.md](README.md) and [LICENSE.md](LICENSE.md).

---

## Deployment

The website is built and deployed automatically via GitHub Actions.

### How it Works

- The preferred way to update the website is by opening a **pull request**.
  Once merged into `main`, the changes will be deployed automatically.

- Advanced users with the necessary permissions can push directly to `main`,
  but using pull requests is recommended for review and tracking.

- Deployments can also be triggered manually from the **GitHub Actions** tab.

- The latest version is published at [GitHub Pages](https://openeox.org/).

No manual deployment is required. Changes go live once reviewed and merged.

---

## Development Setup

When doing changes to the website, you can use a local setup
on a GNU/Linux machine to preview the layout.

### Prerequisites

Install the following:
(either from your GNU/Linux distribution packages
or following the generic instruction).

- **Hugo** (v0.163.0 or later, extended edition):
  Required for generating the static website from the source code files.

  - Check if Hugo is installed, by running `hugo version` in the terminal.

  - [Install Hugo](https://gohugo.io/getting-started/installing/) if necessary.

- **Git**: Required to clone the repository.

  - Check if Git is installed by running `git --version`
    in the terminal.

  - [Install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) if necessary.

- **Node.js** (v20+) and **npm** (v10.8.2+, installed by default together with Node.js 20+):
  Required for managing project dependencies,
  such as the Bootstrap framework used for styling the pages.

  - Check if Node.js and npm are installed by running `node -v` and
    `npm -v` in the terminal.

  - [Install Node.js and npm](https://nodejs.org/) if necessary.

### 1. Pull the Repository

Clone the repository to your local machine using Git,
use the "<> Code" -> "Clone" information on the GitHub repository
you are working to find out which is _Your-Repository-Link_:

```bash
git clone Your-Repository-Link
```

### 2. Install Dependencies

```bash
cd Your-Repository-Name
```

Install project dependencies, including the Bootstrap framework:

```bash
npm install
```

### 3. Development Server with live Reload

```bash
hugo server -D
```

Check the output of the command, by default, the site will be accessible
by default at http://localhost:1313/ (which is the _baseURL_).

'-D' flag allows to include the draft pages to the build.
Leave it out, if you want to see pages like the production mode will show them.

#### 4. Build the Static Site

Check how the static site is build in the github workflow
`.github/workflows/hugo.yaml` file.

It means calling `hugo` (an alias for `hugo build`) with similar options
and you get the site files in `public/`.

---

## Directory Structure

- **assets**: Contains the files that are being pre-processed
  (.scss files compiled into .css)
  and icons that have to be injected into HTML for styling;

- **content/**: Contains content files, most of which have only meta headers;

- **layouts/**: Contains custom templates and layout files for rendering the site;

- **static/**: Stores static assets such as images and fonts;

- **hugo.toml**: The configuration file for the Hugo site,
  where site-wide settings are defined;

- **data/**: Holds additional JSON data files
  used by Hugo for dynamic content generation;

- **LICENSE.md**: an overview over the licences of the used components;

- **LICENSES/**: Contains the license texts, that are referred to from
  licensing headers or files.

- **package.json** and **package-lock.json**: Manages Node.js dependencies;

- **.github/workflows/**: contains code for the automated workflows
  such as deployment to the GitHub Pages.

---

## Project Settings Defined in `hugo.toml`

The `hugo.toml` file contains the main configuration settings for the Hugo project.

- **locale**: Defines the default language for the website
  (set to American English).

- **title**: The title of the website.

- **disableKinds**: Specifies which kinds of content to disable.
  The page types required for generating list-pages are disabled.

---

## History

Originally content from the old openeox.org webpage has been used.

New files developed for the webpage mechanics and the custom styles were
developed for the German Federal Office for Information Security (BSI)
([bsi.bund.de](https://www.bsi.bund.de))

The webpage and repo was constructed 2026-08 by
Intevation GmbH ([intevation.de](https://intevation.de))
