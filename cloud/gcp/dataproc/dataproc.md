デフォルトだとシステムのpythonバージョンは2.7.9
Sparkで使うPythonバージョンとしては、python3.4.2も使える。

初期化操作で以下のようにする。
初期化操作
* 以下のスクリプト
 ```
# setting_python3.sh
#!/bin/bash
echo "export PYSPARK_PYTHON=python3" | tee -a  /etc/profile.d/spark_config.sh  /etc/*bashrc
echo "export PYTHONHASHSEED=123" | tee -a  /etc/profile.d/spark_config.sh  /etc/*bashrc /usr/lib/spark/conf/spark-env.sh
source ~/.bashrc

 ```
* https://github.com/GoogleCloudPlatform/dataproc-initialization-actions
をdataproc_init_scriptsにおく

gs://dataproc_init_scripts/dataproc-initialization-actions-master/jupyter/jupyter.sh
gs://dataproc_init_scripts/dataproc-initialization-actions-master/conda/bootstrap-conda.sh
gs://dataproc_init_scripts/dataproc-initialization-actions-master/conda/install-conda-env.sh
gs://dataproc_init_scripts/setting_python3.sh

## パッケージ追加
conda install pandas numpy matplotlib scikit-learn
/opt/conda/bin/pip install --upgrade pip
sudo /opt/conda/bin/pip install plotly cufflinks

## ポートフォワード
```
gcloud compute ssh --zone=asia-northeast1-a \
  --ssh-flag="-D" --ssh-flag="10000" --ssh-flag="-N" "cluster-etltest-m"
```
さらに--ssh-flag="-n" 、末尾に&を追加するとバックグラウンドで動作する。

```
/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome \
"http://<cluster-name>-m:8123" \
    --proxy-server="socks5://localhost:10000" \
    --host-resolver-rules="MAP * 0.0.0.0 , EXCLUDE localhost" \
    --user-data-dir=/tmp/
```
## 各サービスポート

|ウェブ UI |ポート |URL|
|----------|-------|---|
|YARN ResourceManager |8088 |http://master-host-name:8088|
|HDFS NameNode |50070 |http://master-host-name:50070|
