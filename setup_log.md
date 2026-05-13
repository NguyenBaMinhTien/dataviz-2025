Lỗi 1: ModuleNotFoundError

Cell In[1], line 3
      1 import pandas as pd
      2 import numpy as np
----> 3 import maplotlib.pyplot as plt
      4 import seaborn as sb

ModuleNotFoundError: No module named 'maplotlib'


Lỗi 2: Value Error
Cell In[1], line 4
      1 import pandas as pd
      3 # Dữ liệu điểm thi của sinh viên 3 lớp
----> 4 df_diem = pd.DataFrame({
      5     'lop' : ['A', 'A', 'B', 'B', 'C', 'C'],
      6     'ten' : ['An', 'Bình', 'Chi', 'Dung', 'Em', 'Phúc', 'Giang'],
      7     'diem_toan' : [8.5, 7.0, 9.0, 6.5, 8.0, 7.5, 9.5],
      8     'diem_ly' : [7.0, 8.0, 6.0, 9.0, 7.5, 8.5, 6.5,]
      9 })
     11 #Tính điểm toán trung bình theo từng lớp
     12 tb_toan = df_diem.groupby('lop')['diem_toan'].mean()
ValueError: All arrays must be of the same length