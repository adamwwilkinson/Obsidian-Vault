# Excel

### Exam!
**Legal**
=COUNTIF(C2:C21,"=FRANCE")
=COUNTIF(C2:C21,"="&C2)

=AVERAGE(A2:B21)
=AVERAGE(A2:A21)

{=A2:A21 \* B2:B21}
{=A2:A21 \* B2}
{=AVERAGE(B2:B21) * A2:A21}

**Illegal**
{=COUNTA(C:C),A:A}
=AVERAGE(B2:B21) * A2:A21
### Methods
Mean - *Average(A1:B2)*
Standard Deviation = *STDEV(A1:B2)*

### Conditionals
=IF(B2<B3, "it is less than", "it isn't less than") Excel

### Array Formulas
Instead of A1 X B1 and dragging that result down to A7, we can do *A1:A7 \* B1:B7*.
ctrl + shift + enter if array formula is required element by element.

#### Why
It ensures all cells use the same formula, and prevent accidental edits.

###  IsError
Returns *TRUE* if there is an error, and *FALSE* if there isn't.

### Boolean
*TRUE* can be used as 1
*FALSE* can be used as 0
*=SUM((score >= 50) X (score < 60) X score)*
returns the sum of scores more than 50 and less than 60.

### Charts
#### Histogram
- *bins* - what to count
- requires an array for where to count
#### Line Graphs
- used to *outline trends*
- continuous data
- $R^2$ can indicate how good as a predictor
#### Scatter plot
- useful for *correlations*
- similar to line
#### Surface plot
- useful for finding points of stability