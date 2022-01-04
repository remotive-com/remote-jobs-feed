<p align=center>
<a href="https://remotive.io">
<img src="https://remotive.io/logo"/>    
</a>
</p>

# Remote Jobs Feeds

## About remotive.io
We're one of the largest Remote Work Community. Check out our:
- Our Remote [Job Board](https://remotive.io)
- Our vibrant [Slack Community](https://remotive.io/community)
- Read our [Manifesto](https://remotive.io/manifesto)!


At Remotive, we use XML feeds:
* to share our own live remote jobs with our community
* to receive remote jobs to publish from our partners

So whether you are a developper interested in our data or a partner willing to share remote jobs with us, and you want to do so using XML feed(s), then you are in the right place!

If you'd rather get our remote jobs using our public API, please check [over here](https://github.com/remotive-io/remote-jobs-api).

## I/ Getting Remotive's live remote jobs: our feeds by category

Please note that XML Feed documentation and access is granted so that developers can share our jobs further. Please do not submit Remotive jobs to third Party websites, including but not limited to: Jooble, Neuvoo, Google Jobs, LinkedIn Jobs. 

**Please link back to the URL found on Remotive AND mention Remotive as a source in order to Remotive to get traffic from your listing**. If you don't do that, we'll terminate your access, sorry! 

Here are XML feeds by job categories:
- [Sotware Development](https://remotive.io/remote-jobs/software-dev/feed)
- [Customer service](https://remotive.io/remote-jobs/customer-support/feed)
- [Design](https://remotive.io/remote-jobs/design/feed)
- [Sales](https://remotive.io/remote-jobs/sales/feed)
- [Marketing](https://remotive.io/remote-jobs/marketing/feed)
- [Product](https://remotive.io/remote-jobs/product/feed)
- [Business](https://remotive.io/remote-jobs/business/feed)
- [Data](https://remotive.io/remote-jobs/data/feed)
- [Devops/Sysadmin](https://remotive.io/remote-jobs/devops/feed)
- [Finance/Legal](https://remotive.io/remote-jobs/finance-legal/feed)
- [Human Resources](https://remotive.io/remote-jobs/hr/feed)
- [QA](https://remotive.io/remote-jobs/qa/feed)
- [Writing](https://remotive.io/remote-jobs/writing/feed)
- [All Others](https://remotive.io/remote-jobs/all-others/feed)

## II/ Sharing remote jobs with Remotive

If you are a Remotive's partner and want to share remote jobs with us automatically through XML feed, you are in the right place!

We are working with our partners both with:
* organic/free remote jobs feeds 
* premium/paid-for remote jobs feed

Get in touch with us at hello@remotive.io for more details and to share your feed(s) with us.

### 1. Expected Data to be made available on feed

At Remotive we are interested to display jobs:
- That are 100% remote
- More permanent positions (full-time, part-time, contract), less temporary freelance gigs
- In English language
- Mostly in IT domain / tech / web / software companies (see our job categories on https://remotive.io)

![Remotive's categories](/images/categories.png)

Remotive usually gets XML feed data with open job positions matching these criteria.

It is expected that positions listed at a given time are opened at that time. In other words, when Remotive fetches the XML feed URL, only open positions should be listed. 

Job listings that are not open anymore are expected to be removed from the list. Remotive will detect the jobs that were removed from the list and will remove it from its website (if it was published on Remotive’s website).

### 2. Data Format

Remotive expects the data in XML format. 
See our category feeds above for a live example.
Typical data structure should like like this (you may have different XML tag names, which is OK):

```xml
<?xml version='1.0'?>
<data>
   <jobs>
       ## 1 <job> entry for each job listing
       <job>
           ######### REQUIRED FIELDS ##########
           # A unique ID across your system that will allow Remotive to identify this job listing
           <job-id>002e1ea7bb19</job-id>

           # The job title
           <title>
               Backend Developer
           </title>

           # URL redirectiog to the job listing detail page on your website
           <url>
               https://url.that-redirects.to-your-job.listing.page
           </url>

           # Publication date should be provided for GMT timezone. E.g for 1st of September 2020 at 14:00:00 GMT:
           <publication-date>
               2020-09-01T14:00:00Z
           </publication-date>

           # The full HTML job description, wrapped into a "CDATA"
           <description>
               <![CDATA[
                   <h1>Job Description</h1>
                   <p>We are looking for ....</p>
               ]]>
           </description>

           # Name of company hiring
           <company-name>
               Remotive
           </company-name>

           # The job category. A mapping between your categories and Remotive's category may be discussed.
           <category>
               Software Development
           </category>

           ######### OPTIONAL FIELDS ##########
           # This is a string providing location restriction for the remote candidate
           <candidate-location-restriction>
               North America only
           </candidate-location-restriction>

            # This is a string providing location of the company offices, eg:
           <hq-location>
               New York, NYC, USA
           </hq-location>

           # One of the following values: full_time/part_time/contract/freelance/internship/other.
           # A mapping between your job types and Remotive's job types may be discussed.
           <job-type>
               full_time
           </job-type>

           # URL to the company logo
           <company-logo>
               https://url/to/the/company/logo.png
           </company-logo>

           # Short text describing the company hiring
           <company-description>
               Remotive helps IT professionals land remote jobs.
           </company-description>

           # Salary description. Recommended:The best format is $USD per year with no other text.
           <salary>
               $40-50K per year
           </salary>

       </job>

   </jobs>
</data>


```

