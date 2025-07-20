# Client Side Fork

* Reforkingは当然クライアント側でForkを行うのだが、世の中には"Fork Safe"じゃないライブラリがある
    * byroot氏のblogで説明がある通り、grpc gemがそうだった
    * grpc gemを使っていてPitchforkの使用を検討している場合、[Shopify/grpc_fork_safety](https://github.com/Shopify/grpc_fork_safety) も合わせてチェックしてね
* 他にも、[libvips](https://github.com/libvips/libvips/discussions/3577)もそうらしい
* 詳細は、[Fork Safety](https://github.com/Shopify/pitchfork/blob/master/docs/FORK_SAFETY.md)を見てね
