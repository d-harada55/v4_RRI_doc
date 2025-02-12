Introduction
==================================================

本書は **RRI on iRIC** の「事例集」です。


RRIについて
------------------------------
RRIはRain Runoff Inundationモデルの略で、流域に降った雨が河川に集まる現象、洪水が河川を流下する現象、河川を流れる水が氾濫原に溢れる現象を流域一体で予測するモデルです。
2016年5月からは、RRIモデルを `ICHARMホームページ  <https://www.pwri.go.jp/icharm/research/rri/index_j.html>`_  でも公開し、誰でも無料で入手できます。

モデル詳細については、上記ダウンロードサイトからダウンロードできるデータに同梱されているマニュアルを参照するか、以下の文献 [1]_ ,  [2]_ ,  [3]_ を参照ください。

.. [1] `Sayama, T., Ozawa, G., Kawakami, T., Nabesaka, S., Fukami, K. (2012) Rainfall-Runoff-Inundation analysis of the 2010 Pakistan flood in the Kabul River basin, Hydrological Science Journal, 57(2), 298-312. <https://www.tandfonline.com/doi/full/10.1080/02626667.2011.644245>`_
.. [2] `Sayama, T., Tatebe, Y., Tanaka, S. (2015a) An emergency response-type rainfall-runoff- inundation simulation for 2011 Thailand floods, Journal of Flood Risk Management, 1-8 doi:10.1111/jfr3.12147 (in print). <https://onlinelibrary.wiley.com/doi/full/10.1111/jfr3.12147>`_ 
.. [3] `Sayama, T., Tatebe, Y., Iwami, Y., Tanaka, S. (2015b) Hydrologic sensitivity of flood runoff and inundation: 2011 Thailand floods in the Chao Phraya River basin, Nat. Hazards Earth Syst. Sci., 15, pp. 1617-1630, doi:10.5194/nhess-15-1617-2015. <https://www.researchgate.net/publication/282201567_Hydrologic_sensitivity_of_flood_runoff_and_inundation_2011_Thailand_floods_in_the_Chao_Phraya_River_basin>`_ 

-----

RRI on iRICについて
------------------------------
RRI on iRICは、 `「降雨流出氾濫（RRI）モデルプログラム利用規約 <https://www.pwri.go.jp/icharm/research/rri/rri_contract_j.html>`_ 」、第1章ⅱ、ⅲの項目に基づき改変公開しているものです。
そのため、RRI on iRIC(以降、本プログラム)による計算結果の公表、頒布する場合は下記内容を明記してください。

---

- 本プログラムの原著作物（以降、RRI）の著作権は、土木研究所（ICHARM）にあります
- 本プログラムは、RRIの二次著作物にあたります。
- 計算結果は、RRIを改変したプログラム（本プログラム）によるものです

---


-----

RRI on iRICを利用する準備
------------------------------

- 1. RRI on iRIC をダウンロード

    - `rri_v1 <https://uc.i-ric.org/uc_products/rri_on_iric/v4_rri_240521.zip>`_


- 2. ダウンロードしたデータを展開して、iRICのソルバフォルダにコピー＆ペースト。デフォルトでは、"C:/Users/[ユーザー名]/iRIC_v4/private/solvers"

- 3. 完了。iRICソフトウェアを起動するとRRIが選択できるようになっています。

    .. image:: img/rri_v12.jpg
        :width: 640px





以上。








