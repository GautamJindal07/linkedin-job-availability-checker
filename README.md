<h1>LinkedIn Job Availability Checker</h1>

<p>
A Python-based Selenium automation script designed to check LinkedIn job-search
pages for the presence of job results based on a defined search criterion.
</p>

<h2>Overview</h2>

<p>
This project automates a repetitive hiring research task by checking a list of
LinkedIn job-search URLs and determining whether the page displays a
no-results element.
</p>

<p>
The script opens each URL in Chrome using Selenium, checks for a specific
LinkedIn page element, and records the result for each URL in a CSV file.
</p>

<h2>Workflow</h2>

<p>
<strong>CSV URLs</strong> → 
<strong>Selenium + Chrome</strong> → 
<strong>Open LinkedIn Job Search</strong> → 
<strong>Check Page Element</strong> → 
<strong>Determine Result</strong> → 
<strong>CSV Output</strong>
</p>

<h2>Technologies Used</h2>

<ul>
<li>Python</li>
<li>Selenium</li>
<li>Chrome WebDriver</li>
<li>CSV</li>
</ul>

<h2>Key Features</h2>

<ul>
<li>Processes multiple LinkedIn job-search URLs from a CSV file</li>
<li>Automates Chrome using Selenium</li>
<li>Checks for a specific LinkedIn no-results element</li>
<li>Processes URLs sequentially using a single browser session</li>
<li>Uses CSS selector-based element detection</li>
<li>Exports the URL and result to a CSV file</li>
</ul>

<h2>Detection Logic</h2>

<p>
The script checks for the following CSS selector:
</p>

<p>
<strong>div.jobs-search-no-results-banner__image</strong>
</p>

<ul>
<li>
<strong>NO job</strong> — the no-results element is detected on the page.
</li>
<li>
<strong>YES job</strong> — the no-results element is not detected.
</li>
</ul>

<p>
This is a page-element based detection method and should not be interpreted
as a definitive determination of a company's overall hiring status.
</p>

<h2>Input</h2>

<p>
The input CSV contains a column named <strong>url</strong>.
Each row represents a LinkedIn job-search page to be checked.
</p>

<p>
A sample input file is included in the repository as
<strong>sample_input.csv</strong>.
</p>

<h2>Example Input</h2>

<pre>
url
https://www.linkedin.com/jobs/search/?keywords=POS%20Manager
</pre>

<h2>Output</h2>

<p>
The script records the URL and the detected result for each page.
</p>

<pre>
URL,Result
LinkedIn job-search URL,NO job
LinkedIn job-search URL,YES job
</pre>

<h2>Scraping &amp; Detection Approach</h2>

<ol>
<li>Read URLs from the input CSV.</li>
<li>Open each URL using Selenium and Chrome.</li>
<li>Wait for the page to load.</li>
<li>Search for the configured CSS selector.</li>
<li>If the no-results element is found, return <strong>NO job</strong>.</li>
<li>If the element is not found, return <strong>YES job</strong>.</li>
<li>Write the URL and result to the output CSV.</li>
<li>Close the browser after processing all URLs.</li>
</ol>

<h2>Project Structure</h2>

<pre>
linkedin-job-availability-checker/
│
├── hiring.ipynb
├── sample_input.csv
├── requirements.txt
├── .gitignore
└── README.md
</pre>

<h2>Installation</h2>

<p>
Install the required Python dependency:
</p>

<pre>
pip install -r requirements.txt
</pre>

<h2>Usage</h2>

<p>
Open <strong>hiring.ipynb</strong> using Jupyter Notebook, JupyterLab,
or VS Code with the Jupyter extension.
</p>

<p>
Place <strong>sample_input.csv</strong> in the same directory as the notebook.
</p>

<p>
Run the notebook cells to process the URLs and generate the output CSV.
</p>

<h2>Notes</h2>

<p>
The original workflow uses Selenium with Chrome and a browser profile.
Personal browser profile paths, authentication details, cookies, credentials,
or other private session information should not be included in a public
repository.
</p>

<p>
LinkedIn page structures and CSS selectors can change over time. This project
demonstrates browser automation and page-element detection techniques and
should be used responsibly and in accordance with applicable website terms
and policies.
</p>
