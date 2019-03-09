# GitHub for collaboration.


## Repository structure 

```
-- data
-- docs
   |__manuscript.Rmd
-- packrat
   |__init.R
   |__lib
   |__lib-ext
   |__lib-R
   |__packrat.lock
   |__packrat.opts
   |__src
-- raw_data
   |__iris.csv
-- README.md
-- scripts
-- test.Rproj
```

## Workflow for the workshop

The following is a bulleted list of what we will do in the workshop.

### Set up
- JC will create a GitHub repo on GitHub
- JC will clone the repo
- JC will run `startR::setup()` to create all files
- JC will explain what files were created, show the structure of the repo and tell people to knit the Rmd file
- JC will then send the code to GH with the following:

```
git add -A
git commit -m "Added initial files to repo"
git push
```

- JC to show how these changes show up online

### Starting to collaborate

- JC adds Tracey as a collaborator
- Tracey accepts the invitation to collaborate
- Tracey now clones repo to her computer
- Tracey looks at the Rmd code and HTML document and identifies what might be a horrible mistake:

> JC is fitting a linear model to three distinct groups. The overall trend is negative, but the individual trend is clearly positive. This needs to be fixed, this is where collaboration begins.

> BEFORE you modify any code, you should check-in with the person who wrote the code.

- Tracey goes to GH repo and navigates to `docs/manuscript.Rmd`, then clicks on the `Blame` button to see the story of the file. She confirms that the only person that has modified the file is JC.

### Filing an issue

- Tracey explains what a GitHub issue is, and the three key components of one:
   - A good title
   - Mention someone
   - Description of the problem
   - If possible, a reference to the code
- Tracey navigates back to `docs/manuscript.Rmd`, down to [L50](https://github.com/jcvdav/GitHubCollab/blob/master/docs/manuscript.Rmd#L50) where the code chunk begins and copies the URL. She then enters the following information on the GitHub issue:

> Title: "Simpson's paradox in regression?"
> Description: "@jcvdav: Looks like there might be a problem in estimating the relationship. The figure created in the chunk code begining in [L50](https://github.com/jcvdav/GitHubCollab/blob/master/docs/manuscript.Rmd#L50) each species shows a clear positive trend. Perhaps we should fit three distinct lines?"
- Tracey files GH issue

### Responding to an issue

- JC reviews the issue he just received in his email (Slack is useful too)
- The issue is quite clear, but JC doesn't have time to fix it because he's about to go to the field and collect more data.
- JC answers to the issue with a possible fix, and assigns it to tracey.

The possible fix reads:

> Looks like the call to `geom_point(mapping = aes(color = Species)) +` should me moved to the call of `aes()` in `ggplot()` so that the aesthetics are propagated down to all geoms, not just `geom_point()`.

### Planning on GH - Introduction to GH projects

- JC creates a GH project
- JC shows how to add issues to a project
- JC creates two new GH issues:
   - Add new data
   - Update code to load new data
- JC shows that the issues are autmatically added to the project

### Closing GH issues

- While JC's on the field, Tracey modifies the code
- Tracey re-renders the document, everything looks fine, update repo:

```
git add -A
git commit -m "Fixed Simpson's paradox: close #1"
git push
```

### (Horrible, horrible) merging

- While on the field, without internet, JC kept working on the project
- He added data on new species (`startR::new_iris()`)
- He extended the introduction


--------- 

by: Tracey, JC
