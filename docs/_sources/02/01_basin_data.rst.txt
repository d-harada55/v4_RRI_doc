1. Preparation for the Basin Terrain Dataset
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
First, we need to prepare the following Basin Terrain Datasets. All data must be prepared using the same grid structure:

- Elevation data (DEM): Elevation of each cell [Required]
- Flow accumulation (ACC): Number of upstream flow accumulation pixels for each cell [Required]
- Flow direction (DIR): Flow direction of each cell (1, 2, 4, 8, 16, 32, 64, 128) [Required]
- Land use type: Land use for each cell [Optional]

For instructions on preparing these datasets, please refer to Chapter 3 of the `RRI_Manual <https://www.pwri.go.jp/icharm/research/rri/index.html>`_ for the method using GIS software, and Chapter 9 for the method using the RRI-GUI.

Members of iRIC-UC can obtain the data using `UC tools <https://tools.i-ric.info/login/>`_, which currently provides Japanese domestic data only.

.. note::
   By using UC tools, you can extract and download watershed terrain datasets across Japan.
   The downloadable data is in 1-second mesh size.

   The original data was created by Associate Professor Yamazaki Dai of the Institute of Industrial Science, the University of Tokyo, and is available on Associate Professor Yamazaki's webpage as of September 2020 under the name "Japan Surface Flow Direction Map" data.
   The "Watershed Data Extraction" site adds a function to extract necessary watershed data from the original data, making the data available for use.
   Therefore, the data itself complies with the licenses listed on Associate Professor Yamazaki's webpage, so please review the licenses before using the data.

   `For more details, click here <http://hydro.iis.u-tokyo.ac.jp/~yamadai/JapanDir/>`_

Below are the steps to obtain the data using UC tools:

- [1] Access the `“Watershed Data Extraction” <https://tools.i-ric.info/login/>`_ 
- [2] STEP1: Click on the downstream end of the target watershed river channel. (The image below shows the downstream endpoint of the Toyohira River. A pin mark will appear at the clicked location.)
   .. image:: img/extract_basin_1_click.jpg

- [3] STEP2: Click the "Search" button. After a while, the watershed with the downstream end specified in [2] will be displayed.
   .. image:: img/extract_basin_2_extracted.jpg

- [4] STEP3: Click the "Obtain" button. You can download the watershed terrain dataset extracted in [2]. After unzipping the downloaded file, you can confirm that the following data is included:
   - dir_export.asc: Surface flow direction data (*)
   - elv_export.asc: Hydrologically corrected elevation (*)
   - hnd_export.asc: Relative height from the nearest river channel (*)
   - upa_export.asc: Upstream drainage area (*)
   - upg_export.asc: Number of upstream drainage grids (*)
   - wth_export.asc: River channel width (*)
   - ldu_export.asc: Land use data (**)

(*) For details of each data, please refer to the `“Japan Surface Flow Direction Map” <http://hydro.iis.u-tokyo.ac.jp/~yamadai/JapanDir/>`_ 

(**) The land use data is maintained primarily by Associate Professor Takahiro Sayama (Disaster Prevention Research Institute, Kyoto University), who is also the developer of RRI, and covers all of Japan. The data is lent and distributed as a reference for executing RRI, but its accuracy is not guaranteed. Please use it at your own risk.

- [5] The data downloaded in [4] can be opened and reviewed using GIS software. The following data are used for RRI calculations:

.. figure:: img/elv_img.png
   :scale: 50%
   :alt:

   Visualizing hydrologically corrected elevation

.. figure:: img/dir_img.png
   :scale: 50%
   :alt:

   Visualizing surface flow direction data. Values represent the 8 directions (1, 2, 4, 8, 16, 32, 64, 128).
   

.. figure:: img/acc_img.png
   :scale: 50%
   :alt:

   Visualizing the number of upstream drainage grids


.. figure:: img/ldu_img.png
   :scale: 50%
   :alt:

   Visualizing land use data. Land use is classified into five categories. The original data is "National Land Numerical Information Land Use Detailed Mesh Data."
