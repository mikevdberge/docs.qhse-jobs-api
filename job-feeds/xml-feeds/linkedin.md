---
description: Linkedin XML Feed
---

# Linkedin



The LinkedIn XML feed contains the information required to ingest and post jobs on LinkedIn. To expedite your implementation process, as well as ensure the accuracy of your ingested jobs’ details, create the XML feed in the below format:

### Creating the XML Feed <a id="creating-the-xml-feed"></a>

The XML feed contains two types of job elements:

* Mandatory
* Recommended

#### Mandatory Fields <a id="mandatory-fields"></a>

Following is the list of fields that must be included on the Limited Listings XML feed for the jobs to be considered as valid to be posted on LinkedIn:

* Job ID
* Company Name
* Job Title
* Job Description
* Location String
* Apply URL
* LinkedIn Company ID \[Mandatory for Applicant Tracking Systems \(ATSs\)\]

### Job Posting Field Schema <a id="job-posting-field-schema"></a>

This following table lists and describes the job fields supported by the Limited Listings XML feed:

 Note

Fields that are not mandatory are recommended.

| JOB POSTING FIELD SCHEMA |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- |
| Field Name | Field | Description | Mandatory | Value Type |
| Last Build Date | lastBuildDate | Most recent feed generation timestamp | No | String |
| Publisher URL | publisherURL | Your public web presence | No | String |
| Publisher | publisher | Your company name | No | String |
| Expected Job Count | expectedJobCount | Expected job count for the next feed scrape | No | Integer |
| Partner Job ID | partnerJobId | The unique ID used by the partner to reference the job within their own system | Yes | String \(max. 40 chars\) |
| Company Name | company | Company name of the client \(name of the employer\) | Yes | String |
| Job Title | title | Title of the job. This field cannot be changed once the job is posted | Yes | String |
| Job Description | description | Description of job responsibilities. Requires a minimum of 100 characters to be considered as valid. Accepts a limited set of [HTML tags](https://docs.microsoft.com/en-us/linkedin/talent/job-postings/xml-feeds-development-guide#formatting-guidelines) | Yes | String \(min. 100 chars\) |
| Apply URL | applyUrl | URL to which candidates are directed to apply \(typically the URL of the job on the client's website or ATS system\) | Yes | URL starting with "https://www" |
| Company ID | companyId | Client's company ID on Linkedin. This can be found in the Admin URL for the LinkedIn Page | Yes \(for ATSs\) | Refer [Steps to identify numeric CO ID](https://www.linkedin.com/help/linkedin/answer/a415420/associating-your-linkedin-company-id-with-the-linkedin-job-board-frequently-asked-questions?lang=en) |
| Location | location | This is a description of the job location. US locations - City, State \(for example, “San Francisco, CA”\) Non-US locations - City, Country \(for example, “London, United Kingdom”\) LinkedIn automatically maps this to a country and postal code unless those fields are provided. Separate jobs need to be created for different cities/locations | Yes | String |
| City | city | City of the job location \(for example, “San Francisco”\) | Yes, only if location is not provided | String |
| State | state | State of the job location \(for example, “California”\) | Yes, only if location is not provided | String |
| Country | country | Country of the job location \(for example, “US”\) | Yes, only if location is not provided | String Code from [Country Codes](https://docs.microsoft.com/en-us/linkedin/shared/references/reference-tables/country-codes) |
| Postal Code | postalCode | Postal code of the job location | No | String |
| Is Remote Job | isRemote | Whether a job is hiring remote applicants or not. Location \(city and country\) is a mandatory field for Remote jobs. Available options are: Yes, No | No | String |
| Industry Codes | industryCodes | List of industry codes for the company | No | List of industryCode elements |
| Industry Codes&gt; Industry Code | industryCodes/ industryCode | Represents industries of this job or company. Industry IDs are predefined by LinkedIn and can be retrieved from Industry Codes reference table | No | Numeric Code from [Industry Codes](https://docs.microsoft.com/en-us/linkedin/shared/references/reference-tables/industry-codes) |
| Experience Level | experienceLevel | Experience level of the job position to hire. Available options are: ENTRY\_LEVEL, MID\_SENIOR\_LEVEL, DIRECTOR, EXECUTIVE, INTERNSHIP, ASSOCIATE, NOT\_APPLICABLE | No | String |
| Job Functions | jobFunctions | List of job functions for this job | No | List of jobFunction elements |
| Job Functions&gt; Job Function | jobFunctions/ jobFunction | Represents job functions specific to this job \(for example, Accounting, Marketing, Sales\). Category names are predefined by LinkedIn and can be retrieved from Job Functions Codes reference table | No | String Code from [Job Function Codes](https://docs.microsoft.com/en-us/linkedin/shared/references/reference-tables/job-function-codes) |
| Job Type | jobtype | Employment status of the job position. Available options are: FULL\_TIME PART\_TIME, CONTRACT, INTERNSHIP, VOLUNTEER | No | String |
| Salaries | salaries | Provided salary for this job posting. Each &lt;salary&gt; object under the &lt;salaries&gt; list should represent a component of the total salary for the job | No | List of salary elements |
| Salaries &gt; Salary &gt; High End/Low End &gt; Amount | salaries/salary/ highEnd\(lowEnd\) /amount | The value for the higher/lower end of the range of the salary for this job posting | No | Integer |
| Salaries &gt; Salary &gt; High End/Low End &gt; Currency Code | salaries/salary/ highEnd\(lowEnd\) /currencyCode | The currency for the higher/lower end of the range of the salary for this job posting | No | String Code from [Currency Codes](https://docs.microsoft.com/en-us/linkedin/shared/references/reference-tables/currency-codes) |
| Salaries &gt; Salary &gt; Period | salaries/ salary/period | The time period that this salary component is given at. Available options are: YEARLY, MONTHLY, SEMIMONTHLY, BIWEEKLY, WEEKLY, DAILY, HOURLY, ONCE | No | String |
| Salaries &gt; Salary &gt; Type | salaries/ salary/type | The type of this salary component. Available options are: BASE\_SALARY, TOTAL\_ADDITIONAL | No | String |
| List Date | listDate | The day the job was first posted on LinkedIn | No | String |
| Expiration Date | expirationDate | Date at which the job is expected to close | No | String |

#### Formatting Guidelines <a id="formatting-guidelines"></a>

The following HTML tags are supported for description field. Other HTML tags will be stripped out, and their contents will be displayed as plain text.

| FORMATTING GUIDELINES |  |
| :--- | :--- |
| Tag | Description |
| &lt;b&gt;, &lt;strong&gt; | Bold/Strong |
| &lt;u&gt; | Underline |
| &lt;i&gt; | italic |
| &lt;br&gt; | Line Break |
| &lt;p&gt; | Paragraph |
| &lt;ul&gt; | Unordered List |
| &lt;li&gt; | Ordered List |

### XML Feed Considerations <a id="xml-feed-considerations"></a>

LinkedIn recommends the following feed considerations:

* Ensure all required fields are populated correctly
* Ensure Partner Job Id has a maximum length of 40 characters to be considered as valid
* Ensure job descriptions have a minimum of 100 characters to be considered as valid
* Minimize the number of expired jobs in your XML feed
* Minimize the number of duplicate jobs in your XML feed
* Do not use your company name or other job boards’ company name in place of the name of the company that originally posted the job
* Include maximum information about the location such as full name of cities and countries. Providing only a city name can be ambiguous

### Requirement Considerations <a id="requirement-considerations"></a>

LinkedIn recommends the following requirement considerations:

* Do not have duplicate jobs in feeds
* Do not close and reopen jobs repeatedly
* Do not use redirecting URLs for jobs
* LinkedIn only accepts jobs that are directly posted by employers on your platform. Once the member clicks the 'Apply' button for these jobs on LinkedIn, they should be directly taken to the site where they can complete the application process. Ensure to exclude jobs from the feed that are aggregated from other third-party sites
* A feed can contain maximum 500K jobs. However, for feeds with 500k jobs or more \(large partners\):
  * Split jobs into several feeds based on country location
  * Do not rotate jobs between feeds. Each feed should contain unique and consistent jobs to avoid having a job show on one feed today and later \(or also\) on another feed. Refer the below example of job rotation that may lead to errors at our end:

    | TABLE 3 |  |  |
    | :--- | :--- | :--- |
    | Day | Source | Job ID |
    | 1 | partition1 | 123 |
    | 1 | partition2 | 456 |
    | 2 | partition1 | No Job ID with 123 |
    | 2 | partition2 | 123 |

### Example XML Feed <a id="example-xml-feed"></a>

Spider Name: Jobs\_xmlHTMLCopy

```text
<?xml version="1.0" encoding="UTF-8"?>
<source>
    <lastBuildDate>Thu, 11 Sep 2014 19:39:59 GMT</lastBuildDate>
    <publisherUrl>[https://www.linkedin.com%3c/publisherUrl%3e]https://www.linkedin.com</publisherUrl>
    <publisher>LinkedIn</publisher>
   <expectedJobCount><![CDATA[5596]]></expectedJobCount>
    <job>
        <partnerJobId><![CDATA[12345]]></partnerJobId>
        <company><![CDATA[LinkedIn]]></company>
        <title><![CDATA[Staff Software Engineer - Applications]]></title>
        <description><![CDATA[LinkedIn was built to help professionals achieve more in their careers, and every day millions of people use our products to make connections, discover opportunities and gain insights. Our global reach means we get to make a direct impact on the world’s workforce in ways no other company can. ... ]]></description>
        <industry><![CDATA[Internet,Information Technology and Services]]></industry>
        <applyUrl><![CDATA[https://www.linkedin.com/jobs/view/1234?trk=linkedin]]></applyUrl>
        <companyId><![CDATA[xxxx]]></companyId>
        <location><![CDATA[Sunnyvale, CA, US]]></location>
        <city><![CDATA[Sunnyvale]]></city>
        <state><![CDATA[CA]]></state>
        <country><![CDATA[US]]></country>
        <postalCode><![CDATA[94085]]></postalCode>
        <industryCodes>
            <industryCode><![CDATA[120]]></industryCode>
<industryCode><![CDATA[125]]></industryCode>
        </industryCodes>
        <jobFunctions>
            <jobFunction><![CDATA[eng]]></jobFunction>
            <jobFunction><![CDATA[it]]></jobFunction>
        </jobFunctions>
        <experienceLevel><![CDATA[MID_SENIOR_LEVEL]]></experienceLevel>
        <salaries>
            <salary>
                <highEnd>
                    <amount>![CDATA[100000]]</amount>
                    <currencyCode>USD</currencyCode>
                </highEnd>
                <lowEnd>
                    <amount>![CDATA[50000]]</amount>
                    <currencyCode>USD</currencyCode>
                </lowEnd>
                <period>![CDATA[yearly]]</period>
                <type>![CDATA[BASE_SALARY]]</type>
            </salary>
            <salary>
                <highEnd>
                    <amount>![CDATA[50000]]</amount>
                    <currencyCode>USD</currencyCode>
                </highEnd>
                <lowEnd>
                    <amount>![CDATA[20000]]</amount>
                    <currencyCode>USD</currencyCode>
                </lowEnd>
                <period>![CDATA[yearly]]</period>
                <type>![CDATA[TOTAL_ADDITIONAL]]</type>
            </salary>
        </salaries>
        <isRemote><![CDATA[Yes]]></isRemote>
    </job>
    <job>
    ...
    </job>
</source>

```

### Referenced Links <a id="referenced-links"></a>

* [Country Code](https://docs.microsoft.com/en-us/linkedin/shared/references/reference-tables/country-codes)
* [Industry Codes](https://docs.microsoft.com/en-us/linkedin/shared/references/reference-tables/industry-codes)
* [Job Function Codes](https://docs.microsoft.com/en-us/linkedin/shared/references/reference-tables/job-function-codes)
* [Currency Codes](https://docs.microsoft.com/en-us/linkedin/shared/references/reference-tables/currency-codes)
* Retrieving a LinkedIn Company ID: [https://www.linkedin.com/help/linkedin/answer/a415420](https://www.linkedin.com/help/linkedin/answer/a415420)

