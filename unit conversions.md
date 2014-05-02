
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

Convert from root respiration data reported in George et al (where O\(_2\)
was measured in µL to units of mass

In the appendix table, George 2003 reports the range of root respiration
rates, converted to \(15°C\) and standard units:

\([11.26, 22.52]  \frac{\mathrm{nmol CO}_2}{\mathrm{g}\ \mathrm{s}}\)

In the original publication Allen (1969), root respiration was measured
at \(27°C\). The values can be found in [Table 3] (#Table 3) and [Figure 2] (#Figure 2). The
data include a minimum (Group 2 Brunswick, NJ plants) and a maximum
(Group 3 Newbery, South Carolina), which I assume are the ones used by
George 2003:

\([27.2, 56.2] \frac{\mu\mathrm{L}\ \mathrm{O}_2}{10\mathrm{mg}\ \mathrm{h}}\)


Transformed George 2003 measurements back to the measurement temperature
using a rearrangement of equation 1 from George, the standardized
temperature of \(15°C\) stated in the Georgeh table legend, and
Q\(_{10} = 2.075\) from George 2003, and the measurement temperature of
\(27°C\) reported by Allen 1969:

\(R_T = R_{15}[\exp(\ln(Q_{10})(T- 15))/10]\)

\([11.26, 22.52] * exp(log(2.075)*(27 - 15)/10)\)

Now we have the values that we would have expected to find in the Allen
paper, except that the units need to be converted back to the original:

\([27.03,54.07] \mathrm{nmol CO}_2\ \mathrm{g}^{-1}\mathrm{s}^{-1}\)


####  Required constants


-   \(1\ \mathrm{mol}\ \mathrm{O}_2 = 1\ \mathrm{mol}\ \mathrm{CO}_2\)
    since respiration is
    \(\mathrm{CH}_2\mathrm{O} + \mathrm{O}_2 \to \mathrm{CO}_2 + \mathrm{H}_2\mathrm{O}\)

-   Density of \(\mathrm{O}_2\) at \(27^\circ C\):
    \(\frac{7.69 \times 10^5\ \mathrm{ml}\ \mathrm{O}_2}{\mathrm{g}\ \mathrm{O}_2}\)
    first assume that Allen converted to sea level pressure (101 kPa),
    although maybe they were measured at elevation (Allen may have
    worked at \~ 900 kPa near Brevard, NC)

-   Molar mass of \(\mathrm{O}_2\):
    \(\frac{32\mathrm{g}\ \mathrm{O}_2}{\mathrm{mol}}\)

-   Treat 10mg, which is in the unit of root mass used by Allen, as a
    unit of measurement for simplicity

Now convert
\([27.03,54.07] \mathrm{nmol CO}_2\ \mathrm{g}^{-1}\mathrm{s}^{-1}\) to
units of
\(\frac{\mu\mathrm{L}\ \textrm{O}_2}{10\mathrm{mg}\ \mathrm{root}\ \mathrm{h}}\).
The expected result is the original values reported by Allen:
\([27.2, 56.2] \frac{\mu\mathrm{L}\ \mathrm{O}_2}{10\mathrm{mg}\ \mathrm{h}}\)

\([27.03, 54.07]\ \frac{\mathrm{nmol}\ \mathrm{CO}_2}{\mathrm{g}\ \mathrm{root}\ \mathrm{s}} \times \frac{1\ \mathrm{g}}{100\times10\mathrm{mg}} \times \frac{3600\ \mathrm{s}}{\mathrm{h}} \times \frac{\mathrm{nmol}\ \mathrm{O}_2}{\mathrm{nmol}\ \mathrm{CO}_2}\frac{3.2 \times 10^{-8}\ \mathrm{g}\ \mathrm{O}_2}{\mathrm{nmol}\ \mathrm{O}_2}\times \frac{7.69\times10^5\ \mu\mathrm{L}\ \mathrm{O}_2}{\mathrm{g}\ \mathrm{O}_2}\)

The result is:

\([23.8, 47.8]  \frac{\mu\mathrm{L}\ \textrm{O}_2}{10\mathrm{mg}\ \mathrm{root}\ \mathrm{h}}\)

These are the units reported in the Allen paper, but they appear to be
off by the temperature conversion factor,
\(exp(log(2.075)*(27 - 15)/10)=2.4\), e.g.
\([11.9, 23.9]\times 2.4= [28.6,57.4]\), values which are only 5 and 2
percent larger than the original values of \([27.2, 56.2]\), respectively
to be acceptable, but not exact. Since the ratio of observed:expected
values are different, it is not likely that Q\(_{10}\) or the atmospheric
pressure at time of measurement would explain this error.

####  Convert to units in BETYdb, find \(\textrm{k}\)


:

\(\textrm{k}\times\frac{\mu\mathrm{L}\ \textrm{O}_2}{10\mathrm{mg}\ \mathrm{root}\ \mathrm{h}} = \frac{\mu\mathrm{mol}\ \mathrm{CO}_2}{\mathrm{kg}\ \mathrm{s}}\)

\(k =  \frac{\mathrm{g}\ \mathrm{O}_2}{7.69\times10^5\ \mu\mathrm{L}\ \mathrm{O}_2}\times\frac{\mu\mathrm{mol}\ \mathrm{O}_2}{3.2 \times 10^{-5}\ \mathrm{g}\ \mathrm{O}_2} \times \frac{10^5\ \times 10\mathrm{mg}}{\mathrm{kg}} \times \frac{\mathrm{h}}{3600\ \mathrm{s}}=\)
\(= 1.13\)




<a id="Table 9"></Table 9>
**Table 9: Useful conversions for entering site, management, yield, and trait data**



| From (\(X\)) | to (\(Y\)) | Conversion | Notes |
|:-----------|:---------|:-----------|:------|
| \(X_2=\)root production | \(X_1=\)root biomass & root turnover rate | \(Y = X_2/X_1\) | Gill [2000] |
| DD\(^{\circ}\) MM'SS | XX.ZZZZ | \(\textrm{XX.ZZZZ} = \textrm{XX} + \textrm{MM}/60+\textrm{SS}/60\) | to convert latitude or longitude from degrees, minutes, seconds to  decimal degrees |
| lb | kg | \(Y=X\times 2.2\) | |
| mm/s | \(\mu\) mol CO\(_2\) m\(^{2}\) s\(^{-1}\) | \(Y=X\times 0.04\) | |
| m\(^2\) | ha | \(Y = X/10^6\) | |
| g/m\(^2\) | kg/ha | \(Y=X\times 10\) | |
| US ton/acre | Mg/ha | \(Y = X\times 2.24\) | |
| m\(^3\)/ha | cm | \(Y=X/100\) | units used for irrigation and rainfall |
| % roots | root:shoot (q) | \(Y=\frac{X}{1-X}\) | \(\% \text{roots} = \frac{\text{root biomass}}{\text{total biomass}}\) |
| \(\mu\) mol cm\(^{-2}\) s\(^{-1}\) | mmol m\(^{-2}\) s\(^{-1}\) | \(Y = X/10\) | |
| mol m\(^{-2}\) s\(^{-1}\) | mmol m\(^{-2}\) s\(^{-1}\) | \(Y = X/10^6\) | |
| mol  m\(^{-2}\) s\(^{-1}\) | \(\mu\) mol cm\(^{-2}\) s\(^{-1}\) | \(Y = X/ 10^5\) | |
| mm s\(^{-2}\) | mmol m\(^{-3}\) s\(^{-1}\) | \(Y=X/41\) | Korner et al. [1988] |
| mg CO\(_2\) g\(^{-1}\) h\(^{-1}\) | \(\mu\) mol kg\(^{-1}\) s\(^{-1}\) | \(Y = X\times 6.31\) | used for root_respiration_rate |
| \(\mu\) mol | mol | \(Y= X\times 10^6\) | |
| julian day (1--365) | date | | see ref: http://disc.gsfc.nasa.gov/julian_calendar.shtml (NASA Julian Calendar)
| spacing (m) | density (plants m\(^{2}\)) | \(Y=\frac{1}{\textrm{row spacing}\times\textrm{plant spacing}}\)  | |
| kg ha\(^{-1}\) y\(^{-1}\) | Mg ha\(^{-1}\) y\(^{-1}\) | \(Y= X/1000\) | |
| g m\(^{-2}\) y\(^{-1}\) | Mg ha\(^{-1}\) y\(^{-1}\)  | \(Y= X/100\) | |
| kg | mg | \(Y=X\times 10^6\) | |
| cm\(^2\)  | m\(^2\) | \(Y=X\times 10^4\)  | |


