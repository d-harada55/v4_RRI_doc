4. Boundary condition settings
==============================

Right-clicking on "Object Browser > Boundary Condition Setting" displays the following options.

    .. image:: img/bound_select_en.jpg
        :width: 480px
        :align: center



===================================  ==============================
Boundary Condition                   RRI manual related section
===================================  ==============================
Dam                                  8.11 Dam option
Time series for river discharge      8.8 On Boundary Condition
Time series for river depth          8.8 On Boundary Condition
Time series for slope discharge      8.8 On Boundary Condition
Time series for slope depth          8.8 On Boundary Condition
Flow diversion setting               8.10 Diversion option
===================================  ==============================


5.1 Dam
------------------------------
Dams must be set on river channel cells. 
River channel cells are those with an upstream contributing area (number of pixels) equal to or greater than the "River Channel Determination Threshold." You can identify them by checking cell attributes such as Width and Depth.  
Among the river channel cells, select the cell(s) closest to the dam embankment as the dam cell(s).

    .. image:: img/river_cell_en.jpg
        :width: 480px
        :align: center

The following parameters can be configured for each dam:

    .. image:: img/dam_cond_en.jpg
        :width: 320px
        :align: center

Boundary conditions also need to be mapped as grid attributes. 
After setting the conditions, click "Grid" > "Attribute Mapping" > "Execute". Check the box next to "Boundary Condition Setting > New Dam" and click the "OK" button.

    .. image:: img/map_bound_dam_en.jpg
        :width: 320px
        :align: center


----

5.2 河道セル流量
------------------------------
河道流量が観測されている場合、その観測結果を時系列に与えることができます。
詳しくはRRIのマニュアル、8.8 On Boundary Conditionをご確認ください。


5.3 河道セル水深
------------------------------
河道水深が観測されている場合、その観測結果を時系列に与えることができます。
詳しくはRRIのマニュアル、8.8 On Boundary Conditionをご確認ください。

5.4 斜面セル流量
------------------------------
斜面セルで流量が観測されている場合、その観測結果を時系列に与えることができます。
詳しくはRRIのマニュアル、8.8 On Boundary Conditionをご確認ください。

5.5 斜面セル水深
------------------------------
斜面セルで水深が観測されている場合、その観測結果を時系列に与えることができます。
詳しくはRRIのマニュアル、8.8 On Boundary Conditionをご確認ください。

5.6 流量配分
------------------------------
本境界条件により、強制的に流量をを分配させることができます。

地形データでは表現が困難なトンネル水路などが設置されていることで、流量が河道とは異なる経路で流れる起点となるセルを選択します。
セルは河道セルである必要があります。
設定値には、分派先の出口セルのi,jと分派流量比を指定することができます。

    .. image:: img/bound_div.jpg
        :width: 480px
        :align: center

詳しくはRRIのマニュアル、8.10 Diversion optionをご確認ください。