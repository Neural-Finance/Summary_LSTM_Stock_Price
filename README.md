# Brief View
### <center> A review for stock time series problem based on LSTM (Tensorflow)</center>

### <center> Alex Fang </center>

### <center> THU, Computer Science Department, E-mail: alex.holla@foxmail.com </center>

**I just post several pictures, you can download the html file to read the whole article. I hope it can save you a lot of time, because you may have no need to read other blog articles...If you like it, please give me a start. If you have interest in this field, please feel free to contact me.**

**Abstracts:** Many blog writers have published the articles about using LSTM to solve stock time series problem. But there are several common shortcomings. In this article, I will talk about the details both in experiments and programmings. And I want to use it in equity trading. If you both have some experience and interest in this fields, please feel free to contact me.

1.They just show the codes and not do individual experiments to show the differences. Some peopel did so, because they don't know it clearly. Some people did so just to save time. But it's not good for new beginner. **Many new beginner will just read it and it's hard for them to start their first projects.**

2.Many of them ignore some **experiments details**, to be honest, details is everything, especially in deep learning field. 

3.Some of them ignores the **programming details**, here I mean the specific settings in tensorflow. If you use keras or caffe, I strongly reconmmand you to use tensorflow or pytorch,which push you to figure out the exact network details.

## 1.Easy tasks with low level of noise

At the very begining, let's try to solve a very simple problem. Which is to use LSTM learn the transformation from sin(x) to cos(x). This question exactly has no noise at all. So we don't need to think about the overfitting problem. Let's just write a write LSTM structure to deal with it.

#data
import tensorflow as tf
import numpy as np
import matplotlib.pyplot as plt

steps = np.linspace(0, np.pi*2, 100, dtype=np.float32)
x_np = np.sin(steps)
y_np = np.cos(steps)
plt.plot(steps, y_np, 'r-', label='target (cos)')
plt.plot(steps, x_np, 'b-', label='input (sin)')
plt.legend(loc='best')
plt.show()

![image](https://github.com/Blabala/Summary_LSTM_Stock_Price/blob/master/pictures/1.PNG)
![image](https://github.com/Blabala/Summary_LSTM_Stock_Price/blob/master/pictures/2.PNG)
![image](https://github.com/Blabala/Summary_LSTM_Stock_Price/blob/master/pictures/3.PNG)
![image](https://github.com/Blabala/Summary_LSTM_Stock_Price/blob/master/pictures/4.PNG)
