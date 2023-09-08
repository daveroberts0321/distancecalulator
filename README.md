# Distance Calculator Go Package

The Distance Calculator Go package allows you to easily calculate distances between geographical coordinates using the Haversine formula.

## Installation

To use the Distance Calculator Go package in your Go project, you can follow these steps:

1. Open your terminal or command prompt.

2. Run the following command to install the package:

   ```shell
   go get github.com/daveroberts0321/distancecalculator

## Example Usage 

  ```shell
    func TestDistance() {
        // returns test distance between two reference points of
        // - Meters: 3940132.35 m
        // - Miles: 2448.28 miles
        //both within haversine distance limitations of 0.5% error

        
        // Haversine formula to calculate distance between two points
        fmt.Println("starting distance test")
        // Define coordinates for the origin and destinations
        origin := distancecalculator.Coord{
            Ref:  "reference1",
            Lat:  40.7128,  // Latitude of the origin
            Long: -74.0060, // Longitude of the origin
        }

        destinations := []distancecalculator.Coord{
            {
                Ref:  "reference2",
                Lat:  34.0522,   // Latitude of destination
                Long: -118.2437, // Longitude of destination
            },
            // Add more destination coordinates as needed
        }

        // Calculate distances in meters
        distancesInMeters := distancecalculator.CalculateDistancesMeters(origin, destinations)

        // Calculate distances in miles
        distancesInMiles := distancecalculator.CalculateDistancesMiles(origin, destinations)

        // Display the results
        for i, dest := range destinations {
            fmt.Printf("Distance from %s to %s:\n", origin.Ref, dest.Ref)
            fmt.Printf("- Meters: %.2f m\n", distancesInMeters[i])
            fmt.Printf("- Miles: %.2f miles\n", distancesInMiles[i])
        }
    }



