（オプション）WEBサーバの構築
=================================================

EAPで守る対象のWEBサーバはインターネット経由で接続できれば、すぐに設定可能ですが、お試しされるWEBサーバをすぐに準備できない場合のために、AWS上でWEBサーバをたてる例をご紹介致します。（注：下記手順はあくまでもご参考例となります。オンプレや他のパブリッククラウドのWEBサーバでも構いません。また、コマンドや手順ははAMIのバージョン、AWSの意向によって変わる可能性があります。）

#. AWSのEC2ダッシュボードにて、:guilabel:`インスタンスを起動` を選択します。

    .. image:: images/mod3-1.png
    |  
#. ここでは、**Amazon Linux 2 AMI** を選択します。

    .. image:: images/mod3-2.png
    |  
#. こ無料枠利用のタイプを選択し、:guilabel:`次のステップ: ...` をクリックします。

    .. image:: images/mod3-3.png
    |  
#. **自動割り当てパブリックIP** を **有効** にし、:guilabel:`次のステップ: ...` をクリックします。（ここではパブリックIP割当以外はデフォルト設定としていますが、環境に応じて、VPC、サブネットなどをご選択下さい。）

    .. image:: images/mod3-4.png
        :scale: 60%
    |  
#. ストレージの追加はデフォルト設定のまま、 :guilabel:`次のステップ: ...` をクリックします。

    .. image:: images/mod3-5.png
    |  
#. 分かりやすいタグ名を付け、 :guilabel:`次のステップ: ...` をクリックします。

    .. image:: images/mod3-6.png
    |  
#. SSH（管理IPからの接続のみ）、HTTPとHTTPS（全ソースからの接続を許可）を加えたセキュリティグループを作成し、:guilabel:`確認と作成` をクリックします。（EAPのセットアップ後、本ルールの内容はEAPからのみ接続可能とするようなルールに変更します。）

    .. image:: images/mod3-7.png
    |  
#. 設定内容の確認をし、:guilabel:`起動` をクリックします。

    .. image:: images/mod3-8.png
    |  
#. 設既存のキーがお持ちの方はそれを選択し、お持ちでない方は新しいキーペアを作成、ダウンロードします。アクセス権確認のチェックボックスにチェックを入れ、:guilabel:`インスタンスの作成` ボタンを押します。

    .. image:: images/mod3-9.png
        :scale: 60%
    |  
#. 作成したEC2インスタンスが実行中となり、ステータスチェックに合格したら、該当インスタンスを選択し、:guilabel:`接続` を押します。

    .. image:: images/mod3-10.png
    |  
#. SSHクライアントタブを選択し、SSHコマンドをコピーします。（新しくキーペアを作成した方は、下記のAWSの手順に従って、キーの権限を変更します。）

    .. image:: images/mod3-11.png
    |  
#. SSHクライアントソフトウェアにSSHコマンドをコピーし、SSH接続します。（カレントディレクトリにAWSのキーを配置する必要があります。）

    .. image:: images/mod3-12.png
    |  
#. yumパッケージをアップデートします。Complete!と表示されればインストール完了です。アップデートがない場合もあります。（ご参考サイト： `インスタンス上で Amazon Linux インスタンスソフトウェアを更新する <https://docs.aws.amazon.com/ja_jp/AWSEC2/latest/UserGuide/install-updates.html>`__ ）

    .. code-block:: bash

            sudo yum update -y
#. EPELリポジトリをインストールします。Complete!と表示されればインストール完了です。（ご参考サイト： `CentOS、RHEL、または Amazon Linux を実行している Amazon EC2 インスタンスの EPEL リポジトリを有効にするにはどうすればよいですか? <https://aws.amazon.com/jp/premiumsupport/knowledge-center/ec2-enable-epel/>`__ ）
 
    .. code-block:: bash

            sudo amazon-linux-extras install epel -y
#. インストールしたEPELリポジトリからWEBサーバ（OSS版NGINX）をインストールします。Complete!と表示されればインストール完了です。（ご参考サイト：  `Extras library (Amazon Linux 2) <https://docs.aws.amazon.com/ja_jp/AWSEC2/latest/UserGuide/amazon-linux-ami-basics.html#extras-library>`__ ）

    .. code-block:: bash

            sudo amazon-linux-extras install nginx1 -y
    .. note::
        ここでは、EAPの動作を簡易的に確認するために、OSS版のNGINXを利用しています。NGINXは全世界で幅広く利用されている高性能で軽量なWEBサーバです。ロードバランサ、コンテンツキャッシュ、Ingress Congrollerとしてもご利用可能です。有償版のNGINX Plusをご利用頂くことで様々なメリットがございます。OSS版と有償版の違いは以下のサイトをご確認下さい。
            - `NGINX Plusプロダクトページ <https://www.nginx.co.jp/products/products-nginx/>`__
            - `ブログ：NGINXとは？ NGINXとNGINX Plusを徹底解説します <https://www.nginx.co.jp/blog/what-is-nginx/>`__
#. インストールしたNGINXを毎回起動するように設定にし、NGINXを起動します。

    .. code-block:: bash

            sudo systemctl enable nginx
#. NGINXが起動されていることを確認します。 **Active: active (running)** と表示されれば起動しています。

    .. code-block:: bash

            sudo systemctl status nginx






