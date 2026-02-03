# Poverty Data Gaps

This interactive explorer:

* Uses [airtable](https://airtable.com/) as a database
* Extracts and processes data from airtable using [R](https://www.r-project.org/)
* Builds a website the [Quarto](https://quarto.org/)
* with interactive tables created with [ObservableJS](https://observablehq.com/documentation/cells/observable-javascript).

## Updating the text

* Make any changes to the text in the `index.qmd` file.
* Commit to GitHub, and it will automatically re-deploy.
* The data from airtable will not update when only editing the text.

### Adding a new page

* To add a new tab, create a new file called `page.qmd` where `page` is whatever you want the URL to be. For an example, look at `about.qmd`.
* Update the list of tabs in the `_quarto.yml` file (around line 25-28).
* In the `page.qmd` file, add information such as the page title to the YAML block at the top (the bit in between the `---`). Beneath the YAML block, add any Markdown text you wish.
* You can also add raw HTML if you need to. See the [Quarto documentation](https://quarto.org/docs/authoring/markdown-basics.html#raw-content) for an example of adding an iframe for e.g. embedding an external visualisation.

## Updating the data

* Make any required changes to the airtable data.
* In GitHub, go to *Actions* then select *Update data* from the left hand side.
* Click *Run workflow*, and run from main. 
* The site will automatically re-deploy.

## Changing the airtable base

* Open `R/config.R` and edit the ID of the airtable base.
* In the GitHub repository, go to *Secrets and variables* and add a new repository secret called `AIRTABLE_API_KEY` which contains your airtable API key. 
* Open `about.qmd` and edit URL for the airtable form to submit a new data gap, and make sure the airtable form is set to be shared with anyone on the web.

To run locally:

* Open or create a `.Renviron` file containing your airtable API key in the form `AIRTABLE_API_KEY="XXX"`

## Changing the GitHub repository

* Open the `_quarto.yml` file and edit the `site-url` website.
* Locally, run `quarto publish gh-pages` from a terminal. You only need to do this once.
* Ensure GitHub Actions are enabled.
* Create a Personal Access Token in your GitHub settings (Settings -> Developer settings -> Personal access tokens -> Fine-grained tokens).
* Give it `contents: read and write` and `workflows: read and write` permissions for the repository.
* Add it as a repository secret named `PAT`.
* In the GitHub repository, go to *Secrets and variables* and add a new repository secret called `AIRTABLE_API_KEY` which contains your airtable API key. 


