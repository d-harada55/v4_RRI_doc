Introduction
==================================================

This document is a user manual for RRI on iRIC. (This is a test page v16.3 edited by Harada.)

About RRI:   
The RRI model is to simulate a Rainfall-Runoff-Inundataion processes  [1]_ ,  [2]_ ,  [3]_ .   
The RRI model is available for free on the `ICHARM website <https://www.pwri.go.jp/icharm/research/rri/index.html>`_
  
For details, including the governing equations of the RRI model, please refer to the RRI manual included with the RRI model download.   
This document focuses on explaining how to use this program, RRI on iRIC, within the iRIC interface. 
  
.. [1] `Sayama, T., Ozawa, G., Kawakami, T., Nabesaka, S., Fukami, K. (2012) Rainfall-Runoff-Inundation analysis of the 2010 Pakistan flood in the Kabul River basin, Hydrological Science Journal, 57(2), 298-312. <https://www.tandfonline.com/doi/full/10.1080/02626667.2011.644245>`_
.. [2] `Sayama, T., Tatebe, Y., Tanaka, S. (2015a) An emergency response-type rainfall-runoff- inundation simulation for 2011 Thailand floods, Journal of Flood Risk Management, 1-8 doi:10.1111/jfr3.12147 (in print). <https://onlinelibrary.wiley.com/doi/full/10.1111/jfr3.12147>`_ 
.. [3] `Sayama, T., Tatebe, Y., Iwami, Y., Tanaka, S. (2015b) Hydrologic sensitivity of flood runoff and inundation: 2011 Thailand floods in the Chao Phraya River basin, Nat. Hazards Earth Syst. Sci., 15, pp. 1617-1630, doi:10.5194/nhess-15-1617-2015. <https://www.researchgate.net/publication/282201567_Hydrologic_sensitivity_of_flood_runoff_and_inundation_2011_Thailand_floods_in_the_Chao_Phraya_River_basin>`_ 

-----

About RRI on iRIC
------------------------------
RRI on iRIC is modified and released based on items ii and iii of Chapter 1 of the `Rainfall-Runoff-Inundation (RRI) Model Program Terms of Use <https://www.pwri.go.jp/icharm/research/rri/rri_contract_j.html>`_
Therefore, when publishing or distributing the calculation results using RRI on iRIC (hereafter referred to as "this program"), please clearly state the following:

---

- The copyright of the original work of this program (hereafter referred to as "RRI") belongs to the Public Works Research Institute (ICHARM).
- This program is a derivative work of RRI.
- The calculation results are derived from the modified program (this program) based on RRI.

---


-----

Preparing to Use RRI on iRIC
------------------------------

- 1. Download RRI on iRIC  (the url must be modified later)

    - `rri_v1 <https://uc.i-ric.org/uc_products/rri_on_iric/v4_rri_240521.zip>`_


- 2. Extract the downloaded data and copy & paste it into the solver folder of iRIC. By default, this folder is located at "C:/Users/username/iRIC_v4/private/solvers"

- 3. When you launch the iRIC software, RRI will be available for selection.

    .. image:: img/RRI_v4_en3.jpg
