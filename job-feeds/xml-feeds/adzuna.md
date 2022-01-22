---
description: Adzuna XML specifications
---

# Adzuna

### General Notes <a href="generalnotes" id="generalnotes"></a>

Generic principles regarding the XML files that Adzuna accepts:

#### Delivery <a href="delivery" id="delivery"></a>

The XML file can be made available through a url (it can be password protected) and Adzuna will download it, or alternatively it can be uploaded to Adzuna's FTP server.

To upload a file to Adzuna's FTP server, an IP that Adzuna will whitelist must be provided. The whitelisted IP must be used to upload the XML file and any effort to upload from a non-whitelisted IP will fail.

Adzuna will download the XML file and update the search engine at least once per day, and therefore the file you produce must be updated with at least that frequency.

Compressing the XML file with a well-known compression algorithm like gz or zip is highly preferable.

#### Well-formed XML <a href="well-formedxml" id="well-formedxml"></a>

The XML provided for inclusion must be a well structured and valid XML document. Many freely available tools provide XML validation.

For Linux systems an XML file can be validated with:

```
$ xmllint --noout test.xml
```

#### XML declaration <a href="xmldeclaration" id="xmldeclaration"></a>

The usage of an XML declaration is highly preferable:

```
<?xml version="1.0" encoding="UTF-8" ?>
```

#### File encoding <a href="fileencoding" id="fileencoding"></a>

Data encoded in Unicode is highly preferable. Declaring the encoding of the content data in the XML declaration is also highly preferable.

#### CDATA <a href="cdata" id="cdata"></a>

Adzuna is flexible and accepts XML files both with and without CDATA sections.

If CDATA sections are not used, make sure that the content of the XML tags is properly escaped. Left angle brackets and ampersands may not occur in their literal form and must be escaped using "`&lt;`" and "` &amp;`" ([more details](http://www.w3.org/TR/REC-xml/#sec-cdata-sect)).

### XML structure <a href="xmlstructure" id="xmlstructure"></a>

#### Jobs <a href="jobs" id="jobs"></a>

This section describes the structure of a job XML file

**Root Element and job ad**

The root element is `<jobs>` and each ad should be enclosed in a `<job>` tag. Example:

```
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

| XML tag           | Type               | Notes                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ----------------- | ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| title             | **Mandatory**      | Job title. This should be an actual job title and should not include a location, salary, ID number or any keywords e.g. help wanted, urgent etc. as this will impact search relevancy when Adzuna users are looking for your jobs.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| id                | **Mandatory**      | Unique identifier of the ad from the original.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| description       | **Mandatory**      | Description of the job, this should contain html formatting as opposed to plain text and must be minimum 100 characters. Any inappropriate or offensive content will be removed from Adzuna.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| url               | **Mandatory**      | <p>URL of the job from the original site, this must be a unique URL directing the user to a job description with the ability to apply online for the job.</p><p>Tracking parameters (e.g. utm_source=adzuna) can be included in the original XML or requested to be appended by Adzuna.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| location          | **Mandatory**      | <p>Location of the job.</p><p>We can accept "raw" locations like:</p><ul><li>"10 Downing St, London SW1A 2AA, United Kingdom",</li><li>"London SW1A 2AA",</li><li>"London"</li></ul><p>Ideally this should only include one value which should be the closest suburb, town or city to the job. This allows us to accurately map the job to the most relevant location in our database. If multiple locations appear within one tag then we will only use the first location supplied.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| geo\_lat          |                    | If the latitude of the ad's location is available, then having it in a number format is highly preferable. The lat/lng will be taken into account only if both are present for the ad.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| geo\_lng          |                    | If the longitude of the ad's location is available, then having it in a number format is highly preferable. The lat/lng will be taken into account only if both are present for the ad.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| postcode          |                    | If the postcode of the ad is available, then having it in a separate XML tag is highly preferable.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| country           | **Mandatory**      | <p>Country the job is located in.<br><br><a href="http://en.wikipedia.org/wiki/ISO_3166-1">ISO_3166-1</a> country codes are highly preferable. If custom country identifiers are supplied ("UK", "United Kingdom") they must used consistently throughout the file. Mixing different custom country identifiers for the same country may result in jobs being rejected.<br><br>Adzuna supports the following 16 countries: AU, AT, BR, CA, FR, DE, IN, IT, NL, NZ, PL, RU, SG, ZA, UK, US. In a case where a file has multiple countries we will only ever map jobs that are within that country, e.g. a job in Munich with a country code of UK will be rejected.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| salary            |  Highly preferable | <p>Salary of the job preferably in the format "£20,000 per annum"</p><p>We can also accept raw salary values including text e.g. "150 € per day", "50K", "50K + benefits".</p><p>For UK jobs where no salary is provided then Adzuna will apply a Jobsworth market estimate which is based on keywords, categories, companies and locations.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| salary\_min       |                    | If a salary range is available, then having the minimum salary in a number format is highly preferable.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| salary\_max       |                    | If a salary range is available, then having the maximum salary in a number format is highly preferable.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| salary\_frequency |                    | <p>If a salary frequency is available, then having it as a separate XML tag is highly preferable.</p><p>Acceptable values:</p><ul><li>hour</li><li>day</li><li>month</li><li>year</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| salary\_currency  |                    | If a currency is available, then having it as a separate XML tag is highly preferable.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| company           |  Highly preferable | The employer for the job ad. Recruitment agencies or job site names should not be included.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| category          | Highly preferable  | <p>The category (or job industry) the ad belongs to. Strings (category labels) or integers (category ids) are accepted. Only one value can be supplied.<br><br>The following types are available.<br><br></p><ol><li>Adzuna's own categories. See <a href="https://www.adzuna.co.uk/jobs/xml-specification.html#JobCategories">Job Categories section</a> for more details</li><li><p>The original site's categories. If the original site's categories are used the following must be taken care of:</p><ol><li>A mapping of the original site's categories to Adzuna's categories should be provided. See <a href="https://www.adzuna.co.uk/jobs/xml-specification.html#JobCategories">Job Categories section</a> for more details</li><li>The original site's categories must not change dynamically. Ad-hoc adding categories is not supported.</li></ol></li></ol><p><br>If this data is not provided then we will be unable to surface your jobs to our users when they search using these filters on Adzuna<br><br>Note: in the UK &#x26; US we automatically categorise ads using a Data Science model based on title/descriptions which supersedes any category data supplied in an xml feed.</p> |
| contract\_type    |                    | <p>Only one value can be supplied. Acceptable values:</p><ul><li>permanent</li><li>contract</li></ul><p>If this data is not provided then we will be unable to surface your jobs to our users when they search using these filters on Adzuna</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| contract\_time    |                    | <p>Only one value can be supplied. Acceptable values:</p><ul><li>full_time</li><li>part_time</li></ul><p>If this data is not provided then we will be unable to surface your jobs to our users when they search using these filters on Adzuna</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| date              |                    | The initial publication date of the ad. If this reflects the last modification time of the ad it will be taken into account only the first time it's encountered.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| cpc               |                    | For those advertisers who can support programmatic bidding this field should contain the cpc you would like to pay per job and should be in the format `0.20`. Your account manager will agree a cpc range upfront with you giving you the ability to bid within a min/max range when advertising with us.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |