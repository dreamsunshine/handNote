# 原生与rn交互同行
* RCTDeviceEventEmitter  主动传递事件
> DeviceEventEmitter.addListener
* Callback js异步调用
* Promise js调用
> 暴露方法返回promise，then调用

## get activity result
* startActivityForResult
> to do this,you must extent BaseActivityEventListener or implement ActivityEventListener
> listen to onActivityResult