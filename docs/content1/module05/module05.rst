（オプション）Let’s encryptを利用したサーバ証明書の取得
=================================================

Let’t Encryptを利用してサーバ証明書を取得します。とりあえずhttp/80のWEBサーバでのテストでも構わないという方は本章はスキップして下さい。

#. Certbot とNGINXプラグインをインストールします。Complete!と表示されればインストール完了です。（注：本ガイド作成時点ではAmaon Linux 2では公式にはサポートされていないようですが、正常に動作はするようです。（ご参考サイト： `Certificate Automation: Amazon Linux 2 での Let's Encrypt と Certbot の使用 <https://docs.aws.amazon.com/ja_jp/AWSEC2/latest/UserGuide/SSL-on-amazon-linux-2.html#letsencrypt >`__ 、 `User Guide <https://certbot.eff.org/docs/using.html#nginx>`__ ）

    .. code-block:: bash

            sudo yum install certbot python2-certbot-nginx -y
#. インストール済みのCertbotを利用して、サーバ証明書を取得します。

    .. code-block:: bash

            sudo certbot --nginx -d <WEBサーバのドメイン名>
#. インストラクションに従い、**E-mail address** 、**Y** 、**N** と入力します。**Congratulations!** と表示されれば成功です。/etc/nginx/nginx.confを開き、サーバ証明書、秘密鍵のパスが自動的に記載されていることを確認します。自動的にnginx.confが上書きされていない場合は、手動で修正します。

    .. image:: images/mod5-1.png
    |  
#. ブラウザでhttps://<WEBサーバのFQDN＞にアクセスし、サーバ証明書が表示されることを確認します。

    .. image:: images/mod5-2.png
    |  
#. ensslコマンドを利用し、プライベートキーを **PKCS#8** フォーマットから **PKCS#1** フォーマットに変換し、SCPコマンドなどでプライベートキーと証明書（fullchain.pem）をダウンロードします。(ご参考ページ： `valid PKCS#1, ASN.1 DER form - while adding new certificate <https://f5cloudservices.zendesk.com/hc/en-us/articles/360055650294-Issue-Receiving-error-Private-key-is-not-in-valid-PKCS-1-ASN-1-DER-form-while-adding-new-certificate>`__ ）

    .. code-block:: bash

            sudo openssl rsa -in  /etc/letsencrypt/live/www.xxxx.net/privkey.pem -out /home/ec2-user/privatekey-pkcs1.pem
