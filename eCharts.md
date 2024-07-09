# <font color=red>eCahrts</font>
## option配置参数
title,tooltip,xAxis{},yAxis{},series[{}],

## 切换卡顿原因
beforeDestroy()方法释放该页面的chart资源，clear()方法则是清空图例数据，this.chart.clear()

## div reszie时echarts自适应
``$('.chart').resize(function(){
		myChartx.resize();
})``
