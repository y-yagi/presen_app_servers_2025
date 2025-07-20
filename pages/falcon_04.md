# Fiber

* コンテキストを切り替えるために、"Fiber Scheduler"を実装する必要がある
    * Ruby本体には、この"Fiber Scheduler"の実装は無い
* Falconでは[socketry/async](https://github.com/socketry/async)を使用
    * asyncが先にあって、非同期処理を実際のユースケースに当てはめるために、Falconを作ったという流れらしい
* 因みに、他にも"Fiber Scheduler"を実装したライブラリはある
    * 参考：[bruno-/fiber_scheduler_list](https://github.com/bruno-/fiber_scheduler_list)
