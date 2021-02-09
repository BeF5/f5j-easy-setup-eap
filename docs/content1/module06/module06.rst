EAPのセットアップ
=================================================

#. F5 CloudServiceのアカウントを作成します。 `F5CSのサイト <https://portal.cloudservices.f5.com/>`__ に接続し、:guilabel:`Sign up` をクリックします。

    .. image:: images/mod6-1.png
        :scale: 60%
    |  
#. フォームの内容を記入し、 :guilabel:`Create account` をクリックします。

    .. image:: images/mod6-2.png
        :scale: 60%
    |  
#. F5CSにログオンできるようになったら、**Essentail App Protect** サービスにて、**Try it free** をクリックし、更に表示されるPop-upでも :guilabel:`Yes, start free trial` をクリックします。　

    .. image:: images/mod6-3.png
    |  
#. :guilabel:`Go to this service` をクリックします。

    .. image:: images/mod6-4.png
        :scale: 60%
    |  
#. EAPのトップ画面が表示されます。トップ画面には、24時間以内の世界のThreat mapが表示されています。:guilabel:`Start protecting your app` をクリックします。

    .. image:: images/mod6-5.png
    |  
#. 対象WEBサーバのFQDNを入力し、 :guilabel:`Save＆Confinue` をクリックします。

    .. image:: images/mod6-6.png
    |  
#. EAPが対象のWEBサーバにアクセスし、その情報が表示されるので内容を確認します。確認できたら、EAPをデプロイするAWSリージョンを選択し、 :guilabel:`Save＆Confinue` をクリックします。

    .. image:: images/mod6-7.png
    |  
#. 公開しているWebサーバのプロトコルとポート番号を選択します。httpsを選択場合、サーバ証明書とプライベートキーを設定します。

    .. image:: images/mod6-8.png
    |  
#. サーバ証明書とプライベートキー、チェーン証明書を登録し、:guilabel:`Save＆Confinue` をクリックします。（必ずHTTPSにリダイレクトしたい場合は、リダイレクトのチェックを入れます。）

    .. image:: images/mod6-9.png
    |  
#. 内容を確認し、:guilabel:`Save＆Confinue` をクリックします。

    .. image:: images/mod6-10.png
    |  
#. CNAMEが自動で払い出されするので、その内容をコピーします。

    .. image:: images/mod6-11.png
    |  
#. DNSサーバの設定に戻り（以下の画面はRoute53）、既存のAレコードをCNAMEレコードに変更し、IPアドレスを削除して、先程コピーしたCNAMEをルーティング先として登録し保存します。

    .. image:: images/mod6-12.png
        :scale: 60%
    |  
#. EAPの画面に戻り、**Test updated DNS** をクリックすると、**Success** が表示されることを確認します。 :guilabel:`Done` をクリックすると、EAPのデプロイが始まります。

    .. image:: images/mod6-13.png
    |  
#. EAPのデプロイには10分程度時間がかかります。デプロイ中は、トップ画面の左上に下記のようなメッセージが表示されます。（メッセージの内容に意味はありません。）

    .. image:: images/mod6-14.png
    |  
#. EAPをデプロイしている間に、Webサーバ（ここではEC2インスタンス）のFirewall設定（ここではセキュリティグループ）を変更します。EAPで利用しているIPアドレスを許可する必要があります。最新のEAPで利用しているIPアドレス情報は `こちら <https://f5cloudservices.zendesk.com/hc/en-us/articles/360046016414-How-to-set-up-Essential-App-Protect-Service>`__ にございます。本デモ環境では、HTTPとHTTPSからAllアクセスとしていたものをEAPからのみアクセス許可するように設定変更します。

    .. image:: images/mod6-15.png
    |  
#. EAPのデプロイが終了すると、EAPデプロイ一覧画面において、**Active** と表示されます。

    .. image:: images/mod6-16.png
    |  
#. トップ画面の **PROTECT APPLICATION** をクリックすると、WAFの設定画面が表示されます。

    .. image:: images/mod6-17.png
    |  
#. 以下のようなWAFの設定画面が表示されますので、どのような設定があるか確認してみて下さい。

    .. image:: images/mod6-18.png
    |  
