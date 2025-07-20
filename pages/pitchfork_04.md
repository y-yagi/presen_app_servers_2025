# Reforking

* そこで、Pitchforkでは、リクエストを一定処理したworkerから更に子プロセスを生成し、それをworkerとして使用することで、より効率的にメモリを使用するようになっている(Copy-On-Write対象となるメモリが多くなるようにしている)
    * Shopifyでは、約30%メモリ使用量を削減出来たとのこと
    * [Effects of Pitchfork reforking on Shopify’s Monolith](https://railsatscale.com/2023-10-23-pitchfork-impact-on-shopify-monolith/)
* ちなみに、byroot氏のblogでも説明されているが、Pumaにも類似の機能がある
    * [Fork-Worker Cluster Mode (Experimental)](https://github.com/puma/puma/blob/master/docs/fork_worker.md)
