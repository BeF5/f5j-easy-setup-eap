WEBサーバ冗長構成時の構成例
=================================================

WEBサーバ冗長構成の場合の構成例をご紹介します。

EAPで負荷分散をする場合
---------------

#. EAP配下に複数のWEBサーバのIPアドレス、またはDNS名を登録することで振分けの動作が可能です。Route53のレイテンシベースルーティングで振分けが行われます。

    .. image:: images/mod10-1.png
        :scale: 60%
    |  
#. 設定としては、Regionの設定配下のIPアドレス／DNS名を追加します。

    .. image:: images/mod10-2.png
        :scale: 60%
    |  

AWS ALBで負荷分散をする場合
---------------

#. ALBでWEBサーバの負荷分散をしているケースにもEAPを適用可能です。登録時はALBのエイリアスレコードでDNS設定し、EAPデプロイ時にEAPから払い出されたCNAMEでDNSレコードを書換えます。

    .. image:: images/mod10-3.png
        :scale: 60%
    |  
#. EAPデプロイ後、ALBの登録は名前解決後のIPアドレスで登録されてしまうので、Regionの設定配下のIPアドレスをALBのDNS名に変更します。

    .. image:: images/mod10-4.png
        :scale: 60%
    |  

F5CS DNS Load Balancerで負荷分散をする場合
---------------

#. EAPの他に、`F5CSのDNS Load Balancerサービス <https://clouddocs.f5.com/cloud-services/latest/f5-cloud-services-GSLB-About.html>`__ をご利用頂くことでも負荷分散がです。EAP配下にF5CS DNSLBのDNS名を登録することで連携が可能となります。

    .. image:: images/mod10-5.png
        :scale: 60%
    |  

