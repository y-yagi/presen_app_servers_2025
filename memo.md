## App Servers

### Puma

* [puma/puma](https://github.com/puma/puma)
* Rubyの代表的なアプリケーションサーバ
* マルチスレッド対応
    * ワーカープロセス内でスレッドプールを使用
    * I/O待機時に他のリクエストを処理可能
* クラスタモード
    * 複数のワーカープロセスを起動
    * プロセス間でリクエストを分散
* 設定が柔軟
    * workers（プロセス数）とthreads（スレッド数）を調整可能
    * `config/puma.rb`で詳細設定
* 特徴
    * メモリ使用量が比較的少ない
    * CPUバウンドなタスクにも対応
    * Railsのデフォルトサーバ（Rails 5以降）
    * Hot Restart機能（phased restart）
* パフォーマンス
    * I/Oバウンドなアプリケーションで高いパフォーマンス
    * スレッドセーフなコードが前提
* デプロイ
    * Herokuでのデフォルト
    * Dockerコンテナでも広く使用

### Unicorn

* [bogomips/unicorn](https://bogomips.org/unicorn/)
* https://yhbt.net/unicorn-public/
* Ruby用のHTTPサーバ・アプリケーションサーバ
* プリフォーク型アーキテクチャ
    * マスタープロセスが複数のワーカープロセスを管理
    * 各ワーカーは1つのリクエストのみ処理（シングルスレッド）
* 特徴
    * シンプルで安定した設計
    * メモリ効率が良い（Copy-on-Write最適化）
    * Unixシグナルによる制御
    * ゼロダウンタイムデプロイ（USR2シグナル）
* 利点
    * メモリリークに強い（プロセス再起動で解決）
    * クラッシュ耐性（1つのワーカーがクラッシュしても他に影響なし）
    * スレッドセーフを考慮する必要がない
* 欠点
    * I/O待機時にプロセスがブロック
    * スレッド並行性を活用できない
    * リクエスト処理能力がプロセス数に依存
* 設定例
    * `config/unicorn.rb`で設定
    * ワーカー数、タイムアウト、ソケット設定など
* メンテナンス状況に課題
    * バグがありそう
    * [Handles array in http_response](https://github.com/Shopify/unicorn/pull/5)


### [pitchfork](https://github.com/Shopify/pitchfork)

* https://blog.studysapuri.jp/entry/2024-pitchfork-into-the-largest-rails-application-in-studysapuri
* https://scrapbox.io/ohbarye/pitchfork
* https://speakerdeck.com/riseshia/introducing-pitchfork-as-a-countermeasure-for-traffic-spikes
* https://github.com/Shopify/grpc_fork_safety

### Falcon

* [socketry/falcon](https://github.com/socketry/falcon)
* 非同期I/O（async I/O）ベースのWebサーバ・アプリケーションサーバ
* 作者はSamuel Williams(@ioquatix)
* Ruby 3.0+のFiber Schedulerを活用
* 特徴
    * 高性能な非同期I/O処理
    * HTTP/1.1、HTTP/2、WebSocketサポート
    * TLS（SSL）サポート
    * ファイルサービング機能
    * リバースプロキシ機能
    * Virtual Hostサポート
* アーキテクチャ
    * Fiber-based並行処理
    * イベントループベース
    * ノンブロッキングI/O
* パフォーマンス
    * 大量の同時接続に対応
    * I/Oバウンドなアプリケーションで高性能
    * メモリ効率が良い
* 使用場面
    * マイクロサービス
    * API server
    * リアルタイムアプリケーション
    * 高負荷Webアプリケーション
* 注意点
    * Ruby 3.0以降が必要
    * Fiber Schedulerに対応したgemが必要
    * まだ比較的新しい技術

### Itsi

* [https://itsi.fyi/](https://itsi.fyi/)
* https://www.reddit.com/r/ruby/comments/1k9cptd/itsi_a_fast_new_ruby_rack_server_reverse_proxy/
* Rust製
* アプリケーションサーバではあるが、HTTPサーバとしての機能もある
    * Reverse Proxy、File Server、自動で証明書の設定(Let’s Encrypt certificates)
* gRPCサーバ
* Endpoint


### other

* [bruno-/fiber_scheduler_list?tab=readme-ov-file](https://github.com/bruno-/fiber_scheduler_list?tab=readme-ov-file)
* [Ruby Fiber Scheduler \- Bruno Sutic](https://brunosutic.com/blog/ruby-fiber-scheduler)
