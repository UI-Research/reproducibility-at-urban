# reproducibility-at-urban

This repository contains the code to build the [Reproducibility at Urban website](https://ui-research.github.io/reproducibility-at-urban). The goal of this site is to centralize resources to help staff across the Urban Institute adopt tools and practices to enable more reproducible research and workflows. 

This site is built using Quarto. For an overview of setting up and developing websites with Quarto, see the [official documentation](https://quarto.org/docs/websites/). 

## Adding or updating content 

* To add a new page: Add the `.qmd` file to the root of the directory and update the `_quarto.yml` file with a link to the new page. 
* To update an existing page: Update the relevant existing `.qmd` file. 
* To update styling: Update the `styles.css` file. 

You should always render and inspect your changes locally before pushing to GitHub (see instructions below). 

## Local development 

To preview local changes, use the following command from the terminal (or click the **Render** button in RStudio or VS Code): 

```
quarto preview
```

To render local changes, use the following command from the terminal: 

```
quarto render 
```

This will build the pages in the `_site` directory. Note that the `_site` directory should not be pushed to GitHub (and is ignored via the `.gitignore` file) because GitHub Actions will take care of building the site. 

## Deployment 

This repository uses GitHub Actions to build and deploy the site to GitHub Pages. Pushes to the `main` branch of the repository will trigger new builds. 

**Note:** This uses Quarto's [freeze](https://quarto.org/docs/projects/code-execution.html#freeze) feature to only execute code locally. From the [Quarto docs](https://quarto.org/docs/publishing/github-pages.html#freezing-computations): 
> If you have executable code in your project you’ll notice that a `_freeze` directory has been created at the top level of your project. This directory stores the results of computations and should be checked in to version control. Whenever you change a `.qmd` file with executable code, it will automatically be re-run during your next render and the updated computations will be stored in `_freeze`.

If this causes issues down the line, we can also execute the code through the GitHub Action (but this will make the builds take longer and add complexity). 