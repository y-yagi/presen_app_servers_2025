# `async` gem

* 名前の通り非同期処理用ライブラリ
  * ノンブロッキングにI/Oの為の処理もある
* 先にも説明した通り、Fiber Schdulerが実装されており、非同期処理はFiberで行っている
* I/O周りの処理には、[socketry/io-event](https://github.com/socketry/io-event)を使用している
