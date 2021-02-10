F5 Cloud Services Essential App Protect（EAP）とは
=================================================

F5 Cloud Services Essential App Protect（略してEAP）は、F5が提供するSaaS形式のWAFサービスです。 `F5 Cloud Serviceの管理画面 <https://portal.cloudservices.f5.com/>`__ からアカウントを作成頂くだけで、すぐにご利用頂けます。（今のところ、30日間無料でお試し頂くことも可能です！）

 .. image:: images/mod1-1.png
      :scale: 60%
      :align: center

特徴としては、以下のような点がございます。

- SaaS型WEBセキュリティ
    シグネチャやパッチ適用などはF5のSOC側で全て行いますので、運用のコストを削減することができます。
- かんたん設定で、導入の敷居が低い
    WAFで守るWEBサーバの設定はステップバイステップの設定ガイダンスが表示されますので、敷居があまり高くありません。そして、WAFのポリシー設定もとても分かり易いデザインとなっています。
    守りたいWEBサーバへのエージェントインストールは一切不要です。DNSの設定変更のみが必要で、それ以外のネットワーク構成変更は一切不要です。
- DevOpsフレンドリ
    モダンアプリケーションの開発ですと、一連のCI/CDの開発パイプラインが定められているケースがございますが、そういったDevOpsユーザの皆様にも順応可能なデザインとなっております。
- F5オンプレWAFの専門知識がつまっている
    F5ではBIG-IP ASM、AdvncedWAFというWAF製品を長年に渡って販売してきている会社ですが、そのWAFの専門知識が活かされています。
- AWS CloudFront連携
    EAPのGUIよりCloudFrontの設定が可能です。

因みに本ガイドではEAPのご紹介となりますが、 F5では以下のようなお客様のご要望にあわせた様々なWAFを提供しております

.. csv-table:: 
        :header: "製品名／サービス名", "概要", "ご利用例"
        :widths: 8, 25, 15

        "| F5 Cloud Services Essential
        | App Protect Service (EAP)", "| SaaS型WAF。サービスのGUIまたはAPIを通して、WAFを設定可能。
        | シグネチャ、IPレピュテーションDBなどはF5側で更新。", "お手軽にすぐにWAFをご利用されたいケース"
        "| Silverline 
        | Web Application Firewall", "WAFのマネージド・サービス。24時間365日F5のSOCチームにて運用。", "WAFの専門家に運用を任されたいケース"
        "F5 Advanced Web Application Firewall", "| オンプレ、プラベートクラウド、パブリッククラウドなど
        | 場所を問わずご利用可能なアプライアンス型WAF。", "| BIG-IP LTMにアドオンされたいケース
        | 自社で柔軟にWAFを運用されたいケース"
        "NGINX App Protect", "| NGINX Plusと一緒にご利用可能なソフトウェア型WAF。
        | ホスト型WAF、ゲートウェイ型WAFのどちらでも対応可能。", "| モダンアプリケーション環境において、
        | WAFを適用されたいケース"


