README
20 March 2024

Archive for data and code for:

Relative contributions of size and shape to coral demography

Authors and contacts: (Hidden before peer review)
Guanyan Keelung Chen*, guanyan@hawaii.edu
Lisa C. McManus*, mcmanusl@hawaii.edu
Tung-Yung Fan, tyfan@nmmba.gov.tw
Joshua S. Madin*, jmadin@hawaii.edu

*Corresponding authors

Brief summary: 

We used ArcGIS to delineate all coral colonies on the Orthomosaic. By outlining the polygons, we can calculate the perimeter and area of the coral colonies. This study focuses on the coral species Pocillopora acuta. Each coral colony is assigned a unique ID to track their morphological changes and fate over the years, including events of death, recruit, fission, and fusion, which are annotated in ArcGIS. The raw data exported from ArcGIS are further processed in R. In the R code, we calculate the growth, shrinkage, and area change rate of the colonies, as well as perform calculations and statistical analyses of circularity and the P/A ratio.


GUIDE TO THE CONTENTS OF THESE FILES
There are four folders:
- R: the R codes
	- Binomial_analysis.Rmd: for doing all of the statistical analysis
	- Data_Finalization.Rmd: for finalizing the raw data from ArcGIS
- data: the raw data exported from ArcGIS
- figs: the figure generated for anlysis and results
- output: the data that generated during R analysis

The explanation of column names:
- pa_data_done.csv
	$OBJECTID: the ID that was generated automatically by ArcGIS for polygons in each feature class layer
	$ID: the ID that was assigned manually for tracking the changes in each plot (different plot might have the same ID)
	$Shape_Length: the perimeter of coral colony
	$Shape_Area: the area of coral colony
	$Fate: the modular process or fate of coral colony at next survey time
	$Source: If Fission or Fusion happened, the ID of the original colonies. The other fates, were NAs
	$Recruit: the colony is new recriut (Y) or not (N)
	$Species: Pocillopora acuta (PA)
	$Site: study site. The outlet of the third nuclear power plant in Kenting National Park (OL)
	$Plot_ID: the ID of 3 plots in the study site of this study, M1, M2, TY3
	$Year: the year of underwater photogrammetry survey
	$Month: the month of underwater photogrammetry survey
	$Date: the date of underwater photogrammetry survey
	$Time: the time when starting underwater photogrammetry survey
	$Survey_times: this plot has been surveyed for the nth time
	$size_class: the colony is Juvenile (J) or Adult (A)
	$pa_ratio: the perimeter/area ratio of colony
	$Circle_Length: the ideal circumference of colony
	$circ: the circularity of colony
	$pure_size: the colony classcification by size
	$size_class_pa: the colony classcification by P/A ratio
	$size_class_circ: the colony classcification by circularity
	$sa_change: the area change of colony
	$change_rate: the proportional change of area of colony
	$rate_ad: the proportional change of area of colony after standerdized by survey time interval
