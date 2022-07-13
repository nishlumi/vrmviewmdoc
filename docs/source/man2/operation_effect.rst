.. index:: Effect

####################################
Effect
####################################


　Effectはアニメーションする画面効果をオブジェクトとして追加したり、他のオブジェクトに対して影響を与える効果を設定することができます。

.. contents::

.. index:: Effectのプレビュー

.. image:: ../img/operation_effect_1.png
    :align: center

|

　IKマーカーは他と区別するためにカプセル状になっています。IKマーカーの位置を基準として特殊効果を表示します。同時に表示させる数に制限はありません（ただし動作は重くなる可能性があります）。また、効果音があるエフェクトは同時に音が鳴ります。

　アニメーションプロジェクトではエフェクトのアニメーションの「再生」「停止」などの状態をキーフレームに登録します。


1. ジャンルを選択します。
2. ジャンルに含まれるエフェクト名を選択します。
3. プレビュー再生を押してエフェクトを確認してください。


.. |preview| image:: ../img/operation_effect_2.png
.. |anireg| image:: ../img/operation_effect_3.png

.. csv-table::

    プレビュー再生, アニメーション登録用
    |preview|, |anireg|
    即座に再生されます。こちらの操作はキーフレームには登録されません。, 「再生」や「停止」を選択後にキーフレームに登録します。


.. caution::
    エフェクトの再生が終わっていないうちは再び再生を行うことはできません。

|

.. index:: VRMとの衝突プロパティ

VRMとの衝突プロパティ
------------------------

　VRMの髪などボーンがある部位に対して衝突させて反動で動かすことのできる効果です。

.. image:: ../img/operation_effect_4.png
    :align: center

|

　衝突機能を使用にチェックを入れると衝突の範囲が半透明な球体で描写されます。これはプレビューの意味合いです。

　衝突範囲の大きさで範囲を変更できます。それに合わせてプレビューの球体も変化します。

.. |norange| image:: ../img/operation_effect_5.png
.. |isrange| image:: ../img/operation_effect_6.png

========== ============
|norange|   |isrange|
========== ============

.. |collidertarget| image:: ../img/operation_effect_7.png
.. |colliderdecide| image:: ../img/operation_effect_8.png
.. |colliderdelete| image:: ../img/operation_effect_9.png

:|collidertarget|:
    |
    | 衝突させたいVRMを選びます。

:|colliderdecide|:
    |
    | 選んだVRMに登録します。一つのEffectに複数のVRMを登録可能です。

:|colliderdelete|:
    |
    | 設定を削除したい場合は対象のVRMの右端のボタンで削除します。
