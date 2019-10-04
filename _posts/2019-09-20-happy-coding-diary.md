---
layout: post
title:  "happy coding diary"
date:   2019-10-04 00:00:00 +0800
categories: Default
tags: test Test
comments: 1
---
## 2019-10-04 이벤트처리
#### 1.코드 간단설명
##### + 키를 재정의 해주어서 키를 눌렀을떄 창크게 작게 닫기를 실행
#### 2.핵심 줄
##### + 14~20줄에서 함수의 역할

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

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
