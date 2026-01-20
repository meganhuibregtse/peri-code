# **PERI**: **P**rospective **E**valuation of **R**eproductive aging **I**ndicators

Contact: Megan Huibregtse, PhD (mhuibreg@illinois.edu)

## Overview
This software was written to apply [STRAW+10 stages](https://pmc.ncbi.nlm.nih.gov/articles/PMC3319184/) to prospectively tracked menstrual bleeding data in a longitudinal cohort study of perimenopausal women.  
**Development**: This software was developed by Dr. Megan Huibregtse while a postdoctoral fellow at the Grady Trauma Project under the supervision of Dr. Jennifer S. Stevens and Dr. Vasiliki Michopoulos. Development was supported by R01MH128244 (MPIs: Michoupoulos and Stevens) and F32MH134528 (PI: Huibregtse).  
**Citation**: If you use this software, please cite this article: Huibregtse, M. E., Taylor, L., Prochaska, T., Arnold, A. R., Epperson, C. N., Chahine, E. B., Smith, A. K., Powers, A., Michopoulos, V., & Stevens, J. S. (2026). Considerations and practical recommendations for identifying perimenopause in longitudinal research. *Psychoneuroendocrinology*, 107748. [https://doi.org/10.1016/j.psyneuen.2026.107748](https://doi.org/10.1016/j.psyneuen.2026.107748)

## User guide
### Step 1. File/directory set up
Download and unzip the repo.  
Create the following directories within peri_code:  
- data
- data/archive
- figures
- pipeline_derivatives  

### Step 2. Export your data  
Export your prospective menstrual cycle pattern data as a csv. Save in *peri_code/data*.  
Export visit dates (i.e., the dates participants completed data collection visit) as a csv. Save in *peri_code/data*.  

### Step 3. Preparation 
Open peri_code.Rmd. 
Assumptions about the data (correct your data or adapt the code before proceeding if your data doesn't meet these):  
- There is a column "SID" for the subject ID number.  
- There is a column called "EndDate_date" that corresponds to the day the subject completed the bleeding data survey. In our case, the surveys were distributed every Wednesday.  
- There is a column "bleeding_YN" that indicates if any bleeding was reported for that week (1 = yes, 0 = no)  
- There are columns "bleeding_days_1" through "bleeding_days_7" that correspond to bleeding reported the day before (Tuesday; bleeding_days_1) through the prior Wednesday (bleeding_days_7). A value of 1 in any of these columns indicate that bleeding was reported on that day.  
- Your visit dates (i.e., the dates participants completed data collection visit) are recorded in columns called "V1," "V2," "V3," etc.  
Enter/update your file names and the freeze data in the import data chunk.  
**Run all chunks before the example chunk.**  

### Step 4. Perform staging and generate figures  
Copy and paste the example chunk.  
Update the chunk to perform staging for your first participant (i.e., change the 101 throughout the chunk to the SID of interest).  
Update the chunk title to the SID of interest.  
**Run the `filter_SID` and the `check_duplicates` lines.**  
If any duplicates are idenitified, remove them using the template code provided.  
Once duplicates have been dealt with, **run the remaining lines of code (part 1b thorugh part 4).**  
Figures for this SID will be generated and saved to the the *figures* directory.   

### Step 5. Export the data  
Add QC notes, if applicable. Some QC notes will be automatically generated.  
**Run this chunk.** The exported csv will be saved to the *pipeline_derivatives* directory with the freeze date (i.e., the date the raw data was exported) and today's date in the filename.   






