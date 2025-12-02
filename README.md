# ☀️ X-Class Solar Flare Tracker for TradingView

A comprehensive TradingView Pine Script indicator that tracks and visualizes X-class solar flares - the most powerful classification of solar flares based on X-ray intensity measured by GOES satellites.

## 📊 Features

- **Historical Data**: Includes major X-class flares from 1989 to November 2024
- **Visual Markers**: Color-coded triangles appear on the chart when solar flares occurred
- **Magnitude Labels**: Shows the exact X-class rating (e.g., "2024-10-03 X9.0")
- **Statistics Table**: Real-time statistics showing:
  - Total number of X-flares in the dataset
  - Breakdown by magnitude categories (X1-X5, X5-X10, X10-X20, X20+)
  - The strongest flare and its date
- **Customizable Display**:
  - Filter by minimum magnitude
  - Adjust colors for different flare categories
  - Toggle markers, labels, and statistics table
  - Choose table position on chart

## 🎨 Color Coding

- **Yellow**: X1-X5 flares (moderate)
- **Orange**: X5-X10 flares (strong)
- **Red**: X10-X20 flares (severe)
- **Magenta**: X20+ flares (extreme)

## 📚 Important Information About Solar Flare Data

### X-Class Classification Timeline

The X-class classification system for solar flares only began with GOES satellite X-ray measurements:

- **1975-1996**: NASA tracked solar flare activity, but early data is less reliable
- **1996-Present**: Complete and most accurate public records (Solar Cycle 23 onwards)
- **Before 1975**: No "X-class" data exists because the classification system hadn't been established

This means **there is no "X-class" data from 1900-1975** as originally requested. The dataset in this script includes the most significant historical X-class flares from reliable records.

### Data Coverage in This Script

This script includes:
- Major X-class flares (X5+) from 1989 onwards
- All X-class flares from 2021 onwards (Solar Cycle 25)
- The most significant events including:
  - X45 flare (November 4, 2003) - largest on record
  - X28 flare (November 4, 2003) - measured value before revision
  - X20 flares (August 16, 1989 and April 2, 2001)
  - Record-breaking 2024 with 54 X-class flares

## 🚀 How to Use

### Installation

1. Open TradingView and click on the **Pine Editor** at the bottom of the screen
2. Copy the entire contents of `solar_flare_tracker.pine`
3. Paste it into the Pine Editor
4. Click **"Add to Chart"**

The indicator will appear as an overlay on your chart with triangular markers showing where solar flares occurred.

### Customization

Access the settings by clicking the gear icon ⚙️ next to the indicator name:

**Display Options:**
- **Show Flare Markers on Chart**: Toggle the triangular markers
- **Minimum X-Class Magnitude to Display**: Filter out smaller flares (1.0 to 50.0)
- **Show Flare Magnitude Labels**: Toggle the text labels
- **Show Flare Statistics Table**: Toggle the statistics box
- **Table Position**: Choose where the statistics appear

**Colors:**
- Customize the color for each magnitude category

## 🔄 Updating with New Solar Flares

Solar flares happen regularly, especially during solar maximum. Here's how to add new ones:

### Step 1: Monitor for New X-Class Flares

Check these sources regularly:
- **NOAA Space Weather Prediction Center**: https://www.swpc.noaa.gov/
- **SpaceWeatherLive.com**: https://www.spaceweatherlive.com/en/solar-activity/solar-flares
- **Twitter/X**: Follow @NOAA_Space_Wx for real-time alerts

### Step 2: Get Flare Details

When a new X-class flare occurs, note:
- **Date and Time (UTC)**: e.g., "2025-01-15 14:30 UTC"
- **Magnitude**: e.g., "X5.5"
- **Active Region** (optional): e.g., "AR3567"

### Step 3: Convert Date to Unix Timestamp

Use an online converter like:
- https://currentmillis.com/
- https://www.epochconverter.com/

**Example:**
- Date: January 15, 2025 at 14:30 UTC
- Unix timestamp: 1736951400000 (in milliseconds)

### Step 4: Add to the Script

In the Pine Script, find this section (around line 275):

```pine
// 🆕 TO ADD NEW FLARES, INSERT THEM HERE:
// Example format:
// array.push(flareTimes, TIMESTAMP), array.push(flareMags, MAGNITUDE), array.push(flareDescs, "YYYY-MM-DD XMAG")
```

Add a new line:

```pine
array.push(flareTimes, 1736951400000), array.push(flareMags, 5.5), array.push(flareDescs, "2025-01-15 X5.5")
```

### Step 5: Save and Refresh

1. Click **Save** in the Pine Editor
2. The chart will automatically update with the new flare marker

## 📈 Understanding the Display

- **Triangular Markers**: Appear above the bar on the day the flare occurred
- **Labels**: Show the date and magnitude (e.g., "2024-10-03 X9.0")
- **Statistics Table**: Updates automatically to reflect all flares in the dataset

**Note**: The markers appear on the chart based on the timestamp. Since solar flares are specific events and most financial charts show daily or longer timeframes, the marker will appear on the bar that includes that date.

## 🌟 Notable Solar Flares in the Dataset

### Strongest Flares Ever Recorded:
1. **X45** (November 4, 2003) - Revised estimate; originally measured as X28
2. **X28** (November 4, 2003) - Original GOES measurement before saturation analysis
3. **X20** (April 2, 2001)
4. **X20** (August 16, 1989)
5. **X19.3** (March 9, 2011)

### Recent Notable Events:
- **X9.0** (October 3, 2024) - Strongest of Solar Cycle 25
- **X8.7** (May 14, 2024)
- **X8.7** (December 24, 2014)

### Record-Breaking Year:
- **2024**: 54 X-class flares (highest total since reliable records began in 1996)

## 🔬 Data Sources

This script compiles data from:
- **NOAA Space Weather Prediction Center (SWPC)**: Official U.S. government source for space weather
- **SpaceWeatherLive.com**: Comprehensive historical database since 1996
- **NASA Solar Dynamics Observatory (SDO)**: Solar observation and flare detection
- **GOES Satellites**: X-ray flux measurements for flare classification

## 📖 Learn More About Solar Flares

Solar flares are classified by the peak flux of X-rays in the 0.1-0.8 nanometer wavelength range:

- **C-class**: Small flares with minimal effects on Earth
- **M-class**: Medium-sized flares that can cause brief radio blackouts
- **X-class**: The largest flares, can cause planet-wide radio blackouts and radiation storms

X-class has no upper limit:
- **X1** is "standard" strong
- **X10** is 10 times more intense than X1
- **X20+** are extremely rare and powerful

## ⚠️ Limitations

1. **Historical Coverage**: Only includes X-class data from 1975 onwards (GOES satellite era)
2. **Public Data**: Most comprehensive public records start from 1996
3. **Manual Updates**: Requires manual addition of new flares (TradingView Pine Script cannot fetch external real-time data)
4. **Timestamp Matching**: Flares appear on the bar/candle that includes their timestamp
5. **Date Precision**: Daily or longer timeframes work best for visualization

## 🤝 Contributing

To improve this dataset:
1. Fork the repository
2. Add new verified X-class flare data
3. Submit a pull request with sources cited

## 📄 License

This Pine Script® code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/

## 👤 Author

© salvia420

## 🔗 Additional Resources

### Official Sources:
- [NOAA Space Weather Prediction Center](https://www.swpc.noaa.gov/)
- [SpaceWeatherLive.com](https://www.spaceweatherlive.com/)
- [NASA Solar Dynamics Observatory](https://sdo.gsfc.nasa.gov/)

### Historical Data:
- [Wikipedia: List of Solar Storms](https://en.wikipedia.org/wiki/List_of_solar_storms)
- [Australian BOM: Large Solar Flares Since 1976](https://www.sws.bom.gov.au/Educational/2/3/9)

---

**Enjoy tracking the Sun's most powerful events! ☀️⚡**

*Remember: Solar Cycle 25 is currently approaching solar maximum, so expect increased X-class flare activity through 2024-2025.*
