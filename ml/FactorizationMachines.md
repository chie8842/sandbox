# Factorization Machines

## Thesis
[Factorization Machines](https://www.csie.ntu.edu.tw/~b97053/paper/Rendle2010FM.pdf)

### Abstract
Factorization Machines(FM): SVMとFactorization Modelのコンビネーション  
FMはSVM同様汎用的な予測器であるが、一方でSVMとは対称的に、   
因数分解されたパラメータを用いて変数間の相互作用させる。  
これにより、SVMでは失敗するような非常に疎な場合の問題に対しても相互作用を予想することができる。  
FMのモデル方程式は線形な時間で計算されるため、直接optimizeすることができる。
non linearなSVMとは異なり二重の変換を行う必要がなく、  
support vectorを使うことなく直接モデルパラメータを推定することができる。

Factorization Modelには、Matrix Factorization,  並列ファクタ分析、SVD++, PITF, FPMCのような  
特別なモデルなどのたくさんの異なるモデルがある。  
これらのモデルの欠点は、一般的な予測タスクには適用できず、特殊な入力データでのみ機能することである。  
また、FMに関する専門知識のないユーザであっても簡単に適用することができる。

