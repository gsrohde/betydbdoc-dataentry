
##  BETYdb: Entering new data through the web interface
Before entering data, it is first necessary to add and select the
citation that is the source of the data. It is also necessary for each
data point to be associated with a Site, Treatment, and Species.
Cultivar information is also required when available, but it is only
relevant for domesticated species. Fields with an asterisk (*) are
required. 

###  Adding a Citation
Citation provides information regarding the source of the data. This
section should allow us to locate and access the paper of interest.

A PDF copy of each paper should be available through Mendeley.

1.  Select one of the starred papers from your project's Mendeley folder.
2.  The data to be entered should be specified in the notes associated
    with the paper in Mendeley
3.  Identify (highlight or underline) the data (means and statistics)
    that you will enter
4.  Enter citation information 
    * [Data entry form](https://www.betydb.org/citations/new) for a new
        site: `BETYdb` → `Citations` → `new`
    *  **Author**: Input the first author’s last name only
    *  **Year**: Input the year the paper was published, not submitted, reviewed,
        or anything else
    *  Fill out Title, Journal, Vol, & Pg. For unknown information, input 'NA'
    *  **DOI**: The 'digital object identifier'. If DOI is available, PDF and
        URL are optional. This can be located in the article or in the
        article website. Use Ctrl+F 'DOI' to find it. Some older
        articles do not have a DOI.
    *  **URL**: Web address of the article, preferably from publisher's website
    *  **PDF**: URL of the PDF of the article 
5. [Form for entering a new citation](https://www.betydb.org/citations/new)   

![alt text](figures/newcite.png)

### Adding a Site

Each experiment is conducted at a unique site. In the context of BETY,
the term 'site' refers to a specific location and it is common for many
sites to be located within the same experimental station. By creating
distinct records for multiple sites, it is possible to differentiate
among independent studies.

1.  Before adding a site, search to make sure that site is not already
    entered in the database.
2.  Search for the site given latitude and longitude
    -   If an institution name or city and state are given, try to
        locate the site on Google Maps
    -   If a site name is given, try to locate the site using a
        combination of Google and Google Maps
    -   If latitude and longitude are given in the paper, search by lat
        and lon, which will return all sites within ± 1 degree lat and
        long.
    -   If an existing site is plausibly the same site as the one
        mentioned in the paper, it will be necessary to check other
        papers linked to the existing site.
        -   Use the same site if the previous study uses the *exact same
            location* and experimental setup.
        -   Create a new site if the study was conducted in a different
            fields (i.e., not the exact same location).
        -   Create a new site if one study was conducted in a greenhouse
            and another was conducted in a field.
        -   Do not use distinct sites for seed source in a common garden
            experiment (see ’When not to enter a new site’ below)
3.  To use an existing site, click `Edit` for the site, and then select
    current citation under `Add Citation Relationships`
4.  If site does not exist, add a new site.  
  
    
    | Descriptors              |      Additional Notes | 
|:-----------------------------|:-------------------------
| Site Name |Site identifier, sufficient to uniquely identify the site within the paper |
| City         | Nearest city                 |  
| State           | State, if in the US                |
| Country          |  Country     | 
| Longitude | Decimal Form. For conversion see the equation in [Table 9](#Table 9) |
| Latitude        | Decimal Form. For conversion see the equation in [Table 9](#Table 9)              |
| Greenhouse        | TRUE if plants were grown in a greenhouse, groth champer of post. FALSE if not used as control         |
| Soil             |By percent clay, sand, and silt if given               | 
| SOM      |Soil organic matter (% by weight)              | 
| MAT | Mean Annual Temperature (°C) |
| MAP | Mean Annual Percipitation (mm) |
| MASL |Elevation (meters above sea level, m) |
| Notes | Site Details not included above |
| Soil Notes | Soil details not included above |
| Rooting Zone Depth | Measured in Meters (m) |
|Depth of Water Table| Measured in Meters (m) |

5. Do **not** enter a new site When plants (or seeds) are collected from multiple locations   and then grown in the same location, this is called 'common garden experiment'. In this case, the location of the study is included as site information. Information about the seed source can be entered as a distinct cultivar.
 

### Site Location 

If latitude and longitude coordinates are not available, it is often
possible to determine the site location based on the site name, city,
and other information. One way to do this would be to look up a location
name in [Google Maps](http://maps.google.com) and then locate it on the
embedded map. Google Maps can provide decimal degrees if the LatLng
feature is enabled, which can be done
[here](http://maps.google.com/maps?showlabs=1). Google Earth can be
particularly useful in locating sites, along with their coordinates and
elevation. Alternatively, the site website or address might be found
through an internet search (e.g. Google).

Use Table 2 to determine the number of significant digits to indicate the level
of precision with which a study location is known.  

<a id="Table 2"></Table 2>
                 
| Location Detail |         Degree Accuracy  |
|:----------------|-------------------------:|
| City            |                      0.1 |
| Mile            |                     0.01 |
| Acre            |                    0.001 |
| 10 Meters       |                   0.0001 |
 
<a id="Figure 3"></a> ![alt text](figures/newsite.png)

**Figure 3**: [Form for entering a new site](https://www.betydb.org/sites/new)


### Adding a Treatment
Treatments provide a description of a study’s
treatments. Any specific information such as rate of fertilizer
application should be recorded in the managements table. In
general, managements are recorded when Yield data is collected, but not
when only Trait data is collected.

**When not to use treatment**: predictor variables that are not based on distinct managements, or that are distinguished by information already contained in the trait (e.g. site, cultivar, date fields) should not be given distinct treatments. For example, a study that compares two different species, cultivars or genotypes can be assigned the same control treatment; these categories will be distinguished by the species or cultivar field. Another example is when the observation is made at two sites: the site field will include this information. 

*  A treatment name is used as a categorical (rather than continuous)
variable: it should be easy to find the treatment in the paper based on
the name in the database. The treatment name does not have to indicate
the level of treatment used in a particular treatment - this information
will be included in the management table.


* It is essential that a control group is identified with each study. If
there is no experimental manipulation, then there is only one treatment. In
this case, the treatment should be named 'observational' and listed as
control. To determine the control when it is not explicitly stated, first
determine if one of the treatments is most like a background condition
or how a system would be in its non-experimental state. In the case of
crops, this could be how a farmer would be most likely to treat a crop.

   **Name**:   indicates type of treatment; it should be easy for anyone with the
    original paper to be able to identify the treatment from its name.   
   **Control**:   make sure to indicate if the treatment is the study 'control' by
    selecting true or false    
   **Definition**:   indicates the specifics of the treatment. It is useful for
    identification purposes to use a quantified description of the
    treatment even though this information can only be used for analysis
    when entered as a management.  
![alt text](figures/newtreatment.png)

<a id="Section 5.4"></a>
### Adding a Management 

Managements refers to something that occurs at a specific time and has a
quantity. Managements include actions that are done to a plant or
ecosystem, such as the planting density or rate of fertilization, for example.
Managements are distinct from treatments in that a treatment is used to
categorically identify an experimental treatment, whereas a management
is used to describe what has been done.
Managements are the way a treatment becomes quantified. Each treatment
is often associated with multiple managements. The combination of
managements associated with a particular treatment will distinguish it
from other treatments. The management types that can be entered into
BETY are described in [Table 3](#Table 3).
Each management may be associated with one or more treatments. For
example, in a fertilization experiment, planting, irrigation, and
herbicide managements would be applied to all plots but the
fertilization will be specific to a treatment. For a multi-year
experiment, there may be multiple entries for the same type of
management, reflecting, for example, repeated applications of herbicide
or fertilizer (for example, see [Figure 6](#Figure 6)).

*note:* At present, managements are recorded for Yields but not for
Traits, unless specifically required by the data or project manager.

To associate a management with multiple treatments, first create the
management, then edit the management and add treatment relationships.

**Dateloc**:   date level of confidence, explained in [Adding a Trait](#Section_5.5) and defined in [Table 6](#Table 6)    
**Mgmttype**:   the name of the management being used. A list of standardized
    management types can be found in [Table 3](#Table 3)      
**Level**:   a quantification of mgmttype   
**Units**:   refers to the units of the level. Units should be converted to those
    in  [Table 3](#Table 3)  
    

**Figure 6**: [Form for entering and editing relationships between treatments and managements](https://www.betydb.org/treatments)


<a id="Section_5.5"></a>
### Adding a Trait

In general, a 'trait' is a phenotype (a characteristic that the plant
exhibits). The traits that we are primarily interested in collecting
data for are listed in [Table 6](#Table 6). Before adding trait data, it is necessary to have the citation, treatments, and site information already entered. If the correct
citation is not identified at the top of the page [Figure 8](#Figure 8). To add a new Trait,
go to the [new trait](http://www.betydb.org/traits/new)
page: `Trait` → `new`.

Presently, we are also using the Trait table to record ecosystem level
measurements other than Yield. Such ecosystem level measurements can
include leaf area index or net primary productivity, but are only
collected when required for a particular project. Most of the fields in the Traits table are also used in the Yields table. Here is a list of the fields with a brief description, followed
by more thorough explanations:


 **Species**: Search for species in the database using the search box; if species
    is not found  
  **Cultivar**:   primarily used for crops; If the cultivar being used is not found in
    drop-down box  
**DateLOC**:   Date Level of confidence. See for values.  
**Mean**:   mean is in units of tons per hectare per year (t/ha)  
**Stat name**:   is the name of the statistical method used (usually one of SE, SD, MSE,
    CI, LSD, HSD, MSD). See for more details.  
**Statistic**:   is the value of the statistic associated with Stat name.  
**N**:   Always record N if provided. N is the number of experimental
    replicates, often referred to as the sample size; N represents the
    number of independent units within each treatment: in a field
    setting, this is often the number of plots in each treatment, but in
    a greenhouse, growth chamber, or pot-study this may be the number of
    chambers, pots, or individual plants. Sometimes this value is not
    clearly stated.  



### dateLOC

The date level of confidence (DateLOC) provides an indication of how accurately the date associated with the trait or yield observation is
known. It provides the values that should be entered in this field. If the
event occurred at a level of precision not defined by an integer in this
table, then use fractions. For example, we commonly use 5.5 to indicate a one week level of precision. If the exact year is not known, but the time of
year is, then use 91 to 97, with the second digit to indicate the information
known within the year.

<a id="Figure 9"></a>
**Figure 9**: [Form used to enter a new trait](https://www.betydb.org/traits/new)

#### Statistics

Our goal is to record statistics that can be used to estimate standard
deviation or standard error. Many different methods can be used to
summarize data, and this is reflected in the diversity of statistics
that are reported. An overview of these methods is given in a
description below.

Where available, direct estimates of variance are preferred, including
Standard Error (SE), sample Standard Deviation (SD), or Mean Squared
Error (MSE). SE is usually presented in the format of mean 
(±SE). MSE is usually presented in a table. When
extracting SE or SD from a figure, measure from the mean to the upper or
lower bound. This is different than confidence intervals and range
statistics (described below), for which the entire range is collected.

If MSE, SD, or SE are not provided, it is possible that LSD, MSD, HSD,
or CI will be provided. These are range statistics and the most
frequently found range statistics include a Confidence Interval (95%CI),
Fisher’s Least Significant Difference (LSD), Tukey’s Honestly
Significant Difference (HSD), and Minimum Significant Difference (MSD).
Fundamentally, these methods calculate a range that indicates whether
two means are different or not, and this range uses different approaches
to penalize multiple comparisons. The important point is that these are
ranges and that we record the entire range.

Another type of statistic is a “test statistic”; most frequently there
will be an F-value that can be useful, but this should not be recorded
if MSE is available. Only if there is no other information available should you
record the P-value.

### Adding a Yield and Covariate

The protocol for entering yield data is identical to entering data for a
trait, with a few exceptions:

1.  There are no covariates associated with yield data

2.  Yield data is always the dry harvestable biomass; if necessary,
    moisture content can be added as a trait

Yield is equivalent to aboveground biomass on a per-area
basis, and has units of Mg ha^-1 y1  

To add a new yield, go to the [new
yield](http://www.betydb.org/yields/new) page



Covariates are required for many of the traits. Covariates generally
indicate the environmental conditions under which a measurement was
made. Without covariate information, the trait data will have limited
value.

A complete list of required covariates can be found in . For all
respiration rates and photosynthetic parameters, temperature is recorded
as a covariate. Soil moisture, humidity, and other such variables that
were measured at the time of the measurement may be required in
order to standardize across studies.

When root data is recorded, the root size class needs to be entered as a
covariate. The term ’fine root’ often refers to the \(<\)2mm size class,
and in this case, the covariate `root_maximum_diameter` would be set to 2. 
If the size class is a range, then the `root_minimum_diameter` can also be used.

To add a new covariate, go to the [new covariate](http:www.betydb.org/covariates/new) page

### Adding a PFT, Species, and Cultivar

Plant functional types (PFTs) are used to group plants for statistical
modeling and analysis. PFTs are associated with both a specific set of
priors, and a subset species for which the traits and yields data
will be queried. In many cases, it is appropriate to use default PFTs
(e.g. `tempdecid` is temperate deciduous trees)

In other cases, it is necessary to define PFTs for a specific project.
For example, to query a specific set of priors or a subset of a species, a
new PFT may be defined. For example, Xiaohui Feng defined PFTs for the
species found at the EBI Farm prairie. Such project-specific PFTs can
be defined as `` `projectname`.`pft` `` (i.e. `ebifarm.c4grass` instead
of `c4grass`).


Species that are found or cultivated in the United States should be in
the Plants table. Look it up there first.


To add a new Cultivar, go to the [new
cultivar](https://www.betydb.org/cultivars/new) page: `Cultivar`
 → `new`.  

##  BETYdb: Bulk Data Upload

Currently the web interface does not support bulk data upload, although
this is a planned feature for BETY 2.0.

For bulk data upload, or for a complete view of the tables in BETY, a
blank spreadsheet can be found
[online](https://spreadsheets0.google.com/spreadsheet/pub?hl=en&hl=en&key=0Ai_PDCcY5g2JdFN1UDJJdjNsZk9RM0Z6bnFDdlQ0clE&output=html)
and can be downloaded in .xls format
[spreadsheet](https://spreadsheets0.google.com/spreadsheet/pub?hl=en&hl=en&key=0Ai_PDCcY5g2JdFN1UDJJdjNsZk9RM0Z6bnFDdlQ0clE&output=xls).
Contact [David LeBauer](mailto:dlebauer@illinois.edu) or [Mike
Dietze](mailto:mdietze@illinois.edu) for more information about using
this method of data upload.
