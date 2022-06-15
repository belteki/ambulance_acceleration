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

The Notebook also depends on the supplied helper files which should be in the
same directory as the .ipynb notebook files.

gb_loader.py

gb_stats.py

gb_transform.py

gb_visualizer.py
