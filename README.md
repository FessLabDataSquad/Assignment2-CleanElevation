# Assignment2-CleanElevation

Here are various ways this script could be improved.

##1. Eliminate manual steps

###a. See section "Data preparation in spreadsheet software" -- all of these simple operations could be done in R instead.
###b. Success with (1a) would help address a minor problem discussed in the "Finishing time" section -- Excel was cutting off time data at minutes, even when seconds were available. That's not a huge deal in this project, but it is a bit sloppy and cleaning it up would be good.
###c. See section "Load data" -- I am not consistent in how I modify and use variable names. Develop best practice for this and implement it here.


##2. Brute force vs. efficiency

In many cases, I've done things the hard way instead of the smart way. Any time you see a lot of lines that all look very similar, just with one or two parameters changed, that's probably an opportunity to improve efficiency.

###a. See the "Condensing variables" section, especially Studies 3 & 4.
###b. Reverse-scoring could be more efficient with a list of variables and a custom function
###c. Education section probably could be more efficient with custom function


##3. Magic numbers

Generally, instead of hard-coding specific numeric values, it is preferable to create a descriptive variable name and assign it the numeric value. 

###a. The reverse-scoring section: set something like ''' SCALE_MAX = 7 ; REVERSE_VALUE = SCALE_MAX + 1" and then make a custom function to apply to the relevant list of variables (see 2b)
###b. This issue may or may not be useful for the section about "Playback problems"
###c. Other places?


##4. Excluding cases

As currently written, I have a section where I look at all of the variables that might be used for exclusions (e.g. we want to exclude participants with excessively quick finishing times, so I look at the distribution of finishing times). Then I go on to implement the exclusions in the next section. I bet there's a way to do this that is easier to follow, easier to reconfigure with different judgements, etc. Probably the solution is that, for each exclusion criteria, you create a new logic variable (i.e. is it true or false that this participant finished in less than 5 minutes). You can use that logic variable for (1) counting how many cases violate the condition, and (2) for making the cutoffs (i.e. drop all cases with a "TRUE" in this list of logic variables).
