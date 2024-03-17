# hugo-mock-landing-page-autodeployed
We deploy our mock landing page using a workflow defined as follows:

## Automated Build and Deployment

This repository uses a GitHub Actions workflow to automatically build and deploy the Hugo website to GitHub Pages whenever code is pushed to the `main` branch.

The workflow performs the following steps:

1. **Check Out Source Repository**: Checks out the repository code, including submodules (for fetching Hugo themes) and fetches the entire commit history (not a shallow clone) to ensure accurate `.GitInfo` and `.Lastmod` values.

2. **Initialize Hugo Environment**: Sets up the Hugo environment by installing a specific version of Hugo (`0.123.4`) with extended functionality enabled.

3. **Compile Hugo Static Files**: Runs the `hugo` command to build the static website files, including draft content (`-D`), enabling garbage collection (`--gc`), and minifying the resulting files (`--minify`).

4. **Publish to GitHub Pages**: Publishes the compiled website to the `gh-pages` branch of the repository, which is used by GitHub Pages to host the website. It uses the provided GitHub token for authentication and sets the commit author information to a generic "github-actions[bot]" user.

By automating the build and deployment process, this workflow ensures that the latest changes to the website's source code are immediately reflected on the live website hosted on GitHub Pages. This streamlines the development and publishing workflow, reducing the need for manual interventions.
