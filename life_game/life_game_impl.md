---
tags:
  - CS
---
```python
import numpy as np
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation

def update(frameNum, img, grid, N):
    newGrid = grid.copy()
    for i in range(N):
        for j in range(N):
            # 计算周围活细胞数量
            total = int((grid[i, (j-1)%N] + grid[i, (j+1)%N] +
                         grid[(i-1)%N, j] + grid[(i+1)%N, j] +
                         grid[(i-1)%N, (j-1)%N] + grid[(i-1)%N, (j+1)%N] +
                         grid[(i+1)%N, (j-1)%N] + grid[(i+1)%N, (j+1)%N])/255)
            # 应用生命游戏的规则``
            if grid[i, j]  == ON:
                if (total < 2) or (total > 3):
                    newGrid[i, j] = OFF
            else:
                if total == 3:
                    newGrid[i, j] = ON
    img.set_data(newGrid)
    grid[:] = newGrid[:]
    return img,

# 设置网格大小
N = 100
# 设置细胞状态
ON = 255  # 活细胞
OFF = 0  # 死细胞
# 创建网格
grid = np.random.choice([ON, OFF], N*N, p=[0.2, 0.8]).reshape(N, N)

fig, ax = plt.subplots()
img = ax.imshow(grid, interpolation='nearest')
ani = FuncAnimation(fig, update, fargs=(img, grid, N, ),
                    frames = 10,
                    interval=50,
                    save_count=50)

plt.show()

```