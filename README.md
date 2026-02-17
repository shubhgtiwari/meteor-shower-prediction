# Meteor Shower Prediction

Prediction algorithm that determines the **best date and city** to view major meteor showers by cross-referencing **comet debris schedules**, **moon phase brightness**, **constellation visibility by latitude**, and **city locations** worldwide.

*Built as part of Microsoft's "Explore Space with Python" learning path.*

## Meteor Showers Analyzed

| Shower | Parent Comet | Best Month | Radiant Constellation |
|--------|-------------|------------|----------------------|
| Lyrids | Thatcher | April | Lyra |
| Eta Aquarids | Halley | May | Aquarius |
| Orionids | Halley | October | Orion |
| Perseids | Swift-Tuttle | August | Perseus |
| Leonids | Tempel-Tuttle | November | Leo |

## Algorithm

```
For each city (256 worldwide):
  1. Check latitude against constellation visibility range
  2. Check hemisphere match (northern/southern preference)
  3. For each day in shower's active window:
     a. Compute moon phase illumination percentage
     b. If moon brightness < threshold → mark as optimal viewing
  4. Return best viewing dates ranked by darkness
```

### Data Pipeline

| Dataset | Records | Source |
|---------|---------|--------|
| `meteorshowers.csv` | 5 showers | NASA Solar System Exploration |
| `moonphases.csv` | 366 days (2020) | timeanddate.com |
| `constellations.csv` | 5 radiants | Wikipedia (IAU designated) |
| `cities.csv` | 256 cities | Wikipedia (national capitals by latitude) |

### Processing Steps

1. **Type Conversion:** Month strings → integers, moon phases → numeric illumination values
2. **Missing Data:** Forward-fill moon phase data for all 366 days
3. **Cross-Reference:** Join meteor shower windows with moon phase calendar
4. **Latitude Filtering:** Match city latitudes to constellation visibility bands
5. **Prediction:** Output optimal city + date combinations per meteor shower

## Tech Stack

- **Language:** Python (Jupyter Notebook)
- **Libraries:** pandas, NumPy
- **Data Sources:** NASA, timeanddate.com, Wikipedia

## Skills Demonstrated

- **Data Engineering:** Multi-source data integration, type conversion, missing value imputation
- **Algorithm Design:** Multi-constraint optimization (astronomy + geography + lunar cycle)
- **Domain Knowledge:** Orbital mechanics, meteor shower astronomy, constellation visibility
