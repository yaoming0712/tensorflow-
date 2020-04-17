# Tensorflow-gpu測試
## 先進入創建的環境(tensorflow-gpu)
開啟 Anaconda prompt
```
#激活安裝tensorflow的環境
activate tensorflow-gpu

#安裝ipykernel 為了用jupyter
conda install ipykernel

#安裝keras
pip install keras==2.2.0

#建立新kernel 在jupyter
python -m ipykernel install --user --name myenv --display-name "Python (tensorflow-gpu)"
```

## 開啟 jupyter
new 處會有新的kernel選
![](https://i.imgur.com/vA5YHqE.png)

## 測試
```
import tensorflow as tf 

import keras 

import matplotlib.pyplot as plt

```

matplotlib 報錯 No module named 'matplotlib'
新增matplotlib 
![](https://i.imgur.com/Q0Qur3W.png)


輸入code 測試

```
#Creates a graph. 
a = tf.constant([1.0, 2.0, 3.0, 4.0, 5.0, 6.0], shape=[2, 3], name='a') 
b = tf.constant([1.0, 2.0, 3.0, 4.0, 5.0, 6.0], shape=[3, 2], name='b') 
c = tf.matmul(a, b) 
# Creates a session with log_device_placement set to True. 
sess = tf.Session(config=tf.ConfigProto(log_device_placement=True)) 
# Runs the op. 
print(sess.run(c))
```
回去cmd上查看 如果有類似下圖即算完成
![](https://i.imgur.com/J4R1s3M.png)
