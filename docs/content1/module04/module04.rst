DNSへのAレコードの登録
=================================================

Route53の登録例
---------------

DNSのドメイン名、ホストゾーンの登録がない場合は作成します。（注：下記はあくまでも例となります。他のDNSシステムでも構いません。）

#. ドメイン名を選択します。

    .. image:: images/mod4-1.png
        :scale: 60%
        :align: center
    |  
#. ホストゾーンを設定します。

    .. image:: images/mod4-2.png
        :scale: 80%
        :align: center
    |  
#. レコード名を記載、レコードタイプはAを選択、作成済みのEC2インスタンスのパブリックIPアドレスを記入し、Aレコードを作成します。

    .. image:: images/mod4-3.png
        :scale: 80%
        :align: center
    |  
#. 登録したFQDNにブラウザ経由でhttpアクセスし、テストWEBページが表示されることを確認します。（こちらのページは、あくまでもテストのために利用しています。）

    .. image:: images/mod4-4.png
        :scale: 60%
        :align: center
    |  