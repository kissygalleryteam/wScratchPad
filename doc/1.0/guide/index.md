## 综述

WScratchPad是 Canvas 刮刮乐效果。

* 版本：1.0
* 作者：宝码
* demo：[http://gallery.kissyui.com/wScratchPad/1.0/demo/index.html](http://gallery.kissyui.com/wScratchPad/1.0/demo/index.html)

> 仅用于 支持 `canvas` 的浏览器

## 初始化组件
		
    S.use('gallery/wScratchPad/1.0/index', function (S, WScratchPad) {
         var wScratchPad = new WScratchPad({
             'srcNode': '#div',
             'realtime' : false, // 实时修改 橡皮檫清除百分比,
             'size' : 5, // 橡皮檫 宽度
             'bg' : '#cacaca', // 背景内容
             'fg' : '#6699ff', // 覆盖内容
             'cursor': 'crosshair' // 橡皮檫样式(指针)
         });
         
        wScratchPad.on('afterEraserChange', function(event){
            console.log("已擦除 " + event.newVal + "% 的区域")
        })
    });

## 默认属性 

    {
         'srcNode': '', // 初始化 必填属性
         'realtime' : false, // 实时修改 橡皮檫清除百分比,
         'size' : 5, // 橡皮檫 宽度
         'bg' : '#cacaca', // 背景内容
         'fg' : '#6699ff', // 覆盖内容
         'cursor': 'crosshair', // 指针样式
         'eraser' : 0 // 已刮擦区域 半分比  0~100, 不能设置
     }

## API说明

> 继承 `KISSY.Base` 

*render()*

绘制 wScratchPad 组件

*clear()*

清楚 Canvas 覆盖层

*enable(Boolean)*

设置是否可刮擦


## 响应事件

*down*

橡皮檫按下

*mov*

移动橡皮檫, 当 **realtime** true 时, 实时更新 **eraser**

*up*

橡皮檫弹起, 同时更新 **eraser**
