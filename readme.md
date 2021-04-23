# [Anthroliz](https://anthroliz.netlify.app)

[![Netlify Status](https://api.netlify.com/api/v1/badges/5f6af4bc-0f77-49be-ae8e-cf357269d6f1/deploy-status)](https://app.netlify.com/sites/anthroliz/deploys)

Personal website created on Rstudio using [`blogdown`](https://bookdown.org/yihui/blogdown/get-started.html). Open the link for blogdown help. 
This uses [`hugo`](https://gohugo.io) static site generator

Notes on how to work on this.

### Getting it on local machine

- `git clone` from github to local machine
- `branch` check which branch the project is on and if that is the branch the work needs to happen. Okay to work on `master` branch but my presonal preferance is to create a new branch, make changes, validate, then merge it to master.
- open the `.Rproj` file using rstudio
- install `blogdown` package through RStudio if not installed already. Also install all the dependencies.
- to run site on rstudio console, type `blogdown::serve_site()` or select _Serve Site_ from __Addins__ button on Rstudio


### Creating a New post

- From the __Addins__ button on Rstudio select new post. Fill in post title, author, date and other metadata and the type of file. This will be added on the YAML frontmatter.
- Once hist submitted, the file will be ready to be typed up. Based on the filetype, different things can be achieved. eg. `.mmark` file can be used if rendering math equations etc. `.Rmd` can be used to create post with R code and the output along with text materials. `.md` can be used to write simple markup post.
- Once the file is saved, it is already updated on the local website.


### Updating setting of the website

- Update the `config.toml` file with appropriate setting. 
- This file can be updated for additional navigation on home page, change profile picture, update theme, color, etc. More information can be found on Hugo website. 

### Going live with change

With every save, the website gets built/refreshed locally. The actual website material gets built on the `docs` folder.
Here, some git workflow is needed.

1. `.gitignore` all files that is not not needed for other users, or are sensative such as credentials file. 
2. `stage` the files that needs to be to be tracked on github. 
3. `commit` all the work that is done. Give a short but descriptive commit message
4. `push` the branch to `remote` ie. github.com. Better to keep the local and remote branch the same.

Additionally
5. `pull request` the recently pushed branch from github if it was NOT master. 

The website builds ~~from `docs` subdirectory on `master`~~ in [netlify](htttps://netlify.com) using the hugo engine.


At this point, hopefully everything worked fine. Currently, the website is set to continuously deploy from this github master branch. The updated site should be live at https://anthroliz.netlify.app . If not, who is afraid of debugging, right?

Issues to fix:
- Homepage not rendering to default (check the theme setting or change)
- email/envelope font-awesome icon is not rendering
