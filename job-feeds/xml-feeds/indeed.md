---
description: XML Job Feed
---

# Indeed

## XML Job Feed <a id="xml_job_feed"></a>

Before getting started, review [our partnerships page](https://www.indeed.com/hire/ats-integration).

The Indeed XML feed lists job information that will be displayed on Indeed. By maintaining an XML feed, you have greater control over how jobs are displayed. You can also choose to add the Indeed Apply label to jobs.

When your customers create jobs in your system, the listings are sent via XML feed directly to the Indeed XML feed. By maintaining XML feeds, you have greater control over how jobs are displayed.

### Using the XML feed <a id="using_the_xml_feed"></a>

Create and maintain an XML document containing all job information. Indeed monitors the file for changes in one of three ways:

* Crawling an XML URL
* Crawling a client-hosted FTP site \(SFTP also supported\)
* Receiving the file directly in an Indeed FTP server \(zipped files recommended\)

**Important:** You must include all jobs hosted on your career page in the XML feed. Indeed does not accept incomplete XML feeds and does not support partial opt-in of jobs. An XML file that does not include all jobs may be rejected or receive limited exposure to job seekers. All information available to job seekers from your website should be included in the XML. For example, if you list salaries on your jobs, then you must include an element for that piece of data, i.e., `<salary>`. Salary information is not required for indexing if it is not available to job seekers on your website.

### XML feed example <a id="xml_feed_example"></a>

The following example shows a basic XML feed containing one job.

**Example: Basic XML feed**

```text
<?xml version="1.0" encoding="utf-8"?>
<source>
    <publisher>ATS Name</publisher>
    <publisherurl>http://www.atssite.com</publisherurl>
    <lastBuildDate>Fri, 10 Dec 2008 22:49:39 GMT</lastBuildDate>
    <job>
        <title><![CDATA[Sales Executive]]></title>
        <date><![CDATA[Tue, 29 Jun 2021 22:49:39 GMT]]></date>
        <referencenumber><![CDATA[unique123131]]></referencenumber>
        <url>
            <![CDATA[http://www.examplesite.com/viewjob.cfm?jobid=unique123131&amp;source=Indeed]]>
        </url>
        <company><![CDATA[ABC Hospital]]></company>
        <sourcename><![CDATA[ABC Medical Group]]></sourcename>
        <city><![CDATA[Phoenix]]></city>
        <state><![CDATA[AZ]]></state>
        <country><![CDATA[US]]></country>
        <postalcode><![CDATA[85003]]></postalcode>
        <streetaddress><![CDATA[123 fake street Phoenix AZ, 85003]]></streetaddress>
        <email><![CDATA[example@abccorp.com]]></email>
        <description>
            <![CDATA[Do you have 1-3 years of sales experience? Are you
            relentless at closing the deal? Are you ready for an exciting and
            high-speed career in sales? If so, we want to hear from you! [...]
            We provide competitive compensation, including stock options and a full
            benefit plan. As a fast-growing business, we offer excellent opportunities
            for exciting and challenging work. As our company continues to grow, you
            can expect unlimited career advancement! ]]>
        </description>
        <salary><![CDATA[$50K per year]]></salary>
        <education><![CDATA[Bachelors]]></education>
        <jobtype><![CDATA[fulltime, parttime]]></jobtype>
        <category><![CDATA[Category1, Category2, CategoryN]]></category>
        <experience><![CDATA[5+ years]]></experience>
        <expirationdate><![CDATA[Mon, 08 Nov 2021]]></expirationdate>
        <remotetype><![CDATA[COVID-19]]></remotetype>
        <indeed-apply-data>COVERED IN A LATER SECTION</indeed-apply-data>
    </job>
</source>
```

### XML feed elements <a id="xml_feed_elements"></a>

The XML feed contains basic elements, used once per feed, and a set of job elements that are used for each job in the feed.

#### Basic elements <a id="basic_elements"></a>

| Basic elements table |  |  |  |
| :--- | :--- | :--- | :--- |
| Element | Required | Description | Example value |
| `<?xml ?>` | **Yes** | XML Declaration | `<?xml version="1.0" encoding="utf-8"?>` |
| `<source>` | **Yes** | The root node for the XML feed document. | — |
| `<publisher>` | **No** | The name of the ATS from which this job was published. | `ATS Name` |
| `<publisherurl>` | **No** | The URL for the ATS from which this job was published. | `http://www.atssite.com/` |
| `<job>` | **Yes** | All metadata specific to a job. Include one `<job>` element for each job to be displayed on Indeed. | See following section for details. |

#### Job elements <a id="job_elements"></a>

**Note:**

* Job descriptions must be provided inside `<![CDATA[]]>` sections as raw HTML, just as it would be on the original website. The HTML should be provided as raw characters `(<,>,&)` and not as XML entities/ escaped characters \(&lt;, &gt;, &amp;\).
* If clients do not adhere to the following guidance, their jobs may not be included in Indeed search results. Jobs that are missing required fields or that do not meet Indeed Quality rules may be discarded or hidden. Clients should review Indeed Quality rules if they have any concerns over their postings. Clients in need of assistance should contact Indeed via [our employer pages](https://indeed.force.com/employerSupport1/s/topic/0TO1R000000drwcWAA/search-quality?language=en_US).

<table>
  <thead>
    <tr>
      <th style="text-align:left">Job elements table</th>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Element</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Description</td>
      <td style="text-align:left">Example value</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;title&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>
      </td>
      <td style="text-align:left">The title of the job. Do not include other types of information, such
        as employment type, job location, job descriptions, copies, or headlines.</td>
      <td
      style="text-align:left"><code>&lt;![CDATA[Sales Executive]]&gt;</code>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;date&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>
      </td>
      <td style="text-align:left">The date on which this job was first published.
        <br /><b>Note: </b>If the publish date is posted on your site, the date on the
        site must match what&apos;s in the XML.</td>
      <td style="text-align:left"><code>&lt;![CDATA[Fri, 19 Dec 2014 22:49:39 GMT]]&gt;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;referencenumber&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>
      </td>
      <td style="text-align:left">A unique identifying number for this job. Indeed uses this element to
        identify each job. Do not change the number once you&apos;ve set it.</td>
      <td
      style="text-align:left"><code>&lt;![CDATA[unique123131]]&gt;</code>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;url&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>
      </td>
      <td style="text-align:left">The URL for this job listing on your site. Use the URL for the job description
        page, not the application page. Include the <code>source=Indeed</code> token
        to track clicks from Indeed.</td>
      <td style="text-align:left"><code>&lt;![CDATA[http://www.examplesite.com/viewjob.cfm? jobid=unique123131&amp;source=Indeed]]&gt;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;company&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>
      </td>
      <td style="text-align:left">The company name to be displayed in search results. For example, if there
        are subsidiaries or franchises with multiple branded locations under the
        same company, <code>&lt;company&gt;</code> should be the business unit or
        brand name in the simplest possible form that job seekers quickly understand.</td>
      <td
      style="text-align:left"><code>&lt;![CDATA[[ABC Hospital]]&gt;</code>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;sourcename&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>
      </td>
      <td style="text-align:left">The parent organization hiring for the role. For example, if there are
        subsidiaries or franchises with multiple branded locations under the same
        company, all of those jobs should still have the same value in the <code>&lt;sourcename&gt;</code> node.</td>
      <td
      style="text-align:left"><code>&lt;![CDATA[ABC Medical Group]]&gt;</code>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;city&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>
      </td>
      <td style="text-align:left">The city in which this job is located.</td>
      <td style="text-align:left"><code>&lt;![CDATA[Phoenix]]&gt;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;state&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>
      </td>
      <td style="text-align:left">The state in which this job is located. Use the appropriate postal abbreviation.
        If your job is located outside the US, use the corresponding geographic
        designation such as province or region.</td>
      <td style="text-align:left"><code>&lt;![CDATA[AZ]]&gt;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;country&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>
      </td>
      <td style="text-align:left">The country in which this job is located.</td>
      <td style="text-align:left"><code>&lt;![CDATA[US]]&gt;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;postalcode&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>, if on the job details page.</td>
      <td style="text-align:left">The postal code in which this job is located.</td>
      <td style="text-align:left"><code>&lt;![CDATA[85003]]&gt;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;streetaddress&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>, if on the job details page.</td>
      <td style="text-align:left">The street address of the job&apos;s primary work location. Please include
        the street name and number. If possible, provide the full address including
        city, state, and postal code. Street address may be used by Indeed to improve
        the precision of location-based job search and may also be displayed to
        job seekers.</td>
      <td style="text-align:left"><code>&lt;![CDATA[1234 Sunny Lane Phoenix, AZ 85003]]&gt;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;email&gt;</code>
      </td>
      <td style="text-align:left"><b>No</b>
      </td>
      <td style="text-align:left">The email address to which you want your Indeed Apply applications sent.</td>
      <td
      style="text-align:left"><code>&lt;![CDATA[example@abccorp.com]]&gt;</code>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;description&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>
      </td>
      <td style="text-align:left">The description for this job listing. Ensure the information in the <code>&lt;description&gt;</code> matches
        the details on the <code>&lt;url&gt;</code> page. This field will be the
        source of the raw text displayed to job seekers on Indeed, and should include
        all job-relevant information - including text that may also be provided
        in other fields in the XML, e.g., education, experience.
        <br /><b>Note:</b> Job descriptions require HTML formatting. For a list of supported
        HTML elements, see <a href="https://developer.indeed.com/docs/indeed-apply/enterprise-ats/#formatting_guidelines">Formatting Guidelines</a>.</td>
      <td
      style="text-align:left"><code>&lt;![CDATA[</code>  <code>Do you have 1-3 years of sales</code>  <code>experience? [...] ]]&gt;</code>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;salary&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>, if on the job details page.</td>
      <td style="text-align:left">
        <p>The salary offered for this job. Best practices are as follows:</p>
        <ul>
          <li>Provide data in a single <code>&lt;salary&gt;</code> element. If the salary
            is a range use the following example format: $10 - $20 / hour.</li>
          <li>Always specify a pay period, e.g., per year, per week, per hour, etc.</li>
          <li>Keep number formats as simple as possible</li>
          <li>Include a currency symbol</li>
          <li>Do not use any commas, spaces, apostrophes, etc.</li>
          <li>Do not use shorthand expressions, e.g., &quot;k&quot; to express thousands</li>
          <li>Avoid putting multiple salaries in the job title or description</li>
          <li><a href="https://indeed.force.com/employerSupport1/s/article/203134734?language=en_US">Inputting Salary Amounts Guidelines</a>
          </li>
        </ul>
        <p><b>NOTE: </b>If a job does not have a salary, leave the field blank in
          the XML for that job. Salary ranges that are unreasonably wide will be
          removed.</p>
      </td>
      <td style="text-align:left"><code>&lt;![CDATA[$50000 per year]]&gt;</code>
        <br />OR
        <br /><code>&lt;![CDATA[$4,000-$5,000 per month]]&gt;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;education&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>, if on the job details page.</td>
      <td style="text-align:left">The desired education level for this job.</td>
      <td style="text-align:left"><code>&lt;![CDATA[Bachelors]]&gt;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;jobtype&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>, if on the job details page.</td>
      <td style="text-align:left">The type of job, full- or part-time.</td>
      <td style="text-align:left"><code>&lt;![CDATA[fulltime, parttime]]&gt;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;category&gt;</code>
      </td>
      <td style="text-align:left"><b>No</b>
      </td>
      <td style="text-align:left">A comma-delimited list of job categories, used to aid job seekers when
        searching. While this element is not required, it&#x2019;s highly encouraged
        to include for job management or as a way to reflect additional information
        found on the job details page. For example, you may find it useful to include
        facility or department information in this element.</td>
      <td style="text-align:left"><code>&lt;![CDATA[Category1, Category2, CategoryN]]&gt;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;experience&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>, if on the job details page.</td>
      <td style="text-align:left">The desired experience for this job.</td>
      <td style="text-align:left"><code>&lt;![CDATA[5+ years]]&gt;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;expirationdate&gt;</code>
      </td>
      <td style="text-align:left"><b>Yes</b>, if on the job details page.</td>
      <td style="text-align:left">The date in which you will no longer be actively hiring for a role.</td>
      <td
      style="text-align:left"><code>&lt;![CDATA[Mon, 08 Nov 2021]]&gt;</code>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;tracking_url&gt;</code>
      </td>
      <td style="text-align:left"><b>No</b>
      </td>
      <td style="text-align:left">A unique URL for each job in order to track clicks on Indeed. Indeed creates
        a GET request to this URL each time the job is clicked.</td>
      <td style="text-align:left"><code>&lt;![CDATA[https://www.examplesite.com/</code>  <code>trackjob1234]]&gt;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;remotetype&gt;</code>
      </td>
      <td style="text-align:left"><b>No</b>
      </td>
      <td style="text-align:left">
        <p>Specifies the type of remote work being offered. Please include one of
          the following:</p>
        <ul>
          <li><b>Fully remote</b> (The employer intends all work for the job to be done
            remotely or from home.)</li>
          <li><b>COVID-19</b> (These jobs are temporarily remote during the pandemic,
            but will return to the office when the pandemic ends.)</li>
          <li><b>WFH Flexible</b> (Available for US jobs ONLY: The employer gives employees
            the option to work from home occasionally as a benefit.)</li>
        </ul>
        <p>
          <br />Please see the <a href="https://developer.indeed.com/docs/indeed-apply/enterprise-ats/#xml_feed_faq">FAQ below</a> for
          additional text that can be included in job descriptions and how to properly
          send remote jobs. <b>Note:</b> The data collected from this field will not
          be used to determine location. Please see the <a href="https://developer.indeed.com/docs/indeed-apply/enterprise-ats/#xml_feed_faq">XML Feed FAQ</a> section
          for information on posting jobs remotely.</p>
      </td>
      <td style="text-align:left"><code>&lt;![CDATA[COVID-19]]&gt;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;lastactivitydate&gt;</code>
      </td>
      <td style="text-align:left"><b>No</b>
      </td>
      <td style="text-align:left">The most recent timestamp of any action that was taken on this job within
        your system. This action could include reviewing candidates, modifying
        the job, etc.</td>
      <td style="text-align:left"><code>&lt;![CDATA[Fri, 19 Dec 2014 22:49:39 GMT]]&gt;</code>
      </td>
    </tr>
  </tbody>
</table>

### Formatting guidelines <a id="formatting_guidelines"></a>

Indeed expects the same HTML formatting from your website when you provide job descriptions in XML. Include your formatting in `CDATA` tags.

**Note:** We do not support escaped HTML entities. For example, use `<` instead of `&lt;`. Improper HTML can result in rejection and/or formatting issues for jobs on Indeed. Supported tags include but are not limited to the following examples:

| Formatting guidelines table |  |
| :--- | :--- |
| Tag | Description |
| `<b>` | Bold |
| `<h1>` to `<h6>` | Headers **Note:** Text in header tags transform to consistent sizes when displayed on Indeed pages. |
| `<br>` | Line break **Note:** Indeed automatically inserts line breaks between paragraphs. |
| `<p>` | Paragraph |
| `<ul>` | Unordered list \(bullets\) |
| `<li>` | List item |
| `<strong>` | Strong text \(bold\) |
| `<em>` | Emphasized text \(italics\) |
| `<table>`, `<tbody>`, `<th>`, `<tr>`, `<td>` | Simple tables |

Additionally, we support computed style nodes like the following:

* `<font style="font-weight:bold">Some bold text</font>` will result in bold text.
* `<div><h2 style="display:inline">Label: </h2> Text</div>` will display “Label: Text” in-line, despite the fact that `<h2>` is a block element by default.
* A paragraph tag must have positive top/bottom margin/padding. This is the `<p>` tag’s default behavior

#### Formatting example <a id="formatting_example"></a>

**Formatting for an example job description**

```text
<description><![CDATA[
<h2 id="job_description">Job Description:</h2>
 <ul>
 <li>Do you have 1-3 years of sales experience?</li>
 <li> Are you relentless at closing the deal? </li>
 <li>Are you ready for an exciting and high-speed career in sales? If so, we want to hear from you!</li></ul>
 <font style="font-weight:bold">Benefits</font>
 <p>We provide competitive compensation, including stock options and a full benefit plan. As a fast-growing business, we offer excellent opportunities for exciting and challenging work. As our company continues to grow, you can expect unlimited career advancement! </p>
]]>
</description>
```

**How it looks on Indeed**

**Job Description:**

* Do you have 1-3 years of sales experience?
* Are you relentless at closing the deal?
* Are you ready for an exciting and high-speed career in sales? If so, we want to hear from you!

**Benefits**

We provide competitive compensation, including stock options and a full benefit plan. As a fast-growing business, we offer excellent opportunities for exciting and challenging work. As our company continues to grow, you can expect unlimited career advancement!

### Common issues <a id="common_issues"></a>

The following problems can cause Indeed to reject your XML feed or can cause jobs to not appear in Indeed search results.

| Common issues table |  |
| :--- | :--- |
| Issue | Solution |
| Incorrect special character encoding | Check the feed URL using the “view source” function in your browser and ensure special characters such as brackets \(`< >`\) show up correctly. Verify that the feed is using an XML Declaration like UTF-8 character encoding. Your file must have a header that declares encoding. You can use an encoding other than UTF-8, although UTF-8 is the most common. |
| Jobs missing from the feed or job counts differing between the feed and career sites | Include every job in the feed for each client. Anything published and available on the web should be in the feed. Remember that Indeed is a search engine and indexes the more comprehensive source. |
| Incomplete or empty job descriptions | Include all text related to the job. For example, “required qualifications” may be a separate category in your database, but for Indeed’s purposes, it should be included in the `<description>` field. |
| Jobs that are scams or suspected scams | Indeed works to exclude suspected scams. Ensure that positions have well-written descriptions. If submitting jobs for another company, vet the company to ensure that it is legitimate and the listed jobs are actual open positions. |
| Old jobs in the file | Do not include old or inactive jobs in the XML. Once a job has been filled, remove the role from the XML file. If Indeed notices old or inactive jobs, we’ll ask you to correct that behavior to continue utilizing the XML. |

### XML Feed FAQ <a id="xml_feed_faq"></a>

**How often does Indeed index the XML feed?**

For XML being crawled on a URL or ATS provided FTP site, Indeed will refresh the job data 4 times a day every 6 hours from the time of the last request. For Indeed hosted FTPs we'll refresh the XML feed when a new file is received up to every 2 hours. If more frequent file uploads occur, previous runs may cease and prevent job updates from occurring.

**What metadata can be included?**

You can include any fields you like \(ex. `<job_type>`, `<branch_id>` \) as long as the standard fields are present.

**Will every job in the feed appear in Indeed search results?**

Visibility in search results is based on Indeed’s visibility rules. Our Search Quality team prioritizes jobs that are legitimate, unique, have detailed descriptions and locations, and are easy to apply to. Jobs that do not meet these criteria may be hidden from search results. Make sure your clients follow our search quality team’s [best practices](https://indeed.force.com/employerSupport1/s/article/115005915763?language=en_US) for posting. If clients have issues finding their jobs on Indeed they should [reach out to Indeed](https://www.indeed.com/hire/contact) for assistance.

**If I’m using Indeed Apply and allowing job seekers to apply directly from Indeed, why must I provide a URL?**

We require a URL that points to the job description \(not apply page\), for 3 reasons:

* If Indeed Apply fails, we direct the job seeker back to the job URL.
* If a client opts out of Indeed Apply we need a method for job seekers to apply.
* Our aggregation engine needs an active URL to confirm job content and job activity.

**What happens if I have the same job in multiple languages?**

Provide the job in every language you currently have it as a _unique_ job in the XML. If you duplicate the reference number in the XML, only the first appearance of the job appears on Indeed.

**What happens if I have the same job in multiple countries?**

Provide the job in every location where there is an open position. Region-wide postings that are not region-wide jobs are rejected for organic visibility on Indeed. Each job needs its own unique location, unique reference number, and should represent a unique job, otherwise it will lose visibility on Indeed.

**What happens if I have a statewide/country-wide job?**

Indeed requires city, state/province, country, and postal code elements. If these elements are not provided, the job does not receive organic visibility by default.

If you have legitimate region-wide postings or remote work opportunities, include them in the file and have your clients request organic visibility. If your client has an Indeed account, they can log in to get support. Clients without an account can submit questions to Indeed directly by visiting our [website](https://www.indeed.com/hire/contact).

**Why do you require an email for each job?**

For companies that are new to Indeed, or for new job sources from companies already on Indeed, we require a contact email address to verify the account and enable organic syndication. In some cases the email address is not used, but we require it for all jobs.

**What do we do if a client wishes to opt-out of distribution to Indeed?**

Remove ALL `<job>` elements for the clients jobs from the XML. Please note that clients can NOT opt out job by job and must completely opt out of distribution to Indeed. If a discrepancy in job volume between the XML and a client’s job portal appears the source with the largest job volume will be preferred for accuracy.

**How can I specify whether a job is a remote position?**

Include the `<remotetype>` element from the table above and indicate one of the three following options:

* COVID-19
* WFH Flexible \(**US ONLY**\)
* Fully remote

Additionally, in order to identify roles in one of these three distinct ways, there are certain phrases employers can include in job descriptions:

To be considered a “temporarily remote due to COVID-19” job, include one of the following phrases:

* “Work remotely temporarily due to COVID-19”
* “Work from home during coronavirus”
* “Can start remotely due to COVID-19”

To be considered as a job having “work from home flexibility”, please include one of the following phrases:

* “Flexible work from home options available”
* “Work from home days possible”
* “Options for working from home”

To be considered a “fully remote” job, include one of the following phrases:

* “This is a remote position”
* “Employees will be working remotely”
* “Remote work allowed”

In summary, there are three differentiated options that Indeed uses to accurately identify jobs:

* Use “fully remote” when the employer intends all work for the job to be done remotely or from home.
* Use “work from home flexibility” when the employer gives employees the option to work from home occasionally as a benefit.
* For jobs that are temporarily remote during the pandemic, use the “Temporarily remote due to COVID-19” option.

**How do I post a remote job and utilize the &lt;remotetype&gt; element?**

To properly post remote jobs, you’ll need to utilize the elements that Indeed uses to capture location data: `<city>`, `<state>`, `<country>`, and `<postalcode>`.

To post a job remotely in the US, use this XML:

```text
<city><![CDATA[Remote]]></city>
<state><![CDATA[]]></state>
<country><![CDATA[US]]></country>
<postalcode><![CDATA[]]></postalcode> 
```

Please note in the example above that the `<state>` and `<postalcode>` elements are still present but contain no information. This is how you should provide the data in the `<job>` element for jobs you’re posting remotely. If you do not leave the `<state>` and `<postalcode>` blank, jobs will not post as Remote positions.

To post a job that is temporarily remote due to COVID-19 statewide in Arizona, for example, take advantage of the `<remotetype>` element. The example XML below illustrates how to post this information:

```text
<city><![CDATA[Remote]]></city>
<state><![CDATA[AZ]]></state>
<country><![CDATA[US]]></country>
<postalcode><![CDATA[]]></postalcode> 
<remotetype><![CDATA[COVID-19]]></remotetype>
```

Please note in the example above that the `<postalcode>` element is still present but contains no information. This is how you should provide the data in the `<job>` element for jobs you are posting remotely and due to the COVID-19 global pandemic. If you do not leave the `<postalcode>` blank, the job will not post as a remote position.

