# Puma

* Pumaといえばスロークライアント対策が出来ているでおなじみ(?)
* Pumaは[Reactorパターン](https://en.wikipedia.org/wiki/Reactor_pattern)を使用してスロークライアント対策をしている
  * 不完全なリクエストを受け取った場合、完全になるまで待機し、完全にバッファリングされるまでワーカースレッドに処理を渡さないようにしている
* Puma 4系からnior4を導入して、`epoll`や`kqueue`を使用したイベント駆動型アプローチを行うようになっている
* 詳細は、[Architecture](https://github.com/puma/puma/blob/master/docs/architecture.md)を見て下さい
