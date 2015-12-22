Dokcer compose practice
-----------------------

## 概要

http://qiita.com/kohey18/items/dffe9b11d330576ab852 を参考にして、
Windows環境の docker-machine で docker-compose を試した。

## 実行方法

+ <you> の箇所は適宜修正する。
+ 特に、td-agent の volumeの箇所は、Windows のユーザー名に正しくあわせる。
+ `docker-compose up -d` で起動する。 192.168.99.100 にアクセスすると、"hello world" が表示され、
  volume に指定したフォルダに、flentd経由でログファイルが出力される。
+ 停止するには、 `docker-compose stop`
+ 停止後、コンテナを破棄するには、 `docker-compose rm`
    + ビルドしたイメージを削除するには、停止済みであってもそのイメージから作成されたコンテナを破棄する必要がある。


## メモ

+ イメージ - docker アプリケーション の静的なスナップショットのようなもの。`docker pull` で取得し、`docker images` で表示されるのはこっち。
+ コンテナ - イメージから作成された実行中(または実行済み)のアプリケーションのようなもの。  
             コミットすると新たなイメージになる。`docker run <イメージ>` でコンテナの作成と実行を行う。  
             `docker ps` で表示されるのはこっち。
+ docker-machine には、 /c/Users 配下がマウントされるので、volume の連携も可能。
+ fulentd-address は、 dockermachin のIP でなく, localhostで可。
+ docker-compose は build か images のどちらか片方だけ指定できる。
    + imageの場合は、事前にbuildしたイメージが必要となる。第三者のイメージのような修正が不要なものを使う場合ならこっち。
    + build の場合、cocker-compose.ymlのフォルダ名 + ~.ymlのトップレベル名 + でイメージが作られる。
    + 例えば、 tutorial_sinatra
    + コンテナ名は、そこに連番が付く感じ。例えば、 tutorial_sinatra_1
+ td-agentを最初に起動する必要があり、そのため、 sinatraの links に td-agentを記述している。
    + links の記述があると、リンクされる方のコンテナが優先して起動されるため。
    + コンテナの起動順をリンク以外で制御できないのかな。
