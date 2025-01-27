# Gem
try to publis my project for test using gem ruby


Open Git Bash.

If you don't already have a local copy of your repository, navigate to the location where you want to store your site's source files, replacing PARENT-FOLDER with the folder you want to contain the folder for your repository.

cd PARENT-FOLDER
If you haven't already, initialize a local Git repository, replacing REPOSITORY-NAME with the name of your repository.

$ git init REPOSITORY-NAME
> Initialized empty Git repository in /REPOSITORY-NAME/.git/
# Creates a new folder on your computer, initialized as a Git repository
Change directories to the repository.

$ cd REPOSITORY-NAME
# Changes the working directory
Decide which publishing source you want to use. For more information, see Configuring a publishing source for your GitHub Pages site.

Navigate to the publishing source for your site. For more information, see Configuring a publishing source for your GitHub Pages site. For example, if you chose to publish your site from the docs folder on the default branch, create and change directories to the docs folder.

$ mkdir docs
# Creates a new folder called docs
$ cd docs
If you chose to publish your site from the gh-pages branch, create and checkout the gh-pages branch.

$ git checkout --orphan gh-pages
# Creates a new branch, with no history or contents, called gh-pages, and switches to the gh-pages branch
$ git rm -rf .
# Removes the contents from your default branch from the working directory
To create a new Jekyll site, use the jekyll new command in your repository's root directory:

$ jekyll new --skip-bundle .
# Creates a Jekyll site in the current directory
Open the Gemfile that Jekyll created.

Add "#" to the beginning of the line that starts with gem "jekyll" to comment out this line.

Add the github-pages gem by editing the line starting with # gem "github-pages". Change this line to:

gem "github-pages", "~> GITHUB-PAGES-VERSION", group: :jekyll_plugins
Replace GITHUB-PAGES-VERSION with the latest supported version of the github-pages gem. You can find this version here: Dependency versions.

The correct version Jekyll will be installed as a dependency of the github-pages gem.

Save and close the Gemfile.

From the command line, run bundle install.

Open the .gitignore file that Jekyll created and ignore the gems lock file by adding this line:

Gemfile.lock
Optionally, make any necessary edits to the _config.yml file. This is required for relative paths when the repository is hosted in a subdirectory. For more information, see Splitting a subfolder out into a new repository.

domain: my-site.github.io       # if you want to force HTTPS, specify the domain without the http at the start, e.g. example.com
url: https://my-site.github.io  # the base hostname and protocol for your site, e.g. http://example.com
baseurl: /REPOSITORY-NAME/      # place folder name if the site is served in a subfolder
Optionally, test your site locally. For more information, see Testing your GitHub Pages site locally with Jekyll.

Add and commit your work.

git add .
git commit -m 'Initial GitHub pages site with Jekyll'
Add your repository on GitHub.com as a remote, replacing USER with the account that owns the repository and REPOSITORY with the name of the repository.


$ git remote add origin https://github.com/USER/REPOSITORY.git

Push the repository to GitHub, replacing BRANCH with the name of the branch you're working on.

git push -u origin BRANCH
Configure your publishing source. For more information, see Configuring a publishing source for your GitHub Pages site.

On GitHub, navigate to your site's repository.

Under your repository name, click  Settings. If you cannot see the "Settings" tab, select the  dropdown menu, then click Settings.

Screenshot of a repository header showing the tabs. The "Settings" tab is highlighted by a dark orange outline.
In the "Code and automation" section of the sidebar, click  Pages.

To see your published site, under "GitHub Pages", click  Visit site.

Screenshot of a confirmation message for GitHub Pages listing the site's URL. The gray "Visit site" button is outlined in orange.
Note

It can take up to 10 minutes for changes to your site to publish after you push the changes to GitHub. If you don't see your GitHub Pages site changes reflected in your browser after an hour, see About Jekyll build errors for GitHub Pages sites.

Your GitHub Pages site is built and deployed with a GitHub Actions workflow. For more information, see Viewing workflow run history.

Note

GitHub Actions is free for public repositories. Usage charges apply for private and internal repositories that go beyond the monthly allotment of free minutes. For more information, see Usage limits, billing, and administration.

Note

If you are publishing from a branch and your site has not published automatically, make sure someone with admin permissions and a verified email address has pushed to the publishing source.
Commits pushed by a GitHub Actions workflow that uses the GITHUB_TOKEN do not trigger a GitHub Pages build.
