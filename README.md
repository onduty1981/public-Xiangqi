# 使用手册

## 1 引擎

### 1.1 配置引擎
+ 点击引擎菜单，引擎管理，添加引擎，打开文件选择对话框，选择引擎文件（本程序支持加载uci和ucci协议的中国象棋引擎）。  
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/1.png?raw=true)

+ 等待一两秒之后，引擎读取成功，自动显示引擎路径、引擎名称（如加载多个引擎，建议设置不同名称）、协议等基本信息。如果引擎有提供自定义的可配置选项，也会在右边列表中显示。用户可以手动修改这些引擎配置，不过需要注意输入字符格式为英文半角，且不可含有特殊字符、多余空格等。  
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/2.png?raw=true)

+ 部分引擎支持可配置棋规、nnue权重文件等，你也可以在右边列表中编辑（配置后需重新加载引擎，或重启软件生效）。引擎的自定义配置及设值说明，可以参看引擎输出的相关信息。如果你不知道某个配置的具体含义，建议不要修改，保持默认即可。  
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/3.png?raw=true)

+ 例如皮卡鱼引擎加载后默认是亚规，如需配置成中规，在引擎配置选项里找到Repetition Rule，设置为ChineseRule，保存之后重启或重载引擎即可。
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/16.png?raw=true)

### 1.2 加载引擎
+ 在主界面的引擎列表中选择你要使用的引擎，配置cpu线程数量，哈希表大小。  
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/4.png?raw=true)

### 1.3 引擎走棋
+ 主界面工具栏中，提供引擎执黑、引擎执红、分析模式等功能。按下对应按钮，界面会调用引擎进行计算，并在右边显示引擎的思考细节信息。如需取消引擎走棋，再次点击按钮即可，按钮恢复成未选中状态。  
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/5.png?raw=true)

### 1.4 引擎时间设置
+ 点击引擎菜单，时间设置，可以设置引擎的思考时间及出招延迟等。
	+ 固定时间：引擎搜索固定的时间之后出招，配置单位为毫秒（1秒=1000毫秒）。
	+ 固定深度：引擎搜索到固定的层数之后出招。
	+ 引擎出招延迟：引擎搜到结果后延迟多长时间出招。该配置是一个时间范围A-B，要求A≤B。程序会随机取范围内的一个时间。如果配置为0-0，则不开启延迟。
	+ 库招出招延迟：库招搜到结果后延迟多长时间出招。该配置是一个时间范围A-B，要求A≤B。程序会随机取范围内的一个时间。如果配置为0-0，则不开启延迟。  
	  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/6.png?raw=true)

+ 你也可以在棋盘上右键，对局时间，快速选择引擎的固定搜索时间。  
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/7.png?raw=true)

## 2 连线
### 2.1 使用连线
+ 点击主界面工具栏中的连线按钮，鼠标变成选择状态，然后再点击要连线的目标棋盘。等待识别目标棋盘成功，即可开始连线。如需取消连线，再次点击连线按钮即可，按钮恢复成未选中状态。  
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/8.png?raw=true)

+ Linux系统连线依赖`xdotool`实现，所以连线前确保已经安装该工具，否则连线功能不可用。点击连线按钮，然后在3秒内点击目标棋盘，等待识别目标棋盘成功，即可开始连线。
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/17.png?raw=true)

+ Macos系统连线操作步骤也类似，不过需要注意打开相关系统授权，否则连线会失败。连线时点击连线按钮，然后在3秒内点击目标棋盘，等待识别目标棋盘成功，即可开始连线。
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/18.png?raw=true)

+ 连线支持自动走棋和观战两种模式，在连线前要先选择好想要的模式。自动走棋模式下会自动在目标平台上替我方走棋（连线之前先确认是轮到我方行棋），而观战模式不会自动走棋，只是对局面进行分析，输出思考细节。  
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/9.png?raw=true)

### 2.2 连线设置
+ 点击连线菜单，连线参数，打开连线设置对话框，可以对连线程序进行设置。
	+ 鼠标点击间隔：设置自动走棋时鼠标左键点击（从按下到释放）的时间间隔，单位毫秒。
	+ 鼠标走子间隔：设置自动走棋时鼠标点击棋子原始位置到点击目标位置的时间间隔，单位毫秒。
	+ 识别扫描间隔：设置连线程序每隔多久扫描一次目标棋盘，单位毫秒。如电脑性能较好，可以设置更小值，连线识别会更快。
	+ 识别线程数量：设置用于连线识别的线程数量，如电脑性能较好，可以设置更大的线程数，连线识别会更快。  
	  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/10.png?raw=true)

### 2.3 后台模式
+ 点击连线菜单，再点击勾选后台模式。该模式下连线不会占用桌面和鼠标，目标棋盘可以被其他窗口遮挡，鼠标也可以做其他事不会影响。这是一种效率较高也更友好的连线模式，缺点是并非所有平台都支持（如果该模式下连线识别失败或者不自动走棋，说明不支持）。
+ 如果后台模式不支持，则需要取消勾选该选项，连线程序则以前台模式工作。前台模式下需要保持目标平台不被其他窗口遮挡，且自动走棋时会占用鼠标。该模式理论上可以连线任何平台，只要目标棋子是清晰可识别的。  
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/11.png?raw=true)

### 2.4 动画确认
+ 如果目标平台棋子移动是具有过渡动画的（棋子从A点沿着A-B路径逐渐移动到B点），你需要开启动画确认，否则可能会出现连线失败或识别错误。
+ 如果目标平台棋子移动是闪现方式（棋子从A点消失然后直接在B点出现），你可以关闭动画确认，关闭动画确认后连线效率会更高，识别也更快。  
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/12.png?raw=true)

## 3 开局库
### 3.1 使用开局库
+ 点击主界面工具栏的启用库招按钮，程序则会优先使用开局库的招法来出招。如需关闭开局库，再次点击启用库招按钮即可，按钮恢复成未选中状态。  
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/15.png?raw=true)

### 3.2 库招设置
+ 点击开局库菜单，库招设置，打开设置对话框，可以对开局库出招进行一些设置。
	+ 开启云库，程序会连接云库http://www.chessdb.cn/chessdb.php 查询局面信息。超时时间设置云库查询多久无响应后自动断开，单位毫秒。
	+ 只使用云残局库：只使用云库的残局局面信息。
	+ 优先使用本地库：如果同时配置了本地库并开启了云库，优先从本地库中搜索局面。
	+ 库招选择策略：
		+ 取最高分：选择分数最高的招法。
		+ 取最高胜率：选择胜率最高的招法。
		+ 正分数随机：从分数大于0的招法中随机选择。
		+ 完全随机：从所有招法中随机选择。
	+ 脱谱步数：设置多少回合后不再用库招，只使用引擎计算。  
	  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/13.png?raw=true)

### 3.3 本地库管理
+ 点击开局库菜单，本地库管理，打开本地库设置对话框，可以添加、删除本地库，以及调整本地库的顺序（程序会优先搜索排在前面的库）。  
  ![](https://github.com/sojourners/public-Xiangqi/blob/master/assets/14.png?raw=true)

## 4 界面设置
### 4.1 棋步提示
+ 点击设置菜单，开启棋步提示，引擎计算输出结果时会在棋盘上显示走棋提示的箭头。

### 4.2 走棋音效
+ 点击设置菜单，开启走棋音效，走子时会有吃、将、移动等音效。

### 4.3 显示状态栏
+ 点击设置菜单，勾选显示状态栏，状态栏在棋盘下方，可显示计算深度、时间、思考细节等信息。

### 4.4 棋盘样式
+ 本程序提供默认和红黑两种主题样式，默认样式是程序内部实现的一种主题，红黑样式是采用图片棋盘棋子绘制的主题，用户可以通过替换目录./ui下的资源来自定义自己喜欢的主题。

### 4.5 棋盘大小
+ 本程序提供了大棋盘、超大棋盘、中棋盘、小棋盘多种棋盘大小，以供不同场景使用需要。