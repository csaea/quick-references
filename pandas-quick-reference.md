# Pandas Quick Reference

A quick-reference of basic pandas commands (examples use aviation datasets). 

## Reading Data
- **`df = pd.read_csv('airports.csv')`**: Load an airport dataset CSV into a DataFrame.
- **`planes_df = pd.read_csv('airplanes.csv')`**: Load an airplane dataset CSV into another DataFrame.

## Exploring Data
- **`df.columns`**: View column names, e.g., `['Airport Name', 'IATA Code', 'Latitude', 'Longitude']`.
- **`df.tail(5)`**: View the last 5 rows of airport data.

## Selecting Data
- **`df[['Airport Name', 'IATA Code']]`**: Select the airport names and their IATA codes.
- **`df.iloc[10:15]`**: Select rows 10 to 14, displaying airport details.
- **`df.iloc[2, 3]`**: Select the value from row 2, column 3 (e.g., latitude of an airport).
- **`df.loc[df['IATA Code'] == 'LAX']`**: Filter rows to show only Los Angeles International Airport.
- **`airport = df.loc[df['IATA Code'] == 'JFK', ['Latitude', 'Longitude']]`**: Look up latitude and longitude for JFK Airport.

## Sorting Data
- **`df.sort_values('Airport Name')`**: Sort the DataFrame alphabetically by airport name.

## Cross-Referencing Data
- **`planes_df = planes_df.sort_values('Fuel Efficiency', ascending=False).head(3)`**: Get the top 3 most fuel-efficient planes.
- **`distance = haversine(lat1, lon1, lat2, lon2)`**: Calculate the distance between two airports using latitude and longitude.
- **`planes_df['Estimated Fuel Usage'] = distance / planes_df['Fuel Efficiency']`**: Estimate fuel usage for each plane.


