# Learning Log — Bài 01

## Lỗi 1: Syntax error khi tạo numpy array
**Code bị lỗi:**
# 1. Phụ nữ có tỉ lệ sống sót cao hơn đàn ông không?
ti_le_gioi_tinh = df.groupby('sex)['survived'].mean()
print("Tỉ lệ sống sót theo giới tính: ")
print(ti_le_gioi_tinh)

**Thông báo lỗi:**
Cell In[25], line 2
    ti_le_gioi_tinh = df.groupby('sex)['survived'].mean()
                                        ^
SyntaxError: invalid syntax

**Nguyên nhân:** Gõ nhanh hay bỏ sót dấu `,` giữa các phần tử

**Bài học:**
- `np.array()` — ngoặc tròn bên ngoài, ngoặc vuông bên trong
- Mỗi phần tử cách nhau bằng dấu `,`



## Lỗi 2: Gọi sai hàm sb.load_dataset() với đường dẫn file
**Code bị lỗi:**
import pandas as pd
import numpy as np 
import matplotlib.pyplot as plt
import seaborn as sb

df = sb.load_dataset('/Users/nguyentien/Documents/dataset_Titanic.csv')
df.head()

**Thông báo lỗi:**
ValueError                                Traceback (most recent call last)
Cell In[27], line 6
      3 import matplotlib.pyplot as plt
      4 import seaborn as sb
----> 6 df = sb.load_dataset('/Users/nguyentien/Documents/dataset_Titanic.csv')
      7 df.head()

File ~/Library/Python/3.9/lib/python/site-packages/seaborn/utils.py:573, in load_dataset(name, cache, data_home, **kws)
    571 if not os.path.exists(cache_path):
    572     if name not in get_dataset_names():
--> 573         raise ValueError(f"'{name}' is not one of the example datasets.")
    574     urlretrieve(url, cache_path)
    575 full_path = cache_path

ValueError: '/Users/nguyentien/Documents/dataset_Titanic.csv' is not one of the example datasets.

**Nguyên nhân:** Nhầm 2 hàm khác nhau:
- `sb.load_dataset('titanic')` → chỉ nhận tên ngắn,
  tải dataset có sẵn của seaborn
- `pd.read_csv('đường/dẫn/file.csv')` → đọc file CSV trên máy

**Bài học:** Đọc kỹ docs trước khi dùng hàm mới —
`load_dataset` và `read_csv` trông giống nhau nhưng
hoàn toàn khác mục đích

## 3 câu tổng kết:
- **Khó nhất:** Hiểu khi nào dùng `merge` vs `groupby` — 
  dễ nhầm vì cả 2 đều liên quan đến nhiều cột.
  Sau khi thực hành mới hiểu: groupby để tính thống kê theo nhóm,
  merge để ghép 2 bảng lại với nhau.