The dataset is derived from sampling Modbus commands in RS485 fieldbus networks, where the communication baud rate is 9.6k bit/s and the sampling frequency is set to 100 KS/s.  In the dataset, 2000 signals are stored as normal data and abnormal data based on different intrusion devices in `.xlsx` format, respectively, with a total size of 170 MB.

 

In this dataset, the attack scenario is the unauthorized insertion of a silent intrusion device into the fieldbus, thereby eavesdropping communication data. The data in the `DifferentIntrusion_data` folder is sampled from a real distribution cabinet under a constant temperature of 21℃. The data in the `DifferentTemperature_data` folder is sampled from an RS485 testbed inside the temperature-controlled box, where data sampling is conducted every 3℃ from 0℃ to 54℃.



The data in both folders is divided into *BV signal* and *CV signal*, where the *BV signal* is the fail-safe biasing voltage signal and the *CV signal* is the command voltage signal from the client. The data in the `Normal` folder is sampled when there are no external intrusion devices in the fieldbus network. In contrast, the data in the `Abnormal` folder is sampled when intrusion devices made by ZLAN, MOXA, and KonNaD are attached to the fieldbus network, respectively.

 

The following are descriptive examples of how to load '.xlsx' file data using Python and MATLAB, respectively.

> **Python**

- Step 1: Please ensure that the ‘pandas’ and ‘matplotlib’ libraries are installed in your Python environment. You can use `pip install pandas matplotlib` to install them.

- Step 2: Load data from the `.xlsx` file and plot the data following `readfile.py`.

```python
import pandas as pd
import matplotlib.pyplot as plt
file_path = 'DifferentIntrusion_data/BV_signal/Abnormal/KonNad/BV_KonNaD_Part1.xlsx' # Your file path
data = pd.read_excel(file_path)
plt.plot(data)
plt.show()
```

Then you can obtain 200 abnormal *BV signal* samples when the intrusion device made by KonNaD is attached to the fieldbus.

 

> **Matlab**

You can use the ‘xlsread’ function to read data from a specified file.

```matlab
clc;clear;
filePath = 'DifferentTemperature_data/CV_signal/Abnormal/KonNad/CV_KonNaD_3.xlsx';%Your file path
[data,~,~] = xlsread(filePath);
plot(data)
```

Then you can obtain 200 abnormal *CV signal* samples when the intrusion device made by KonNaD is attached to the fieldbus at 3℃.

 

If you need any further information, please feel free to contact us.

 

Yang Liu

Associate Professor

E-mail: yangliu@xjtu.edu.cn

Ministry of Education Key Lab for Intelligent Networks and Network Security (MOEKLINNS), Xi'an Jiaotong University, Xi'an, Shaanxi, China 710049

 