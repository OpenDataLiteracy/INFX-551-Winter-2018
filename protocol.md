---
Title: Data Curation Protocol
Date: 01.01.2017
Course: INFX 551 - Foundations of Data Curation
---

# Protocol Report 

**Abstract** 

This protocol addresses the curation of licensing data for pets that reside in the two largest cities in the USA: Los Angeles, CA; and New York City, NY. While a larger cache of data related to all licensed pets is available in the `Raw` data folders, this protocol focuses specifically on normalizing and providing documentation about dog licensing data obtained from the two cities. 

These two cities were chosen for strategic reasons; both are located in states with Freedom of Information laws that require the release of public records [1], and they represent two geographically, culturally, and environmentally distinct areas to compare pet ownership. Further, the data provided in this repository allows one to explore the thesis put forward by Stefanos Chen that dog ownership can be used as a proxy to neighborhood gentrification. That is, patterns in dog breed ownership may correlate with certain owner demographics, and tracing licensing data across the geography of a large city can result in a deeper understanding of human migratory patterns [2].   

Data were obtained from a number of different sources - each described (by city) in detail below: 

- Los Angeles: An initial dataset listing breeds, zip codes, and birthdates of dogs were obtained from the open data platform [MuckRock](https://www.muckrock.com/) - a subsequent FOIA request was submitted for data the LA country of Department of Animal Services which resulted in [an unnormalized dataset]( https://cdn.muckrock.com/foia_files/Lics_by_Zip_w_Animal_Names_1.txt) in an Excel (XLSX) format, with no additional metadata or documentaiton available (discussion of documentation is below).

- New York City: An [initial dataset](https://cdn.muckrock.com/foia_files/2016/04/29/NYC_Dog_Licenses_Current_as_of_4-28-2016.xlsx) was obtained from the open data platform MuckRock in an Excel (XLX) format, with no additional documentation These data were incomplete in a number of ways, including a missing zip code, and secondary breed name. A [second dataset](https://data.cityofnewyork.us/Health/NYC-Dog-Licensing-Dataset/nu7n-tubp) was obtained from the [New York City Open Data portal](https://data.cityofnewyork.us) to supplement the original. The two datasets were combined (as described in detail below) to form a composite dataset that was normalized following the best practices outlines in this protocol.  

For the rest of this document the two data sources will be referred to as LA and NY as a shorthand. 

**Data Management**

LA and NY data were obtained, as described above, from multiple online sources, but both originated from published FOIA requests to the MuckRock open data platform. Both datasets also aggregate information that is filled out by a city resident when they register a new dog, or renew a dogs current license. The application for a new and renewal license in LA [3] and NY [4] ask demographic information about owners, as well as breed, vaccination, and age information about pets. For the sake of 

Both datasets were originally published as Excel formatted files - and both had macro-formulas that calculated or summed certain values. For the sake of long-term preservation, both original XLSX formats, and a converted TSV (UTF-8 encoding) will be stored. This allows users that want to obtain the raw data to ensure that there is no difference between the originally published data and the normalized data. 

In total then, there will be six files total available, three from each city: 

- LA: Original XLSX file, a TSV File that migrates all content from the original XLSX file, and a normalized TSV file.  
- NY: Original XLSX file, a TSV File that migrates all content from the original XLSX file, and a normalized TSV file.

**Documentation** 

**Explanation**

This protocol uses the V1 [Project Open Data (POD)](https://project-open-data.cio.gov/v1.1/schema/ ) schema to create structured metadata at file level. POD was chosen because the data being curated are from local governments, and the audience is a general public. POD was designed specifically to provide attribute-value pairs that help a general public make use of open government data. The POD standard requires 10 attribute value pairs - all of which were included in the structured metadata for these datasets - with the exception of bureauCode and programCode - both of which do not apply to these datasets. 

Four 'optional' attributes from the POD metadata schema were included: 

- Spatial - The place, or area covered by the dataset - which is either LA county, or New York City (This was chosen so that a designation between different files could easily be recognized by potential reusers.)
- Temporal - The period covered by each dataset - which ranges from 2010-2016 (This was chosen because the two datasets have slightly different dates of coverage, which may limit comparisons.)
- DescribedByType - The machine readable file format - for these files is either XSLX, or TSV (This was chosen to clearly communicate the formats that are available for reuse.)
- Theme - Main category addressed by the data - for these data will be Dog Licenses. (This was chosen so that a broad search in a repository might easily turn up the data related to dog licenses - as opposed to more general datasets related to pet licensing)

All metadata were created in XML compliant metadata (see repository for actual files.)

In addition to structured metadata, an unstructured `ReadMe.txt` file is included in the following repository. The ReadMe includes information about the sources from which data were obtained, file formatting and naming conventions, and how data were transformed

Data normalization performed: 

- - Zip codes - All zip codes have been converted to standard 5 digit formats
- - Breeds - Breeds have been separated into two columns - Main and Secondary. Mixed breeds and "mut" (and all its variants) were transformed to Mixed in both Main and Secondary column. All blank, and "unknown" have been converted to NA. Non-english characters were removed (e.g. Japanese characters) and replaced by English name for breed. 
- - Birth Date -  Birth dates have been normalized to MM-DD-YYYY
- - Age at Registration - A variable was created that calculates the date of the license application and the age of the dog. This could be useful for a number of different questions about the age of rescued dogs, etc. 

The readme.txt file also established a file naming convention with the following logic:

Two Letter City Code (either NY or LA) - Title (always PetLicenseData) - State (either Original or Normalized) - and Date Last Updated (using the MMDDYYYY format)

An example file name using this convention then is as follows: 

`NY_PetLicenseData_Original_01012017.tsv` 


A data dictionary that describes each variable is included in the ReadMe.txt file as a table. 

**Data** 

The repository contains the following datasets

LA: 
- LA_PetLicenseData_Original_01012018.xlsx - Original XLSX file with 14 variables
- LA_PetLicenseData_Original_01012018.tsv Migrated TSV file with 14 variables 
- LA_PetLicenseData_Normalized_01012018.tsv Normalized data with 16 variables 

NY: 
- NY_PetLicenseData_Original_01012018.xlsx - Original XLSX file with 12 variables
- NY_PetLicenseData_Original_01012018.tsv Migrated TSV file with 12 variables 
- NY_PetLicenseData_Normalized_01012018.tsv Normalized data with 14 variables 

**Reflection** 

In the chapter "Conceptualizing Data" Rob Kitchin differentiates data, and by extension data curation tasks, along a number of lines: spatial and temporal resolution; ethical; philosophical; economic and political, etc [5]. The data that I choose to curate for this protocol appear, at first glance, to be ethically and politically neutral. But, even initial analysis necessary to explore the data demonstrated some curious trends, and troubling public information disclosures. For example, the NYC open data portal published a dataset that included nine digit zip-codes that allow for fairly granular location data. When combined with the FOIA dataset, which not only includes breed, but also name (oten including owners who list their dog's last name) there is the potential to identify owners by their pets - this gets even more accurate if there is a known rare breed owner. 

To normalize the data and remove this information, I choose to eliminate nine digit zip codes (which may in fact make the data less valuable for some research purposes) as well as last names that were included with dogs license information. This goes against some of the literature that we read about "data quality" in this course, including recommendations on long term data storage and provenance [6]. However, as Floridi argues privacy should trump accuracy in the public record [7]. 

I believe there are a number of ways in which the release of public records - of the type that were posted to MuckRock and used in this exercise - could be improved. First, data that are made available to the public should come with a set of license, terms of use, and structured metadata. This would make understanding the origins of this data much easier, and eliminate guesswork that goes into drawing inferences from under-described variables. Second, as discussed through the quarter, there is a need to use open and non-proprietary formats so that data can be reliably archived. Each of these datasets were provided by government bodies (and MuckRock) in Excel formatted tables. Third, and most importantly the data that were generated as the result of public records request were never made available by LA county, or NYC open data program. It seems like an incredibly large waste of government resources to provide data to the public ONLY when requested. Each dataset could have been easily deposited in the city's open data repository for other citizens to discover and use. 

This assignment also brought to light the need to coordinate and plan for documentation at varying levels of granularity. For example - the POD standard allowed for easily creating file level metadata, but did not clearly have a way to create collection level metadata that would describe all six datasets. I also sought a better way to connect individual variables described in the data dictionary to the structured metadata. This is a feature of the DDI metadata standard for social science data, and I believe future versions of POD should also include the capability to create formal representations of data variables in structured metadata (as attribute-value pairs).  
 

**Works Cited** 

[1] - New York: https://www.dos.ny.gov/coog/foil2.html and California: http://www.leginfo.ca.gov/cgi-bin/displaycode?section=gov&group=06001-07000&file=6250-6270.5 

[2] We Analyzed Every Dog Registration in New York https://www.muckrock.com/news/archives/2016/may/17/nacho-chihuahua-what-people-name-their-dogs-new-yo/ 

[3] LA Dog License Application http://www.laanimalservices.com/wp-content/uploads/2011/06/DogLicenseApplication-English.pdf

[4] NY Dog License Application https://www1.nyc.gov/assets/doh/downloads/pdf/vet/vet-doglicense-form.pdf

[5] Kitchin, R. (2014). The data revolution: Big data, open data, data infrastructures and their consequences. Sage. 

[6] Goodman, A., Pepe, A., Blocker, A. W., Borgman, C. L., Cranmer, K., Crosas, M., ... & Hogg, D. W. (2014). Ten simple rules for the care and feeding of scientific data. PLoS computational biology, 10(4), e1003542.

[7] Floridi, L. (2014). Open data, data protection, and group privacy. Philosophy & Technology, 27(1), 1-3. 
