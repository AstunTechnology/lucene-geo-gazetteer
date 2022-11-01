Noting some discrepancies or odd return of results when using the geoparser as compared to searching using Luke:

| Search Term | Luke Query| Luke Result | Geoparser Query | Geoparser Result |
|-------------|------------|------------|-----------------|------------------| 
| Abraham Heights | `name: Abraham name: Heights` | Top Result = "Abraham Heights" | s=Abraham&s=Heights | `{"Abraham":[{"name":"Abraham Close","countryCode":"GB","admin1Code":"SO30","admin2Code":"transportNetwork","latitude":449958.0,"longitude":112436.0}],"Heights":[{"name":"Harrington Heights","countryCode":"GB","admin1Code":"LU5","admin2Code":"transportNetwork","latitude":501489.0,"longitude":224175.0}]}` |
|Lancaster | `name: Lancaster` | Top Result = "Lancaster" | s=Lancaster | `{"Lancaster":[{"name":"Lancaster Close","countryCode":"GB","admin1Code":"LU6","admin2Code":"transportNetwork","latitude":500983.0,"longitude":222710.0}]}` |

