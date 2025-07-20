# nio4rとio-event

* Rubyで非同期I/O用のライブラリといえば、[nio4r](https://github.com/socketry/nio4r)
* 元々、asyncもnio4rを使っていたが、nior4は[libev](https://github.com/enki/libev)を使っている影響で少し制約があったらしい
* そこで、よりfiber schedulerで使いやすくする為、gemを自作したとのこと
  * io-eventでは、CのAPI(epollやkqueue)を直接操作している

