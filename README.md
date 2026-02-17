# Meteor Shower Viewing Prediction

## Overview

A data-driven analysis that combines astronomical event data, geographic coordinates, constellation positions, and lunar phase calendars to predict the optimal viewing conditions and locations for meteor shower observation. The project merges multiple datasets to determine when and where specific meteor showers will be most visible.

## Datasets

| File | Description | Size |
|------|-------------|------|
| `meteorshowers.csv` | Meteor shower events with dates and radiant points | 455 B |
| `cities.csv` | City names with geographic coordinates (lat/lon) | 7.3 KB |
| `constellations.csv` | Constellation position data (right ascension, declination) | 256 B |
| `moonphases.csv` | Moon phase calendar (new moon, full moon dates) | 5.5 KB |

## Analysis

The notebook performs the following analysis:

1. **Data Integration:** Merge meteor shower schedules with constellation positions to determine radiant visibility
2. **Geographic Filtering:** Cross-reference city locations with constellation visibility windows based on latitude
3. **Lunar Interference:** Factor in moon phase brightness to identify dark-sky viewing windows
4. **Prediction:** Generate optimal viewing recommendations combining time, location, and lunar conditions

### Key Factors Considered

- **Radiant Altitude:** Whether the meteor shower's radiant constellation is above the horizon at the observer's latitude
- **Moon Phase:** New moon periods provide the darkest skies for optimal viewing
- **Viewing Window:** Peak activity dates for each meteor shower
- **Geographic Position:** Latitude-dependent visibility of source constellations

## Tech Stack

- **Language:** Python
- **Libraries:** Pandas, NumPy, Matplotlib
- **Environment:** Jupyter Notebook

## Project Structure

```
meteor-shower-prediction/
├── meteor-showers.ipynb    # Complete analysis notebook (57 KB)
├── meteorshowers.csv       # Meteor shower event data
├── cities.csv              # City coordinates
├── constellations.csv      # Constellation positions
├── moonphases.csv          # Moon phase calendar
├── README.md
└── LICENSE
```

## Getting Started

```bash
git clone https://github.com/ShubhGTiwari/meteor-shower-prediction.git
cd meteor-shower-prediction

pip install pandas numpy matplotlib jupyter
jupyter notebook meteor-showers.ipynb
```

## License

MIT
