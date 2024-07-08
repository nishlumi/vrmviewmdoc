#######################
ユーザーフロー
#######################

ここでは本アプリを使うにあたり、まず何をどうすればよいのかそのとっかかりを紹介していきます。

本アプリを使うステップは3段階あると仮定します。

.. mermaid::

    flowchart TB
    subgraph Open
        direction TB
        open_func[["Open"]]

        file_vrm[("VRMs")]
        file_3d[("3D models")]
        file_cam[("Camera")]
        file_other[("etc...")]
        file_vrm -..-> open_func
        file_3d -..-> open_func
        file_cam -..-> open_func
        file_other -..-> open_func

        style open_func fill:#FFFF00
    end
    
    subgraph Change
        direction TB
        chtarget_pose["Pose"]
        chtarget_transform["Transform"]
        chtarget_properties["Properties"]
        chtarget_resolution["Resolution"]
        change_duration["Duration"]
        change_easing["Easing"]
        change_syseff["SystemEffect"]

        change_func[["Change"]]

        chtarget_pose -..-> change_func
        chtarget_transform -..-> change_func
        chtarget_properties -..-> change_func
        chtarget_resolution -..-> change_func
        change_duration -..-> change_func
        change_easing -..-> change_func
        change_syseff -..-> change_func

        style change_func fill:#FFFF00

    end

    reg_keyframe[["Register a keyframe"]]

    subgraph Play
        direction LR
        
        play_animation[["Play an animation"]]
        get_screenshot[["Take screenshot"]]
        get_movie[["Recording"]]
        play_vrar[["Play VR/AR space"]]

        file_picture[("Picture")]
        file_movie[("Video")]

        play_animation -..-> get_movie -..-> file_movie
        play_vrar -..-> get_movie -..-> file_movie
        get_screenshot -..-> file_picture

        style reg_keyframe fill:#FFFF00
        style play_animation fill:#FFFF00
        style get_screenshot fill:#FFFF00
        style get_movie fill:#FFFF00
        style play_vrar fill:#FFFF00
    end

    Open ~~~ Change  ~~~ Play 

    Open --> Change
    Change ---> reg_keyframe --> Play
    Play --> Change

:Open: VRMや3Dモデル・その他オブジェクトを開く。準備のステップ。
:Change: 各オブジェクトのプロパティを変更する。確認や作り込むステップ
:Play: アニメーション再生したりVR/AR空間で見る・スクリーンショットを撮るなどの実行のステップ。

**Second** と **Next** を繰り返していくことになると思います。

細かい操作説明は文章のマニュアルよりも動画のほうがよいでしょう。

私のYouTubeチャンネルとウェブサイトにて、動画式のマニュアルを公開しています。順次増やしていく予定です。こまめにアクセスしてみてください。

:YouTubeチャンネル: `VRM鎮守府ポータル動画版 <https://www.youtube.com/@vroid2502>`_
:ウェブサイト: `VRMViewmeister Video Manual - VRM鎮守府ポータル <https://sites.google.com/view/lumis-vroidbase/pubcontents/vvmdoc-onevid>`_