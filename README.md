## The Climate Cost of Urban Sprawl

**Data Download Instructions**

Due to file size limits, the high-resolution geospatial datasets required for this project are hosted externally. 

Please [download the raw datasets (Exeter_Cranbrook_DSM_1m.tif and Exeter_Cranbrook_DTM_1m.tif) here](https://1drv.ms/f/c/e3728fa2676589e0/IgBrFByM0gMrQJ1YtDG72NKJAbRauchZOFmX3Y6dPIc24yo?e=qSYJRS).

---

### Setup Instructions
Depending on your environment, please follow the specific setup instructions below before running the scripts.


#### Option A: Local Jupyter Notebook
If you are running this project locally on your own machine:

**1. Install Dependencies**
Ensure you have the required packages installed in your Conda environment. It is also recommended to install these using Conda to prevent conflicts with other packages:
```bash
conda install -c conda-forge rasterio geemap earthengine-api numpy matplotlib seaborn
```
**2. Data Placement**
Please ensure the following files are placed directly into the same working directory as the scripts:

- Study_Area_Boundary.geojson
- Exeter_Cranbrook_DSM_1m.tif
- Exeter_Cranbrook_DTM_1m.tif


#### Option B: Google Colab
If you are using Google Colab, create two new cells immediately after each script's header.

**1. Install Dependencies**

*For Script 1:*
Cell 1:  Install these extra packages (Others are pre-installed):
```bash
%pip install rasterio geemap
```
*For Script 2:*
Cell 1:  Install rasterio (Others are pre-installed):
```bash
%pip install rasterio
```

**2. Mount Google Drive**
Upload the three files to a folder in your Google Drive. Preferably, name the folder the same name you will define when exporting the Geotiff files from Google Earth Engine's task bar.

Cell 2 (in both scripts): Run
```bash
from google.colab import drive
drive.mount('/content/drive')
```

**3. Update the file path in the scripts to point to the Drive folder** - 
```bash
BASE_DIR = "/content/drive/MyDrive/Folder_Name/"
```
**Remember to change the "Folder_Name" to the exact Google Drive folder name**.

## Run Order: ##
Regardless of your environment, execute the notebook in this exact order: 
1. Run **`Exeter_Cranbrook_Project_Script1.ipynb`** first. This will process the raw datasets and generate the intermediate files required for the next phase.
2. Then, run **`Exeter_Cranbrook_Project_Script2.ipynb`**.

### PLEASE NOTE ###
### Local Jupyter Notebook Option
After running Script 1, you will need to download the exported `Validated_Sprawl_Mask_10m.tif` file from the Google Drive folder into your local working directory before running Script 2.

### Google Colab Option
If you set the folder as described above, all the results, including the Geotiffs and images generated will be automatically saved to the same Google Drive folder. This means you can run Script 2 without moving files around.
