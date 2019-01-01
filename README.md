## Keras MNIST TensorFlowJs

学習済みのモデルを TensorFlow.js で読み込み，ブラウザ上で Prediction してみる

## MNIST 学習済みモデルを作成
### Run a TensorFlow container
[tensorflow](https://www.tensorflow.org/install/)
```
docker pull tensorflow/tensorflow                  # Download latest image
docker run -it -p 8888:8888 tensorflow/tensorflow  # Start a Jupyter notebook server
```

### Jupyter Notebook
localhost:8888 へアクセス

keras.py をコピーし、RUN する

[mnist_cnn](https://github.com/keras-team/keras/blob/master/examples/mnist_cnn.py)

model_mnist_cnn.h5 をダウンロード

## 学習モデルを TensorFlowJs に変換
```
pip install tensorflowjs
tensorflowjs_converter --input_format keras \
                       model_mnist_cnn.h5 \
                       model_mnist_cnn.json
```

## ブラウザで手書き文字を分類
ローカルで起動
```
python -m SimpleHTTPServer 8888
```
