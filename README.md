# Thesis plan

## Check the [PIC](/aux/93748_PIC_Rafael_Candeias.pdf) for better information

## 1. Abstract

24950: Semi-Supervised Learning Applied to Soil Nutrient Estimation Using Earth Observation Data
This project involves developing and evaluating semi-supervised machine-learning algorithms for estimating the number of soil nutrients (e.g., potassium) from satellite images. The developed algorithms will be incorporated into an existing toolkit (TerraSenseTK) that is being developed to facilitate the development of machine-learning algorithms for satellite data. Some of the tasks involved are the following:
• Become familiarized with the problem of soil sensing using earth observation data and with the TerraSenseTK
• Conduct initial analysis of an existing dataset collected on Madeira Island
• Become familiarized with semi-supervised learning and implement different algorithms
• Integrate the developed algorithms in the TerraSenseTK
• Conduct an extensive performance evaluation of the developed semi-supervised approaches and benchmark against the algorithms already available in the TerraSenseTK.

## 2. To know

### 2.1 Photosynthesis

The process that plants do to convert sunlight into sugars/minerals.

### 2.2 Chlorophyll

Green pigment found in plants that performs photosynthesis. The greener a plant is, the healthier.

### 2.3 Spectral Vegetation Indices, or SVI

Represent any indices resultant of the combination of several spectral bands into a single value to evaluate vegetation.
NIR corresponds to the near infra-red band.
R correlates to the red band.
G correlates to the green band.

#### 2.3.1 Sensors in sentinel 2A and 2B from the Copernicus program

- *B01* spatial resolution = 60m , wavelength = 442.2nm / 442.7nm & bandwidth = 21nm
- *B02* spatial resolution = 10m , wavelength = 492.4nm / 492.1nm & bandwidth = 66nm
- *B03*, G spatial resolution = 10m , wavelength = 559.8nm / 559.0nm & bandwidth = 36nm.
- *B04*, R spatial resolution = 10m , wavelength = 664.6nm / 664.9nm & bandwidth = 31nm
- *B05*, RE1 spatial resolution = 20m , wavelength = 704.1nm / 703.8nm & bandwidth = 15nm / 16nm.
- *B06*, RE2 spatial resolution = 20m , wavelength = 740.5nm / 739.1nm & bandwidth = 15nm
- *B07*, NIR spatial resolution = 20m , wavelength = 782.8nm / 779.7nm & bandwidth = 20nm
- *B08* spatial resolution = 10m , wavelength = 832.8nm / 832.9nm & bandwidth = 106nm
- *B8A* spatial resolution = 20m , wavelength = 864.7nm / 866.0nm & bandwidth = 21nm / 22nm
- *B09* spatial resolution = 60m , wavelength = 945.1nm / 943.2nm & bandwidth = 20nm / 21nm
- *B10* spatial resolution = 60m , wavelength = 1373.5nm / 1376.9nm & bandwidth = 31nm / 30nm
- *B11* spatial resolution = 20m , wavelength = 1613.7nm / 1610.4nm & bandwidth = 91nm / 94nm
- *B12* spatial resolution = 20m , wavelength = 2202.4nm / 2185.7nm & bandwidth = 175nm / 185nm

#### 2.3.2 SVI, Spectral Vegetation Indices

- *NDVI74* Normalized Difference Vegetation Index, evaluates the amount of vegetation.
    -1 <= (NIR - R) / (NIR + R) <= 1
    Big values mean more vegetation.
- *IRECI* Inverted Red-Edge Chlorophyll Index, estimates clorophyll content.
    (NIR - R) / (RE1 / RE2).
    Near direct measure of field clorophyll(g/m²).
- *REM // VCI* Vegetation Condition Index, compares the vegetation with values from previous years.
    Expressed in %.
    ((NDVIa - NDVImin) / (NDVImax - NDVImin)) * 100
- *GM* There are a lot here. How was this calculated?
- *REPLI* NOT FOUND.
- *RECHI* NOT FOUND.
- *S2REP* Sentinel-2-Red-Edge Position, NOT FOUND
    705 + 35 * ((((NIR + R)/2) − RE1) / (RE2 − RE1))
- *NDI45* NOT FOUND.
    (RE1 - R) / (RE1 + R).
- *GNDVI* Green Normalized Difference Vegetation Index, estimates canopy chlorophyll.
    (NIR - G) / (NIR + G).
    Detects values of vegetation with green-band instead of the red-band.
- *NDVINB* NOT FOUND
- *RVI* Simple Ratio Vegetation Index, evaluates the amount of green vegetation.
    NIR / R
    High values mean good amounts of green.

### 2.3.3 Variability in SVIs

- The angle that the sunrays have on the floor affects the amount of energy that it is reflected, thus disturbing the values captured by the sensors.
- Same place in different seasons will have divergent values.
- Values received might be diferent from what the ground emited. Atmospheric events tend to lower the SVI values.
- The satelite might take pictures looking straight down, nadir, or from the side, off-nadir. Seeing a field from the nadir point of view allows to detect more soil, rocks, leafs, etc.. than the off-nadir, which might mostly catch vegetation.
- As time goes by, the sensors lose some of their precision, moreover its recalibration is hard to perform as they are in orbit. So, even if the ground did not change, the values read might be different.

### 2.4 Soil reflectance

Green/cholrophyll is higly reflectant to NIR but little to R.
Bare soil and rocks reflect the same amount of NIR and R.
Water, clouds and snow reflect more R than NIR.

### 2.5 Soil fertility

Nutrients required for a good plant growth. Can be splitted into macronutrients, which are needed in big quantities, and micronutrients.
Ph should be between 6 - 7.

#### 2.5.1 Macronutrients

- *Nitrogen(N)*, protein and enzyme component.
- *Phosporus(P)*, membranes, enenrgy, DNA.
- *Potassium(K)*, osmotic balance.
- *Calcium(Ca)*, cell structure.
- *Magnesium(Mg)*, clorophyll, enzyme activation.
- *Sulfur(S)*, protein and enzyme compontent.

#### 2.5.2 Micronutrients

- *Iron(Fe)*, enzyme function, required for chlorophyll production
- *Zinc(Zn)*, enzyme component.
- *Copper(Cu)*, enzyme function.
- *Boron(B)*, cell wall.
- *Molybdenum(Mo)*, enzyme function.
- *Nickel(Ni)*, enzyme component.
