概要
ここでは、TensorFlowにおけるGraph Attention Network（GAT）レイヤーの実装と、最小限の実行例（Coraデータセット上）を提供します。リポジトリは以下のように構成されています。

data/ Coraに必要なデータセットファイル。
models/ GATネットワークの実装(gat.py)が含まれています。
pre_trained/ 学習済みのCoraモデル(テストセットで84.4%の精度を達成)が含まれています。
utils/ には以下のものが含まれています。
アテンションヘッドの実装と、実験的なスパースバージョン(lays.py)。
前処理サブルーチン(process.py)。
PPIベンチマークの前処理ユーティリティ(process_ppi.py)。
最後に、execute_cora.pyで上記をまとめ、Coraのフルトレーニングを実行します。

スパースバージョン
実験的なスパースバージョンもあり、バッチサイズが1の時のみ動作します。スパースモデルはmodels/sp_gat.pyにあります。

スパースモデルは、execute_cora_sparse.pyを使用して、Cora上でフルトレーニングを実行することができます。

依存性
このスクリプトは、Python 3.5.2、以下のパッケージ（と依存関係）がインストールされた環境で動作確認をしています。

numpy==1.14.1
scipy==1.0.0
ネットワークx==2.1
tensorflow-gpu==1.6.0
また、CUDA 9.0とcuDNN 7が使用されています。

参考
GATモデルを研究において活用する場合は、原稿中に以下を引用してください。

article{
  velickovic2018graph,
  title="{グラフアテンションネットワーク}",
  author={Veli{Camerav{c}}kovi{'{c}}, Petar and Cucurull, Guillem and Casanova, Arantxa and Romero, Adriana and Li{Camera`{o}}, Pietro and Bengio, Yoshua}}。
  journal={International Conference on Learning Representations},
  year={2018},
  url={https://openreview.net/forum?id=rJXMpikCZ},
  note={ポスターとして受理されました},
}
GATや一般的なグラフ表現学習を始めるには、Aleksa Gordićによるpytorch-GATリポジトリを強くお勧めします。このリポジトリには、帰納的（PPI）例も含まれています。

GATは、グラフ表現学習のための一般的な手法で、事実上すべての標準的なGRLライブラリに最適化された実装が含まれています。

[PyTorch] PyTorch Geometric (幾何学的)
[PyTorch/TensorFlow] ディープグラフライブラリ
[TensorFlow】 Spektral
[JAX】 jraph
これらの実装は、より簡単にテストされているので、どちらかを使用することをお勧めします（あなたの好きなフレームワークによって）。

リリース後の早い段階で、様々なフレームワークへのGATモデルの非公式な移植が2つ、すぐに現れました。GATレイヤーのアーリーアダプターである開発者の努力に敬意を表し、ここにポインタを置いておきます。

[Keras] keras-gat, Daniele Grattarolaによって開発されました。
[PyTorch] pyGAT, Diego Antogniniによって開発されました。
ライセンス
MIT

www.DeepL.com/Translator（無料版）で翻訳しました。