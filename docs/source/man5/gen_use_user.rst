#######################
ユーザーフロー
#######################

ここでは本アプリを使うにあたり、まず何をどうすればよいのかそのとっかかりを紹介していきます。

本アプリを使うステップは3段階あると仮定します。

.. mermaid::

    flowchart TB
    subgraph First
        direction LR
        input_vrm[["Load VRM"]]
        input_3d[["Load 3D model"]]
        open_internalobj[["Generate Light/Camera etc"]]

        file_vrm[("VRMs")]
        file_3d[("3D models")]
        file_vrm -..-> input_vrm
        file_3d -..-> input_3d

        style input_vrm fill:#FFFF00
        style input_3d fill:#FFFF00
        style open_internalobj fill:#FFFF00
    end
    
    subgraph Second
        direction TB
        change_pose[["Change pose"]]
        change_transform[["Change transform"]]
        change_properties[["Change properties"]]

        data_vrm[("VRMs")]
        data_3d[("3D models")]
        data_camera[("Camera etc")]

        %%data_vrm & data_3d & data_camera -..-> change_pose & change_properties
        change_pose -..-> data_vrm
        change_transform & change_properties -..-> data_vrm & data_3d & data_camera

        style change_pose fill:#FFFF00
        style change_transform fill:#FFFF00
        style change_properties fill:#FFFF00
    end

    reg_keyframe[["Register a keyframe"]]

    subgraph Next
        direction LR
        
        change_duration[["Change a duration"]]
        change_easing[["Change an easing"]]
        play_animation[["Play an animation"]]
        get_screenshot[["Take screenshot"]]
        get_movie[["Recording"]]
        play_vrar[["Play VR/AR space"]]

        file_picture[("Picture")]
        file_movie[("Video")]

        change_duration & change_easing -..-> play_animation -..-> get_movie -..-> file_movie
        play_vrar -..-> get_movie -..-> file_movie
        get_screenshot -..-> file_picture

        style reg_keyframe fill:#FFFF00
        style change_duration fill:#FFFF00
        style change_easing fill:#FFFF00
        style play_animation fill:#FFFF00
        style get_screenshot fill:#FFFF00
        style get_movie fill:#FFFF00
        style play_vrar fill:#FFFF00
    end

    First ~~~ Second  ~~~ Next 

    First --> Second
    Second ---> reg_keyframe --> Next
    Next --> Second

:First: VRMや3Dモデル・その他オブジェクトを開く。準備のステップ。
:Second: 各オブジェクトのプロパティを変更する。確認や作り込むステップ
:Next: アニメーション再生したりVR/AR空間で見る・スクリーンショットを撮るなどの実行のステップ。

**Second** と **Next** を繰り返していくことになると思います。

細かい操作説明は文章のマニュアルよりも動画のほうがよいでしょう。

私のYouTubeチャンネルとウェブサイトにて、動画式のマニュアルを公開しています。順次増やしていく予定です。こまめにアクセスしてみてください。

:YouTubeチャンネル: `VRM鎮守府ポータル動画版 <https://www.youtube.com/@vroid2502>`_
:ウェブサイト: `VRMViewmeister Video Manual - VRM鎮守府ポータル <https://sites.google.com/view/lumis-vroidbase/pubcontents/vvmdoc-onevid>`_