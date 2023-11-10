# reproducibility-at-urban

This repository contains the code to build the [Reproducibility at Urban website](https://ui-research.github.io/reproducibility-at-urban). The goal of this site is to centralize resources to help staff across the Urban Institute adopt tools and practices to enable more reproducible research and workflows. 

This site is built using Quarto. For an overview of setting up and developing websites with Quarto, see the [official documentation](https://quarto.org/docs/websites/). 

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
