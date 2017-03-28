# libqtwebkit-qupzillaplugins

Deb package for qtwebkit-plugins library created for QupZilla: https://github.com/QupZilla/qtwebkit-plugins

## Requirements

Install required packages:

    sudo apt-get install qt5-default libqt5webkit5-dev libhunspell-dev

## Build the .so library

Enter the package folder:

    cd libqtwebkit-qupzillaplugins-1.0

Update the `Makefile`:

    qmake

Then build with:

    make

Install with:

    sudo make install


## Test

You can build a `pyqt` simple browser and test the spell checker plugin typying any mispelled word in the text input.

Of course, a requirement is `python3-hunspell` and related dictionaries.

For Qt4:

```python
#!/usr/bin/env python3
import sys
from PyQt4.QtGui import QApplication
from PyQt4.QtCore import QUrl
from PyQt4.QtWebKit import QWebView

if __name__ == '__main__':
    app = QApplication(sys.argv)
    view = QWebView()
    view.load(QUrl('http://www.google.com'))
    app.exec_()
```

and the same version for Qt5:

```python
#!/usr/bin/env python3
import sys
from PyQt5.QtWidgets import QApplication
from PyQt5.QtCore import QUrl
from PyQt5.QtWebKitWidgets import QWebView

if __name__ == '__main__':
    app = QApplication(sys.argv)
    view = QWebView()
    view.load(QUrl('http://www.google.com'))
    app.exec_()
```
