2. Preparation for a rainfall dataset
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A rainfall dataset for the target basin during a specific period is required for the calculation.
The dataset should include rainfall data that covers the target watershed, for the specified period (e.g., from July 2, 2020, 20:00 to July 4, 2020, 10:00), at regular time intervals (e.g., hourly intervals).

Rainfall intensity data, including both observed and forecasted data, is created and distributed by the Japan Meteorological Agency. Additionally, researchers may generate their own rainfall data using mesoscale models or other methods.

For instructions on preparing the rainfall dataset, please refer to Chapter 4 or Chapter 9 of the RRI_Manual.
The iRIC-UC tool also provides a tool for extracting rainfall data within Japan.

You can use any type of data, but the rainfall data for RRI calculations must be in the following format:


.. figure:: img/rain_dat_fmt.jpg
   :scale: 50%
   :alt:

   Rainfall data format:  
   The header row repeats for each time step with `time (sec)`, `ncols`, and `nrows`.
   The mesh size must be consistent.

