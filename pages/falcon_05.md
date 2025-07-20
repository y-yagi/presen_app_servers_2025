# Falcon

* Async gemはノンブロッキングI/Oをサポートしているいため、Falconの処理もノンブロッキングI/Oをサポート
    * [socketry/io-event](https://github.com/socketry/io-event)を使用している
* I/O周りの対応は一番頑張っている印象
* I/Oバウンドなアプリケーションで高性能になりそう
* Streaming処理のサポートも手厚いよ
    * [Streaming Rack with Falcon](https://www.codeotaku.com/journal/2024-11/streaming-rack/index)
