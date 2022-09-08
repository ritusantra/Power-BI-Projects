## Employees Attendance Analysis



### Data Cleaning and manipulation

* The data was in cvs format and it was present in different sheets. Each sheet had data of the employee's attendance i.e, number of days present, sick leaves, work from home etc. details from each month (April, May, June).
* The columns of the sheets had different dates of the month and so the data was modified to bring all the dates in a single row.
* Managed Parameter was created so that the same modification of the data could be applied to all the sheets for different months.
* Custome Function was created to capture all the steps in a single function.
* This way in future the data could be modified automatically when additional monthly sheets will be added.
* All the above steps were performed in Power Query.

### DAX Measures and Calculated Columns

**Calculated Columns**

* **WFH Count** <br>
WFH Count = SWITCH(TRUE(), 
                      'Final Data'[Value]="WFH", 1,
                      'Final Data'[Value]="HWFH",0.5,
                      0)
* **SL Count**<br> 
SL Count = SWITCH(TRUE(),
                      'Final Data'[Value] = "SL",1,
                      'Final Data'[Value] = "HSL",0.5,
                      0)
* **Month**<br>
Month = STARTOFMONTH('Final Data'[Date])

* **Day of Week**<br>
Day of the Week = FORMAT('Final Data'[Date],"ddd")

**Measures**

* **Total Working Days**<br>
Total Working Days = 
VAR total_days = COUNT('Final Data'[Value])
VAR total_nonworking_days = CALCULATE(COUNT('Final Data'[Value]),'Final Data'[Value] in {"WO","HO"})
RETURN total_days - total_nonworking_days

* **Present Attendence**<br>
Present Attendence = 
VAR presentdays = CALCULATE(COUNT('Final Data'[Value]),'Final Data'[Value]="P")
RETURN presentdays + [WFH Count]

* **WFH Count**<br>
WFH Count = SUM('Final Data'[WFH Count])

* **SL Count**<br>
SL Count = SUM('Final Data'[SL Count])

* **Presence %**<br>
Presence % = DIVIDE([Present Attendence],[Total Working Days],0)

* **SL %**<br>
SL % = DIVIDE([SL Count],[Total Working Days],0)

* **WFH %**<br>
WFH % = DIVIDE([WFH Count],[Present Attendence],0)

### Data Visualization

