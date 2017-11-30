# A Cure for Jersey City: Showing Our Work
How we got our data, and how we used it
<hr>
<h2> The Story </h2>
<p>A metropolis of high-rise towers, power players in government (including President Trump’s son-in-law, Jared Kushner) and finance have made once-barren Jersey City a fancy home to 264,000 people living in the shadow of Manhattan, just across the Hudson River. But as of October this year, there have been 16 homicides and 98 total shootings in Jersey City. Most have occurred around the Greenville neighborhood, an area referred to locally as “The Hill.” Almost all of the deaths were caused by guns, according to an independent analysis conducted by NationSwell.  

Jersey City Mayor Steven Fulop says that additional law enforcement patrols and proactive policing in high-crime areas are addressing the problem, but NationSwell’s analysis — which only includes reported shootings published in local papers and cross referenced with reported shootings via the Gun Violence Archive — reveals that Jersey City has seen a 200 percent increase in the number of shootings in the past three years. Twenty-six people were shot during the last six months of 2014; two years later, that number increased to 57 during the same time period. 

In the first week of 2017, seven shootings resulted in two people injured, including a 14-year-old boy, and three more were shot inside a home less than two weeks late. 

Compared to neighboring New York City, whose population is almost 40 times the population in Jersey City, shootings and gun homicides have gone down continually over the past decade. 

The total number of homicides recorded by Jersey City police in monthly CompStat reports — the system that logs city crimes — does not specify the murders by gun deaths, nor does it record number of shootings without an injury.  

So regular citizens and residents have started their own grassroots initiatives, of which include a team to mend the peace between rivaling gangs and a coalition of victims’ mothers, to make the southern part of Jersey City a safer place for everyone. <p>
  
 <hr>
 
#The Data

<h2> How we found our numbers </h2>
 
There is very little data available for how many shots fired and shootings happen in Jersey City. There are a number of open source websites (Gun Violence Archive and Spotcrime, for example) that list shootings on record (based on user input data or news articles), but we knew that would be an icnomplete data set. 

We initially sent in a OPRA (Open Public Records Act) request to the Jersey City Clerk on August 30, requesting records for: <i>For the years between 2000-current (1) all recorded shootings (fatal and non-fatal) (2) arrests made for crimes dealing with gun possession and shootings (3) number of guns recovered (4) number of calls made to respond to gunshots fired in the South Jersey City area and, specifically, with the Greenville Precinct.</i> 

However, the city clerk (after dozens of emails and phone calls), never responded and pushed back the date. So, in a good faith effort to capture the data, we pulled from three data sets: Gun Violence Archive, SpotCrime and cross checked with the local newspaper -- the Jersey Journal -- to account for duplicates. 

<b>First</b>, we found every single article from the Jersey Journal website archives that had "gunshots" as a keyword dating back to 2014. For every article, we made data entry notes for these columns: (1) name (if any), (2) cross roads (if mentioned -- if not, would be street name listed followed by neighborhood), (3) shots fired OR (4) persons injured OR (5) persons killed

<b>Second</b>, we culled (simply copy/pasted) every single recorded shooting from the Gun Violence Archive and SpotCrime databases for the same time period. However, Gun Archive and SpotCrime only go back so far, so we had to limit our search to the last six months of 2014 through the first six months of 2017. We then cleaned up that data sheet in OpenRefine. 

<b>Third</b>, we cross referenced every shooting by date. If there were discrepancies in number of people injured or recorded shots fired, we made note of it and edited the data set to reflect what the newspaper reported. If there was no instance of an article published in the local paper, we added in good faith the data from SpotCrime or Gun Violence Archive. Instances of shootings with no injured or dead are recorded with zeros. 

<hr>

<h2> Cross Check with Known Public Records </h2>

Recognizing that this data is imperfect because official records woud have been more helpful, we decided to cross check what we had with CompStat, the software used to record violent crimes. However, immediately there was an issue: CompStat does not record data based on shootings, specifically. The publci records available only list homicides and armed robbery. We know that homicides in Jersey City are primarily caused by guns, but there have been stabbings in the past, as well. Those aren't quantifiable within CompStat's data. 

We did find that our numbers were -- in most cases -- higher than CompStat's. There was one case where our numbers were actually lower than CompStat's. We couldn't account for the difference except that some crimes go unreported in the news or old cases are resurfaced. 

<hr>

We mainly used excel formulas to find out total numbers after figuring out discrepancies. The way we did this was primarily through summing together total injuries or deaths if it matched a certain month string by year value. Example formula below. 

SUMIFS('# Killed', A, "July", Year, "2014")




