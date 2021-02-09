キャッシュ機能（AWS CloudFront）の設定
=================================================

EAPは、AWSのCloudFrontと連携が可能です。またその設定もEAPの管理画面上から行うことができます。

#. **PROTECT APPLICATION** の **Integrations** タブにて、**Manage** をクリックします。

    .. image:: images/mod8-1.png
    |  
#. **Enabele Caching** にチェックを入れます。

    .. image:: images/mod8-2.png
    |  
#. Japanが含まれているキャッシュロケーションを選択し、:guilabel:`Update` をクリックします。CloudFrontのデプロイには数分かかります。

    .. image:: images/mod8-3.png
    |  
#. CloudFrontがデプロイされると、Statusが **Deployed** となります。

    .. image:: images/mod8-4.png
    |  


