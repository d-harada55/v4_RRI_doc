Example 1: Sorachi River, August 2016
==================================================
From August 29th to 31st, 2016, heavy rainfall caused a levee breach and river flooding in the Sorachi River. Details on the heavy rainfall and flooding conditions are described in the investigation report [1]_, and the paper [2]_ (we apologize, but those references are in Japanese.).

This section demonstrates the procedure for simulating the flooding in the Sorachi River basin during that event using RRI on iRIC.

.. [1] `2016 年 8 月北海道豪雨災害 調査団報告書, 土木学会災害調査団 <http://committees.jsce.or.jp/report/system/files/2016%E5%B9%B48%E6%9C%88%E5%8C%97%E6%B5%B7%E9%81%93%E8%B1%AA%E9%9B%A8%E5%9C%9F%E6%9C%A8%E5%AD%A6%E4%BC%9A%E8%AA%BF%E6%9F%BB%E5%9B%A3%E5%A0%B1%E5%91%8A%E6%9B%B8_20170501.pdf>`_ 
.. [2] `2016年8月北海道豪雨における空知川幾寅地区の氾濫被害に関する調査および要因検証, 土木学会論文集B1（水工学）Vol.73, No.4, I_1429-I_1434, 2017. <https://www.jstage.jst.go.jp/article/jscejhe/73/4/73_I_1429/_pdf>`_ 

-----

1. Sample data
--------------------------------------------------
The sample data used in this example can be downloaded from the following links:

- Terrain and rainfall dataset  → `data_1 <https://uc.i-ric.org/uc_products/rri_examples/data_1.7z>`_ 
- iRIC software project file 　→ `data_1_iRIC <https://uc.i-ric.org/uc_products/rri_examples/2016_minami-furano.ipro>`_  



１．Preparation for the Basin Topographic Dataset
--------------------------------------------------
The basin topographic dataset is included in the data downloadable from "0. Sample Data".
(Please also refer to the section 'Overview 1.')
Members of iRIC-UC can obtain those using the following method:

- [1] Access the tool `'Basin Data Extraction'  <https://tools.i-ric.info/login/>`_ 
- [2] Download the 3-second mesh MERIT Hydro data.
- [3] STEP 1: Zoom in on the Ikutora area of the Sorachi River and click on the downstream end of the target watershed.

   .. image:: img_1/step1_click2.jpg
        :width: 640px

- [4] STEP 2: Click the "Search" button, and the target watershed will be extracted.

    .. image:: img_1/step2_extract2.jpg
        :width: 640px

- [5] STEP 3: Click the "Download" button and download the extracted data to a suitable location.


-----

２．Preparation of Rainfall dataset
--------------------------------------------------
The rainfall dataset is included in the "data_1/02_rain" folder of the data downloadable from "0. Sample Data". 
This folder contains processed rainfall data for the target area and period, extracted from analyzed rainfall data. 
For details on analyzed rainfall data, please refer to the `Japan Meteorological Agency website <https://www.jma.go.jp/jma/kishou/know/kurashi/kaiseki.html#:~:text=%E8%A7%A3%E6%9E%90%E9%9B%A8%E9%87%8F%E3%81%A8%E9%80%9F%E5%A0%B1%E7%89%88,%E3%81%94%E3%81%A8%E3%81%AB%E4%BD%9C%E6%88%90%E3%81%95%E3%82%8C%E3%81%BE%E3%81%99%E3%80%82>`_ をご確認ください。

The rainfall data for each time step, indicated in the filename, is stored in a separate file in ASC format. 
The time is in UTC. Data in ASC format can be visualized and displayed in GIS.
"asc2raindat.py" is a Python script that creates a rainfall data file in the RRI format from the ASC format data in the folder. 
If you have a Python execution environment, you can use it. 
If you do not have a Python execution environment, a file "rain.dat", which has already been converted to the RRI rainfall data format, is also included.

**<Data check>**

Time-series ASC format files can be visualized and checked on iRIC using the following procedure. 
The data imported here is not used for calculation. This function is only for visualization and confirmation.

- Launch iRIC and select RRI.
- Right-click on "Rain[mm/h]: Data Check Only" in the Object Browser and select "Import".
- Select one file in the folder where the time-series, ASC format rainfall data is stored, and click "Open".
- A screen will appear asking you to specify the coordinate system used for the file data. Click "OK".


   .. image:: img_1/set_coordinates_for_file2_en.jpg
        :width: 480px
        :align: center

- Select "EPSG:4326: WGS84" and click "OK".

   .. image:: img_1/set_coordinates_for_file_2_en.jpg
        :width: 480px
        :align: center


-  screen will appear again asking you to specify the coordinate system used for the file data. Click "OK".

   .. image:: img_1/set_coordinates_for_file_en.jpg
        :width: 480px
        :align: center

- Select "EPSG:4326: WGS84" again and click "OK".

   .. image:: img_1/set_coordinates_for_file_2_en.jpg
        :width: 480px
        :align: center


- iRIC assumes that the file name includes the date and time. Here, you specify the format. 
- If an appropriate date and time are displayed in the recognition result, click "OK."

   .. image:: img_1/set_datetime2_en.jpg
        :width: 480px
        :align: center

- A list of correctly recognized data will be displayed. Click "OK".

   .. image:: img_1/import_list2_en.jpg
        :width: 480px
        :align: center

- Import will begin. Once the import is complete, you can visualize the rainfall data as shown below. You can also check the time-series changes. It will be easier to check if you display map on the background image.

   .. image:: img_1/finish_import_data_en.jpg
        :width: 640px
        :align: center

-----

３．計算条件設定
--------------------------------------------------

3.1 格子・格子属性の作成・確認
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
「計算条件＞設定」から計算条件設定画面を開きます。「グループ＞基本条件」で以下のように条件を設定します。


.. list-table:: 基本条件グループ
   :widths: 70 30
   :header-rows: 1

   * - 画面
     - 条件
   * - .. image:: img_1/cond_1.jpg
     - | モード：「格子・格子属性生成」
       
       | データファイル設定
       |  - DEM: 水文補正標高(elv_export.asc)
       |  - Acc: 上流集水グリッド数(upg_export.asc)
       |  - Dir: 表面流向データ(dir_export.asc)

       | 河道形状をパラメータ-
       |  - :math:`C_w=5, S_w=0.35`
       |  - :math:`C_d=0.95, S_d=0.2`
       |  - 堤防高[m]=2, 堤防セル閾値=1000


「保存して閉じる」をクリックし、「計算＞実行」をクリックします。
以下のような警告が表示されるかもしれませんが、問題ないので無視してください。

「いいえ」をクリックします。
    .. image:: img_1/warning_mapping.jpg
        :width: 480px
        :align: center


「はい」をクリックします。
    .. image:: img_1/warning_nogrid.jpg
        :width: 480px
        :align: center

以下のような警告が表示されるかもしれませんが、問題ないので無視してください。
「OK」をクリックします。
    .. image:: img_1/warning_mapping2.jpg
        :width: 480px
        :align: center


保存はipro形式としてください。
    .. image:: img_1/save_ipro.jpg
        :width: 480px
        :align: centeraa

データ処理が始まると以下の画面が表示されます。
    .. image:: img_1/running2.jpg
        :width: 640px
        :align: center

処理が完了すると以下の画面が表示されます。
    .. image:: img_1/end_run.jpg
        :width: 240px
        :align: center

プロジェクトを保存し、「ファイル＞開く」から再度プロジェクトを開いてください。

「オブジェクトブラウザ＞格子」の格子形状、および、セル属性で作成された値を確認することができます。

格子形状（293×481=140933）
    .. image:: img_1/ini_grid.jpg
        :width: 640px
        :align: center

Elevation[m] 各セルの標高値です。
    .. image:: img_1/ini_elv.jpg
        :width: 640px
        :align: center

ACC　各セルの上流集水ピクセル数です。セル面積を乗じると上流集水面積:Aになります。
    .. image:: img_1/ini_acc.jpg
        :width: 640px
        :align: center

DIR　各セルの流向です。East(1),South-East(2),South(4),South-West(8),West(16),North-West(32),North(64),North-East(128)。
    .. image:: img_1/ini_dir.jpg
        :width: 640px
        :align: center

Width[m]　上流集水面積:Aと指定したパラメータによる関数 :math:`W = C_w A^{S_w}` で河道幅が設定されています。
    .. image:: img_1/ini_width.jpg
        :width: 640px
        :align: center

Depth[m]　上流集水面積:Aと指定したパラメータによる関数 :math:`D = C_d A^{S_d}` で河道深が設定されています。
    .. image:: img_1/ini_depth.jpg
        :width: 640px
        :align: center

Height[m]　上流集水ピクセル数が堤防セル閾値以上の箇所に、堤防高で指定された堤防が設定されています。
    .. image:: img_1/ini_height.jpg
        :width: 640px
        :align: center

-----


3.2 降雨条件の設定
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
降雨条件は、「2.降雨データセットの作成」で示したデータ"rain.dat"を利用します。
"rain.dat"には、2016年8月29日 0:00UTCから2016年8月31日 23:30UTC（71.5時間分）の北海道付近の降雨データが30分間隔で格納されています。
ASCファイルをテキストエディタで開くことで、データ詳細を確認することができます。

「計算条件＞設定」で計算条件設定画面を表示し、「グループ＞降雨データ」を選択し、以下のように設定します。

.. list-table:: 降雨データ　グループ
   :widths: 70 30
   :header-rows: 1

   * - 画面
     - 条件
   * - .. image:: img_1/cond_2.jpg
     - | 降雨データファイル：サンプルデータとして
       | ダウンロードした"rain.dat"を指定します。
       
       | xllcorner_rain:139
       | yllcorner_rain:41
       | cellsize_rain_x:0.0125
       | cellsize_rain_y:0.0083333

以上で降雨データを設定は完了です。

-----

3.3 計算時間の設定
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
計算条件設定画面で、「グループ＞時間管理」を選択し、以下のように設定します。

.. list-table:: 時間管理　グループ
   :widths: 70 30
   :header-rows: 1

   * - 画面
     - 条件
   * - .. image:: img_1/cond_3.jpg
     - | シミュレーション時間[hour]：70
       | 斜面計算タイムステップ[sec]：600
       | 河道計算タイムステップ[sec]：60
       | 出力回数：70

-----

3.4 河道シミュレーション設定
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ここでは、河道セルの判定値と河道セルと認識されたセルのマニング粗度係数を指定します。


.. list-table:: 河道シミュレーション　グループ
   :widths: 70 30
   :header-rows: 1

   * - 画面
     - 条件
   * - .. image:: img_1/cond_4.jpg
     - | 河道のマニング粗度係数：0.03
       | 河道セル判定閾値：100


3.5 斜面シミュレーション設定
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
斜面シミュレーションは、セル属性"Land Use Type"と関連してパラメータ設定を行います。
この事例では、"Land Use Type"を全く指定していないため、すべてのセルの"Land Use Type"は"Region1"となります。
ここでは地下浸透、地下水流れは考慮しないことにするため、以下のように設定します。

.. list-table:: 斜面シミュレーション　グループ
   :widths: 70 30
   :header-rows: 1

   * - 画面
     - 条件
   * - .. image:: img_1/cond_5.jpg
     - | Region1のパラメータのみ有効
       
       | Green-Ampt ...
       | ksv[m/s]：0

       | lateral subsurface...
       | ka[m/s]：0

       | 上記以外のデフォルトのまま


-----

４．計算実行
--------------------------------------------------
計算条件画面で、「基本条件」の実行モードを「計算実行」にします。
「保存して閉じる」で、計算条件設定画面を閉じます。

.. image:: img_1/cond_0.jpg
        :width: 480px
        :align: center


「計算＞実行」から計算を実行してください。
計算実行前には必ず、データを保存してください。
計算が開始されると以下の画面が表示されます。

.. image:: img_1/calc_status.jpg
        :width: 640px
        :align: center

計算が終了すると、終了を知らせる画面が表示されます。

-----

５．計算結果分析・可視化
--------------------------------------------------
計算が正常に終了すると、可視化ウィンドウの表示が可能となります。
RRI on iRICは以下の値を計算結果として出力しています。

============== ========================================== ======
表示名            意味                                      補足
============== ========================================== ======
total_qp_t[mm]  総雨量[mm]                                  1
qp_t[mm/h]      雨量強度[mm/h]                              1
hs[m]           氾濫原水深[m]                               1
hr[m]           河道水深[m]                                 1 
qr[m]           河道流量[m3/s]                              1
qu              斜面流量x方向[m/s]                          1
qv              斜面流量y方向[m/s]                          1
hg[m]           地下水深[m]                                 1
gu              地下流量x方向[m/s]                          1
gv              地下流量y方向[m/s]                          1
gampt_ff        Green-Ampt cumulative water depth [m]      1
============== ========================================== ======

iRICソフトウェアの基本機能を利用して、様々な角度から計算結果を確認することができます。
以下に可視化例を表示します。

流域総雨量：2016年8月29日 0:00UTCから2016年8月31日 22:00UTC（70時間）の間に500mm以上降った箇所が複数地点あることが確認できます
    .. image:: img_1/res_sum_rain.png
        :width: 640px
        :align: center

河道流出流量（i=107, j=163)　ピーク流量は1100m3/s程度であったという結果でした。
    .. image:: img_1/res_runoff.png
        :width: 640px
        :align: center

ピーク時（2016年8月31日 1:00時）の河道水深と斜面水深
    .. image:: img_1/res_depth.png
        :width: 640px
        :align: center

ピーク時（2016年8月31日 1:00時）の河道水深と斜面水深　市街地部分を拡大。市街地部分で氾濫が生じている様子が確認できます。
    .. image:: img_1/res_depth_2.png
        :width: 640px
        :align: center

-----

まとめ
--------------------------------------------------
ここではRRI on iRICの使い方として、地形と降雨データを準備、それらを計算条件として設定し、計算を実行し、計算結果を可視化、確認する流れを紹介しました。
得られた計算結果と実現象との比較は、ここでは行いません。各自実践してみてください。
必要に応じて、パラメータを調整し再計算するなどして、現象に対する理解を深めていただければと思います。

