
##  Converting Units and Adjustment to Temperature

For many transformations, particularly when automated, please use the udunits2 software where possible. For example, in R, you can use

    library(udunits2)
    ## transform meters to mm
    ud.convert(10, "m", "mm")
    ## equivalently, via the udunits synonym database
    ud.convert(10, "meters", "millimeters")
    ## it can also handle more complex units
    ud.convert(10, "m/s", "mm/d")

NB: Many of these conversions have been automated within [PEcAn](https://github.com/PecanProject/pecan).



