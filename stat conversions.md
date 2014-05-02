<a id="Table 8"></Table 8>
**Table 8: How to convert statistics from \(P\), \(LSD\), or \(MSD\) to \(SE\)**

Most of these (and others) are implemented in the [transformstats](https://github.com/PecanProject/pecan/blob/master/utils/R/transformstats.R) function within the PEcAn.utils package

| From | To | Conversion | R code | Notes |
|:-----|:---|:-----------|:------|:------|
| P | SE | SE\( = \frac{\bar{X}_1-\bar{X}_2}{t_{1-P/2,2n-2}\sqrt{2/n}}\) | `(x1-x2)/(qt(1-P/2,2*n-2)*sqrt(2/n))` | \(\bar{X}_{1,2}\) are two means being compared. |
| LSD | SE | \(SE = \frac{LSD}{t_{1-\alpha/2,n}*\sqrt{2b}}\) | `LSD/(qt(1-P/2,n)*sqrt(2*b))` | where \(b\) is the number of blocks, \(n\) is the number of replicates, and \(n=b\) in a Randomized Complete Block Design |
| MSD | SE | \(SE = \frac{MSD*n}{t_{1-\alpha, 2n-2}*\sqrt{2}}\) | `msd*n/(qt(1-P/2,2*n-2)*sqrt(2))` | |


See related questions on Stats.SE: http://stats.stackexchange.com/q/2917/1381 and http://stats.stackexchange.com/q/4485/1381



####  Calculating \(MSE\) given \(F\), \(df_{\text{group}}\), and \(SS\)


Given:

\(\label{eq:f}
  F = MS_g/MS_e\)

Where \(g\) indicates the group, or treatment. Rearranging this equation
gives: \(MS_e=MS_g/F\)

Given

\(MS_x = SS_x/df_x\)

Substitute \(MS_e/df_e\) for \(SS_e\) in the first equation

\(F=\frac{SS_g/df_g}{MS_e}\)

Then solve for \(MS_e\)

\(\label{eq:mse}
  MS_e = \frac{SS_g}{df_g\times F}\)

\(\label{eq:dft}
  df_{\text{total}}=(df_a+1)\times(df_b+1)...\times(n)-1\)

Which depends on the experimental design:

For factors a, b... (usually 1 or 2, sometimes 3) where \(n\) is the
number of replicates within each treatment combination.

-   One-way anova \(df_{\text{total}}=an-1\); where \(a\) is the number of
    treatments

-   Two-way anova without replication \(df_{\text{total}}=(a+1)(b+1)-1\)
    also known as ’’randomized complete block design’’ (RCBD)

-   Two-way anova with \(n\) replicates
    \(df_{\text{total}}=(a+1)(b+1)(n)-1\) aka ’’RCBD with replication’’

#### Example

An example application of this is in Starr et al. [2008] table 3 [Figure 11] (Figure 11).
The results are from one (two?) factor ANOVA with repeated measures,
with treatment and week as the factors and no replication.

We will calculate MSE from the \(SS_{\text{treatment}}\)
\(df_{\text{treatment}}\), and \(F\)-value given in the table; these are
\(109.58\), \(2\), and \(0.570\), respectively; \(df_{\text{weeks}}\) is given
as \(10\).

For the 1997 *Eriphorium vaginatum*, the mean \(A_{max}\) in table 4 is
\(13.49\).

Calculate \(MS_e\):

\(MS_e = \frac{109.58}{0.57 \times 2} = 96.12\)

