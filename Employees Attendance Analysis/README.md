## Employees Attendance Analysis



### Data Cleaning and manipulation

* The data was in cvs format and it was present in different sheets. Each sheet had data of the employee's attendance i.e, number of days present, sick leaves, work from home etc. details from each month (April, May, June).
* The columns of the sheets had different dates of the month and so the data was modified to bring all the dates in a single row.
* Managed Parameter was created so that the same modification of the data could be applied to all the sheets for different months.
* Custome Function was created to capture all the steps in a single function.
* This way in future the data could be modified automatically when additional monthly sheets will be added.
* All the above steps were performed in Power Query.

### DAX Measures and Calculated Columns

<b>Calculated Columns</b>
* <b>WFH Count<\b> -> WFH Count = SWITCH(TRUE(), 
                      'Final Data'[Value]="WFH", 1,
                      'Final Data'[Value]="HWFH",0.5,
                      0)
* <b>SL Count<\b> - 
* <b>Month<\b> ->
* <b>Day of Week<\b> -> Day of the Week = FORMAT('Final Data'[Date],"ddd")

<b>Measures</b>


### Data Visualization

