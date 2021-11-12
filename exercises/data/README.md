# NationalParkService_VisitationStats.csv- A.K.A. The National Parks Dataset

The United States National Park Service (NPS) has a [query builder](https://irma.nps.gov/STATS/SSRSReports/National%20Reports/Query%20Builder%20for%20Public%20Use%20Statistics%20(1979%20-%20Last%20Calendar%20Year) webpage.  This query builder allows you to explore visitation statistics for any complete year since 1979 for any unit within the NPS system.  The data includes recreational visitors, overnight stays of various types and is granular to the month level.  As the database is very large if you try to include too many parks or park types, you’ll overshoot the query size limits.  If you want to view National Park and National monument data at the same time in the query builder, you’ll need to select the Annual Summary Only option.

The file in this repository is a combination of multiple queries, downloaded from the query builder webpage and recombined.  In each case, the query selected all parks, all regions, all field names, all months and all years.  There were two seperate queries downloaded and recombined into a third file.  The park types contained in the files are:

1. Query Builder for Public Use Statistics (1979 - Last Calendar Year).csv
  * national parks
  * national lakeshores
  * national seashores
  * national wild and scenic rivers

2. Query Builder for Public Use Statistics (1979 - Last Calendar Year) (nm).csv
  * national monuments
  * national recreation areas

3. NationalParkService_VisitationStats - Sheet1.csv
  * all of the above park types

Additionally, the collated data is [mirrored on a public Google sheet]([https://docs.google.com/spreadsheets/d/1vi8fPg00o1ws-GptHCsMTdZkk_cQ3tz1hae6z7tQ0b4/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1vi8fPg00o1ws-GptHCsMTdZkk_cQ3tz1hae6z7tQ0b4/edit?usp=sharing)).  Because SAP Analytics Cloud can read directly from Google sheets as a data source and import jobs from data connections can be re-wrangled, but uploaded files can't be, this workshop uses the Google sheet copy.
