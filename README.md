# Automatically upload R packages to a {drat} repo

This action checks out the git repo for an R package, builds it (via `R CMD build`), adds it to a [{drat}](https://github.com/eddelbuettel/drat) repository (via `drat::insertPackage` and `drat::updateRepo`), and then pushes that `drat` repo to GitHub.

This action accepts the following input parameters:

+ `package`: The GitHub repository for the package you want to upload. Defaults to the repository the action is running in.
+ `drat_repo`: The GitHub repository for the drat repo to update. No default, **must be specified**.
+ `token`: A PAT used to clone `package` and clone _and_ push to `drat_repo`. It is highly recommended you use a service account with the fewest permissions possible for this job.
+ `commit_message`: The message to use when committing to `drat_repo`.
+ `commit_author`: The author to write the commit as; used to set `git config user.name`.
+ `commit_email`: The author to write the commit as; used to set `git config user.email`. No default, **must be specified**.

[Click here to see a live example of this action in use.](https://github.com/ropensci/terrainr/blob/main/.github/workflows/drat.yml)

