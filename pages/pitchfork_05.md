# Client Side Fork

* Reforkingは当然クライアント側でForkを行うのだが、世の中には"Fork Safe"じゃないライブラリがある
    * byroot氏のblogで説明がある通り、grpc gemがそうだった(古いgrpc gemはまだそう)
    * grpc gemを使っていてPitchforkの使用を検討している場合、[Shopify/grpc_fork_safety](https://github.com/Shopify/grpc_fork_safety) も合わせてチェックしてね
* 他にも、[libvips](https://github.com/libvips/libvips/discussions/3577)もそうらしい
