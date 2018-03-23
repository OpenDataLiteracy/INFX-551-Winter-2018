---
Title: Data Curation Protocol
Course: INFX 551
Quarter: Winter 2018
Last revised: 03.21.2018
---

### Objectives
This assignment asks you to create a protocol for curating a set of data. Think of a protocol as a recipe – it provides procedural steps as well as a list of necessary materials (ingredients) to produce a consistent (replicable) outcome.

In this case, you will be finding some structured or unstructured data (see sources below), transforming that data to be compliant with a community standard, creating metadata to describe the data, and documenting your plan to manage this data over time.

You are to choose both a project topic and an intended audience from the lists below. You can mix and match topics and audiences as you see fit. For example, I might want to curate recycling data for urban planning researchers; or, Public Library data for a citizen activist groups.

These are very broad topics and audiences – this assignment will require you to do some background research, and potentially even use tools like Tabula to extract relevant data from unstructured sources (e.g. PDFs). Describing this work in detail, as well as justifying your choices is part of the challenge (and fun!) of this assignment. You should not feel bound to use only the suggested resources below. Go explore and find other related data.

You may also choose a topic or audience outside of this list – but you MUST get permission from your instructor to do so. Please email me and your TA with a relevant topic and audience if you are NOT choosing one from the proposed list below.

All data used for this assignment MUST be openly accessible, and without personally identifying information.

### Suggested Topics

**Homeless Counts**

One of the most basic challenges in combatting homelessness is obtaining an accurate and reliable measure of how many people are homeless, for how long, and in what locale. Often, this problem is made worse by competing (and contradictory) definitions of what homeless means. There are also many different methodologies and strategies for constructing a homeless census in the USA. The goal of this protocol should be to create a resource that either:

- Contains homogenous homelessness count data (e.g. All the cities that depend on event-based counts)
- Represents heterogeneous homeless count data (e.g. How cities in the same state (WA) collect different homeless data)

Some relevant data sources:

- Seattle King County Homeless data http://allhomekc.org/wp-content/uploads/2016/11/2017-Count-Us-In-PIT-Comprehensive-Report.pdf (Links to an external site.)Links to an external site.
- Washington Homeless Data http://www.commerce.wa.gov/wp-content/uploads/2015/08/Commerce-Homelessness-in-Washington-2016.pdf (Links to an external site.)Links to an external site.
- Homeless student data http://www.k12.wa.us/LegisGov/2015documents/HomelessStudentsJan2015.pdf (Links to an external site.)Links to an external site.
- HUD data http://www.hudhdx.info/ (Links to an external site.)Links to an external site. + https://www.hudexchange.info/programs/coc/coc-homeless-populations-and-subpopulations-reports/ (Links to an external site.)Links to an external site.


**Recycling Effectiveness**

Measuring the efficacy of recycling programs in the USA is difficult for a variety of reasons: not all municipalities offer curbside pick-up, recyclable materials are tracked and measured differently in different states, etc. Increasingly, researchers and policymakers want to know more about what programs work, where, and for which reasons? The goal of this protocol should be to locate data that is representative of 3 or more municipal recycling programs in the USA.

Some relevant data sources:
- City of Seattle Annual Recycling Report http://www.seattle.gov/util/cs/groups/public/@spu/@garbage/documents/webcontent/1_064754.pdf
- State of Washington Recycling Data https://ecology.wa.gov/Research-Data/Data-resources/Solid-waste-recycling-data
- Pew Survey on Attitudes towards Recycling http://www.pewresearch.org/fact-tank/2016/10/07/perceptions-and-realities-of-recycling-vary-widely-from-place-to-place/
- Statstica Reports on Recycling Data https://www.statista.com/topics/1275/recycling-in-the-united-states/
- EPA Data on Waste and Recycling (by state!) https://www.epa.gov/smm/advancing-sustainable-materials-management-facts-and-figures
- Gov holdings on Recycling https://catalog.data.gov/dataset?tags=recycling


**Public Libraries**
As a whole, the United States invests a great deal of local resources in public libraries. Traditionally, these institutions have been slow to publish data that support their local impacts, but some public libraries are beginning to publish data about their circulation, service populations, programming, etc  The goal of this protocol should be to create a resource that either:

- Contains homogenous data about public libraries (e.g. a dataset of 3-5 cities circulation records)
- Represents heterogeneous types of public library data (e.g. a dataset of circulation data, programming data, door-count data, etc).

Some relevant resources:
- OCLC Circulation Data https://www.oclc.org/research/themes/systemwide-library/ohiolink/circulation.html
- Open Gov Data on Libraries in the USA https://catalog.data.gov/dataset?tags=library
- Public Library Service Report https://storage.googleapis.com/co_drive/Documents/PLDS/2017PLDSReport(FINAL).pdf

Your protocol must identify a target audience. This is whom you will be curating data for, in other words - these are the data users.
- Policymakers
- Journalists
- Citizen Activist groups (e.g.
- Researchers (e.g. Urban Planning, Public Health, Public Policy, Social Workers / Social Services.) (note: you should just choose one.)


### Deadlines
- By March 2nd, you should post to the Discussion Forum the topic that you will be working on, the data source you will be using (or creating). Again, if you plan to choose a topic or audiences that is NOT on this list you must have approval of your instructor beforehand.
- Your complete protocol is due on March 15th.  The final protocol that you turn in should include all of the components described below.


### Protocol Report

**Project Abstract**
- Describe the problem that the data are meant to address
- Describe the data
- - What is the topic of this dataset / collection?
- - From where were data obtained?
- - What are some challenges in finding, accessing, or comparing different sources for this data?
- Describe the intended audience for this dataset / collection
- - What might be the needs for this community to meaningfully use this data?
- - What might be some intended uses?

You should imagine your audience for this abstract as fellow curators, potential data reuses, etc. That is to say, I want you to write this as if it were aimed at helping potential users of the data understand how the data were curated, why you made the decisions you did, etc.

**Data Management**
This should describe (in 1-2 paragraphs):
- The origin of the data - where did it come from, how was it collected, and how should it be transformed for long-term storage?
- The format the data was obtained in, and the format it should be stored in.

**Documentation**
Structured Metadata: Choose a descriptive metadata schema (from those listed below) and create a record for each data file in your dataset. You may choose to encode this in XML, or you may simply create a table listing attribute value pairs.
- Project Open Data- https://project-open-data.cio.gov/v1.1/schema/
- Dublin Core- http://dublincore.org/
- DDI - http://www.ddialliance.org
- For a complete list of research data schemas http://rd-alliance.github.io/metadata-directory/subjects/

Create a Readme.txt file that explains:
- How data have been normalized
- The file naming convention that your dataset uses
- Any information about variable names, definitions etc. (you may choose to structure this like a data dictionary)

An explanation (1-2 paragraphs) that justifies the documentation that you created. For example, why did you use the particular metadata schema that you did? Did you choose to include or not include any metadata elements? Did you choose to create or leave out any information in the readme file?

**Data**
A data file, or set of data files (at most 3).
You must provide this data following best practices that we have described
The format must be open – meaning it does not require proprietary software to open and use.
All variables must be labeled, and explained or referenced in your documentation.
Values should follow best practices we discussed around data quality and normalization.
File names should follow the naming convention you described above.

**Reflection**
A 2-3 paragraph retrospective on the process of both curating this data, and documenting your steps in the protocol above. You may include things that were difficult or easier than expected, available standards, potential ways to improve data on this topic, etc. I want you to focus, as is possible, on using concepts from the course to guide your reflection (e.g. don’t say “the data were messy”… discuss characteristics of data quality that were missing or hard to improve for the data that you curated).
