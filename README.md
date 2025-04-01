# Python -> AWS-NHL-Data
Since I am a hockey fan and like to track average stats by team, 
I created a python script which grabs every game and score from a URL in the 2024-2025 season,
then filters the dataset to the last 2 months of games (in this case, I am more interested in the average goals for and goals against for just the most recent 2 months).

The python script updates the dataset daily to pull in the most recent 2 months of game data as I have the start_date and end_date set to dynamic date variables.

After python cleans the data that I scraped from the web, I have a block of code that automatically writes the file into an AWS s3 bucket.
From there, I set up an AWS Redshift database that pulls in the updated s3 file so users can query the dataset using SQL.

Once the data is in Redshift, I like to create re-usable SQL code that runs on a schedule and shows me the average goals scored by team when they are the home team and the away team.
