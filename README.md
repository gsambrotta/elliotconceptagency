# Elliot Concept Agency

## Your concept agency. We work with few selected brands and elevate their online presence.

This is the portfolio of Elliot Concept Agency made with 11ty and based on the starter repository [Eleventy](https://github.com/11ty/eleventy)

[![Build Status](https://travis-ci.org/11ty/eleventy-base-blog.svg?branch=master)](https://travis-ci.org/11ty/eleventy-base-blog)

## Website

- [Netlify](https://priceless-kirch-dee3bc.netlify.app/)

## Getting Started

### 1. Clone this Repository

```
git clone https://github.com/gsambrotta/elliotconceptagency elliot-concept-agency && cd elliot-concept-agency
```

### 2. Navigate to the directory

Specifically have a look at `.eleventy.js` to see if you want to configure any Eleventy options differently.

### 3. Install dependencies

```
npm install
```

### 4. Edit \_data/metadata.json

### 5. Run Eleventy

```
npx eleventy
```

Or build and host locally for local development

```
npx eleventy --serve
```

Or build automatically when a template changes:

```
npx eleventy --watch
```

Or in debug mode:

```
DEBUG=* npx eleventy
```

### Implementation Notes

- Data:
  - global data are: `_data/metadata.json`, `_data/people.json`, `_data/services.json`
  - projects are saved as collection.
- How a collection works?
  In 11ty a collection is specify by a tags.
  In `projects/projects.json` tags is defined as `projects`
  Each markdown file in the projects folder is a projects and will be display as separate page under `projects/the-markdown-file-name` url.
- We uses three layouts:
  - `_includes/layouts/base.njk`: the top level HTML structure
  - `_includes/layouts/home.njk`: the home page template (wrapped into `base.njk`)
  - `_includes/layouts/projects.njk`: the projects template (wrapped into `base.njk`)
- And some reusable components:
  - `_includes/projectslist.njk`: display a list of all the projects. Used on `index.njk`
  - `_includes/serviceslist.njk`: display a list of our services. Used on `index.njk`
  - `_includes/peoplelist.njk`: display a list of the team members. Used on `index.njk`
  - `_includes/form.njk`: Contact form. Used on `index.njk`
- Content can be any template format (projects needn’t be markdown, for example). Configuration file for supported templates is in `.eleventy.js` -> `templateFormats`.
  - Because `assets` are listed in `templateFormats` but are not supported template types, any files with these extensions will be copied without modification to the output (while keeping the same directory structure).
- The project feed template is in `feed/feed.njk`. This is also a good example of using a global data files in that it uses `_data/metadata.json`.
