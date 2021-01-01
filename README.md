# bootstrap4.pop
## 基于bootstrap4，封装的消息组件 dialog, alert, confirm, prompt, notice，支持鼠标及手势拖拽 (surface笔记本)
 - [GitHub: https://github.com/aiv367/bootstrap4.pop](https://github.com/aiv367/bootstrap4.pop)
 - [Demo: https://aiv367.github.io/bootstrap4.pop/demo/](https://aiv367.github.io/bootstrap4.pop/demo/)
 - [Author：aiv367 (大花猫花大)](mailto:aiv367@qq.com)
 ## 更新
 - V1.1 [2021/01/01] 
	- 调整了代码
	- 修复了触控模式下无法关闭对话框的bug

 - V1.0.0 [2019/06/05]
	- 提交代码

## 依赖
 - [jQuery2.0+](http://jquery.com)
 - [bootstrap 4.0.0+](https://github.com/twbs/bootstrap/releases/download/v4.0.0/bootstrap-4.0.0-dist.zip)
 ## 导入

 ``` html
<script src="libs/jquery/jquery.js"></script>

<link rel="stylesheet" href="libs/bootstrap-4.5.0-dist/css/bootstrap.css">
<script src="libs/bootstrap-4.5.0-dist/js/bootstrap.js"></script>

<link rel="stylesheet" href="../bs4pop.css">
<script src="../bs4pop.js"></script>
 ```

## 说明
``` javascript
let dialog = bs4pop.dialog(opts);

//opts 参数说明
opts = {
	id: '',//'#xxx，对话框ID，可以不填
	title: '', //标题
	content: '', //可以是 string、element，$object
	className: '', //自定义样式
	width: 500,
	height: '',
	target: 'body', //在什么dom内创建 dialog

	closeBtn: true, //是否有关闭按钮
	hideRemove: true,//关闭时移除dom
	escape: true, //按 Esc 键关闭对话框
	autoFocus: true,//初始化时自动获得焦点
	show: true,//是否在一开始时就显示对话框
	backdrop: true,//模态背景 true: 显示模态，false: 没有模态，'static': 显示模态，单击模态不关闭对话框
	btns: [], //footer按钮 [{label: 'Button',	className: 'btn-primary',onClick(cb){}}]
	drag: true,//是否启用拖拽

	onShowStart() { },
	onShowEnd() { },
	onHideStart() { },
	onHideEnd() { },
	onClose() { },
	onDragStart() { },
	onDragEnd() { },
	onDrag() { }
}

// dialog返回值说明
{
	$el: $el,
	show() {},
	hide() {},
	toggle() {},
	destory() {}
}
```

``` javascript
// 其它方法
bs4php.dialog(opts); //对话框
bs4pop.removeAll(); //移除全部对话框
bs4pop.alert(content, cb, opts); //创建个简易提示框
bs4pop.confirm(content, cb, opts); //创建选择框
bs4pop.prompt(content, value, cb, opts); //创建输入框
bs4pop.notice(content, opts); //创建提示消息

// 各个方法总的 opts 参数说明参考 dialog 的 opts
```