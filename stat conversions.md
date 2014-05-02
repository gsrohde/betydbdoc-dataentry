<a id="Table 8"></Table 8>
**Table 8: How to convert statistics from \(P\), \(LSD\), or \(MSD\) to \(SE\)**


| From | To | Conversion | Rcode | Notes |
|:-----|:---|:-----------|:------|:------|
| P | SE | SE\( = \frac{\bar{X}_1-\bar{X}_2}{t_{1-P/2,2n-2}\sqrt{2/n}}\) | (x1-x2)/(qt(1-P/2,2*n-2)*sqrt(2/n)) | \(\bar{X}_{1,2}\) are two means being compared. |
| LSD | SE | \(SE = \frac{LSD}{t_{1-\alpha/2,n}*\sqrt{2b}}\) | LSD/(qt(1-P/2,n)*sqrt(2*b)) | where \(b\) is the number of blocks, \(n\) is the number of replicates, and \(n=b\) in a Randomized Complete Block Design |
| MSD | SE | \(SE = \frac{MSD*n}{t_{1-\alpha, 2n-2}*\sqrt{2}}\) | msd*n/(qt(1-P/2,2*n-2)*sqrt(2)) | |


See related questions on Stats.SE: http://stats.stackexchange.com/q/2917/1381 and http://stats.stackexchange.com/q/4485/1381