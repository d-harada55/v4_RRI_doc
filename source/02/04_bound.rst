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


5.1 ダム
------------------------------
ダムは河道セル上に設定する必要があります。
河道セルは、上流集水ピクセル数が「河道セル判定閾値」以上セルで、セル属性WidthやDepthなどから確認することできます。
河道セルのうちダム堤体に近いセルをダムセルとして選択します。

    .. image:: img/river_cell.jpg
        :width: 480px
        :align: center

各ダムに設定できるパラメータは以下のとおりです。

    .. image:: img/dam_cond.jpg
        :width: 320px
        :align: center

境界条件も格子属性としてマッピングする必要があります。
条件を設定したら、「格子＞属性マッピング＞実行」をクリックしてください。
「境界条件設定＞New Dam」にチェックを入れ、「OK」ボタンをクリックしてください。

    .. image:: img/map_bound_dam.jpg
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