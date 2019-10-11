---
layout: post
title:  "happy coding diary"
date:   2019-10-04 00:00:00 +0800
categories: Default
tags: test Test
comments: 1
---
## <strong>2019-10-04 이벤트처리(key press event)</strong>
#### 1.코드 간단설명
##### + 키를 재정의 해주어서 키를 눌렀을떄 창크게 작게 닫기를 실행
#### 2.핵심 줄
##### + 14~20줄
#### 코드 설명
###### 10~12줄-창이 생길위치,크기  | 14~20-키를 눌렀을때 일어날 일 정의
#### 실행화면

![image](https://gyubo.github.io/assets/res/post image/image.PNG)

{% highlight ruby %}
import sys
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *

class MyWindow(QWidget):
    def __init__(self):
        super().__init__()
        self.initUI()

    def initUI(self):
        self.setWindowTitle('SWH Academy Window.')
        self.setGeometry(300, 300, 300, 200)

    def keyPressEvent(self, e):
        if e.key() == Qt.Key_F:
            self.showFullScreen()
        elif e.key() == Qt.Key_N:
            self.showNormal()
        elif e.key() == Qt.Key_0:
            self.close()
        
if __name__ == "__main__":
    app = QApplication(sys.argv)
    window = MyWindow()
    window.show()
    sys.exit(app.exec_())

{% endhighlight %}
##### 일기&요약
오늘은 저번시간에 이어 PYQT를했다. 계속 창을 디자인 하고있는데 이번에는 키(키보드)를 누름에따라 작동하게하는 함수였다. 원하는 키를 이용해서 간단하고 눈에보이는 코드를 만들수 있으면 좋을거같다.

 