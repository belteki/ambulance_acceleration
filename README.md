# ambulance_acceleration

This repository contains the Python code used for data processing, statistical
analysis and visualization described in the following paper:

Belteki G, Morley CJ. **Acceleration during neonatal transport and its impact on mechanical ventilation** _Arch Dis Child Fetal Neonatal Ed._
2022 June 15

Link to the paper: [https://fn.bmj.com/content/early/2022/06/14/archdischild-2021-323498](https://fn.bmj.com/content/early/2022/06/14/archdischild-2021-323498)

Contact: gusztav.belteki@addenbrookes.nhs.uk; gbelteki@aol.com

____


The outputs (numbers, tables, graphs) of the cells of the Jupyter Notebooks
(.ipynb files) have been suppressed in order to comply with copyrights.
Some of the corresponding data and graphs can be found in the paper and its
only supplementary material.

This code can be viewed in any web browser. If the code is displayed (rendered)
in Github, copy and paste the URL (web adress) of the Notebook into **nbviewer**
(https://nbviewer.jupyter.org) for a read-only display.

To run the code, you need to use Jupyter.
The raw ventilator data are not shared but the user can run this code on his or
her own data obtained in the same format.

____

Packages required to run this Notebook:

Python version: 3.7.4

IPython version: 7.10.2

pandas version: 0.25.3

matplotlib version: 3.1.1

Seaborn version: 0.9.0

NumPy version: 1.17.4

SciPy version: 1.3.1


I recommend downloading these packages using the freely availably Anaconda
built: https://www.continuum.io/downloads

____

# Jupyter Notebooks

### 1. Initial processing of raw ventilator slow (0.5 Hz) data

[ventilator_data_1_150](ventilator_data_1_150.ipynb): This notebook imports all ventilator data of these recordings (including ventilator parameters, settings, alarms (0.5Hz sampling rate) and waveform data (150Hz sampling rate).

- Total: **150 cases**
- 21 cases were removed as they were less than 15 minutes long (empty or partial recordings) 
- **129 cases** remaining

Dictionary containing the processed ventilation data exported as pickle archive: **data_pars_1_150.pickle** 


[ventilator_data_151_300](ventilator_data_151_300.ipynb): This notebook imports all ventilator data of these recordings (including ventilator parameters, settings, alarms (0.5Hz sampling rate) and waveform data (150Hz sampling rate).

- Total: **150 cases**
- 1 case (AL000257) was removed it was fragmented with multiple in data
- 32 cases were removed as they were less than 15 minutes long (empty or partial recordings) 
- **117 cases** remaining

Dictionary containing the processed ventilation data exported as pickle archive: **data_pars_151_300.pickle** 


[ventilator_data_301_450](ventilator_data_301_450.ipynb): This notebook imports all ventilator data of these recordings (including ventilator parameters, settings, alarms (0.5Hz sampling rate) and waveform data (150Hz sampling rate).

- Total: **150 cases**
-  19 cases were removed as they were less than 15 minutes long (empty or partial recordings) 
- **131 cases** remaining

Dictionary containing the processed ventilation data exported as pickle archive: **data_pars_300_450.pickle**


[ventilator_data_451_600](ventilator_data_451_600.ipynb): This notebook imports all ventilator data of these recordings (including ventilator parameters, settings, alarms (0.5Hz sampling rate) and waveform data (150Hz sampling rate).

- Total: **150 cases**
-  26 cases were removed as they were less than 15 minutes long (empty or partial recordings) 
- **124 cases** remaining

Dictionary containing the processed ventilation data exported as pickle archive: **data_pars_451_600.pickle**


[ventilator_data_601_674](ventilator_data_601_674.ipynb): This notebook imports all ventilator data of these recordings (including ventilator parameters, settings, alarms (0.5Hz sampling rate) and waveform data (150Hz sampling rate).

- Total: **74 cases**
-  7 cases were removed as they were less than 15 minutes long (empty or partial recordings) 
- **67 cases** remaining

Dictionary containing the processed ventilation data exported as pickle archive: **data_pars_601_674.pickle**


##### From AL000001-AL000674: Appropriate ventilator data are available for a total of: **129 + 117 + 131 + 124 + 67 = 568 cases**

____

### 2. Initial processing of fast (125 Hz) ventilator data

1. [fabian_fast_data_conversion](fabian_fast_data_conversion.ipynb): This file extracts fast (125 Hz) pressure, flow and volume data from the raw hexdecimal data and converts them into pandas DataFrames. Data are exported as `csv` files. Currently it does not work with every ventilator data file. List of files with errors is written in a log file.

____

### 3. Processing of clinical data

[clinical_data_1_665](clinical_data_1_665.ipynb)

- Total: **665 cases**
- Clinical data available in **539 cases**
- Only keep clinical data for cases where ventilation recordings (>15 minutes) are also available: **511 cases**

DataFrame containing the processed clinical data exported as **clin_df_1_665.pickle** 

This Notebook also generates and exports disease-specific Excel sheets: **clinical_data_diseases_1_665.xlsx**
It also exports pickle archives:
**clin_df_RDS, clin_df_MAS, clin_df_PPHN**,
**clin_df_cardiac** (except PFO and PDA), 
**clin_df_HIE**,
**clin_df_CDH, clin_df_NEC, clin_df_surgical** (except NEC and CDH)

____

### 4. Further processing of slow (0.5Hz) ventilator data

[ventilator_data_processing_1_300](ventilator_data_processing_1_300.ipynb)

Imported: **data_pars_1_150.pickle**, **data_pars_151_300.pickle**, **clin_df_1_300.pickle**

- Total: **246 cases** with ventilator data available (with >15 minutes recording time)
- Clinical data were not available for **4 cases** 
- Appropriate ventilator and clinical data are available for **242 cases**

Exported: dictionaries containing ventilation data as **data_pars_measurements_1_300.pickle,  data_pars_settings_1_300.pickle, data_pars_alarms_1_300.pickle**


[ventilator_data_processing_301_600](ventilator_data_processing_301_600.ipynb)

Imported: **data_pars_301_450.pickle**, **data_pars_451_600.pickle**, **clin_df_301_600.pickle**

- Total: **255 cases** with ventilator data available (with >15 minutes recording time)
- Clinical data were not available for **38 cases** 
- Appropriate ventilator and clinical data are available for **217 cases**

Exported: dictionaries containing ventilation data as **data_pars_measurements_301_600.pickle,  data_pars_settings_301_600.pickle, data_pars_alarms_301_600.pickle**


[ventilator_data_processing_601_665](ventilator_data_processing_601_665.ipynb)

Imported: **data_pars_601_674.pickle**, **clin_df_1_665.pickle**

- Total: **67 cases** with ventilator data available (with >15 minutes recording time)
- Clinical data were not available for **15 cases** 
- Appropriate ventilator and clinical data are available for **52 cases**

Exported: dictionaries containing ventilation data as **data_pars_measurements_601_665.pickle,  data_pars_settings_601_665.pickle, data_pars_alarms_601_665.pickle**

____

### 5. Further processing of recordings with mechanical ventilation

[ventilator_data_processing_1_300_ventilated](ventilator_data_processing_1_300_ventilated.ipynb)

This notebook ventilator data to keep only periods of mechanical ventilation. Recordings have also been inspected and trimmed _manually_ to remove periods when the ventilator was working but the patient was not connected.

Imported: **data_pars_measurements_1_300.pickle,  data_pars_settings_1_300.pickle, data_pars_alarms_1_300.pickle**, **clin_df_1_300.pickle**

- Total: **242 cases**
- Containing >15 minutes of mechanical ventilation: **146 cases remaining**
- After removing periods when the patient was not connected, containing >15 minutes of mechanical ventilation: **145 cases**

Exported: 
**data_pars_measurements_ventilated_1_300.pickle,  data_pars_settings_ventilated_1_300.pickle, data_pars_alarms_ventilated_1_300.pickle, 
vent_modes_1_300.pickle, vent_modes_ventilated_1_300.pickle, 
ventilation_modes_1_300.xlxs, ventilation_modes_ventilated_1_300.xlsx**


[ventilator_data_processing_301_600_ventilated](ventilator_data_processing_301_600_ventilated.ipynb)

This notebook ventilator data to keep only periods of mechanical ventilation. Recordings have also been inspected and trimmed _manually_ to remove periods when the ventilator was working but the patient was not connected.

Imported: **data_pars_measurements_301_600.pickle,  data_pars_settings_301_600.pickle, data_pars_alarms_301_600.pickle**, **clin_df_301_600_pickle**

- Total: **217 cases**
- Containing >15 minutes of mechanical ventilation: **114 cases**
- **8 cases** removed as there was no flow sensor used (and hence no tidal volume measurement), **106 cases remaining**
- After removing periods when the patient was not connected, containing >15 minutes of mechanical ventilation: **106 cases**

Exported: **data_pars_measurements_ventilated_301_600.pickle,  data_pars_settings_ventilated_301_600.pickle, data_pars_alarms_ventilated_301_600.pickle, vent_modes_301_600.pickle, vent_modes_ventilated_301_600.pickle, 
ventilation_modes_301_600.xlxs, ventilation_modes_ventilated_301_600.xlsx**


[ventilator_data_processing_601_665_ventilated](ventilator_data_processing_601_665_ventilated.ipynb)

This notebook ventilator data to keep only periods of mechanical ventilation. Recordings have also been inspected and trimmed _manually_ to remove periods when the ventilator was working but the patient was not connected.

Imported: **data_pars_measurements_601_665.pickle,  data_pars_settings_601_665.pickle, data_pars_alarms_601_665.pickle**, **clin_df_1_665_pickle**

- Total: **52 cases**
- Containing >15 minutes of mechanical ventilation: **22 cases**
- **1 case** removed as there was no flow sensor used (and hence no tidal volume measurement), **21 cases remaining**
- After removing periods when the patient was not connected, containing >15 minutes of mechanical ventilation: **21 cases**

Exported: **data_pars_measurements_ventilated_601_665.pickle,  data_pars_settings_ventilated_601_665.pickle, data_pars_alarms_ventilated_601_665.pickle, vent_modes_601_665.pickle, vent_modes_ventilated_601_665.pickle, 
ventilation_modes_601_665.xlxs, ventilation_modes_ventilated_601_665.xlsx**

______


### 6. Analysis of accelerometer data and associated ventilator data during invasive mechanical ventilation


[accelerometer_ventilated_processing_1](accelerometer_ventilated_processing_1.ipynb) 

Identification and processing of ventilated cases with matched accelerometer recordings.

- This notebook first reads the start time of all accelerometer recordings and calculates the stop time of accelerometer data. It corrects the timestamps of the recordings if the correct timestamps can be found out, otherwise it removes the recordings 

- It imports ventilator data of ventilated recordings from pickles archives:

**data_pars_measurements_ventilated_1_300.pickle,  data_pars_settings_ventilated_1_300.pickle, data_pars_alarms_ventilated_1_300.pickle, 
data_pars_measurements_ventilated_301_600.pickle,  data_pars_settings_ventilated_301_600.pickle, data_pars_alarms_ventilated_301_600.pickle,
data_pars_measurements_ventilated_601_665.pickle,  data_pars_settings_ventilated_601_665.pickle, data_pars_alarms_ventilated_601_665.pickle** 

- It identifies the start and stop times of ventilator recoridings
- It identifies overlapping accelerometers and ventilator recordings
- It imports relevant accelerometer recordings from the original files
- It trims ventilator and accelerometer data to contain only the overlapping regions: **153 recordings**
- It exports trimmed accelerometer data as **accelero_ventilated_1.pickle** 
- It exports trimmed ventilator data for ventilated_ recordings: **data_pars_measurements_ventilated_accelero.pickle, data_pars_settings_ventilated_accelero.pickle, data_pars_settings_ventilated_accelero.pickle**


[accelerometer_ventilated_processing_2](accelerometer_ventilated_processing_2.ipynb)

Further processing of the matched ventilated and accelerometer recordings.

- It imports the following pickle archives **data_pars_measurements_ventilated_accelero, data_pars_settings_ventilated_accelero, data_pars_alarms_ventilated_accelero, accelero_ventilated_1**

- It starts from **153 recordings** when both ventilator and accelerometer data were available
- Removed recordings when the net ambulance movement time was <10 minutes  - **113 remaining**
- The gravity (9.81 m/sec2) is subtracted from the vertical (Z) acceleration
- Absolute values of X (front-back), Y (side-to-side) and Z (up-down) accelerations are calculated
- The length (Euclidean (L2) norm) of the acceleration vector is calculated
- Accelerometer data are resampled with 0.5 Hz sampling rate using median and interquartile range (IQR) as aggregating function
- Ventilator data (0.5 Hz) are combined with accelerometer data (0.5 Hz, aggregating function: median and IQR)
- Ventilator data are aggregated over 1-minute periods using mean and standard deviation (SD)
- Ventilator data (1/min, aggregating function: mean and SD) are combined with accelerometer data (1/min, aggregating function: median and IQR)

Exported: **combined_ventilated_2sec.pickle** (0.5 Hz aggregated accelerometer and unaggregated ventilator data), **combined_ventilated_1min.pickle** (1/min aggregated accelerometer and ventilator data)
**accelero_ventilated_2.pickle** (unaggregated accelerometer data with absolute values and total vector length)
**ventilator_mode.pickle** (ventilator modes used)


[accelerometer_ventilated_analysis_1](accelerometer_ventilated_analysis_1.ipynb)

Generating time series graphs for acceleration and selected ventilator data

- It imports the following pickle archives: **accelero_ventilated_2.pickle**,**combined_ventilated_2sec.pickle**, **combined_ventilated_1min.pickle**, **ventilator_mode.pickle**
- It generates and exports time series plots for the **113 matched recordings**:  
  1. 3-dimensional accelerations
  2. Length (Euclidean norm) of the acceleration vector)
  3. Unaggregated acceleration data and unaggregated ventilator data (VTemand, (RR), MV, PIP FiO2)
     (Graphs with RR can only be exported for some recording as during SIMV RR is not recorded by AcuLinkLog)
  4. Aggregated (2-sec median and IQR) acceleration data and unaggregated (0.5 Hz) ventilator data (VTemand, MV, PIP FiO2)
  5. Aggregated (1-min median and IQR) acceleration data and aggregated (1-min mean) ventilator data (VTemand, MV, PIP FiO2)
  5. Generic function to visualize the Euclidean norm of acceleration together with a chosen ventilator parameter


[accelerometer_ventilated_analysis_2](accelerometer_ventilated_analysis_2.ipynb)

Analysis of ventilator parameter data together with accelerometer data in ventilated cases with matched accelerometer recordings.

Imported: **accelero_ventilated_2.pickle**, **combined_ventilated_2sec.pickle**, **combined_ventilated_1min.pickle**, **ventilator_mode.pickle**, **clin_df_1_665**

- It starts with **113 recordings**
- Removes cases that were > 46 weeks (term plus 6 weeks) of corrected gestations at the time of the transfer (**4 recordings removed**)
- **109 recordings remaining** final dataset for analysis
- Calculates and exports descriptive statistics and plots on clinical data
- Calculates and exports duration of the final dataset
- Analyses ventilator modes in the final dataset

- Generates and exports histograms of accelerations using the original accelerometer data (~100 Hz sampling)
   1. `X` (front-back), `Y` (left-right) and `Z` (up-down) acceleration vectors individually or together (with linear or logarithmic Y-scale)
   2. Absolute values of `X` (front-back), `Y` (left-right) and `Z` (up-down) acceleration vectors individually or together (linear or logarithmic Y-scale)
   3. Length (Euclidean (L2) norm) of the 3-dimensional acceleration vectors (linear or logarithmic Y-scale)
        
- Calculates the median absolute values of X, Y, Z acceleration in each recording and studies the distribution of the medians and compares them.
- Analyse and visualise the correlation between 1-minute IQRs of acceleration in X (front-back) or Y (side-to-side) direction with IQR in Z (vertical) direction
- Analyse and visualise the correlation between the 1-minute  median and IQR of the various components (X, Y, Z) of the acceleration vector
- Identify periods of vibration and sustained acceleration
- Compare periods of vibration with periods of no acceleration
- Compare periods of low and high sustained acceleration

Exported as pickle archives: **combined_ventilated_1min, combined_ventilated_1min_all, low_1_vibr_frame,
high_1_vibr_frame, low_1_accel_frame, high_1_accel_frame**


[accelerometer_ventilated_fast_data_analysis](accelerometer_ventilated_fast_data_analysis.ipynb)

Analysis of ventilator waveform data and loops during periods of high and low vibration

Imported from pickle archives: **combined_ventilated_1min, combined_ventilated_1min_all, low_1_vibr_frame,
high_1_vibr_frame, low_1_accel_frame, high_1_accel_frame**

Also imported all ventilator fasta (waveform) data for the relevant recordings

- Generate composite P-V curves for the minute with the lowest and the highest vibration for each recording and export them as images
- Study the disorder of loops (expressed as the number of P-V data pairs during the given minute)
