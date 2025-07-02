# Forest Loss in Colombia's Indigenous Lands: A Decade of Change (2016-2025)

## Project Overview

This project analyzes deforestation patterns in the Llanos del Yari-Yaguara II Indigenous Reserve in Colombia over a 10-year period (2016-2025) using satellite imagery and vegetation indices. The study focuses on understanding vegetation changes and identifying deforestation patterns to support informed decision-making in forest management.

## Study Area

- **Location**: Llanos del Yari-Yaguara II Indigenous Reserve spanning three Colombian municipalities: San Vicente del Caguán, La Macarena, and Calamar
- **Area**: 146,500 hectares (127,000 hectares of forest and 19,500 hectares of grassland)
- **Communities**: Home to Pijao, Tucano, and Piratapuyo ethnic groups

## Objectives

- Assess vegetation changes over a 10-year period using satellite imagery
- Identify deforestation patterns and their temporal distribution
- Analyze the impact of illegal activities on forest cover
- Support forest management decision-making with scientific evidence

## Methodology

### Data Sources
- **Primary**: Sentinel-2 satellite imagery (10m resolution, 5-day revisit)
- **Secondary**: Landsat 8 data for validation
- **Verification**: ESRI Global Land Use/Land Cover dataset

### Vegetation Indices
- **NDVI** (Normalized Difference Vegetation Index): Vegetation health and density assessment
- **EVI** (Enhanced Vegetation Index): Enhanced vegetation monitoring with atmospheric correction

### Analysis Techniques
- Time series analysis of vegetation indices
- Before-after comparison mapping
- Seasonal variation analysis
- Land use/land cover change detection
- Change trend analysis

## Key Findings

### Temporal Patterns
- **Two major deforestation periods**: 2018-2019 and 2022-2024
- **Peak deforestation**: 2,348 hectares lost in 2018 (~6 hectares/day)
- **Recent impact**: 856 hectares destroyed by new 14-kilometer illegal road (2023-2024)

### Land Use Changes (2017-2023)
- **Tree cover decrease**: 15% reduction (275 km² to 235 km²)
- **Rangeland increase**: 140% expansion (30 km² to 70 km²)
- **Primary driver**: Forest-to-rangeland conversion

### Seasonal Patterns
- **Wet season** (Jan-Jun): Higher vegetation health
- **Dry season** (Jul-Dec): More pronounced vegetation stress
- **Consistent pattern**: NDVI values higher than EVI across all seasons

## Drivers of Deforestation

1. **Illegal road construction** - Primary access facilitator
2. **Cattle ranching expansion** - Major land use change
3. **Land grabbing** - Territorial control issues
4. **Coca cultivation** - Illicit crop production
5. **Indigenous displacement** - Loss of traditional forest guardians



## Tools and Technologies

- **Google Earth Engine** - Satellite data processing
- **Python** - Data analysis and visualization
  - `geemap` - Interactive mapping
  - `pandas` - Data manipulation
  - `matplotlib/seaborn` - Visualization
  - `numpy` - Numerical computations
- **QGIS** - Spatial analysis
- **Jupyter Notebooks** - Analysis workflows

## Code Examples

### NDVI Calculation
```javascript
// Google Earth Engine code
var ndvi = image.normalizedDifference(['B8', 'B4']).rename('NDVI');
```

### EVI Calculation
```javascript
// EVI = G * ((NIR - RED) / (NIR + C1 * RED - C2 * BLUE + L))
var evi = image.expression(
  '2.5 * ((NIR - RED) / (NIR + 6 * RED - 7.5 * BLUE + 1))', {
    'NIR': image.select('B8'),
    'RED': image.select('B4'),
    'BLUE': image.select('B2')
}).rename('EVI');
```

## Interactive Resources

- **Time Series Analysis**: [Google Earth Engine Code](https://code.earthengine.google.com/6d20cf2ddb833c3006a3704ae29366aa)
- **Seasonal Analysis**: [Google Earth Engine Code](https://code.earthengine.google.com/da773e5dc3b63a77e71269753287cd43)
- **NDVI/EVI Calculation**: [Google Earth Engine Code](https://code.earthengine.google.com/6d1200cc44e1a7005c28d9ab16bae50e)

## Results

### Quantitative Outcomes
- **Total forest loss**: 1,119.5 km² cumulative (2016-2025)
- **Lowest forest cover**: 5.1 km² (2019)
- **Partial recovery**: 144.8 km² by 2025
- **Community impact**: Displacement of indigenous communities

### Visual Outputs
- Time series maps showing vegetation changes
- NDVI difference maps highlighting deforestation areas
- Seasonal variation charts
- Land use change statistics

## Environmental and Social Impact

The deforestation has severely impacted:
- **Indigenous communities** forced to abandon traditional lands
- **Biodiversity loss** in critical Amazon region
- **Traditional forest protection** systems disrupted
- **Regional ecosystem services** compromised

## Installation and Usage

### Prerequisites
```bash
pip install earthengine-api
pip install geemap
pip install pandas matplotlib seaborn
```

### Authentication
```python
import ee
ee.Authenticate()
ee.Initialize()
```

### Running the Analysis
```bash
# Clone the repository
git clone https://github.com/rafimt/DeforestationAnalysis.git

# Navigate to notebook directory
cd DeforestationAnalysis/notebook/

# Launch Jupyter
jupyter notebook
```
