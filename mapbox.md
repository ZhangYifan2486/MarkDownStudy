# <font color=red>地图初始化以及图层添加</font>
## 地图初始化
mapboxgl.Map({\
container:\
style；\
})
## 图层操作
<font color=green>图层和数据源操作</font>\
map.addLayer({\
id:\
type:\
source:\
layout:\
paint:\
})\
map.addSoure('name',{参数\
})\
<font color=green>获取图层</font>\
map.getStyle().layers\
<font color=green>图层控制显示</font>\
map.setLayoutProperty\

# <font color=red>弹窗设置</font>
## 一般弹窗创建以及添加到地图
const pop = new mapboxgl.Popup 初始化弹窗\
.setlngLat.setHTML().addTo() 设置显示参数以及添加到地图\

# <font color=red>要素Feature操作</font>

# 获取mapbox画布
map.getCanvas()









