---
layout: pages/default.pug
title: Home
description: This is Nera, a light weight static site generator
keywords: nera, light weight, static site generator
---
# Nera meets Tailwindcss
Nera is a really simple static site generator. It creates static html files out of  
Markdown files. Here we combine it with [Tailwindcss](https://tailwindcss.com/)

## Get started
> Make sure you run at least Node version 10.2 on your system

```bash
git clone git@github.com:seebaermichi/nera-tailwind.git

# Install dependencies
npm install

# Build css depending on your tailwind configuration
npm run build-css

# Run local server
npm run serve

# Render the static files
npm run render

# Local development
npm start
```

## Directory and file structure
```
|-- assets/
    |-- src/
        |-- index.css
|-- config/
    |-- app.yaml
|-- pages/
|-- src/
    |-- plugins/
    |-- nera.js
|-- views/
|-- index.js
```

### Assets
Are all CSS, JavaScript, font and image files which are used on your website. During the render process all assets are copied to the `public` directory. For nera-tailwind we alread put an `src/index.css` in `assets`, so you can directly start with tailwindcss.

### Config
Here you can define global settings for your website. All the global settings should got to the `config/app.yaml`. Like lang, name, etc.

### Pages
Within the pages directory you add the Markdown files which actually include the content of your page. Find more information about the Markdown files below.

### Src
The `src` directory include the app itself. Here you find the `nera.js` file which includes all the functionality to run the  
app.

### Plugins
The `src` folder also includes the `plugins` folder. In it you would place additional functionality. There is already an  
example, the main navigation. Find detailed documentation about plugins in the plugins [README file](https://github.com/seebaermichi/nera-plugins/tree/master/plugins).

### Views
In the views directory you put all the layout files. We use [pug](https://pugjs.org/api/getting-started.html) as a templating framework.

## Page Markdown files
Each Markdown file which includes the content of a dedicated webpage needs to have some settings in the head. See an example below:
```markdown
---
layout: pages/default.pug
title: Homepage
---
# Content
Content goes here...
```
> Of course you can add many more so called meta data. It will be available in the view files as `meta` object.  
> In addition the basic config values are available within the `app` object.
