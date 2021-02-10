WEBサーバ冗長構成時の構成例
=================================================

WEBサーバ冗長構成の場合の構成例をご紹介します。

EAPで負荷分散をする場合
---------------

#. EAP配下に複数のWEBサーバのIPアドレス、またはDNS名を登録することで振分けの動作が可能です。Route53のレイテンシベースルーティングで振分けが行われます。

    .. image:: images/mod10-1.png
    |  
#. 設定としては、Regionの設定配下のIPアドレス／DNS名を追加します。

    .. image:: images/mod10-2.png
    |  

AWS ALBで負荷分散をする場合
---------------

#. ALBでWEBサーバの負荷分散をしているケースにもEAPを適用可能です。登録時はALBのエイリアスレコードでDNS設定し、EAPデプロイ時にEAPから払い出されたCNAMEでDNSレコードを書換えます。

    .. image:: images/mod10-3.png
    |  

F5CS DNS Load Balancerで負荷分散をする場合
---------------

#. EAPの他に、F5CSのDNS Load Balancerサービスをご利用頂くことでも負荷分散がです。EAP配下にF5CS DNSLBのDNS名を登録することで連携が可能となります。

    .. image:: images/mod10-4.png
    |  

