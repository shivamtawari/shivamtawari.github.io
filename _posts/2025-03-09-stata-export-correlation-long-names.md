---
title: 'Exporting Correlation Tables from Stata to Excel Without Losing Long Variable Names'
date: 2025-03-09 # Use the actual publication date
permalink: /posts/2025/03/stata-export-correlation-long-names/ # Descriptive permalink
tags:
  - stata
  - correlation
  - excel
---
When working with Stata, exporting correlation tables to Excel seems simple. However, if your dataset contains long variable names, the exported table might cut them short. This makes the table hard to read.

I ran into this issue recently. This blog shows the problem and how to export correlation tables *without* losing those long variable names.

The Problem: Truncated Variable Names
======

I had variables like:

```stata

long_random_variable_name_A
long_random_variable_name_B
long_random_variable_name_C
long_random_variable_name_D
long_random_variable_name_E

```

Running the correlation command in Stata:

```
pwcorr long_random_variable_name_A long_random_variable_name_B long_random_variable_name_C ///
       long_random_variable_name_D long_random_variable_name_E, star(5)
```      
displays the results with shortened names:

![Image of truncated names in Stata](/images/blogs/truncated_names.png)

As you can see, Stata automatically shortens variable names in the output, even before exporting!

The same issue occurs when exporting using putexcel. This makes the output difficult to interpret.

The Fix: Exporting the Correlation Matrix to Excel
======

Here's the code I used to export the correlation matrix to Excel.  It successfully includes the full variable names:

```stata
putexcel set correlation_table.xlsx, replace
matrix C = r(C)
putexcel A1 = matrix(C), names
```

The Outcome: Correctly Formatted Export
======

Now, the exported Excel file contains:

![Output of Correlations in Excel](/images/blogs/excel_output_correlations.png)