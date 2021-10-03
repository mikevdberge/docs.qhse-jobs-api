---
description: Adzuna XML specifications
---

# Adzuna

### General Notes <a id="GeneralNotes"></a>

Generic principles regarding the XML files that Adzuna accepts:

#### Delivery <a id="Delivery"></a>

The XML file can be made available through a url \(it can be password protected\) and Adzuna will download it, or alternatively it can be uploaded to Adzuna's FTP server.

To upload a file to Adzuna's FTP server, an IP that Adzuna will whitelist must be provided. The whitelisted IP must be used to upload the XML file and any effort to upload from a non-whitelisted IP will fail.

Adzuna will download the XML file and update the search engine at least once per day, and therefore the file you produce must be updated with at least that frequency.

Compressing the XML file with a well-known compression algorithm like gz or zip is highly preferable.

#### Well-formed XML <a id="Well-formedXML"></a>

The XML provided for inclusion must be a well structured and valid XML document. Many freely available tools provide XML validation.

For Linux systems an XML file can be validated with:

```text
$ xmllint --noout test.xml
```

#### XML declaration <a id="XMLdeclaration"></a>

The usage of an XML declaration is highly preferable:

```text
<?xml version="1.0" encoding="UTF-8" ?>
```

#### File encoding <a id="Fileencoding"></a>

Data encoded in Unicode is highly preferable. Declaring the encoding of the content data in the XML declaration is also highly preferable.

#### CDATA <a id="CDATA"></a>

Adzuna is flexible and accepts XML files both with and without CDATA sections.

If CDATA sections are not used, make sure that the content of the XML tags is properly escaped. Left angle brackets and ampersands may not occur in their literal form and must be escaped using "`&lt;`" and " `&amp;`" \([more details](http://www.w3.org/TR/REC-xml/#sec-cdata-sect)\).

### XML structure <a id="XMLstructure"></a>

#### Jobs <a id="Jobs"></a>

This section describes the structure of a job XML file

**Root Element and job ad**

The root element is `<jobs>` and each ad should be enclosed in a `<job>` tag. Example:

```text
<?xml version="1.0" encoding="UTF-8" ?>
<jobs>

    <job>
    ...
    </job>

    <job>
    ...
    </job>

</jobs>
```

**Job ad fields**

<table>
  <thead>
    <tr>
      <th style="text-align:left">XML tag</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">title</td>
      <td style="text-align:left"><b>Mandatory</b>
      </td>
      <td style="text-align:left">Job title. This should be an actual job title and should not include a
        location, salary, ID number or any keywords e.g. help wanted, urgent etc.
        as this will impact search relevancy when Adzuna users are looking for
        your jobs.</td>
    </tr>
    <tr>
      <td style="text-align:left">id</td>
      <td style="text-align:left"><b>Mandatory</b>
      </td>
      <td style="text-align:left">Unique identifier of the ad from the original.</td>
    </tr>
    <tr>
      <td style="text-align:left">description</td>
      <td style="text-align:left"><b>Mandatory</b>
      </td>
      <td style="text-align:left">Description of the job, this should contain html formatting as opposed
        to plain text and must be minimum 100 characters. Any inappropriate or
        offensive content will be removed from Adzuna.</td>
    </tr>
    <tr>
      <td style="text-align:left">url</td>
      <td style="text-align:left"><b>Mandatory</b>
      </td>
      <td style="text-align:left">
        <p>URL of the job from the original site, this must be a unique URL directing
          the user to a job description with the ability to apply online for the
          job.</p>
        <p>Tracking parameters (e.g. utm_source=adzuna) can be included in the original
          XML or requested to be appended by Adzuna.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">location</td>
      <td style="text-align:left"><b>Mandatory</b>
      </td>
      <td style="text-align:left">
        <p>Location of the job.</p>
        <p>We can accept &quot;raw&quot; locations like:</p>
        <ul>
          <li>&quot;10 Downing St, London SW1A 2AA, United Kingdom&quot;,</li>
          <li>&quot;London SW1A 2AA&quot;,</li>
          <li>&quot;London&quot;</li>
        </ul>
        <p>Ideally this should only include one value which should be the closest
          suburb, town or city to the job. This allows us to accurately map the job
          to the most relevant location in our database. If multiple locations appear
          within one tag then we will only use the first location supplied.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">geo_lat</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">If the latitude of the ad&apos;s location is available, then having it
        in a number format is highly preferable. The lat/lng will be taken into
        account only if both are present for the ad.</td>
    </tr>
    <tr>
      <td style="text-align:left">geo_lng</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">If the longitude of the ad&apos;s location is available, then having it
        in a number format is highly preferable. The lat/lng will be taken into
        account only if both are present for the ad.</td>
    </tr>
    <tr>
      <td style="text-align:left">postcode</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">If the postcode of the ad is available, then having it in a separate XML
        tag is highly preferable.</td>
    </tr>
    <tr>
      <td style="text-align:left">country</td>
      <td style="text-align:left"><b>Mandatory</b>
      </td>
      <td style="text-align:left">Country the job is located in.
        <br />
        <br /><a href="http://en.wikipedia.org/wiki/ISO_3166-1">ISO_3166-1</a> country
        codes are highly preferable. If custom country identifiers are supplied
        (&quot;UK&quot;, &quot;United Kingdom&quot;) they must used consistently
        throughout the file. Mixing different custom country identifiers for the
        same country may result in jobs being rejected.
        <br />
        <br />Adzuna supports the following 16 countries: AU, AT, BR, CA, FR, DE, IN,
        IT, NL, NZ, PL, RU, SG, ZA, UK, US. In a case where a file has multiple
        countries we will only ever map jobs that are within that country, e.g.
        a job in Munich with a country code of UK will be rejected.</td>
    </tr>
    <tr>
      <td style="text-align:left">salary</td>
      <td style="text-align:left">Highly preferable</td>
      <td style="text-align:left">
        <p>Salary of the job preferably in the format &quot;&#xA3;20,000 per annum&quot;</p>
        <p>We can also accept raw salary values including text e.g. &quot;150 &#x20AC;
          per day&quot;, &quot;50K&quot;, &quot;50K + benefits&quot;.</p>
        <p>For UK jobs where no salary is provided then Adzuna will apply a Jobsworth
          market estimate which is based on keywords, categories, companies and locations.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">salary_min</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">If a salary range is available, then having the minimum salary in a number
        format is highly preferable.</td>
    </tr>
    <tr>
      <td style="text-align:left">salary_max</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">If a salary range is available, then having the maximum salary in a number
        format is highly preferable.</td>
    </tr>
    <tr>
      <td style="text-align:left">salary_frequency</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>If a salary frequency is available, then having it as a separate XML tag
          is highly preferable.</p>
        <p>Acceptable values:</p>
        <ul>
          <li>hour</li>
          <li>day</li>
          <li>month</li>
          <li>year</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">salary_currency</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">If a currency is available, then having it as a separate XML tag is highly
        preferable.</td>
    </tr>
    <tr>
      <td style="text-align:left">company</td>
      <td style="text-align:left">Highly preferable</td>
      <td style="text-align:left">The employer for the job ad. Recruitment agencies or job site names should
        not be included.</td>
    </tr>
    <tr>
      <td style="text-align:left">category</td>
      <td style="text-align:left">Highly preferable</td>
      <td style="text-align:left">
        <p>The category (or job industry) the ad belongs to. Strings (category labels)
          or integers (category ids) are accepted. Only one value can be supplied.
          <br
          />
          <br />The following types are available.
          <br />
          <br />
        </p>
        <ol>
          <li>Adzuna&apos;s own categories. See <a href="https://www.adzuna.co.uk/jobs/xml-specification.html#JobCategories">Job Categories section</a> for
            more details</li>
          <li>The original site&apos;s categories. If the original site&apos;s categories
            are used the following must be taken care of:
            <ol>
              <li>A mapping of the original site&apos;s categories to Adzuna&apos;s categories
                should be provided. See <a href="https://www.adzuna.co.uk/jobs/xml-specification.html#JobCategories">Job Categories section</a> for
                more details</li>
              <li>The original site&apos;s categories must not change dynamically. Ad-hoc
                adding categories is not supported.</li>
            </ol>
          </li>
        </ol>
        <p>
          <br />If this data is not provided then we will be unable to surface your jobs
          to our users when they search using these filters on Adzuna
          <br />
          <br />Note: in the UK &amp; US we automatically categorise ads using a Data
          Science model based on title/descriptions which supersedes any category
          data supplied in an xml feed.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">contract_type</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Only one value can be supplied. Acceptable values:</p>
        <ul>
          <li>permanent</li>
          <li>contract</li>
        </ul>
        <p>If this data is not provided then we will be unable to surface your jobs
          to our users when they search using these filters on Adzuna</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">contract_time</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Only one value can be supplied. Acceptable values:</p>
        <ul>
          <li>full_time</li>
          <li>part_time</li>
        </ul>
        <p>If this data is not provided then we will be unable to surface your jobs
          to our users when they search using these filters on Adzuna</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">date</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">The initial publication date of the ad. If this reflects the last modification
        time of the ad it will be taken into account only the first time it&apos;s
        encountered.</td>
    </tr>
    <tr>
      <td style="text-align:left">cpc</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">For those advertisers who can support programmatic bidding this field
        should contain the cpc you would like to pay per job and should be in the
        format <code>0.20</code>. Your account manager will agree a cpc range upfront
        with you giving you the ability to bid within a min/max range when advertising
        with us.</td>
    </tr>
  </tbody>
</table>

