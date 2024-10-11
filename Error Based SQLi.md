# Error:

- The used SELECT statements have a different number of columns 
	![[Pasted image 20240717163305.png]]
### the reason for this error: 5 ta column valid na theres either a larger or smaller amount of actual columns (but we saw with the group statement that there was just 5 columns)
# process: 

- try diff injection points to see if the column amounts vary (for example for the site above id=93 gives us 10 columns coz diff injection point)
- try the group by statement just to be sure (injection point 93 gave us 10 columns but the group by says 14 so there was actually 14 columns)
- DIOS might not work so might have to manually use the get tables and then get columns to manually peek at the database to dump the data by fiddling with the limit parameters
 