# ananyadas_bitsom_ba_2511216_part1_data_cleaning

## Part 1: Business Data Cleaning, Validation & Excel Reporting


## Task 3: Cleane and Validate DATE 
=IFERROR(
IF(MID(B2,5,1)="-",DATE(LEFT(B2,4),MID(B2,6,2),RIGHT(B2,2)),
IF(ISNUMBER(SEARCH("/",B2)),
DATE(RIGHT(B2,4),LEFT(B2,2),MID(B2,4,2)),
DATEVALUE(B2)
)),
"Invalid Date")
