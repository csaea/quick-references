# Pandas Quick Reference

## Reading Data
- **`df = pd.read_csv('airports.csv')`**: Load an airport dataset CSV into a DataFrame.

## Exploring Data
- **`df.columns`**: View column names, e.g., `['Airport Name', 'IATA Code', 'Latitude', 'Longitude']`.
- **`df.tail(5)`**: View the last 5 rows of airport data.

## Selecting Data
- **`df[['Airport Name', 'IATA Code']]`**: Select the airport names and their IATA codes.
- **`df.iloc[10:15]`**: Select rows 10 to 14, displaying airport details.
- **`df.iloc[2, 3]`**: Select the value from row 2, column 3 (e.g., latitude of an airport).
- **`df.loc[df['IATA Code'] == 'LAX']`**: Filter rows to show only Los Angeles International Airport.

## Sorting Data
- **`df.sort_values('Airport Name')`**: Sort the DataFrame alphabetically by airport name.


