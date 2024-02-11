# Group-3-Assignment-3
## Homework Assignment 3: Integer Programming Example---Algorithmic Redistricting
Griffin Arnone, Anhua Cheng, & Bailey Scoville
## Objective
Redistricting requires assigning each county to a district in a fair and equitable plan to ensure population balance (one-person-one-vote), district compactness, and equal representation across races within a state. The team aims to use integer programming to map voting districts in the state of Washington, where there are 39 counties and 10 legislative districts. 
## Data
- County adjacency data was pulled from the [National Bureau of Economic Research website](https://www.nber.org/research/data/county-adjacency)
- County demographic data was pulled from the [United States Census Bureau website](https://www.census.gov/topics/population.html)
- County boundaries shapefile data was sourced from the [Washington State Department of Natural Resources](https://geo.wa.gov/datasets/12712f465fc44fb58328c6e0255ca27e/explore?location=47.250857%2C-120.817600%2C8.28)
## Integer Programming Model
King County, Pierce County, and Snohomish County were manually assigned to 5 counties before running the model. The model's objective is to allocate the remaining 36 counties among the remaining 5 districts.
### Objective Function
Minimize the number of counties assigned to each district
### Constraints
- The entire county population must be allocated to a district
- Every county must be allocated to a district
- Districts must have a population between 663,573 and 811,034 voters
- Counties added to a district must neighbor other counties in the same district
- The districts must have equal percentages of white voters (added to the second model)
## Programming
The integer programming code utilizes the Python PuLP library. Python code and output are included in the repository.
## Solution
King County, Pierce County, and Snohomish County, were not included in the programming.
### Model 1 Assignments: 
- District 1: Douglas, Grays Harbor, Okanogan, Pacific, Klickitat, Pend Oreille, Spokane, Whitman
- District 2: Grant, Island, Whatcom, Yakima
- District 3: Adams, Cowlitz, Franklin, Kitsap, Walla Walla, Mason, Skagit
- District 4: Chelan, Clallam, Clark, Columbia, Ferry, Garfield, Kittitas, Lincoln, Stevens
- District 5: Asotin, Benton, Lewis, San Juan, Skamania, Thurston, Jefferson Wahkiakum
- View the [assignment map](https://github.com/bscov/Group-3-Assignment-3/blob/main/Model_1_Map.png)
### Model 2 Assignments (% White Population Constraint): 
- District 1: Lewis, Skamania, Grays Harbor, Klickitat, Spokane
- District 2: Stevens, Walla Walla, Whatcom, Yakima, Grant, Columbia, Whitman
- District 3: Wahkiakum, Skagit, Okanogan, Mason, Pacific, Adams, Lincoln, Kitsap, Island, Garfield, Cowlitz
- District 4: Clark, Franklin, Pend Oreille, Chelan, San Juan, Kittitas
- District 5: Ferry, Douglas, Thurston, Jefferson, Asotin, Clallam, Benton
- View the [assignment map](https://github.com/bscov/Group-3-Assignment-3/blob/main/Model_2_Map.png)
# Discussion
Comparing these maps to the actual Washington district map visually illustrates the failure of both models’ adjacency constraints. In future iterations of the model, the group would explore tightening the adjacency constraint to two neighboring districts and consider the distribution of political party affiliation, Hispanic voters, and Asian voters to create a fair and equitable representation of the Washington voter population.
