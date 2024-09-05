Website for ContraMontreal located at [contramontreal.org](https://www.contramontreal.org)

This website is built using [Jekyll](https://jekyllrb.com/) and hosted on [GitHub Pages](https://pages.github.com/). Changes pushed to this repository should automatically build and update the live site.

## Making changes
If you're reading this you're probably a ContraMontreal organizer.

There are many technologies that go into this site: Jekyll, Ruby, Liquid, Markdown, YAML, HTML, CSS, git, GitHub, and so on. Knowledge of some of them may help, but should not be necessary. Copy and paste will take you a long way.

First you will need to make a GitHub account and ask me to add you as a collaborator for this repository.

### Small changes
Small changes can be made directly in the GitHub website.
1. Open the file you want to change (probably `_data/dances.yml` or `_pages/home_page.html`)
2. Click "Edit this file" (the small pencil icon in the top right)
3. Make your changes
4. Click "Commit changes...", optionally describe the changes with a commit message, then click "Commit changes" again to confirm
5. Wait 2 minutes, then verify that the changes have taken effect on the website.

### Larger changes
For larger changes, such as adding a new page, it is necessary to build the site locally in order to verify that the changes are working before commiting and pushing to the public page.

1. Install and run locally

Instructions for installing on Debian:
```
git clone https://github.com/neilguertin/contramontreal-org
cd contramontreal-org
sudo apt install ruby-full gcc g++ make
gem install jekyll bundler jekyll-theme-cayman
bundler install
bundler exec jekyll serve --livereload --baseurl="" --drafts
```
The website should now be live at http://localhost:4000/

2. Make changes. The website should automatically update after saving each file.
3. Commit and push changes. Unfortunately there is not space here to write a full git and GitHub tutorial.

## Site design
Jekyll does not have great multi-lingual support. Here is a simple workaround that works well enough for a website of this size. Each page has three files: `title_en.html`, `title_fr.html` and `title_page.html`. title_en and title_fr have [front matter](https://jekyllrb.com/docs/front-matter/) (The lines at the top of the file between `---`) that tell Jekyll to process the files and create an html file on the final site. They also have a `lang` attribute. The title_page file contains the html for the actual page, and contains the text for both languages. It is done this way so that the English and French text can be next to each other in the same file, in order to keep them in sync more easily.

The site uses the built in [Cayman](https://github.com/pages-themes/cayman) theme. The most visible parts of the theme have been hidden, but we still benefit from some default colors, default layout, SEO setup, and so on.

To add a new page: Add the three pages `title_en.html`, `title_fr.html` and `title_page.html`. Also add an entry to `_data/about_items.yml`.
