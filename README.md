# FEMA Relief Declarations Analysis, 1999-2021


Matthew Lintemuth

NSS Data Analytics Cohort 4 Capstone

https://www.linkedin.com/in/matthewlintemuth/

## MOTIVATION
I have called Nashville home for 31 years. My family and I moved here from Michigan in 1990. I got to experience some of the most devastating weather- related events in the state's recorded history. Some of these events included the blizzard of 1995, the tornadoes that ripped through downtown Nashville in 1998, the tornadoes of 2009 and 2020, the flood of 2010 and the winter ice storm of 2021. Growing up I enjoyed watching a storm blow through town or enjoy a snow day that cancelled school. I would enjoy sitting back watching a movie or taking a nap as a thunderstorm rolled through the city. There was very little thought given to just how these events affected the city around me. Given the tools I have acquired over the past 6 months at NSS I wished to analyze FEMA data specifically related to weather events. To gain a more indepth understanding of the cost these storms have caused to my community. I chose to explore the following:
###
•	How many claims had been submitted per weather related event?
###
•	What was the cost of damages during these events to both public infrastructures and homeowners?
###
•	How much financial relief was provided by FEMA programs compared to the cost of damages?

###
•	How much of a gap remained, if any, after relief was received?

## THE DATA
The data used to dive into this analysis, I used two raw datasets provided by FEMA on their National Emergency Management Information System (NEMIS). The datasets covered inforamtion regarding public infrastructures and homeowners. The year range spanned from May 1999 to March 2021.


## Data Challenges: Public Infrastructure and Homeowners
Public Infrastructure:
###
•	Column headers were messy and difficult to read. Required renaming and proper punctuations.
###
•	Columns declarationDate and obligatedDate pulled in as an object datatype and required to have their datatype changed to datetime using “pd.to_datetime”.
###
•	Column county had its challenges with spacing. The county name would appear correct but in fact had a space character at the end of each county name. So, when attempting to filter it would error as it did not recognize the county name without a space character at the end. 

Homeowners:
###
•	Like the public infrastructure dataset. Column headers were messy and difficult to read. Required renaming and proper punctuations.
###
•	Columns county had an unnecessary “(County)” text beneath each county name. Filtering would not recognize the county name without the unnecessary text beneath. However, it proved to be difficult to include the unnecessary text. I stripped out the unnecessary text using the code: owners_tn['county'] = owners_tn['county'].str.replace(r'\(.*\)','',regex=True).
###
•	Column zipCode was accurate but only provided in the Homeowners dataset. I wished to drill down by zip code for the public infrastructures data as well. This was not possible with the data provided in the two datasets and time restrictions.


## TECHNOLOGIES USED
###
•	Excel – Used for the preliminary viewing of the data before coding.
###
•	Python/Pandas – for cleaning, exploration, and organization.
###
•	Tableau – for creating visuals and public story board.
###
•	Visual Studio Code – for editing/creating of Readme file.
###
•	Git – for document control

## RESOURCES
The raw datasets used were provided at the links below.
###
•	https://www.fema.gov/openfema-data-page/public-assistance-funded-projects-details-v1 
###
•	https://www.fema.gov/openfema-data-page/housing-assistance-program-data-owners-v2



## TABLEAU STORY
Please follow the link below to see my analysis in Tableau Story format.
https://public.tableau.com/app/profile/matthew.lintemuth/viz/FEMA_Disaster_Relief/Capstone


## Special Thanks
I wanted to use this section to thank our TA's Andrew Marsee, Kristen Lucas and Teresa Whitesell. Thank you for the tools you taught us, your unwavering support and valued advise provided at each juncture of this program.