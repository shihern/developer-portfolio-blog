# Developer Portfolio and Blog Site
Developer portfolio and blog website made with Hugo and TailwindCSS. Live demo can be found at my personal site [connorlim.net](https://connorlim.net/)

## Prerequisites
Install required dependencies
```bash
npm run setup
```

## Configuration

### Configure Hugo
Enter your site URL and title in `config.yaml`.

```yaml
baseURL: "https://example.com/"
title: "Site Name"
```

### Fill in your contact details
Edit `config.yaml`. Put your name in the `author` section. Enter your various email addresses and social media accounts under the `social` section. Links will be auto-generated in the footer for each social item.

For the svg icon, enter the name of an svg file. The icon file should be stored at `assets/icons/<icon-name>.svg`.

**Note: the icon is REQUIRED**

```yaml
params:
  author: Author
  social:
  - title: Email
    url: mailto:hello@example.com
    svg: calendar
```

### Set up the Homepage Portfolio
Edit `data/homepage.yaml` to populate the portfolio on the home page.

1. Change the giant welcome text and subtext on the homepage
```yaml
heading: Heading
description: Description
```

2. Enter some personal details about yourself in bullet point
```yaml
aboutme:
  - name: About Me Subheading 1
    items:
      - Hello World
```

3. Enter your various developer skills
```yaml
skills:
  - name: Skill 1
    svg: calendar
```
#### Note:
Each skill has a **mandatory** `svg` field. The svg file has to be added at `assets/icons/<icon-name>.svg`. Hugo will throw an error if the svg file is not found or the field is not filled.

Note that the icons are generated on the page by directly outputting the svg into the HTML source. **You will have to modify the templates to use `<img>` tags if you wish to use other file formats.**

Additionally, Hugo live reload is not able to detect if you modify the svg file. You have to forcibly reload the server if you edit the svg file on disk

1. Enter your working experience
```yaml
experience:
  - title: Job Title
    subtitle: Employer
    description: Description
    startDate: 2020-01-01
    endDate: 2020-01-01
```

5. Fill in the various projects you would like to showcase. 
```yaml
projects:
  - title: Project
    description: Description
    url: https://github.com/
    tags: 
      - Your Skill Name
```
#### Note:
Put the relevant skills for the project under the `tags` section. Ensure that the skill name matches one of the skills from the `skills` section earlier. The icon will be automatically populated based on the icon in the `skills` section. **Hugo WILL throw an error if the skill and icon is not found**

6. Enter your educational history
```yaml
education:
  - title: College
    subtitle: Course
    startDate: 2020-01-01
    endDate: 2020-01-01
```

### Favicon
Place `favicon-32x32.png`, `favicon-16x16.png`, and `favicon.ico` in the root of the `static/` folder.


## Running
Run the Hugo dev server:
```bash
npm run dev
```

## Deployment
Generate minified static files for deployment. Files will be stored in `public/`
```bash
npm run build
```

## Licenses
Parts of this theme are taken from Dirk Olbrich's excellent [Hugo Starter Theme with Tailwind CSS](https://github.com/dirkolbrich/hugo-theme-tailwindcss-starter). Per the MIT license requirements, I have placed the license and Olbrich's copyright notice at the top of every file that is copied from his theme.

The MIT-licensed files are:
- `postcss.config.js`
- `styles.css`
- `dev-size-indicator.html`

All other files are written are by me and licensed under the AGPLv3 (or any later version).