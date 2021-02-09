WAFの動作確認テスト
================================

#. クライアントブラウザから、Webサーバに情報取得目的（https://xxxxxx/nginx.config）でアクセスします。

    .. image:: images/mod7-1.png
        :scale: 50%
        :align: center
    |  
#. EAPのトップ画面から、**VIEW EVENTS** をクリックすると、ファイルへのイリーガルアクセスのバイオレーションのログが確認できます。Statusは、**Not blocked** となっていることが確認できます。

    .. image:: images/mod7-2.png
    |  
#. それぞれのログをクリックすると以下のような詳細が表示されます。

    .. image:: images/mod7-3.png
    |  
#. **View full request** をクリックすると更に詳細なログが表示されます。

    .. image:: images/mod7-4.png
    |  
#. EAPのWAF設定画面に戻り、**Monitoring** モードから **Blocking** モードに変更し、Updateボタンをクリックします。

    .. image:: images/mod7-5.png
    |  
#. 再度クライアントブラウザから情報取得目的でアクセスすると、ブロックされます。（デフォルトでは以下のような猫の絵と、サポートIDが表示されます。）

    .. image:: images/mod7-6.png
        :scale: 60%
        :align: center
    |  
#. EAPのログを確認すると、**Blocked** となっていることが確認できます。

    .. image:: images/mod7-7.png
    |  
#. 詳細なログが確認できます。

    .. image:: images/mod7-8.png
    |  
#. 更に詳細なログが確認できます。

    .. image:: images/mod7-9.png
    |  
#. EAPのトップ画面にて、**MONITOR APPLICTION** をクリックすると、以下のようなWAF統計レポートが確認できます。

    .. image:: images/mod7-10.png
    |  
