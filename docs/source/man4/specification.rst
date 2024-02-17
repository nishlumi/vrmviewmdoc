.. index:: アニメーションプロジェクトの構成

#####################################
アニメーションプロジェクトの構成
#####################################

.. contents::


　アニメーションプロジェクトの構成について説明します。大まかに言うと次のようになっています。

.. mermaid::

    flowchart LR
        subgraph File
            VRM[(VRM)]
            3dobj[(3D models)]
        end
        subgraph Project
            direction LR
            subgraph Timeline
                subgraph role[Role]
                    direction LR
                    cast((Cast))
                    
                    subgraph keyframe
                        direction TB
                        keys1{" "}
                        keys2{" "}
                        keys3{" "}
                    end
                end
            end
            subgraph tl2["Timeline 2"]
                cast2((Cast))
            end
            subgraph tl3["Timeline 3"]
            end
        end

        style Project fill:#AAAAFA
        style role fill:#00FF00
        style cast fill:#FF9090
        style cast2 fill:#FF9090
        style keyframe fill:#FFFF25
        style keys1 fill:#FFFF00
        style keys2 fill:#FFFF00
        style keys3 fill:#FFFF00

        tl2 ~~~ tl3 
        VRM ==> cast
        3dobj ==> cast2

各要素
################

.. index:: タイムライン（アニメーションプロジェクトの構成）

タイムライン
    .. mermaid::
        :align: left

        flowchart LR
        subgraph tl1[Timeline 1]
            avatar1((Role))
        end
        subgraph tl2[Timeline 2] 
            avatar2((Role))
        end
        subgraph tl3[Timeline 3]
            avatar3((Role))
        end

        style avatar1 fill:#00FF00
        style avatar2 fill:#00FF00
        style avatar3 fill:#00FF00

        tl1 ~~~ tl2 ~~~ tl3

    | 　タイムラインはアニメーションの基本単位です。1つのタイムラインに1つのロール、1つのキャストが対応しています。
    | 　実際の機能としては次のロールがすべて受け持っています。

..
    .. image:: img/specifi_1.png
    :align: left

|
|
|
|
|
|

.. index:: ロール・役割（アニメーションプロジェクトの構成）

ロール・役割
    .. mermaid::
        :align: left

        flowchart LR
        subgraph role[Role]
            direction LR
            cast((Cast))
            
            subgraph keyframe
                direction TB
                keys1{" "}
                keys2{" "}
                keys3{" "}
            end
        end

        style role fill:#00FF00
        style cast fill:#FF9090
        style keyframe fill:#FFFF25
        style keys1 fill:#FFFF00
        style keys2 fill:#FFFF00
        style keys3 fill:#FFFF00

    | 　ロールとは、各オブジェクトがタイムラインにおいてどう動くかの役割・キャラクターの動作のまとまりです。
    | 　ロールの中には割り当てるキャスト、そしてキーフレームのデータが存在します。
    | 　ロールは同じオブジェクトの種類であれば、別のオブジェクトに差し替えることができます。

    　実質的には、 **タイムライン＝ロール** です。本説明書でタイムラインというときはロールを指し、その逆としても使われます。

|
|
|
|

.. index:: キャスト・オブジェクト（アニメーションプロジェクトの構成）

キャスト・オブジェクト・アバター
    .. mermaid::
        :align: left

        flowchart LR
        
            cast((Cast))
            
            

        style cast fill:#FF9090
    
    | 　キャストとはロールに割り当てるオブジェクトのことです。ここが実際のVRoid/VRM、FBX、Light、Audioなどのオブジェクトの実体となっています。
    | 　本アプリでは単にオブジェクトとか、アバターなどとも言い換えています。

|
|
|

.. index:: キーフレーム（アニメーションプロジェクトの構成）

キーフレーム
    .. mermaid::
        :align: left

        flowchart LR
        subgraph keyframe
            direction TB
            keys1{" "}
            keys2{" "}
            keys3{" "}
        end

        style keyframe fill:#FFFF25
        style keys1 fill:#FFFF00
        style keys2 fill:#FFFF00
        style keys3 fill:#FFFF00

    　キーフレームはロールの実際の動きのデータ、モーションです。このデータはあくまでロールが保持しており、原則として各オブジェクトには依存しない形になっています。

|
|
|


タイムライン・ロール・キャストの関係
################################################

| 　タイムラインは最終的にはロールと同じ意味です。それからキャストは実際のオブジェクトと同じ意味です。
| 　ロールはキャスト（オブジェクト）と１：１で紐付いています。ロールはキャストなしの状態がありえますが、そのロールは一切アニメーションされません。

　ロールには後から別のキャスト（オブジェクト）を割り当てることができます。

　例で言うと次のようになります。(色とアイコンは上記の例に対応しています)


.. mermaid::

    flowchart LR
    subgraph File
        VRM1[(VRM 1)]
        VRM2[(VRM 2)]
    end
    subgraph Timeline
        subgraph role[Role]
            direction LR
            cast((Cast))
            
            subgraph keyframe
                direction TB
                keys1{" "}
                keys2{" "}
                keys3{" "}
            end
        end
    end

    style role fill:#00FF00
    style cast fill:#FF9090
    style keyframe fill:#FFFF25
    style keys1 fill:#FFFF00
    style keys2 fill:#FFFF00
    style keys3 fill:#FFFF00

    VRM1 & VRM2 ==> cast

:ロール: アニメやドラマの人物

:キャスト: 声優、俳優本人


| 　実際のアニメーションデータはロールが持っています。そのためそのモーションを再生するのに実際のキャスト（オブジェクト）が何であるかは問いません。
| 　上記の仕組みのために、好きなアニメーションを好きなオブジェクトで再生することができるようになっています。
