### 库
- 控制流和主要设置库 `QApplication`
- 自定义信号库 `pyqt5Signal`
- 纯粹的普通窗口 `QWidget`
	- 包含菜单栏的窗口 `QMainWindow`
	- 对话框 `QDialog`
#### 布局
- #垂直布局 `QVBoxLayout` 上下布局
- #水平布局 `QHBoxLayout` 左右布局
- #组 `QGroupBox` 把一些控件放在一起
- #抽屉布局 `QStackLayout` 一次只显示其中一个


#### 控件
- #按钮 `QPushButton` 显示字的按钮
- #文本框 `QLabel` 显示字的文本输入框
- #单选框 `QRadioButton` 只能选一个

### 变量
### 方法 记得加上self
括号里的放在前面里
- 创建一个类，继承QWidget库 `class 类名(QWidget)`
	- 定义一个__init__方法，初始化UI `super().__init__()`
- 声明一个信号 `信号变量名 = pyqtSignal(信号类型)`
- 设置一个窗口 `窗口变量名称 = QWidget()`
- 设置可变窗口大小 `.resize(x, y)`
- 设置固定窗口大小 `.setFixedSize(x, y)`
- 设置窗口标题 `.setWindowTitle("窗口标题")`
- 创建线程 `self.线程名称 = 类名称()`
	- 开始线程 `self.线程名称.strat()`
	- 在开始定义一个类作为线程 `class 类名称(QThread);`
- 添加事件，绑定信息和槽函数 `对象(控件)名称.信号.connect(槽函数)`
	- 获取文本`text`
	- 单击`clicked`
	- 自定义信号 `self.需要发射的信号.emit(参数)`  调用了槽函数，把参数给到
> 方法名称不用加括号，因为不是直接调用
- 设置引索值 `.setCurrentIndex(值)`
- 创建组 `组变量名称 = QGroupBox("组名称")`
- 设置水平/垂直布局 `布局变量名称 = QHBoxLayout()/QVBoxLayout()`
- 添加抽屉布局 `布局变量名称 = QStackLayout()`
- 添加到布局器 `布局变量名称.addWidget(控件变量名称)`
- 把布局添加到组中 `组变量名称.setLayout(布局变量名称)`
- 让当前窗口使用布局 `.setLayout(布局变量名称)`
>布局和组可以相互嵌套
- 创建一个含参数对象 `程序名 = QApplication(sys.argv)`
- 把窗口作为类的一个子类 `窗口变量名 = 类名()`
- 自动刷新程序 `程序名.exec()`

### 控件
- 定义按钮 `按钮变量名称 = QPushButton("显示内容")`
- 定义文本框 `文本框变量名称 = QLineEdit()`
- 设置文本框背景文字 `文本框变量名称.setPlaceholderText("显示内容")`
- 定义单选框 `单选框变量名称 = QRadioButton("显示内容")`
- 添加"弹簧" `布局变量名称.addStretch(比例)`

### 多线程
- 