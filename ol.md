# <font color=red>1.初始化地图以及图层添加</font>
## 地图初始化
ol.map({})
图层layer
容器target
视图view
## WMS服务
### WMS数据源
ol.source.TileWMS()\
ol.layer.Tile()\

ol.source.ImageWMS()\
ol.layer.Image()
### WMTS切片服务
ol.source.WMTS()\
ol.layer.Tile()
### wfs服务(一种xml服务)
 ol.source.Vector({\
    format:new ol.format.GeoJSON(),\
    strategy:ol.loadingstrategy.bbox,\
    url:''\
 })\
 ol.layer.Vector()
### geoJson直接加载
ol.source.Vector({\
	format:new ol.format.GeoJSON(),\
	url:'js/data/road3.json'\
})\
 ol.layer.Vector()


# <font color=red>2.添加地图控件</font>
鹰眼空间
视图控件
显示坐标控件    

# <font color=red>3.视图控制view,zoom</font>
view = map.getView()\
zoom = view.getZoom()\
view.setCenter()\
view.setZoom()

# <font color=red>4.图层控制以及显示</font>
layer.setVisible() 图层显示\
layer = layers.item() 获取图层项目

# <font color=red>5.绘制</font>
## 简单绘制
①定义位置点数组常量，coord = ol.proj.fromLonLat({点数据})，将coord存入数组。\
再用ol.Feature(ol.geom.Polygon([位置点数组]))
再定义适量数据源以及图层，将要素存入

## 交互绘制 (按照点绘制)
定义空的矢量数据源以及图层\
draw = new ol.interaction.Draw({})\
参数：数据源，绘制类型\
移除地图上的绘制map.removeInteraction()

## 自由绘制
ol.interaction.Draw({\
   freehand:徒手绘制\
})

# <font color=red>6.弹出框以及要素属性</font>
## 基础的点击弹出框以及获取要素属性
①获取点击地图事件回调\
map.on('click',callback)\
②获取地图上的要素\
map.forEachFeatureAtPixel(pixel,callback)\
③获取要素属性\
feature.getProperties()\
④定义弹窗\
ol.Overly({})\
容器element\
⑤获取点击事件的坐标,并数组弹窗具体位置\
var coodinate = evt.coordinate;\
overlay.setPosition(coodinate);\
⑥添加弹窗到地图上\
map.addOverlay(overlay)\
⑦关闭弹窗\
overlay.setPosition(undefined)\
⑧判断是否有要素\
获取位置像素值信息\
var pixel = map.getEventPixel(e.originalEvent);\
获取像素值内是否有要素\
var hit = map.hasFeatureAtPixel(pixel);\
更改光标要素\
map.getTargetElement().style.cursor\


# <font color=red>7.Style添加以及定义</font>
ol.style.Style({\
image:\
text:\
})\
添加图标\
ol.style.Icon({\
   anchor：\
   anchorOrigin:\
   anchorXUnits:\
   anchorYUnits:\
   scale:\
   opacity:\
})\
添加文字：\
ol.style.text({\
   txetAlign:\
   textBaseline:\
   text:文字内容\
   fill：\
   stroke:\
})
文字填充以及边框：
ol.style.Fill({})\
ol.style.Stroke({})\








