# Workflow for the Biofuel Ecophysiological Traits and Yields Database (BETYdb)

This is the userguide for entering data into the BETYdb database. The goal of this guide is to provide a consistent method of data entry that is transparent, reproducible, and well documented. The steps here generally accomplish one of two goals. The first goal is to provide data that is associated with the experimental methods, species, site, and other factors associated with the original study. The second goal is to provide a record of all the transformations, assumptions, and data extraction steps used to migrate data from the primary literature to the standardized framework of the database.
      
You will need to create the following accounts:

* Redmine https://ebi-forecast.igb.illinois.edu/redmine/account/register  
* BETYdb https://www.betydb.org/signup  
* GitHub https://github.com/  
* Mendeley www.mendeley.com/ 

## <a id="Section_2.1"></a>  Using Mendeley

Mendeley provides a central location for the collection, annotation, and tracking of the journal articles that we use. Features of Mendeley that are useful to us include: 

* Collaborative annotation & notes sharing
    * Text highlighter   
    * Sticky notes for comments in the text
    * Notes field for text notes in the reference documentation
* Read/ unread & favorites:
Papers can be marked as **read** or **unread**, and may be **starred.**
* Groups
* Tagging


Each project has two groups: "projectname" and "projectname_out" for the papers with data to be entered and for the papers with data that has been entered, respectively. Papers in the _out group may contain data for future entry (for example, traits that are not listed in [Table 6](#Table 6)). 

Each project manager may have one or more projects and each project should have one group. Group names should refer to plant species, plant functional types, or another project specific name. A list of current groups can be found in [Table 1](#Table 1). Please make sure that, at a minimum, Mike Dietze and David LeBauer are invited to join each project folder. 

   1. Open Mendeley desktop
   2. Click `Edit` → `New Group` or `Ctrl+Shift+M`
   3. Create group name following instructions above
   4. Enter group name 
   5. Set `Privacy Settings` → `Private`
   6. Click `Create Group`
   7. Click `Edit Settings`
   8. Under `File Synchronization`, check `Download attached files to group`

### <a id="Section_2.2"></a>  Adding and Annotating Papers  

When naming a group, tag folders so that instructions for a technician would include the folder
and the tag to look for, e.g. "please enter data from projectx" or
"please enter data from papers tagged y from project x".
To access the full text and PDF of papers from off campus, use the [UIUC
VPN](http://www.cites.illinois.edu/vpn/download-install.html) service.
If you are managing a Mendeley folder that undergraduates are actively
entering data from, please plan to spend between 15 min and 1 hour per
week maintaining it - enough to keep up with the work that the
undergraduates are doing.

###  Adding a reference to Mendeley

-   If the DOI number is available (most articles since 2000)
    1.  Select project folder
    2.  Right click and select `Add entry manually...`
    3.  Paste DOI number in *DOI* field
    4.  Select the search spyglass icon
    5.  Drag and drop PDF onto the record.
-   If DOI not available:
    1.  Download the paper and save as `citation_key.pdf`
    2.  Add using the *Files* field
    3.  The citation key should be in `authorYYYYabc` where `YYYY` is
        the four digit year and `abc` is the acronym for the first three
        words excluding articles (the, a, an), prepositions (on, in,
        from, for, to, etc...), and the conjunctions (for, and, nor,
        but, or, yet, so) with less than three letters.

###  Annotating a Reference in Mendeley

Each week, please identify and prepare papers that you would like to be
entered next by completing the following steps:  

1. Use the star label to identify the papers that you want the student
    to focus on next.  
    -   Start by keeping a minimum of 2 and a maximum of 5 highlighted
        at once so that students can focus on the ones that you want.
        Students have been entering 1-3 papers per week, once we get
        closer to 3-5, the min/max should change.  
    -   Choose papers that are the most data rich.  

2. For each paper, use comment bubbles, notes field, and highlighter to indicate:
    -   Name(s) of traits to be collected
    -   Methods:
       * Site name
       * Location
       * Number of replicates
       * Statistics to collect
       * Identify treatment(s) and control
       * Indicate if study was conducted in greenhouse, pot, or growth chamber  
    -   Data to collect
       * Identify figures number and the symbols to extract data from.
       * Table number and columns with data to collect
    -   Covariates
    -   Management data (for yields)
    -   Units in 'to' and 'from' fields used to convert data
    -   Esoteric information that other scientists or technicians might not catch and that is not otherwise recorded in the database
    -   Any data that may be useful at a later date but that can be skipped for now.

####  **Comment or Highlight** the following information

* Sample size
* Covariates (see [Table 7](#Table 7))
* Treatments
* Managements
* Other information entered into the database, e.g. experimental
    details

###  Finding a citation in Mendeley

To find a citation in Mendeley, go to the project folder. Group folders
and personnel are listed in [Table 1](#Table 1). By default, data entry technicians should
enter data from papers which have been indicated by a yellow star and in
the order that they were added to the list. Information and data to be
collected from a paper can be found under the 'Notes' tab and in
highlighted sections of the paper.

<a id="Section 3"></a> 
## Google Spreadsheets: Recording data transformations
Google Spreadsheets are used to keep a record of any data that is not
entered directly from the original publication.

* Any raw data that is not directly entered into the database but that
    is used to derive data or stats using equations in [Table 1](#Table 1) and [Table 5](#Table 5).
* Any data extracted from figures, along with the figure number
* Any calculations that were made. These calculations should be
    included in the cells.

Each project has a Google document spreadsheet with the title
’’project\_data’’. In this spreadsheet, each reference should have a
separate worksheet labeled with the citation key (`authorYYYabc`
format). Do not enter data into excel first as this is prone to errors and
information such as equations may be lost when uploading or
copy-pasting.

## Redmine: Reporting errors, suggesting features

#### Reporting errors in Redmine 
1. Go to [Redmine: BetyDB] (https://ebi-forecast.igb.illinois.edu/redmine/projects/bety-db/) project page.
2. Click the `New Issue` tab in the center of the ribbon. 
3. Set `Tracker` to `Bug`
4. Fill out necessary fields
5. Click `Create`  

####  Suggesting features in Redmine
1. Go to [Redmine: BetyDB] (https://ebi-forecast.igb.illinois.edu/redmine/projects/bety-db/) project page.
2. Click the `New Issue` tab in the center of the ribbon. 
3. Set `Tracker` to `Feature`
4. Fill out necessary fields
5. Click `Create`  

## BETYdb: QA/QC with the Web Interface

Quality assurance and quality control (QA/QC) is a critical step that is
used to ensure the validity of data in the database and of the analyses
that use these data. When conducting QA/QC, your data access level needs
to be elevated to “manager”.

1.  Open citation in Mendeley
2.  Locate citation in BETYdb
    -   Select `Use`
    -   Select `Show`
    -   Check that author, year, title, journal, volume, and page
        information is correct
    -   Check that links to URL and PDF are correct, using DOI if
        available
    -   If any information is incorrect, click ’edit’ to correct
3.  Check that site(s) at bottom of citation record match site(s) in
    paper
    -   Check that latitude and longitude are consistent with
        manuscript, are in decimals not degrees, and have appropriate
        level of precision
    -   Click on site name to verify any additional information site
        information that is present
    -   Enter any additional site level information that is found
4.  Select
    [treatments](http://www.betydb.org/treatments/) from
    menu bar
    -   Check that there is a control treatment
    -   Ensure that treatment name and definition are consistent with
        information in the manuscript
    -   Under “treatments from all citations associated with associated
        sites”, ensure that there is no redundancy (i.e. if another
        citation uses the same treatments, it should not be listed
        separately)
    -   If managements are listed, make sure that managment-treatment
        associations are correct
5.  Check [managements](http://www.betydb.org/managements/) if
    there are any listed on the treatments page.
    -   If yield data has been collected, ensure that required
        managements have been entered
    -   If managements have been entered, ensure that they are
        associated with the correct treatments
6.  Click [Yields](http://www.betydb.org/yields/) or
    [Traits](http://www.betydb.org/traits/) to check
    data.
    -   Check that means, sample size, and statistics have been entered
        correctly
    -   If data has been transformed, check that transformation was
        correct in the associated google spreadsheet (or create a new
        google spreadsheet following instructions)
    -   For any trait data that requires a covariate

