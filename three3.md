## 初始化所需要的参数
相机camera,场景scene

## 加载三维数据
OBJLoader\
MTLLoader\

##  mapbox添加three数据
``onAdd:function(map,gl){
①添加three灯光
②加载obj模型,mtl材质,添加到场景
③触发模型回调
④设置渲染器参数renderer
⑤bind(this)
}``


``render:function(gl,matrix){
 const rotationX = new THREE.Matrix4().makeRotationAxis(
new THREE.Vector3(1, 0, 0),
this.modelTransform.rotateX
        );
}
``