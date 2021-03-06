# Highcharts简单介绍
## Highcharts
Highcharts 非商业免费，商业需授权，代码开源。    
Highcharts 基于SVG，方便自己定制，但图表类型有限。         
Highcharts 兼容 IE6 及以上的所有主流浏览器，完美支持移动端缩放、手势操作。

### 组成
Highcharts 系列软件包含 Highcharts JS，Highstock JS，Highmaps JS 共三款软件       
* Highchartsa：基本图表 其主要包含直线图、曲线图、区域图、柱状图、饼状图、散状点图、仪表图、气泡图、瀑布流图等20多种图表。
* Highstock：股票图表控件 包含多个高级导航组件（预设置数据时间范围，日期选择器、滚动条、平移、缩放功能）
* Highmaps：优秀地图组件 它可以方便快捷的创建用于展现销售、选举结果等其他与地理位置关系密切的交互性地图图表。

### 使用
* 下载使用： https://www.highcharts.com/blog/download/        
* 直接引入CDN文件： `<script src="http://cdn.hcharts.cn/highcharts/highcharts.js"></script>`

使用方式与echarts很像：     
1. 创建容器并指定大小供后续操作
2. 通过highcharts.chart函数来创建图表，highcharts.chart函数有两个参数 第一个参数是容器的id，第二个则是图表配置信息。

```html
<!DOCTYPE html>
<html>
<head>
    <title>Test</title>
</head>
<script src="http://cdn.hcharts.cn/highcharts/highcharts.js"></script>
<body>
<div id="container" style="width:400px;height:400px"></div>

<script type="text/javascript">
// 图表配置
var options={
    //去除生成后的图表水印链接,否则默认会在图标的右下角添加highcharts网站的水印
     credits: { enabled: false },
    chart:{
        type:"bar"  //指定图表的类型，默认是折线图（line）
    },
     title: {
                text: '我的第一个图表'                 // 标题
            },
            xAxis: {
                categories: ['苹果', '香蕉', '橙子']   // x 轴分类
            },
            yAxis: {
                title: {
                    text: '吃水果个数'                // y 轴标题
                }
            },
            series: [{                              // 数据列
                name: '小明',                        // 数据列名
                data: [1, 0, 4]                     // 数据
            }, {
                name: '小红',
                data: [5, 7, 3]
            }]
};
var chart=Highcharts.chart("container",options);
</script>
</body>
</html>
```
