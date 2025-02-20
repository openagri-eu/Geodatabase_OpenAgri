# Geodatabase_OpenAgri

This document provides metadata for the GeoPackage associated with the study titled 
*"Geospatial Framework for Assessing the Suitability and Demand for Agricultural Digital Solutions in Europe: A Tool for Informed Decision-Making"*. 
The GeoPackage contains a single layer of **NUTS3 polygons**, representing regional boundaries across Europe. 
Each polygon is attributed with:

**Environmental, socio-economic, and connectivity variables**: These variables form the basis for the geospatial analysis conducted in the study.
**Derived indexes**: The indexes assess regional suitability and demand for agricultural digital solutions (ADS), as well as connectivity performance. These include:
-Natural Characteristics Similarity Index (NCSI)
-Socio-Economic Characteristics Similarity Index (SCSI)
-Fertilization Need Index (FNI)
-Irrigation Need Index (INI)
-Pest Management Need Index (PMNI)
-Rural Connectivity Performance Index (RCPI)


**Citation Guidelines**

Users of this dataset are required to cite the article *"Geospatial Framework for Assessing the Suitability and Demand for Agricultural Digital Solutions in Europe: A Tool for Informed Decision-Making"* 
in any publication or project utilizing this data. 
Additionally, detailed references to the original databases from which the environmental, socio-economic, 
and connectivity variables were sourced are provided in the article and this documentation. 
These sources should also be appropriately cited to acknowledge the original data providers.

This documentation serves as a quick reference to the dataset structure and content. 
For detailed information on the variables, their calculation methodologies, and the broader context of the study, please consult the associated article.



The variables **Soil\_Organic\_Carbon, Nitrogen, Phosphorous, Soil\_Texture\_Sand, Soil\_Texture\_Clay, Soil\_Texture\_Silt** were derived from the LUCAS 2018 Soil Module and were aggregated to the NUTS3 level polygons as part of the analysis for the creation of relevant indexes. The aggregated values for these variables are not provided here but the original datasets can be acquired/requested from the European soil data centre:
https://esdac.jrc.ec.europa.eu/content/lucas-2018-topsoil-data#tabs-0-description=0
https://esdac.jrc.ec.europa.eu/content/topsoil-physical-properties-europe-based-lucas-topsoil-data

Related references:

Orgiazzi, A., Ballabio, C., Panagos, P., Jones, A., Fernández-Ugalde, O. (2018). *LUCAS Soil, the largest expandable soil dataset for Europe: A review*. European Journal of Soil Science, 69(1): 140-153. <https://doi.org/10.1111/ejss.12499>

Fernandez-Ugalde, O., Scarpa, S., Orgiazzi, A., Panagos, P., Van Liedekerke, M., Marechal A., & Jones, A. (2022). *LUCAS 2018 Soil Module. Presentation of dataset and results*. EUR 31144 EN, Publications Office of the European Union, Luxembourg. ISBN 978-92-76-54832-4, <https://doi.org/10.2760/215013>.

Ballabio C., Panagos P., Montanarella L. Mapping topsoil physical properties at European scale using the LUCAS database (2016) Geoderma, 261 , pp. 110-123.




**Geodatabase Columns**

1) **column\_name: fid**
- **Data Type**: Integer
- **Description**: A unique identifier for each feature in the dataset.

2) **column\_name: NUTS\_ID**
- **Data Type:** Text
- **Description:** Unique identifier for each NUTS 3 region.
- **Notes:** Based on the NUTS (Nomenclature of Territorial Units for Statistics) classification.

3) **column\_name: LEVL\_CODE**
- **Data Type:** Integer
- **Description:** Code representing the NUTS level of the polygon.
- **Notes:** For NUTS 3, this value is typically 3.

4) **column\_name: CNTR\_CODE**
- **Data Type:** Text
- **Description:** ISO country code indicating the country to which the NUTS 3 region belongs.

5) **column\_name: NAME\_LATN**
- **Data Type:** Text
- **Description:** Official name of the NUTS 3 region in Latin characters.

6) **column\_name: NUTS\_NAME**
- **Data Type:** Text
- **Description:** Name of the NUTS 3 region in the native language.

7) **column\_name: MOUNT\_TYPE**
- **Data Type:** Integer
- **Description:** Classification of the region based on mountain typology.
- **Notes:** Values typically range from 0 (non-mountainous) to specific codes for mountainous regions.

8) **column\_name: URBN\_TYPE**
- **Data Type:** Integer
- **Description:** Classification of the region based on urban typology.
- **Notes:** Values typically range from 1 (urban) to 3 (rural).

9) **column\_name: COAST\_TYPE**
- **Data Type:** Integer
- **Description:** Classification of the region based on coastal proximity.
- **Notes:** Values typically range from 0 (non-coastal) to 1 (coastal).

**NUTS\_ID, LEVL\_CODE, CNTR\_CODE, NAME\_LATN, NUTS\_NAME, MOUNT\_TYPE, URBN\_TYPE, and COAST\_TYPE** are derived from Eurostat's NUTS classification system.

**Eurostat (2021)**: *Nomenclature of Territorial Units for Statistics (NUTS)*. Available at: <https://ec.europa.eu/eurostat/web/nuts>

10) **column\_name: Annual\_Precipitation**
- **Data Type:** demical (double)
- **Description:** Aggregated annual precipitation within the NUTS3 region.
- **Units:** millimeters per square kilometer (mm/km²)
- **Notes:** Derived/Calculated from geospatial analysis of the Copernicus Climate Change Service ERA5.** 

References:

Hersbach, H., Bell, B., Berrisford, P., Biavati, G., Horányi, A., Muñoz Sabater, J., Nicolas, J., Peubey, C., Radu, R., Rozum, I., Schepers, D., Simmons, A., Soci, C., Dee, D., Thépaut, J-N. (2023): ERA5 hourly data on single levels from 1940 to present. Copernicus Climate Change Service (C3S) Climate Data Store (CDS).

11) **column\_name: Surface\_Soil\_Moisture (average for highest FAPAR) (volume fraction)**
- **Data Type:** demical (double)
- **Description:** Average surface soil moisture during the month with the highest Fraction of Absorbed Photosynthetically Active Radiation (FAPAR) within the NUTS3 region.
- **Units:** Volume fraction (m³/m³)
- **Notes:** Derived/Calculated from geospatial analysis of the NASA-USDA Enhanced SMAP Global Soil Moisture data and FAPAR datasets.** 

References:

Entekhabi, D., Njoku, E. G., O'neill, P. E., Kellogg, K. H., Crow, W. T., Edelstein, W. N., ... & Van Zyl, J. (2010). The soil moisture active passive (SMAP) mission. Proceedings of the IEEE, 98(5), 704-716.

12) **column\_name: Days\_year\_over\_10°C**
- **Data Type:** Integer
- **Description:** Mean annual number of days with temperatures exceeding 10°C within the NUTS3 region.
- **Units:** Days per year
- **Notes:** Derived/Calculated from geospatial analysis of climatic datasets (e.g., Copernicus Climate Change Service ERA5). column\_name: Species\_Richness

13) **column\_name: Species\_Richness**

- **Data Type:** Integer
- **Description:** Aggregated number of distinct species observed within the NUTS3 region, representing biodiversity.
- **Units:** Count (number of species)
- **Notes:** Derived/Calculated from geospatial analysis of the European Environment Agency's Article 17 spatial data under the Habitats Directive 92/43/EEC. 

References:

European Commission, Council Directive 92/43 CEE on the conservation of natural habitats and of wild fauna and flora, European Community Gazzette 206 (1992) 1-50.

14) **column\_name: Farms\_Predominant\_Size**
- **Data Type:** Text
- **Description:** The predominant farm size in hectares (Ha) within the NUTS3 region, representing the most common size category of agricultural holdings.
- **Units:** Hectares (Ha)
- **Notes:** Derived from Eurostat's Farm Structure Survey (FSS) and aggregated to the NUTS3 level.** 

15) **column\_name: Farms\_Predominant\_Economic\_Size**
- **Data Type:** Text
- ` `**Description:** The predominant economic size of farms in euros (€) within the NUTS3 region, representing the most common economic size category of agricultural holdings.
- **Units:** Euros (€)
- **Notes:** Derived from Eurostat's Farm Structure Survey (FSS) and aggregated to the NUTS3 level.** 

16) **column\_name: Farms\_Predominant\_Legal\_Form**
- **Data Type:** Text
- **Description:** The predominant legal form of agricultural holdings within the NUTS3 region, indicating whether farms are primarily individual, or legal entities.
- **Units:** Categorical (e.g., "Legal", "Natural")
- **Notes:** Derived from Eurostat's Farm Structure Survey (FSS) and aggregated to the NUTS3 level.

17) **Column\_name: Natural\_Person\_Legal\_Form\_to\_Total**
- **Data Type:** Text
- **Description:** The proportion of farms operating under form of a natural person (e.g., individual or family-owned farms) relative to the total number of farms within the NUTS3 region.
- **Units:** Ratio (0-1)
- **Notes:** Derived from Eurostat's Farm Structure Survey (FSS) and aggregated to the NUTS3 level.

The variables Farms\_Predominant\_Size, Farms\_Predominant\_Economic\_Size, Farms\_Predominant\_Legal\_Form, and Natural\_Person\_Legal\_Form\_to\_Total are derived from Eurostat's Farm Structure Survey (FSS). These data provide critical insights into the structural characteristics of farms across Europe.


For more information, refer to Eurostat's Farm Structure Survey data: <https://ec.europa.eu/eurostat/databrowser/view/ef_m_farmang/default/table?lang=en>.

18) **column\_name: Rural\_Fixed\_Broadband\_Coverage**
- **Data Type:** Integer
- **Description:** The percentage of rural households within the NUTS3 region covered by fixed broadband infrastructure.
- **Units:** Percentage (%)
- **Notes:** Derived from Eurostat's broadband coverage statistics and aggregated to NUTS3 regions

19) **column\_name: Rural\_5G\_Cellular\_Network\_Coverage**
- **Data Type:** Integer
- **Description:** The percentage of rural households within the NUTS3 region covered by 5G cellular network infrastructure.
- **Units:** Percentage (%)
- **Notes:** Derived from Eurostat's broadband and cellular network statistics and aggregated to NUTS3 regions

The variables Rural\_Fixed\_Broadband\_Coverage and Rural\_5G\_Cellular\_Network\_Coverage are derived from Eurostat's broadband and cellular network coverage statistics. These datasets provide detailed insights into the level of digital infrastructure available in rural areas across Europe.

For more information, refer to Eurostat's broadband coverage statistics: <https://ec.europa.eu/eurostat/databrowser/view/isoc_cbt/default/table?lang=en>.

20) **column\_name: Population**
- **Data Type:** Integer
- **Description:** Total population within the NUTS3 region, representing the number of residents.
- **Units:** Count (number of people)
- **Notes:** Calculated from the JRC database and aggregated to the NUTS3 level through geospatial analysis.

References:

Schiavina, M., Freire, S., Carioli, A., & MacManus, K. (2023). GHS-POP R2023A–GHS Population Grid Multitemporal (1975-2030). In European Commission. Joint Research Centre (JRC).

21) **column\_name: NUTS3\_Area**
- **Data Type:** demical (double)
- **Description:** Total land area of the NUTS3 region, calculated in square kilometers (km²).
- **Units:** Square kilometers (km²)
- **Notes:** Derived from geospatial analysis of the NUTS3 polygons. 

22) **column\_name: Population\_Density**
- **Data Type:** demical (double)
- **Description:** Population density within the NUTS3 region, calculated as the total population divided by the total land area.
- **Units:** Population per square kilometer (population/km²)
- **Notes:** This variable is derived by dividing the Population column by the NUTS3\_Area column, both of which were aggregated or calculated through geospatial analysis within the NUTS3 boundaries.

23) **column\_name: Median\_Elevation**
- **Data Type:** demical (double)
- **Description:** Median elevation of the NUTS3 region, representing the middle value of elevation when all elevation measurements within the region are sorted.
- **Units:** Meters (m)
- **Notes:** Copernicus Digital Elevation Model (COP-DEM), accessed via [Copernicus Data Space Ecosystem](https://dataspace.copernicus.eu/explore-data/data-collections/copernicus-contributing-missions/collections-description/COP-DEM). Geospatial analysis was performed to aggregate the elevation data within the NUTS3 boundaries. Elevation values were calculated and aggregated for each NUTS3 polygon to provide a representative measure of terrain characteristics.

24) **column\_name: Natural\_Characteristics\_Index**
- **Data Type:** Integer
- **Description:** Cluster classification representing groups of NUTS3 regions with similar natural characteristics, such as soil properties, elevation, precipitation, and soil moisture.
- **Units:** Cluster ID (categorical, integer values)

25) **column\_name: Socio-economic\_Similarity\_Index**
- **Data Type:** Integer
- **Description:** Cluster classification representing groups of NUTS3 regions with similar socio-economic characteristics, such as farms predominant size, economic size and legal status
- **Units:** Cluster ID (categorical, integer values)

26) **column\_name: Fertilization\_Need\_Index**
- **Data Type:** demical (double)
- **Description:** Performance index ranging from 0 to 1 representing the need (low need for low values, high need for high values) for fertilization ADSs  on NUTS3 regions. 
- **Units:** 0 to 1 (performance values)

27) **column\_name: Irrigation\_Need\_Index**
- **Data Type:** demical (double)
- **Description:** Performance index ranging from 0 to 1 representing the need (low need for low values, high need for high values) for irrigation ADSs on NUTS3 regions.** 
- **Units:** 0 to 1 (performance values)

28) **column\_name: Pest\_Management\_Need\_Index**
- **Data Type:** demical (double)
- **Description:** Performance index ranging from 0 to 1 representing the need (low need for low values, high need for high values) for pest management ADSs on NUTS3 regions. 
- **Units:** 0 to 1 (performance values)

29) **column\_name: Rural\_Connectivity\_Performance\_Index**
- **Data Type**: demical (double)
- **Description:** Performance index ranging from 0 to 1 representing the Rural Cloud connectivity capabilities (low for low values, high for high values) on NUTS3 regions.** 
- **Units:** 0 to 1 (performance values)
