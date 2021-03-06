title: 简单Dialog组件

speaker: 时扬扬

[slide]
# 基本组件

* 半透明遮罩层 Mask
* 弹出框容器 Holder
	* 内容头部 head
    * 内容主体 body
    * 底部操作 foot

[slide]
# 遮罩层

* 覆盖全屏幕 （考虑高度100%, fixed定位）
* 半透明实现方式
    * opacity
    * rgba
    * 图片

[slide]
# 容器头部

* 标题（一般用来标示对话框的标题）
* 关闭按钮
    * 实现方式（字符、图片）
    * 事件处理

[slide]
# 容器主体

* 考虑留出边距
* 考虑最低高度

[slide]
# 底部操作

* 确定取消按钮
    * 确定按钮和取消按钮事件区分
    * 取消按钮事件处理类似关闭按钮
* 按钮排版位置

[slide]
# 考虑配置项

* 遮罩层
    * `showMask: true` 显示遮罩层
    * `closeWithMask: true` 点击遮罩层关闭弹框 (onClose)
* 容器头部
    * `showHead: true` 显示头部
    * `title: '温馨提示'`  显示标题
* 容器主体
    * `content`: ''`    主体内容（考虑支持HTML Element）
* 底部操作
    * `buttons: ['确定', '取消']`
    * `onClose: function () {}` 关闭时候支持的事件绑定
* 综合方法
    * show/hide

[slide]
# 模态窗口

* 默认显示
* 确认框

    ```
    {
        closeWithMask: false,
        onClose: function (yes) {
            yes ? yesFn() : noFn();
        }
    }
    ```

[slide]
# 更优雅的接口
* 考虑在回调内阻止弹框的关闭
* 考虑Promise写法

    ``` 
    Dialog.confirm('确认执行操作?').yes(function () {
        /* 执行 */
    }).no(function () {
        /* 关闭窗口 */
    })；
    ```

[slide]
# 前端工具的作用
* 避免在代码细节中的失误
* 
