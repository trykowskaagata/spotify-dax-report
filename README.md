# spotify-dax-report
## PROJECT OVERVIEW
This is a personal Power BI project, created out of curiosity to explore my own Spotify listening history. 
The goal was to analyze my individual streaming behavior and compare it to the insights typically presented in Spotify Wrapped — but in a much more detailed, data-driven way.
Using Power BI, I transformed raw streaming data into an interactive dashboard that reveals how, when, and what I listen to most.
The project allowed me to practice the full data analytics workflow — from cleaning and modeling the dataset, through DAX measure creation, to designing visually engaging reports with storytelling insights.

## DATA UNDERSTANDING
The dataset was obtained via Spotify’s Data Access Request feature, through which users can download their Extended Streaming History.
The data was provided as multiple JSON files, each containing detailed playback records, such as song metadata, playback duration, timestamps, and listening context.
I merged the original JSON file into a CSV format using Python. The resulting dataset was imported into Excel, where I initiated data transformation and cleaning using Power Query before loading it into Power BI for further analysis.
The key columns included:
- User activity
- Location and device
- Music metadata
- Podcast metadata
- Playback context
An initial data exploration revealed that many columns were thematically grouped, suggesting a potential for restructuring the dataset into a star schema. This would allow for more efficient modeling and analysis in Power BI, with separate dimension tables for users, tracks, episodes, and time.


## DATA PREPARATION 
Initially, the columnss had long and technical names such as: master_metadata_track_name, master_metadata_album_artist_name, and master_metadata_album_album_name.
To simplify further work, these columns were renamed to Track, Artist, and Album for clarity and easier reference.
Several columns with significant amounts of missing data—such as those related to audiobooks and podcasts—were removed during preprocessing. Additionally, the conn_country column was excluded due to containing only a single unique value, which provided no analytical relevance.
A new column called s_played was created by dividing the ms_played values by 1000, converting playback time from milliseconds to seconds.
Additional time-based columns were extracted from the timestamp (ts) field.
To build a more flexible data model, I created separate dimension tables — Artists, Albums, and Tracks — from distinct values of their respective columns.
These tables were then connected to the main Spotify_Streams table to form a star schema model.

## KEY MEASURES
Total minutes listened
Skip rate
YoY Growth %: Habit evolution over time
Discovery Rate: Openness to new music
Loyalty Score: Artist loyalty strength
New Artists
Peak Hour


DEPLOYMENT
The final Power BI dashboard contains three main pages:
Listening Overview: general engagement and time distribution
Behavior Analysis: detailed view of listening patterns across days and hours
Year-over-Year Comparison: long-term trends and artist loyalty metrics
The dashboard is designed for personal insight but also demonstrates my technical and analytical skills in Power BI and DAX.


For a more detailed explanation of the dataset structure and fields:
https://support.spotify.com/us/article/understanding-your-data/

