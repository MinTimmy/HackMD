###### tags: `PyQt`

# Header
```python=
import sys
from PyQt5.QtGui import *
from PyQt5.QtCore import *
from PyQt5.QtWidgets import *
```

# main()
```python=
if __name__ == "__main__": # 當執行這個檔案的時候，__name__ 被賦予 "__main__" 這個字串，如果只是單純將檔案引用 （import），則 __name__ 會等於檔案名稱
    app = QApplication(sys.argv) # 創建 QApplication，注意括號內 sys.argv 一定要寫，才能將檔案名稱（argv[0]）傳給 QApplication

    ex = Widget() # 創建 QWidget
    ex.resize(400, 280) # 調整視窗大小
    ex.setWindowTitle('Canvas') # 設定視窗名稱
    ex.setWindowIcon(QIcon('404.png')) # 設定視窗 Icon
    ex.show() # 顯示視窗，一定要寫，不然執行續會卡住（app 開始執行了，但沒有顯示視窗，所以也無從點選叉叉）

    sys.exit(app.exec_()) # 執行 QApplication，一定要寫，不然視窗不會定格在螢幕上，只會快速出現視窗，執行完程式碼，然後消失
```



# Canvas

## Call Painter
```python=
    painter = QPainter(self) # 呼叫畫筆
    painter.setPen(Qt.red) # 把畫筆顏色變紅色
```
## Draw Line
```python=
    painter.drawLine(10, 10, 100, 140) # 畫線，方法為 (start_x, start_y, end_x, end_y)
```

## Draw Rectangle
```python=
    painter.drawRect(120, 10, 80, 80) # 畫長方形，方法為 (start_x, start_y, end_x, end_y)
```

## Draw Rounded Rectangle
```python=
    rectf = QRectF(230.0, 10.0, 80.0, 80.0) # 畫圓角長方形，方法為 (start_x, start_y, end_x, end_y)
    painter.drawRoundedRect(rectf, 20, 20)
```

## Draw Pologon
```python=
    p2 = [QPoint(120, 110), QPoint(220, 110), QPoint(220, 190)] # 畫多邊形，一個 QPoint 代表一個點
    painter.drawPolygon(QPolygon(p2))
```

