# Matplotlib-Challenge
This is the 5th homework from my coding bootcamp course.
In this one I am asked to sorting and cleaning an experiment based data for plots which helps further understand the outcomes. Again, kids running around so I had to complete it at once. In terms of personnal learning that I feel the dataframe.plot are extremly convenient to use and I think this task is more related to real-world cases where we need to play around with the raw datasets to generate outcomes or analysis and then study it accordingly.

## Key Reflects

### New Findings
For statistics summary, importing numpy and scipy.stats always come in handy. Also it is very important that before starting to get some results, a good look at the raw data will help alot to know what we are dealing with. We can go .info, .shape, .descr etc. to check out about the data. In my workbook I just delete these scripts at the end to give a tidy view.
The aggregation method is also 'overpowered' and I believe there should be a more easier way of applying it, this is something defintely worth a further studying at.
When it comes to plt.legend, to show the full name of the variable name of the legend, there must be a ',' outside the ['Variable'], otherwise it only shows the initial letter of your variable name.
Regarding to the pie drawing, I applied the unique sex counts of all the mice instead of including all duplicated mouse ID on its sex, I think both will provide similar result. I do it this way just because as I have noticed that the 'study_results' not having the full records of Tumor volume for each mouse, i.e. that some of the mouse do not have 10 sets of timepoint values. To limit this to its minimum effects, I reduce the range to the unique sex counts.


### New Tricks
When merging the 'final tumor volume' data to the original one, I just discovered that if I sort_values on both 'mouse ID' and 'Timepoint', the new dataframe shows the timepoint with all the same mouse ID, then I can just go 'df.drop_duplicates(subset=['Mouse ID'])' to eliminate un-wanted tumor values for the same mouse ID at other timepoints. However this feels bit doggy it does not sound like the 'formal' way of sorting and merging data so I put # in front of it.

### Uncertainties
The first one that really gave me headache is the loop of collecting tumor values on each drug part. I understand that the basic reason of applying a for loop is just because we need to repeat the steps from 'selecting target drug - selecting tumor value - calculate requested values' 4 times as there are 4 drugs. To be honest that if not because of the 'for loop' is stated under the instruction line, I would not think of it at the first place. More likely I will just split into 4 dataframe with each one of them containing the tumor values and then for the calculations.
The other one is that when print my findings of the same topic, the drug, 'infubinol' has an outlier where the other 3 do not. I have tried multiple times involving a if statement, while statement to show when there is no outiler, print '0' and 'mouse id, drug regimen and the tumor value' when there is one. I end up with '[]' for no outiler, and the whole row information when there is one. A big failure!!!
