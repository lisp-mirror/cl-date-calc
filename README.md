# cl-date-calc

https://gitlab.common-lisp.net/cl-date-calc/cl-date-calc (this mirror is not synced)

[https://common-lisp.net/project/cl-date-calc/index.html](https://common-lisp.net/project/cl-date-calc/index.html)

```
 Description of the functions:
 
*language* Global Variable in Package 	0=Default, 1=English, 2=Francais, 3=Deutsch, 4=Espanol, 5=Portugues, 6=Nederlands, 7=Italiano, 8=Norsk, 9=Svenska, 10=Dansk, 11=suomi

decode-day-of-week (STR) 	Reads in a string and returns the DOW as integer with respect to *language*.
decode-month (STR) 	Returns number of month. STR can partially name the month according to *language*. Computes a (search ...:test #'char-equal)
decode-language (N) 	Reads in the Lang as NUM and returns the corresponding textual representation.
fixed-window (YY) 	Convert two digit YEAR to four digit YEAR; YEAR<=70 -> 2000+YEAR; YEAR<100&&>70 -> 1900+YEAR.
center (str width) 	Return a string that is WIDTH long with STRING centered in it.
valid-year-p (Y) 	Checks if Y >= 1
valid-month-p (M) 	Checks if Y<=12 && Y>=1
leap-year (Y) 	Returns 1 if Y is a leap year. Else 0.
leap-year-p (Y) 	Returns T if Y is a leap year. Else NIL.
days-in-month (Y M) 	Returns the number of days in MONTH of YEAR.
days-in-year (Y &optional M) 	This function returns the number of days in the given YEAR and optional MONTH. If MONTH is [1..12], return the number of days in that YEAR as of the last of that MONTH.
check-date (Y M D) 	This function returns t if the given three numerical values YEAR MONTH DAY constitute a valid date, and nil otherwise.
check-business-p (Y W DOW) 	This function returns true if the given three numerical values YEAR WEEK DOW constitute a valid date in business format, and nil otherwise. Beware that this function does NOT compute whether a given date is a business day (i.e., Monday to Friday)! To do so, use (< (day-of-week year month day) 6) instead. DOW not CL conform.
check-time-p (H M S) 	This function returns t if the given three numerical values HOUR MIN SEC constitute a valid time, and nil otherwise.
day-of-year (Y M D) 	This function returns the sum of the number of days in the months starting with January up to and including MONTH in the given year YEAR. 0 on failure.
date-to-days (Y M D) 	This function returns the (absolute) number of the day of the given date, where counting starts at the 1.Jan 1.
day-of-week (Y M D) 	Returns the Number of the Day of the Week. Monday=1.
weeks-in-year (Y) 	Returns the number of weeks in YEAR.
delta-days (Y1 M1 D1 Y2 M2 D2) 	Returns the diff of the two YMD values in Days.
week-number (Y M D) 	This function returns the number of the week of the given Y M D lies in. If the given date lies in the LAST week of the PREVIOUS year, 0 is returned.
week-of-year (Y M D) 	Returns WEEK YEAR where week is the week number of YEAR.
add-delta-days (Y M D dD) 	Returns YMD = YMD + dD. dD can be neagtive.
monday-of-week (W Y) 	Return YEAR MONTH DAY corresponding to the Monday of WEEK in YEAR.
nth-weekday-of-month-year (Y M DOW n) 	This function returns the YEAR MONTH DAY of the N-th day of week DOW is in the given MONTH and YEAR; such as, for example, the 3rd Thursday of a given month and year. DOW is not CL conform.
standard-to-business (Y M D) 	Returns the Business date of Y M D.
business-to-standard (Y W DOW) 	Returns the standard date of Y M DOW.
delta-hms (H1 M1 S1 H2 M2 S2) 	This function returns H M S as the difference of H1 M1 S1 and H2 M2 S2.
delta-dhms (D1 H1 M1 S1 D2 H2 M2 S2) 	Returns D H M S as the difference of D1 H1 M1 S1 and D2 H2 M2 S2.
delta-ymd (Y1 M1 D1 Y2 M2 D2) 	Returns Y M D as the difference of Y1 M1 D1 and Y2 M2 D2.
delta-ymdhms (Y1 M1 D1 H1 M1 S1 Y2 D2 H2 M2 S2) 	Returns Y M D H M S as the difference of Y1 M1 D1 H1 M1 S1 and Y2 M2 D2 H2 M2 S2.
normalize-dhms (D H M S) 	This function takes four arbitrary values for days, hours, minutes and seconds (which may have different signs) and renormalizes them so that the values for hours, minutes and seconds will lie in the ranges [-23..23], [-59..59] and [-59..59], respectively, and so that they have the same sign (Except for D).
add-delta-dhms (Y M D H M S dD dH dM dS) 	This function serves to add a days, hours, minutes and seconds offset to a given date and time (YEAR MONTH DAY HOUR MINUTE SECOND DDAY DHOUR DMINUTE DSECOND), in order to answer questions like "today and now plus 7 days but minus 5 hours and then plus 30 minutes, what date and time gives that?". Returns: Y M D H M S.
add-year-month (Y M dY dM) 	Returns YM=Y+dY+M+dM.
add-delta-ym (Y M D dY dM) 	Returns YM=YM+dY+dM+D
add-delta-ymd (Y M D dY dM dD) 	Returns YMD=YMD+dY+dM+dD
add-delta-ymdhms (Y M D H M S dY dM dD dH dM dS) 	Returns YMDHMS=YMDHMS+dY+dM+dD+dH+dM+dS
today NIL 	Returns YMD of Today.
now NIL 	Returns the time of now in HMS.
today-and-now NIL 	Returns Today and now in YMDHMS.
this-year NIL 	Returns this year.
date-to-text (Y M D) 	Returns a text representation of YMD with respect to *language*.
date-to-text-long (Y M D) 	Returns a longer text representation of YMD with respect to *language*.
iso-lc (char) 	Converts CHAR to ISO Lower Case.
iso-uc (char) 	Converts CHAR to ISO Upper Case.
year-to-days (Y) 	Returns the number of days for YEAR since 1 Jan 1.
yesterday NIL 	Returns YMD of Yesterday.
tomorrow NIL 	Returns YMD of tomorrow.
cl-day-of-week NIL 	Returns the DOW in CL notation. Monday=0.
cl-check-business-p (Y W DOW) 	This function returns true if the given three numerical values YEAR WEEK DOW constitute a valid date in business format for CL (Monday=0), and nil otherwise. DOW is CL conform.
cl-nth-weekday-of-month-year (Y M D) 	This function returns the (year month day) of the N-th day of week DOW in the given MONTH and YEAR; such as, for example, the 3rd Thursday of a given month and year. DOW is CL conform.
cl-decode-day-of-week (STR) 	Returns number of weekday. STR can partially name the Weekday according to *language*. DOW is CL conform.
cl-standard-to-business (Y M D) 	Returns Business date in CL notation of given YMD.
cl-business-to-standard (Y W DOW) 	Returns the YMD of given Business date in CL notation. 
```
