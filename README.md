# Election_Analysis

## Election Audit Overview
A Colorado Board of Elections employee has given you the following tasks to complete the election audit of a recent local congressional election.

1. Calculate the total number of votes cast.
2. Get a complete list of candidates and counties that received votes.
3. Calculate the total number of votes each candidate received.
4. Calculate the voter turnout by county.
5. Calculate the percentage of votes each candidate won.
6. Calculate the percentage of votes each county had.
7. Determine which county had the largest turnout.
8. Determine the winner of the election based on popular vote.

## Resources
- Data source. [election_results.csv](/Resources/election_results.csv)
- Software: Python 3.7.6, Visual Studio Code, 1.68.1

## Election Audit Results
The analysis for the election show that:
- There were 369,711 votes cast in the election.
- The counties were:
  - Jefferson
  - Denver
  - Arapahoe
- The county turnout was:
  - Jefferson County had 10.5% of the total voters with 38,855 votes. 
  - Denver County had 82.8% of the total voters with 306,055 votes.
  - Arapahoe County had 6.7% of the total voters with 24,801 votes.
- The county with the largest turnout was:
  - Denver County
- The candidates were:
  - Charles Casper Stockham
  - Diana DeGette
  - Raymon Anthony Doane
- The candidate results were:
  - Charles Casper Stockham received 23.0% of the vote and 85,213 number of votes.
  - Diana DeGette received 73.8% of the vote and 272,892 number of votes.
  - Raymon Anthony Doane received 3.1% of the vote and 11,606 number of votes.
- The winner of the election was:
  - Diana DeGette who received 73.8% of the vote and 272,892 number of votes.
 
## Election Audit Summary
### Business Proposal on How to Use Script
It is important that the data provided for the script is formatted correctly and in the proper directory. In order for the script to run without any changes, a csv file with Ballot ID, County Name, and Candidate Name needs to be provided. These data points need to be in columns 1,2, and 3 respectively. And lastly, the csv file has to be uploaded into the resources directory named "election_analysis.csv". If those conditions are satisfied the results will be printed to a text file in the analysis directory labelled "election_analysis.txt". These results will have county and candidate names, county turnout by percentage and votes, the county with the largest turnout, candidate results by percentage and votes, and the winner of the election with their percent votes received and total number of votes received.

### Modifying the Script
If it is not possible to fulfill the above conditions, the script has to be modified. It is very important that the data is read correctly, so if the election data is not in the resource folder and not named "election_results" (It must be a csv file), then *line 9* in the code must be adjusted.

*Lines 8 and 9*
```
# Add a variable to load a file from a path.
file_to_load = os.path.join("Resources", "election_results.csv")
```
*Line 9* of the code is finding the data, so if the election results data is not in resources, then it must be changed to `os.path.join("wherever your data is stored on file", "name of file.csv")`. This will allow the script to find the data and perform the proper analysis.

And secondly, if the county names and candidate names are not in columns 2 and 3 of the election_analysis.csv, then lines 50 and 53 must be changed. See below:

*Lines 49 and 50*
```
# Get the candidate name from each row.
candidate_name = row[2]
```
For line 50, the input for `row[2]` must be the column number of where the candidate data is minus 1 or `row[candidateData_column - 1]`. For example, if you have your candidate data in column 7, then the input for *line 50* must be `row[6]`. The same can be said for county data:

*Lines 52 and 53*
```
# 3: Extract the county name from each row.
county_name = row[1]
```
The code on *line 53* needs to be modified the same way to represent where the county data is. `row[1]` needs to be changed to `row[countyData_column - 1]`. 