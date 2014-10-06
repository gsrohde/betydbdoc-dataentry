#  BETYdb: Bulk Data Upload \label{sec:bulk_upload}

Currently the web interface does not support bulk data upload, although this is a planned feature for BETY 2.0.
 
There are three phases for a basic bulk upload of data : 

1. Use the web interface 
    * to enter metadata (new sites, citations, treatments, managements)
    * obtain a template appropriate for your data set.
2. Fill in the template with your data. 
 * [traits.csv](https://docs.google.com/spreadsheets/d/1lans4FMJ8avn34dcKkMzkEavqyZu6I4WuPP9oqeepc4/export?format=csv&gid=0) and can be downloaded in .xls format 
 * [yields.csv](https://docs.google.com/spreadsheets/d/1maK1uKr6i9KERaYdU5zSiXcBndQoiG4Vgn2DTnqdfbA/export?format=csv&gid=0).
3. Use the web interface to upload your data set and insert it into the database.

For now, only the steps needed to upload yields data will be outlined in order to make this case simpler. 

For clarity, in what follows, the term "field" wll be used to refer to the heading used in the uploaded CSV file and the term "column" or "attribute" to refer to an attribute of a yield datum in the yields table of the database. 

## **Required fields**:

1. For yields uploads, the only required field is a `yield` column.
2. For trait uploads, there must be at least one column whose label exactly matches the variable name for the trait value being specified.  (Leading and trailing spaces are permitted, but letter case must exactly match the name of the variable specified in the database.)

## Information that may be specified globally for the entire dataset.


1. Citation
    * If only one citation for the entire dataset exists, it may be specified interactively by choosing a citation on the citations page instead of including citation information in the CSV file.
    * Otherwise, specify the citation in the CSV table using either (doi) or (author, year, first n characters of (title)) for some number n; or perhaps (author, year, first 3 words of (title)) _[Clarify this.  Currently, the full title must be specified.]_
    * If a `citation_doi` is available for all citations in the data set, the citation corresponding to each row may be specified in a `citation_doi` column.  In this case, the `citation_author`, `citation_year`, and `citation_title` columns must all be deleted.  (Alternatively, the string `-ignore` may be appended to each of these headings.  One might want to do this, for example, to keep a visual record of the author, year, and title even when it is the citation doi that is being used to determine how the data will associated with a citation in the database.)
    * Conversely, if a `citation_doi` is not available for all citations in the data set, or if it is preferred to specify the citation by author, year, and title, then the `citation_doi` column should be deleted and the `citation_author`, `citation_year`, and `citation_title` must all be entered. 
2. Site
    * If all of the data in the data set pertains to a single site, that site may be specified interactively.
    * Otherwise, the `site` column is required.  The value must match an existing `sitename` column value in the `sites` table of the database.  (Letter case, leading and trailing spaces, and extra internal spaces are ignored when searching for a match.) 
3. Species
    * If all of the data in the data set pertains to a single species, that species may be specified interactively.
    * Otherwise, the `species` column is required.  The value must match an existing `scientificname` column value in the `species` table of the database.  (Again, letter case, leading and trailing spaces, and extra internal spaces are ignored when searching for a match.) 
4. Treatment
    *       use name 
5. date: require one of the forms "2003-07-25", "2003-07", or "2003".

Of these, the citation, site, species, treatment, and access_level may be specified interactively when uploading the dataset (if they are uniform for the whole set) rather than appearing as a field or set of fields of the CSV file. As noted above, for citations, this is done outside of the upload wizard by choosing a citation on the citations page.  

## **Data for Yields** 
1. mean: must be one of the fields of the CSV table, though for uploads of yields data, we will by default call this field "yield" in the provided templates
2. n: required if and only if an SE column is given 
3. SE: required if and only if an n column is given; this datum will be inserted into the stat column, and the statname will be set to "SE" access_level 

## **Data for Traits** 
1. \<variable\_1\>, \<variable\_2\>, ... \<variable\_n\>: 
   These column names should be replaced with values from \ref{tab:traits} (or see the [variables table](https://www.betydb.org) for a comprehensive listing).
2. \<covariate\_1\>, \<covariate\_2\>, ... \<covariate\_n\>
   these columns should be replaced with values from \ref{tab:covariates}.
3. To enter n and SE, add additional columns "\<variable\_1\> n" and "\<variable\_1\> SE" as needed.
 

## **Optional fields**:

1. n and SE: as noted above, if one of these is present, the other must be as well; if SE is given, the value will go into the stat column of the yields table, and the statname column will be set to "SE" 
2. cultivar: use name; defaults to NULL (for the cultivar_id column) if not provided 
3. notes: defaults to the empty string if not provided 
If a uniform value for the species is provided interactively when uploading the data set, the cultivar may be specified this way as well provided that it also has a uniform value for the whole data set. If n and SE are not given fields of the uploaded CSV file, the value of the n column of the yields table will default to 1 and the stat and statname column values will default to NULL. 
