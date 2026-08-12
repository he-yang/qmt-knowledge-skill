# QMT新人上手教程

## 前言

在本教程中，我们将直奔主题，避免无关紧要的内容。我们的目标是确保您能够顺利完成QMT的初次安装和配置，并成功运行您的第一个策略。跟着教程的步骤走，我们会尽量确保在您首次使用过程中，减少遇到任何非预期问题的可能性。

教程将分为如下部分： ![](https://dict.thinktrader.net/assets/QMT新手教程大纲-d781f1ed.png)

## 一、注册申请

券商 QMT 与投研端的区别：

1.  券商 QMT 侧重于交易，使用需跟券商申请
2.  投研端侧重于策略研究，使用需在投研网站注册购买

### 券商 QMT 申请

券商 QMT 需要跟对应券商申请，每家券商有各自不同的要求，具体可参考： [券商支持 QMT 的列表（含资金门槛)](https://www.xuntou.net/forum.php?mod=viewthread&tid=232&extra=&user_code=e2M5nZ)

### 投研端购买

![](https://dict.thinktrader.net/assets/投研端_购买页面-1a47363e.png) 登录注册[投研网站](https://xuntou.net/#/productvip?id=e2M5nZ)，购买对应投研产品即可。

需注意的是，微信登录用户，一定要绑定手机号，设置好密码，这是客户端登录的基础。

## 二、下载安装

### 下载

#### 券商 QMT 的下载地址

开通权限后，可向自己的券商客户经理咨询。

#### 投研端的下载地址

![](https://dict.thinktrader.net/assets/投研端_下载页面-a6a49670.png)

登录[投研网站](https://xuntou.net/#/userInfo?id=e2M5nZ)后，在[用户中心](https://xuntou.net/#/userInfo?id=e2M5nZ)可以看到下载中心，在这里付费用户可以下载到**投研端正式版**，非付费用户将看到**试用版**，而且存在一定差异，不影响核心功能体验。

### 安装

> **提示**
>
> 视频安装教程[视频讲解](https://dict.thinktrader.net/videos/touyan/ty_register_install.html?id=e2M5nZ)

1.  双击打开安装包，点击下一步
2.  阅读并同意后点击下一步
3.  点击浏览选择安装目录。**请不要安装在C盘**，选择完路径后点击安装 ![安装](https://dict.thinktrader.net/assets/安装3-84917b29.png)
4.  安装完成后选择创建快捷方式，点击下一步
5.  点击完成，结束安装

在安装 QMT 软件时，**请不要安装在C盘**，以避免因权限问题导致的使用问题。

若是只能安装到C盘，请在启动时选择以管理员权限启动。

![](https://dict.thinktrader.net/assets/以管理员身份运行-6a022b9e.png)

#### 权限问题可能导致（非必现）

1.  设置不生效
2.  数据下载无法写入文件

#### 安装目录的几个关键文件夹

##### **bin. x64 主文件夹**

`{安装目录}\/bin.x64`

![](https://dict.thinktrader.net/assets/打开文件所在位置-a74b59f8.png)

右键点击客户端启动的快捷方式，点击`打开文件所在的位置`，可以进入`bin.x64` 主文件夹，在这个文件有下载的 Python 库、软件启动程序。

##### **datadir 数据文件夹**

`{安装目录}/datadir`

在安装目录，即 `bin.x64` 主文件夹的上一级文件夹，我们可以找到`datadir`数据文件夹，下载的数据文件都在这里。

##### **log 日志所在文件夹**

`{安装目录}/userdata/log`

日志文件是最常用的，你要记住，出了问题，技术同事最快的方式就是通过日志给你进行检查。

-   `XtClient_20210922. log` - 客户端常规日志
-   `XtClient_Formula_20210922. log` - 策略运行日志
-   `XtClient_FormulaOutput. log` - 策略输出日志
-   `XtClient_PerformanceFile_20210922. log` - 客户端流程节点日志

## 三、通信设置

### 基础操作

![](https://dict.thinktrader.net/assets/通信设置_行情选择-18427e82.png)

**行情主站**与历史数据相关；

**交易中心**与全推数据有关，包括涨幅、全推数据等

右上角全推行情，设置为五档行情。

部分未升级的券商 QMT，因市场状态服务器未选择迅投相关服务器，会导致：

> **注意**
>
> 1.  下载不到过期合约列表
> 2.  交易日列表缺失，导致数据下载问题
> 
> 以上问题的解决方案，务必选择带**迅投**字样的交易/行情服务器。

## 四、登录

### 基础操作

#### 券商QMT

![](https://dict.thinktrader.net/assets/登录_行情_交易-05751c95.png)

1.  一定选择**行情+交易**，确保功能完善。
2.  不要勾选【极简模式】

#### 投研端

![](https://dict.thinktrader.net/assets/ty登录界面-99619508.png)

1.  一定选择**登录**按钮，确保功能完善。
2.  不要勾选【交易通】

### 账号密码

#### 券商 QMT

券商QMT，使用券商给你的账号密码

#### 投研端

投研端，使用注册投研网站的手机号和密码 ![](https://dict.thinktrader.net/assets/ty登录-570e8810.png)

1.  **界面没有行情、没有回测、没有交易等情况**

以上情况都请退出，切换到**行情+交易**/**登录**，再重新登录。

## 五、下载 Python 库

### 基础操作

1.  **首次下载软件后的第一件事情，就是下载 Python 库，**
    
2.  **注意，该 Python 库与您本地已经安装的没有任何关系，也不要将地址指向已经安装好的Python，并不能产生作用。**
    
3.  **下载完成后，需要重启生效**
    
4.  **请不要在盘中操作，会限速，下载速度较慢。**![](https://dict.thinktrader.net/assets/下载Python库-f0c623ba.png)
    

1.  **报错带有pandas相关的，多半是Python库的问题。**

> **解决方案**
>
> 1.  关闭软件，通过任务管理器确认所有`QMT`相关的进程已经退出，然后重启软件
> 2.  如果问题仍然存在，**删除`安装目录下/bin.x64`下的`Lib`文件夹** ，然后重新下载python库
>
> ⚠️ **破坏性操作警示**：删除 `Lib` 文件夹会移除本地已安装的 Python 运行时库（包括您手动 `pip install` 装入 `site-packages` 的第三方库），可能导致已有策略无法运行，并需要重新下载/安装 Python 环境。执行前请**先备份 `Lib` 文件夹**（如重命名为 `Lib.bak`），确认重启后策略运行正常再删除备份。

## 六、行情设置

### 基础操作

1.  **登录后，首先确认行情是否连接, 点击行情按钮并检查行情连接状态**

![](https://dict.thinktrader.net/assets/登录后_行情绿色-4b8b604c.png)

2.  **点击行情，切换行情选择，如果状态显示连接，并且行情数据有显示，则连接正常。**

![](https://dict.thinktrader.net/assets/登录后_行情设置-ed2503a5.png)

1.  **板块列表界面无行情或数据不更新，一般是行情或交易中心连接失败**

> **解决方案**
>
> 1.  如果没有在策略运行，切换一次行情和交易中心
> 2.  如果有策略在运行，停止策略并重启客户端

2.  这么多行情站点如何进行选择？

> **解决方案**
>
> VIP用户建议优先连接VIP站点，数据更全，带宽更充裕；非VIP用户选择自己延迟低的站点连接即可

### 券商 QMT 修改 VIP 行情账号

请参考[修改账号的教程](https://dict.thinktrader.net/dictionary/?id=e2M5nZ#_1-%E5%A6%82%E4%BD%95%E5%9C%A8%E5%88%B8%E5%95%86-qmt-%E4%B8%AD%E4%BD%BF%E7%94%A8)

## 七、数据下载

> **提示**
>
> 1.  本地数据是系统运行策略与计算指标的基础，因此做好历史数据补充非常重要
> 2.  视频教程链接：[数据下载的视频教程](https://dict.thinktrader.net/videos/touyan/ty_data_download.html?id=e2M5nZ)

### 基础操作

#### 手动下载历史数据

在软件界面上，点击右下角行情按钮，进入**行情界面**，点击标签进入对应功能。

**我们以下载行情数据为例：**

1.  **下载K线数据的步骤**
    
    1.  **点击右下角行情按钮**
    2.  **点击历史数据下载标签**
    3.  **点击数据选项下拉框，选择K线数据（如要下载其他数据，如分笔数据/财务数据等清在下拉框选择对应按钮）**
    4.  **选择要下载的数据范围和数据周期**
    5.  **点击补充按钮开始下载**

![界面下载历史数据](https://dict.thinktrader.net/assets/界面下载历史数据-5c48b682.png)

#### 自动下载历史数据

1.  自动下载历史数据的步骤：
    
    1.  点击右下角行情按钮
    2.  点击调度任务标签
    3.  点击新增方案
    4.  输入【自定义】的方案名称，并点击确认 ![定时下载1](https://dict.thinktrader.net/assets/收盘作业1-b3b524fb.png)
    5.  点击【右侧】增加下载任务
    6.  在【方案设置左侧】数据下拉框选择下载的数据类目，一个下载方案中可以有多个下载任务
    7.  在板块列表选择要下载的板块
    8.  在【方案设置右侧】选择数据下载范围，并点击确定 ![定时下载1](https://dict.thinktrader.net/assets/收盘作业2-ca22b4cf.png)
    9.  在调度任务界面选择需要定时下载的选项【推荐在盘后下载，例如16：00】
    10.  点击应用按钮，即可完成自动下载历史数据的设置 ![定时下载1](https://dict.thinktrader.net/assets/收盘作业3-faba2412.png)

#### 通过python下载历史数据

参考链接：[`download_history_data`的使用方法](https://dict.thinktrader.net/innerApi/data_function.html#download-history-data-%E4%B8%8B%E8%BD%BD%E6%8C%87%E5%AE%9A%E5%90%88%E7%BA%A6%E4%BB%A3%E7%A0%81%E6%8C%87%E5%AE%9A%E5%91%A8%E6%9C%9F%E5%AF%B9%E5%BA%94%E6%97%B6%E9%97%B4%E8%8C%83%E5%9B%B4%E7%9A%84%E8%A1%8C%E6%83%85%E6%95%B0%E6%8D%AE)

1.  下载历史过期合约提示下载失败

> **解决方案**
>
> 1.  部分券商服务器不支持下载此数据，需要将行情和交易服务器都切换到带【迅投】字样的服务器

2.  下载数据速度慢/数据少

> **解决方案**
>
> 1.  目前券商用户激增给迅投服务器带来了巨大的带宽压力，为了大部分客户能够正常使用，因此我们不得不对普通权限用户进行限速/限量，如果对数据的下载速度/数据量有需求，可以在官网购买\[VIP权限\]进行解锁

3.  界面显示【下载完成】后还是没有数据

> **解决方案**
>
> 1.  切换行情服务器重置链接状态，再次进行下载

## 八、策略指标

### 基础操作

#### 新建策略

1.  **在【我的】主页，点击新建策略按钮**
2.  **点击【pyhton策略】模型**
3.  **会弹出一个策略编辑器框 【新建策略文件】**
4.  **编辑完点击【编译】按钮**
5.  **关闭策略编辑器**![新建策略rzrk](https://dict.thinktrader.net/assets/新建策略rzrk-b4b14f0e.png)

#### 导入策略

**券商 QMT：****1**. 点击进入【模型研究】界面 **2**. 右键 -> 选择本地. rzrk导入 ![导入rzrk文件](https://dict.thinktrader.net/assets/导入rzrk文件-0fcb8953.png)

**投研端：****1**. 点击【行情】界面,选择模型 **2**. 右键 -> 选择本地. rzrk导入 ![导入rzrk文件](https://dict.thinktrader.net/assets/ty导入rzrk文件-a8700536.png)

#### 策略在副图作为指标运行

在主图上双击策略 VBA策略可以直接输出图像 ![副图VBA](https://dict.thinktrader.net/assets/策略作为副图运行-6405c06b.png)

#### 策略指标选股

**操作流程**

1.  在行情界面双击【板块】打开股票列表界面，在股票列表界面【右键】打开选项菜单,选择【添加自定义指标】 ![指标选股](https://dict.thinktrader.net/assets/指标选股1-e4686839.png)
    
2.  在弹窗中选择要添加的【策略文件】，【指标】，【周期】，【复权方式】，在左侧选择 【策略文件】后，需要在右侧选择具体的【指标】
    

> **提示**
>
> 选股时的复权方式要与自己实际看盘时的复权方式一致

![指标选股](https://dict.thinktrader.net/assets/指标选股2-5a4ffa63.png)

3.  如需要【盘中实时选股】，需要在添加完【指标】后，右键指标名称，在选项框中选择【刷新设置】 ![指标选股](https://dict.thinktrader.net/assets/指标选股3-d14f2a23.png)
4.  在弹窗中点击勾选【自动刷新】按钮，如果指标名称变成【绿色】则表示设置成功 ![指标选股](https://dict.thinktrader.net/assets/指标选股4-40e5c8f4.png)

1.  **策略在主图无输出**

> **解决方案**
>
> 1.  `VBA`策略:
>     
>     1.  变量没有用 `:` 输出
>     2.  策略内有报错或者计算空值
> 2.  `python`策略:
>     
>     1.  策略内没有调用画图函数

## 九、策略回测

参考视频教程[内置python回测](http://dict.thinktrader.net/videos/touyan/ty_backtest_strategy.html?id=7zqjlm)

## 十、策略实盘

### 账号区分

所谓实盘，其实也分为两种：模拟仿真账户和真实资金账户。

**模拟仿真账户**：投研网站提供的账户，账户自动绑定到对应账号的投研端中，登录即可看到。[登录投研网站](https://dict.thinktrader.net/signin/)

**真实资金账户**：即券商提供给你的资金账户，存入真实资金的。该账号只能联系券商获取

### 基础操作

#### 交易账号登录

操作流程如下图：

![交易账号登录](https://dict.thinktrader.net/assets/交易账号登录-f61933d6.png)

#### 策略交易运行

操作流程：

1.  点击界面上的【模型交易】按钮，进入策略设置界面
    
2.  在左侧策略文件列表中，选择要进行交易的【策略】
    
3.  在弹窗中选择【主图代码】，【账号类型】，【账号】，【周期】，特别要说明的是，在实盘交易中，无论选择什么周期，策略都是以`tick`级进行运行，周期选项只影响非快速下单时的`passorder`调用 ![策略交易](https://dict.thinktrader.net/assets/策略交易1-b1df2ba3.png)
    
4.  点击【运行模式】栏按钮，选择策略是否对账户进行操作，其中：
    
    1.  模拟：不下单到设置的账号，只在软件进行信号记录
    2.  实盘：产生实际下单
5.  点击【操作】栏按钮，即可开始策略交易 ![策略交易](https://dict.thinktrader.net/assets/策略交易2-651b85c1.png)
    

1.  **策略在实盘模式下，调用下单后不下单**

> **解决方案**
>
> 2.  **在 `passorder` 语句后边进行一次`print`,确保进行了调用**
> 3.  **查看策略信号栏，如果有策略信号，但是没有实际下单到账户，是选错了运行模式**
> 4.  **passorder的快速下单参数设置错误，关于快速下单的说明，参考文档[内置python](http://dict.thinktrader.net/innerApi/enum_constants.html?id=7zqjlm#quicktrade-%E5%BF%AB%E9%80%9F%E4%B8%8B%E5%8D%95)**
> 5.  **账号是否配置正确**
> 6.  **被柜台拒绝：在界面下方`消息提示`或`执行中任务`查看被拒原因**

2.  **行情不更新/k线的ohlc值一样**

> **解决方案**
>
> 1.  行情订阅超限，非VIP只允许同时存在300个订阅

## 十一、查看日志

日志对于发现和解决应用程序中的故障和错误非常有帮助。通过记录关键步骤、变量值和异常信息，可以追踪代码执行路径，帮助定位问题所在，便于我们分析。

### 基础操作

1.  **选中客户端->右键选择【打开文件所在位置】**
2.  **实例路径`\bin.x64`结尾**
3.  **【点击箭头】向上退一级目录**
4.  **查询【userdata】文件并点击进去**
5.  **选择双击【log】文件,对以下文件进行创建副本并压缩文件**

-   `XtClient_xxx. log` - 客户端常规日志
-   `XtClient_Formula_xxx. log` - 策略运行日志
-   `XtClient_FormulaOutput_xxx. log` - 策略输出日志
-   `XtClient_PerformanceFile_xxx. log` - 客户端流程节点日志
-   `XtClient_debug_xxx. log` - 客户端debug日志 ![日志目录\_log](https://dict.thinktrader.net/assets/日志目录_log-35f30a91.png)

1.  **日志打开查看后缺失实时记录信息，或日志无法压缩/传输**

> **解决方案**
>
> 1.  将日志复制后粘贴到其他文件夹，再进行传输/压缩
> 2.  关闭软件后再进行传输/压缩

## 十二、VIP函数列表

### 通过GMD系列获取的函数

> **提示**
>
> gmd系列VIP数据都是通过指定period,或stock\_list参数进行获取；如无特殊说明，其他参数与gmd函数一致

| 函数功能 | 原生python | 内置python | 备注 |
| --- | --- | --- | --- |
| 获取股票历史涨跌停价格 | period="stoppricedata" | None | 获取该数据前需要先调用xtdata.download\_history\_data进行下载，period参数选择"stoppricedata" |
| 股票快照指标 | period="snapshotindex" | None | 获取时需要先通过subscribe\_quote进行订阅 |
| ETF实时申赎 | period="etfstatistics" | None | 支持下载历史行情，订阅实时行情，period参数需指定为etfstatistics， |
| 获取股票资金流向数据 | period="transactioncount1d" 或者 "transactioncount1m" | period="transactioncount1d" 或者 "transactioncount1m" | 获取该数据前需要先调用xtdata.download\_history\_data进行下载，period参数选择""transactioncount1d" 或者 "transactioncount1m" |
| 订单流数据 | period = "orderflow1m"等 | period = "orderflow1m"等 | 获取历史数据前需要先用download\_history\_data下载历史数据，订单流数据仅提供orderflow1m周期数据下载，其他周期的订单流数据都是通过1m周期合成的，该数据支持订阅 |
| 问董秘文本数据 | period='interactiveqa' | period='interactiveqa' | 获取数据前需要先用download\_history\_data下载历史数据 |
| 北向资金流数据 | 品种需指定为 'FFFFFF.SGT' # 北向资金代码；period需指定为 `northfinancechange1m` 等 | 见其他VIP函数表 | 获取前需要进行下载，不支持订阅 |
| 行业指数数据 | stock\_list指定为\['xxxxxx.BKZS'\] | stock\_code指定为\['xxxxxx.BKZS'\] | 各行业指数代码参考客户端界面,如SW1农林牧渔为 '260000.BKZS' |
| 商品市场指数 | stock\_list指定为\['xxxxxx.BKZS'\] | stock\_code指定为\['xxxxxx.BKZS'\] | 各商品板块指数代码参考客户端界面,如商品市场指数为 '290000.BKZS' |
| 历史主力合约数据 | period = "historymaincontract" | 见下表 | 原生：获取该数据前，需要通过download\_history\_data接口下载数据，下载时period参数需指定为historymaincontract  
内置: 通过界面端数据管理 - 过期合约数据 - 过期合约列表 |
| 上期所/上期能源五档盘口 | period = "l2quote" | period = "l2quote" | 支持订阅 |
| 期货仓单 | period = 'warehousereceipt' | None | 获取数据前需要先用download\_history\_data下载历史数据,period = 'warehousereceipt' |
| 期货席位 | period='futureholderrank' | None | 获取数据前需要先用download\_history\_data下载历史数据,period='futureholderrank' |
| 现货价格 | stock\_list=\["xxxxxxxxxxx.spor"\] | stock\_code=\["xxxxxxxxxxx.spor"\] | 获取数据前需要先用download\_history\_data下载历史数据,标的范围选择现货指数板块 |
| 期货加权指数 | stock\_list = \['xxJQ00.xx'\] | stock\_code=\["xxJQ00.xx"\] | 获取数据前需要先用download\_history\_data下载历史数据,标的范围选择加权品种，支持订阅 |
| 交易所公告 | period='announcement' | period='announcement' | 获取数据前需要先用download\_history\_data下载历史数据 |

### 其他VIP数据

| 函数功能 | 原生python | 内置python | 备注 |
| --- | --- | --- | --- |
| 获取历史ST数据 | xtdata.get\_his\_st\_data | ContextInfo.get\_his\_st\_data | 获取前需要先进行下载 |
| 获取交易日历 | xtdata.get\_trading\_calendar | get\_trading\_calendar | 内置需要通过界面端 - 节假日数据 - 下载  
原生的需要调用xtdata.download\_holiday\_data()下载 |
| 历史主力合约数据 | 见上表 | C.get\_main\_contract | 原生：获取该数据前，需要通过download\_history\_data接口下载数据，下载时period参数需指定为historymaincontract  
内置: 通过界面端数据管理 - 过期合约数据 - 过期合约列表 |
| 北向资金流数据 | 通过gmd获取，见上表 | C.get\_north\_finance\_change | 使用前需要进行下载，不支持订阅 |
| 沪深港通持股数据 | None | C.get\_hkt\_details | 获取前需要通过界面端 - 港股资金流向数据 - 下载 |
| ETF申赎清单 | xtdata.get\_etf\_info | get\_etf\_info | 原生: 使用前需要调用xtdata.download\_etf\_info()下载数据  
内置: 通过界面端数据管理 - etf申赎清单下载数据 |
| 可转债信息 | xtdata.get\_cb\_info | None | 获取前需要先用download\_cb\_data下载可转债信息 |