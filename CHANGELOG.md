#### 3.0.3 (2017-12-25)

##### New Features

* chore(dev): remove useless dependency (cheerio)
* chore(dev): upgrade torchjs (testing framework)
* chore(doc): replacing demos screenshot in README.md
* chore(legend): better continous legend's mouse cursor.
* feat(chart): support auto padding

##### Bug Fixes

* fix(axis): axis'title setting. Close #299
* fix(axis): fill gaps near edges when gridAlign is `center`
* fix(axis): left axis grid cover the axis line
* fix(chart): Endless loop after chart.forceFit()
* fix(chart): crush after resize. Closes: #241
* fix(demos): @lite-js/torch => torchjs
* fix(demos): map drilling down problem
* fix(scale): throw an error to avoid stack overflow, etc.
* fix(theme): allow set partial theme. Closed #205.
* fix(theme): set theme for legend.html but not work
* fix(tooltip): fixed bug of #318, size(filed) caused error of tooltip

#### 3.0.2 (2017-12-14)

##### New Features

* chore(dev): add `index.d.ts`
* chore(dev): working with Windows
* chore(dev): better scripts for dev
* chore(demos): better demos solution & add more demos

##### Bug Fixes

* fix(tooltip): set title for tooltip, change does not take effect(#280)
* fix(shape): fixed bug of #252
* fix(view): fix bug of filter and view event
* fix(eslint): close the linebreak-style rule to support windows os
* fix(dependencies): be more careful on dependencies management (like uglify-js)
* fix(scale): very little number ticks
* fix(component): set appropriate value of zIndex
* chore(demos): fixing demos style, etc.
* chore(demos): remove screenshots

#### 3.0.1 (2017-12-01)

##### New Features

* add appendInfo to help distinguish shape in graphical element events. ([39934761](https://github.com/antvis/g2/commit/399347616be541ef5f254d3a7f03c16e3c91dbdc))
* support `title: true` to display the axis's title. ([7f4cf307](https://github.com/antvis/g2/commit/7f4cf30788c70d2137c62ca41de569b4c61cc15f))
* add `hideMarkers` for `chart.tooltip()`, to close the display of tooltipmarkers for line, path and area. ([bfe3738f](https://github.com/antvis/g2/commit/bfe3738fc3ce07fbfb60698737c583c0a3483ab6))

##### Bug Fixes

* fix tooltip bug. ([2933b777](https://github.com/antvis/g2/commit/2933b7777c4365c5fd8f52bb37fd4ee35250c627))
* Unified the easing function of all geoms. ([78849666](https://github.com/antvis/g2/commit/78849666be78b0b3754c1ed43bfff05e0fff1361))

#### 3.0.0 (2017-11-22)

* A complete upgrade, all the interfaces were sorted and upgraded，[details](http://g2-dev.site.alipay.net/zh-cn/g2/3.x/tutorial/g2-v3-changes.html)


---

#### 2.3.13

- fix: 修复分组层叠柱状图图例项重复的问题
- fix: 修复单选模式下未设置 `chart.filter()` 点击失败的问题

#### 2.3.12

- feature: `chart.tooltip()` 方法添加 `inPlot` 属性，用于控制是否在绘图区域内展示，默认为 true
- fix: 修复 `chart.getSnapPoints()` 查找不精准的问题
- fix: 修复 tooltip 层级问题
- fix: 修复连续图例无法过滤 [0, 1] 的问题

#### 2.3.10

* fix: 修复 dodge 情况下 filter 掉所有选项的问题
* fix: 修复 interval 和 line 同时存在是 tooltip 的 crosshair 线跟 marker 不对齐的问题
* fix: 修复 在极小的数值下坐标轴上出现长浮点数的问题

#### 2.3.9

* fix: 回滚 off 仅带有 eventType 不带有 callback 清理所有同名事件
* fix: 修复饼图文本在临界值（正下方）offset < 0 时的对齐问题

#### 2.3.8

- fix: 2.3.7 导致 tooltip 默认的 title 不可见

#### 2.3.7

- feat: chart.off  支持仅传入事件名，所有同名的事件都会被清理
- feat: tooltipchange 中更改第一个 items 项的 title，会影响 tooltip 的 title
- feat: legend 在 bottom 时增加一个 alignPlot 的选项，使得图例跟绘制区域对齐
- feat: tooltip 增加 background 的配置项
- fix: 多边形在极坐标下 hit 的问题
- fix: 切换皮肤时图例、labels 样式不生效的问题

#### 2.3.6

- fix: 修复混合图例筛选问题
- fix: 修复连续型数据，设置了 min max 导致 size 运算不准确的问题
- feat: `chart.downloadImage(name)` 支持仅返回文件对象不触发浏览器的下载动作
- feat: 分面 Facet 支持 Guide 辅助元素的绘制

#### 2.3.5

- fix: 修复框选部分区域不生效的问题
- fix: 修复 `G2.Stat.summary.percent` 统计函数问题
- feat: area line point schema 四种 geom 支持选中交互

#### 2.3.4

- fix: 修复折线图查找逼近值时又很小一段区域无法找到值的 bug
- fix: 层叠区域图处理了 null 的数据，如果数据为空时报错
- fix: 数据为空是，栅格线绘制时出错
- improve: 内置列定义属性允许覆盖

#### 2.3.3

- fix: 修复 legend 激活错误
- fix: 自定义的列定义设置属性值无法覆盖 global 上的定义
- fix: 修复 tooltip 关闭时 chart.showTooltip() 调用报错的问题
- improve: 优化 toFixed 位数小于 20，防止报错

#### 2.3.2

- feat: 自定义 shape 场景下，支持覆写 `getActiveCfg` 方法
- feat: chart 支持设置 pixelRatio 属性
- fix: 修复时间类型（time 或者 timeCat）数据为 0 时被转换成当前时间的问题
- fix: 修复坐标轴第一条网格线未绘制的问题
- fix: 修复全局关闭坐标轴标题的显示（如 `G2.Global.axis.left.title = null`）无法生效的问题
- fix: 修复窗口改变时 chart 报错的问题
- improve: 优化 `Stat.link.sankey` 变换函数，提升桑基图数据处理性能

#### 2.3.1

- feat：坐标轴网格线支持奇偶背景设置，[demo](http://antvis.github.io/g2/demo/14-radar/radar-line.html)
- feat：支持全局字体设置 `G2.Global.fontFamily`
- feat: 统一层叠柱状图，层叠区域图的图形、tooltip 以及图例的顺序，[demo](http://antvis.github.io/g2/demo/03-area/area-percent.html)
- fix: 修复饼图文本层叠、文本连接线交叉的问题
- fix: 饼图文本线在动画时不显示，暂时停止动画
- improve: 设置 labels 的属性 custom 为 true 时生成的 html 不再自动换行
- improve: 设置 `G2.Global.showSinglePoint` 控制区域图、折线图仅有一个点时是否显示成点，默认为 false

#### 2.3.0

- feat: 添加动画自定义接口，详见 [api](http://antvis.github.io/g2/api/animate.html)
- feat: 支持配置项式声明，详见 [api](http://antvis.github.io/g2/api/chart-options.html)
- improve: 动画效果优化
- improve: 绘图底层性能优化

#### 2.2.7

* fix: 修复饼图标签线（labelLine）有交叉的问题
* fix: 不绘制点图中纵轴的数据值为 null 的点
* fix: 修复层叠柱状图（intervaDodge）分组间距计算错误的问题
* fix: 修复多 view 下同步度量下，当个 view changeData 后同步度量失效的情况
* improve: 当线图（line）、区域图（area）只有一条数据时，以点的形式绘制
* improve: tooltip 的辅助线调整至 tooltipmarker（圆点）后部

#### 2.2.6

* fix: 修复绘制 intervalDodge 时，当 x 轴数据类型为 timeCat 且仅有一个分类时显示不正确的问题
* fix: 修复区间柱状图，相同 x 不同 y 区间下鼠标移动 tooltip 不改变的问题
* fix: 修复 tooltip 中展示 undefined 的问题

#### 2.2.5

* feat：`chart.legend()` 方法为**分类类型图例**新增 `formatter` 回调函数，用于图例文本的格式化，详见 [API](http://antvis.github.io/g2/api/chart.html#legend)，[使用实例](http://antvis.github.io/g2/demo/05-pie/pie.html)
* feat：新增 `chart.cols()` 方法，用于一次性定义多个列定义操作，[API](http://antvis.github.io/g2/api/chart.html#cols)
* improve：优化 interval、schema 两种 geom 生成图形的默认宽度计算策略
* fix：修复地理坐标系 tooltip 报错问题
* fix：修复参与加法运算的数据字段无法通过列定义指定度量类型的问题
* fix：修复数据源只有一条记录时 tooltipmarker 无法展示的问题

#### 2.2.4

* fix: 修复 tooltip 不更新的问题
* fix: 修复线图绘制使用渐变色，当仅有一条数据时报错的问题（`Failed to execute 'createLinearGradient' on 'CanvasRenderingContext2D': The provided double value is non-finite.`）
* feat: 为视图 view 添加 `id` 属性用于唯一标识视图对象，同时添加 `chart.getView(id)` 方法，用于获取对应 id 的视图对象

#### 2.2.3

* feat：`chart.legend()` 方法添加 `marker` 属性，支持指定 `point` 几何标记支持的所有 shape（除去'rect'），详见 [api](http://antvis.github.io/g2/api/chart.html#legend)，默认值为 `circle`
* feat：`chart.guide()` 增加回调函数支持动态更新，[实例](http://antvis.github.io/g2/demo/18-other/dynamic-guide.html)
* improve：完善功能，使绘制的柱状图的 y 轴刻度从 0 开始
* improve：完善 log 度量，使其支持 `min: 0` 的设置
* fix：修复某些场景（如线图、面积图等） `geom.getData()` 返回结果为空的错误
* fix：修复饼图中数值为 0 的类别不能显示文本的问题

#### 2.2.2

* feat: 新增功能：chart 下创建的 view 默认共享[列定义](http://antvis.github.io/g2/doc/tutorial/start/col-defs.html)、坐标轴 axis 配置、坐标系 coord 配置，即如果 view 不自己定义则默认同 chart 的配置相同；（所以这里对于地理投影坐标来说，直接在 chart 上声明坐标系类型就可以全部统一了），如果 view 自己定义了相应的配置，则以自己的为准，详见 [view](http://antvis.github.io/g2/api/view.html)
* feat: 新增 `syncXYScales` 属性，由用户选择是否需要统一所有视图的度量，使用详见 [chart API](http://antvis.github.io/g2/api/chart.html#syncxyscales)
* improve: 优化坐标轴刻度线个数计算
* fix: 修复 tooltipmarker 覆盖 tooltip 的问题
* fix: 修复线图层叠颜色的问题
* fix: 修复时间格式在 firefox 下的问题
* fix: 修复层叠直方图 active 的问题

#### 2.2.1

* improve: 优化鼠标当前位置所在图形的查找
* improve: 优化几何标记 Geom 选中交互，增加 `animate` 和 `cancelable` 配置项，详见 [api](http://antvis.github.io/g2/api/geom.html#selected)
* improve: 支持图表数据源中字段名包含空格的情况，如 "an apple"
* fix: 修复极坐标旋转圆心变化的问题
* fix: 修复开启框选时鼠标点击以及高精屏下框选报错的问题

#### 2.2.0

* feat: 丰富图例交互，详见教程[图例筛选模式设置](http://antvis.github.io/g2/doc/tutorial/start/legend.html# 图例的选择模式设置)：
  1. 支持鼠标 hover 高亮相关图形
  2. 支持单选多选模式
  3. 支持混合图表的图例筛选
  4. 支持连续图例的筛选
* feat: 支持鼠标框选交互，详见教程[图表框选交互](http://antvis.github.io/g2/doc/tutorial/start/action.html# 图表框选交互)
* feat: 支持 geom 几何标记的选中交互，详见教程[geom 选择交互](http://antvis.github.io/g2/doc/tutorial/start/action.html# 几何标记 - geom - 的选中)
* feat: 新增关系类图表：[弧长链接图](http://antvis.github.io/g2/demo/13-link/arcDiagram.html)、[和弦图](http://antvis.github.io/g2/demo/13-link/chordDiagram.html)、[桑基图](http://antvis.github.io/g2/demo/13-link/sankey.html)
* feat: 新增 `chart.downloadImage()` 方法，提供图表下载功能
* fix: 修复 getPosition 当原始数据 y 为零时失效的问题
* fix: 修复 time 度量设置 min 和 max 不生效的问题

#### 2.1.5

* fix: 修复 2.1.4 版本 **Cannot read property 'maxY' of undefined** 问题
* fix: 修复坐标轴中使用自定义 html 显示 label 无法销毁的问

#### 2.1.4

* feat: 添加打点监控开关 `G2.track(boolean)`，默认打开，用户通过设置 `G2.track(false)` 关闭
* feat: 鼠标移动事件 `plotmove` 返回 `shape` 属性，表示当前鼠标所在的 shape
* feat: 列定义中支持分类类型声明 range 属性（数组类型，[min, max]，min 和 max 均为 0~1 范围的数据），用于指定图形在坐标轴上收尾位置
* improve: 优化 `chart.source(data, cfgObj, nameArr)`  方法，`nameArr` 参数作为附加字段，而不是全部字段
* improve: 优化生成图例的顺序，与用户声明的图形属性（size、shape、color）顺序相同
* fix: 修复二维情况下点图 dodge 发生 stack 的问题

#### 2.1.3

* improve: 优化 tooltip 查找性能
* fix: 修复 changSize 的时候 guide html 反复绘制的问题

#### 2.1.2

* fix: Aniamte CPU 问题

#### 2.1.1

* fix: Aniamte labelLine id 识别错误
* fix: Animate label 显示错误
* fix: Animate fanIn 入场动画改进

#### 2.1.0

* feat: 新增高交互动画
* feat: 新增连续数据过滤 chart.filter()
* fix: 连续图例在 bottom、top 时应交换宽高

#### 2.0.6

* fix: 修复 chart.guide().html() 无法清除的问题
* fix: 修复列定义部分属性无法更改的问题
* fix: 自定义 tooltip 事件问题
* fix: 修复当原始数据不存在某个字段时，仍在 Y 轴刻度 0 处绘制的问题

#### 2.0.5

* feat: 新添加 chart.guide().html() 方法，支持自定义 html，[详见](http://antvis.github.io/g2/doc/tutorial/start/guide.html# 辅助 html)
* feat: 优化右侧边缘 tooltip 显示，当宽大于 plot 宽两倍的时候，顶左边
* feat: tooltip 增加自定义 html 边距自动检测
* fix: 双轴图例显示问题
* fix: 修复连续图例两端文本显示错误问题
* fix: 修复连续类型数据 tooltip 生效问题
* fix: 修复饼图相同占比不同类别 tooltip 显示结果相同的问题
* fix: 修复坐标轴 tickCount 设置为 1 时导致坐标轴文本渲染错误
* fix: 修复图例取消选中项不受 word 参数控制问题
* fix: 修复分类类型数据图表化后顺序错乱问题

#### 2.0.4

* improve: 优化 G2 映射后的数据结构，解决原始数据中属性名同 G2 关键字（x y color size 等）冲突问题
* improve: 优化 Stat.map.center() 方法，空值不执行统计
* fix: 修复区域图首条数据鼠标 hover 时绘图区域蒙白问题
* fix: 修复分面 Facet 度量未统一的问题，各个分面的坐标轴范围如果不统一在可视化上没有意义的

#### 2.0.3

* feat: 新增螺旋坐标系，详见 [api](http://antvis.github.io/g2/api/chart.html#coord)
* feat: 根据边距自动计算自定义 html tooltip 位置
* fix: 修复线图 tooltip 部分不展示的问题
* fix: 修复饼图只有一项数据时 label 不展示的问题
* fix: 修复折线图在极坐标系下转曲绘制错误问题

#### 2.0.2

* feat: 多视图（view）图例支持，[demo](http://antvis.github.io/g2/demo/01-point/scatter-matrix.html)
* feat: 支持数据源中记录包含不同属性值的场景，此时 chart.source() 的时候需要传入 names 数组，例如 chart.source(data,defs,names)
* feat: 地理投影坐标系坐标轴平滑处理， [demo](http://antvis.github.io/g2/demo/10-map/world-albers.html)
* feat: 图例取消选择时字体置灰
* optimize: 优化图表动画性能
* fix: 修复图例列定义的别名不生效的问题，详见 [issue](https://github.com/antvis/feedback/issues/80)
* fix: 修复数据源为空的报错问题

#### 2.0.1

* fix： 修复分面绘制时包含统计语法未进行度量训练的问题
* fix： 修复分面动画卡顿的问题

#### 2.0.0

- feat: 自定义 shape
- feat: 多视图 View 功能，支持图表组合和异构数据的绘制
- feat: 新增 edge 几何标记，用于支持关系图的绘制

**移除的功能**
- delete: chart.legendVisible() 废除，不再支持
- delete: chart.legend('left|top|right|bottom') （即原先直接传入位置字符串来设定图例位置） 废除，不再支持
- delete: 移除了部分 G2 默认提供的 shape:

对应的 GEOM  |  废弃的 shape
--- | ---
point |  pointerArrow
point | pointerLine
point  | pointerRect
interval | stroke
polygon | stroke

#### 1.2.7

* fix： 修复第一个值为 null 时报错
* fix： 修复极坐标 Dodge
* fix： time 类型下，只有一个数据时 min、max 报错

#### 1.2.6

* fix： 修复 tooltip 去重中颜色的判断

#### 1.2.5

* feat: 支持背景区域设置主题背景色
* fix: 调整坐标轴和背景区域的绘制顺序
* fix: 修复多个图例情况下对单独一个图例设置 position 将默认的 position 覆盖的问题

#### 1.2.4

* feat: 支持图表宽度自适应配置属性 forceFit
* feat: 支持不同图例单独设置显示位置
* feat: 为 Linear、Time 类型度量添加 tickInterval 属性，用于指定坐标轴各个标度点的间距
* fix: 修复区域图不支持连续的 null 值的问题
* fix: 修复字体大小无法设置
* fix: 修复创建 chart 对象时使用 container 属性导致原容器 DOM id 属性被覆盖的问题
* fix: 修复极坐标下动画的旋转中心

#### 1.2.3

* improve: 图例自动换行
  * 废弃 lineHeight 概念，使用 bbox.height 代替。对于大小连续图例，会使其不重叠，同时文本竖直分布不均
  * fix: theme 中 spacingX 及 spacingY，概念为每个图例之间的左右间距及上下间距。在默认 theme 中根据视觉进行了优化
* feat: chart.guide() 新添加 min 和 max 关键字，用于快速定位坐标轴起点和终点
* fix: 修复 treemap 部分分层边框无法绘制的问题
* fix: 修复 tooltip 辅助线首次出现的位置问题
* fix: 修复 axis label 旋转 text-anchor 失效问题

#### 1.2.2

* fix: 修复 Safari 浏览器下，时间戳含‘Z’出错问题
* fix: 修复仪表盘白边
* fix: 修复饼图文本重叠的问题
* fix: 饼图选中动画 bug
* improve: 优化 tooltip 出现的效果

#### 1.2.1

* improve: guide/Arc 算法优化
* fix: tooltip corsshair 遮盖点的问题
* fix: treemap 字段写死的问题

#### 1.2.0

* improve: 精度性能优化，图表的性能是原来的 4+ 倍
* feat: 支持简单的加法运算符，简化了区间数据图表的绘制
* feat: 增加 map 坐标系，用于地图投影的绘制
* feat: 新增两套主题，并修改默认主题

#### 1.1.5

* fix: 修复全局设置 plotCfg facetCfg 无法生效的问题
* fix: 修复饼图文本重叠的问题，#146

#### 1.1.4

* improve: 优化 polygon 图形的文本颜色，默认使用内部文本的样式
* feat: 新增 chart.getPosition({xDim: value, yDim: value})接口，用于原始数据到对应画布坐标的转换

#### 1.1.3

* fix: 混合图例的 marker 颜色未渲染出来
* fix: intervalDodge 当数组只有一个分组时，绘制有问题
* fix: chart.showTooltip() 调用无效
* fix: 半圆饼图动画问题: g-canvas 升级 1.3.21， g-animate 升级 1.2.3

#### 1.1.2

* fix: 饼图中数据占比很小的时导致文本重叠并且展示不正确
* fix: 当数据中都一个记录值为 undefined 的时候，图例绘制出错
* fix: 热力图中使用 log 度量时，透明度没有参与 log 度量

#### 1.1.1

* 调整多边形 (polygon) 在极坐标下的文本展示
* 支持颜色渐变方式的连续图例
* 一些 BUG 修复：
  1. 饼图 label 展示的问题
  2. 相同图形同类别的 tooltip 取值问题
  3. 饼图选中动画问题
  4. treemap 文本问题

#### 1.1.0

* 替换了底层的绘图库，优化渲染性能和 tooltip 性能
* 更改了生成 shape 的机制，简化接口
* 补充单元测试，代码覆盖 98%，分支 90% 以上
* 接口优化

#### 1.0.5

* 修复饼图 bug

#### 1.0.4

* 所有图表的文本调整，不在跟随坐标系的旋转而变化

#### 1.0.3

* 如果 tooltip 的 title 指定的文本不是数据的字段，则直接显示
* 初始化代码存在问题
* 调整文本位置和角度
* 坐标系 tranpose 后 label 的 offset 的方向错误
* 等高线 tooltip 报错

#### 1.0.2

* 修复 tooltip 优化带来的部分 bug
  * 选中饼图时残存白线
  * change data 导致 tooltip 不可用

#### 1.0.1

* 优化 tooltip 性能

#### 1.0

* 正式发布

#### 0.9.18

* 多个 y 轴的图表，各自生成对应的图例
* 统计函数在外部执行
* tooltip 的信息获取
* 需要把分类数据从通过度量把索引值改成对应的数据，而不是原始数据
* 时间数据转换成为时间戳
* 数据将分类类型、时间类型转换成数字的时间点需要调整
* changeData 时，分类类别发生改变时，scale 未更新
* scale 的 ticks 覆盖问题
* chart.line().label() 的 label 多个 chart 共享
* 一维的箱型图，tooltip 存在问题
* G2.Global.shape 设置 point 配置不生效

#### 0.9.15

* 代码放到页头 header 内部报错, 原因是计算颜色时，需要添加一个临时元素，未考虑 document.body 为空的情形
* 图例标题和文本太近
* 添加蜡烛图
* 自动计算 time 类型的 scale，而不需要用户指定，仅能计算字符串日期格式，时间戳无法判断
* 时间坐标系，interval 无法计算宽度，均匀的时间类型已经处理，非均匀的暂时不作处理
* 计算值是数组的字段对应的类型
* 如果 x 坐标轴上的文本比较长时，会遮住图例，所以图例的位置需要向上调整
* 图例的一系列问题：
  * 图例顶部和底部位置的默认位置
  * 多个图例时的对齐问题和位置调整
* summary.percent('time*value') 统计函数，仅返回了占比，没有将原始的 value 进行累加
* 自定义 tooltip 移动时的闪烁问题，tooltip 的格式化
* 控制不显示 tooltip
* area 图 spline 的支持, 限定范围, 统一 smooth 和 spline ，支持 smooth 形式下的断点
* 添加漏斗图
* point.dodge 点的位置存在问题
* 增加 time category 类型的度量，处理股票图不连续的问题
* 纵向坐标轴 title 不存在的时候，文本不需要自动旋转
* 度量改造，统一数据类型
* 柱状图的 transpose 功能，其他图形的 transpose 功能未实现
* 从左向右的动画错误
* 坐标轴标题不居中
* scale 在处理跟预期数据格式不相符时，translate 和 scale 会发生问题

#### 0.9.14

* 图表颜色渐变
* 多图 tooltip 信息的去重
* 支持多图联动，在一个图表上移动，显示所有的 tooltip
* 图表事件支持
  + 增加了 plotmove,plotenter,plotleave 的支持
  + 增加了 tooltipshow 和 tooltiphide 事件
  + 增加了 itemselected,itemunselected,itemselectedchange 事件
* 增加 chart 开放的的接口
  + chart.getScale(dim)
  + chart.getTooltipItems()
  + chart.getGeoms()
  + chart.getFacets()
* 饼图样式的自定义选项，连接线的 bug 修复
* 将所有 chart 对应的 3 个 canvas 包入指定的容器，并设置 relative

#### 0.9.13

* fixed bug of toolitp，隐藏 tooltip 时，tooltip 已经被 destroy
* fixed bug of legend, 连续数据的图例，不可勾选
* 等高线
* 支持统计函数的马赛克图
* 连续调用 changeData 时报错(tooltip 引起的 bug)
* polygon 支持 desity 、smooth 函数
* 连续数据的图例，过滤数据时错误(连续数据不再支持数据过滤）
* 分类 scale 对应的字段是数字时，过滤出现问题（解决）
* 统一处理热力图、等高线等多个维度的 tooltip 的统一实现
* region 统计函数 range、sd、se 实现，confidence interval 暂时未实现
* 镜像分面坐标轴文本显示问题
* 当分类类型只有一个时，绘图失败
* 分类 interval 自动计算宽度时错误

#### 0.9.12

* 二维 kernel 密度函数的支持
* 三维 kernel 平滑函数的支持
* 热力图的支持
* mirror 分面的支持
* color 渐变色支持

#### 0.9.11

* 热力图六边形的支持
* 辅助线、辅助图片、辅助框等辅助元素的支持

#### 0.9.10

* 修复没有 gemo，调用 clear 报错的 bug
* 一维 kernel 密度函数的支持
* 二维 smooth 的支持
* smooth 在数据不对称、无法会超出最小值、最大值范围

#### 0.9.9

* 添加 filter 功能，图例控制显示隐藏
* 添加 changeData 功能
* 添加 changeSize 功能
* 增加 kernel 统计函数的支持，包括 density 和 smooth 类型的统计函数
