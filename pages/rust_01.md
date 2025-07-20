# 余談：Rustで作るRuby拡張

* 過去色々ライブラリがあったが、現在は[rb-sys](https://github.com/oxidize-rb/rb-sys/) + [Magnus](https://github.com/matsadler/magnus)がデファクトという印象
    * `rb-sys`が低レベルAPI(CのAPIから自動生成されたコードがベース)で、`magnus`はそれを便利に使えるようにしたライブラリ
    * `bundler gem --ext=rust`でgemを生成した場合もこの組み合わせ
* 色々ハマり所があるので注意は必要
    * 参考：[Rustで作るtree\-sitterパーサーのRubyバインディング \- Speaker Deck](https://speakerdeck.com/joker1007/rustdezuo-rutree-sitterpasanorubybaindeingu)
    * 個人的には、[GVLで困った](https://github.com/matsadler/magnus/issues/129)
