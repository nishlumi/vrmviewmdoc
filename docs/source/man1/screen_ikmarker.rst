.. index:: IKマーカーの位置変更（画面の構成）

####################################
IKマーカーの位置変更
####################################

.. image:: ../img/screen_ikmarker.png
    :align: center

　VRoid/VRMの場合に使う機能です。本アプリで用いるモデルの体パーツの位置と回転を直接指定できます。別ウィンドウが開きます。アプリとは別ウィンドウです。

ver 2.9.0より、設定によりアプリのメインウィンドウ内部に表示することもできるようになりました。

**上部：**

:ポーズを適用:
    下部のスプレッドシートで指定した値でポーズを適用。
:再読み込み:
    現在のポーズの情報を再読み込みする。
:ポーズを反転する:
    現在のポーズの値を左右逆転する


**下部：**

スプレッドシート:
    体の部位ごとのPosition（位置）・Rotation（回転）を数値で指定する。


.. note::
    * このウィンドウを表示している最中もVRoid/VRMを直接移動・回転できますが、仕様によりすぐにこのウィンドウのスプレッドシートには反映されません。再読み込みボタンを押すことで位置・回転の情報がすぐに取得できます。
    * オブジェクトの選択を変えた時、タイムラインのキーフレームの選択を変更した時には自動的に再読み込みされます。
    * VRM以外を選択した場合はスプレッドシートは使用できなくなります。


