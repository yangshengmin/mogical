# mogical
<!DOCTYPE html>
<!--[if lt IE 9]><html class="ie6-8"><![endif]-->
<html>
<head>
	<meta charset="utf-8">
	<title>CSS+Js制作的一款响应式导航条-前端开发-BeyondWeb.cn</title>
	<style type="text/css">
		* {margin: 0; padding: 0;}
		body {font: 14px/22px "宋体", arial, serif;}

		.navBar {margin-top: 80px; width: 100%; height: 38px; background: #333;}

		.nav {margin: 0 auto; border: 0px solid #ccc;}
		.nav ul {list-style: none; width: auto;}
		.nav ul li {height: 38px; text-align: center;}
		.nav ul li a {display: block; font-size: 16px; color: #fff; text-decoration: none; line-height: 39px;}

		.ie6-8 .nav {width: 1000px; height: 38px;}
		.ie6-8 .nav ul li {float: left;}
		.ie6-8 .nav ul li a {padding: 0 30px 0 30px;}
		.ie6-8 .nav ul li.current {background: #f60;}
		.ie6-8 .nav ul li:hover a {color: #f60;}
		.ie6-8 .nav ul li a:hover {_color: #f60;}/*IE6 Hack*/
		.ie6-8 .nav ul li.current:hover a {color: #fff;}

		.ie6-8 .nav .hot {float: left; margin-left: 20px; padding-top: 8px;}
		.ie6-8 .nav .hot a {padding: 0 5px 0 5px; font-size: 12px; color: #fff; text-decoration: none;}
		.ie6-8 .nav .hot a:hover {color: #f60; text-decoration: underline;}

		.ie6-8 .nav .title {display: none;}

	@media screen and (min-width: 1000px) {
		.nav {width: 1000px; height: 38px;}
		
		.nav ul li {float: left; width: auto;}
		.nav ul li a {padding: 0 30px 0 30px;}
		.nav ul li.current {background: #f60;}
		.nav ul li:hover a {color: #f60;}
		.nav ul li.current:hover a {color: #fff;}

		.nav .hot {margin-left: 20px; padding-top: 8px;}
		.nav .hot a {padding: 0 5px 0 5px; font-size: 12px; color: #fff; text-decoration: none;}
		.nav .hot a:hover {color: #f60; text-decoration: underline;}

		.nav .title {display: none;}
	}

	@media screen and (min-width: 640px) and (max-width: 1000px) {
		.nav {width: auto; height: 38px;}

		.nav ul li {float: left; width: 14%; min-width: 50px;}

		.nav ul li.current {background: #f60;}
		.nav ul li:hover a {color: #f60;}
		.nav ul li.current:hover a {color: #fff;}

		.nav .hot {display:none;}
		.nav .title {display: none;}
	}

	@media screen and (max-width: 640px) {
		.navBar {margin-top: 0; height: auto; background: #444;}
		.nav {width: auto; height: auto;}

		.nav ul li {margin-top: 1px; width: 100%; min-width: 100px;background: #333;}
		
		.nav ul li a:active,
		.nav ul li a:hover {background: #f60;}

		.nav .hot {display:none;}

		.nav .title {position: relative; width: 100%; height: 38px; border-top: 1px solid #444; background: #333; text-align: center; font:normal 20px/35px "Microsoft YaHei", arial, serif; letter-spacing: 2px;}
		.nav .title a {color: #f60; text-decoration: none;}
		.nav .title .btn {position: absolute; right: 10px; top: 0; width: 34px; height: 34px; padding: 2px; background: url(btn.png) center center no-repeat; cursor: pointer;}
	}
	</style>
	<script type="text/javascript">
		var $$ = function (id) {
			return document.getElementById(id);
		}
		
		var move = function (obj, target) {
			var timer;
			clearInterval(timer);
			timer = setInterval(function () {
				var speed = (target - obj.offsetTop)/3;
				speed = speed > 0 ? Math.ceil(speed) : Math.floor(speed);
				if (Math.abs(obj.offsetTop - target) < 4) {
					clearInterval(timer);
					obj.style.marginTop = target + "px";
				} else {
					obj.style.marginTop = obj.offsetTop + speed + "px";
				}
			}, 30);

		}

		var toggle = function (menuId, btnId) {
			var menu = $$(menuId);
			var btn = $$(btnId);
			var countNum = 0;
			var menuHeight = menu.offsetHeight;
			menu.style.marginTop = - menuHeight + "px";
			btn.onclick = function () {
				if (countNum === 0) {
					move(menu, 0);
					countNum = 1;
				} else {
					move(menu, -menuHeight);
					countNum = 0;
				}
			}
		}

		onload = function () {
			if ($$("btn")) {
				toggle("menu", "btn");
			} else {
			}
		}

		onresize = function () {
			location.reload();
		}

	</script>
</head>
<body>
	<div class="navBar">
		<div class="nav">
			<ul id="menu">
				<li class="current"><a href="http://beyondweb.cn/" target="_blank" title="前端开发-BeyondWeb.cn">首页</a></li>
				<li><a href="http://beyondweb.cn/" target="_blank" title="前端开发-BeyondWeb.cn">电影</a></li>
				<li><a href="http://beyondweb.cn/" target="_blank" title="前端开发-BeyondWeb.cn">电视剧</a></li>
				<li><a href="http://beyondweb.cn/" target="_blank" title="前端开发-BeyondWeb.cn">动漫</a></li>
				<li><a href="http://beyondweb.cn/" target="_blank" title="前端开发-BeyondWeb.cn">综艺</a></li>
				<li><a href="http://beyondweb.cn/" target="_blank" title="前端开发-BeyondWeb.cn">纪录片</a></li>
				<li><a href="http://beyondweb.cn/" target="_blank" title="前端开发-BeyondWeb.cn">公开课</a></li>
			</ul>
			<!--判断浏览器是否是IE9,IE10或者是非IE浏览器-->
			<!--[if (gt IE 8) | !(IE)]><!-->
			<h1 class="title" id="title">
				<a href="http://beyondweb.cn/" target="_blank" title="前端开发-BeyondWeb.cn">风驰网</a>
				<span class="btn" id="btn"></span>
			</h1>
			<!--<![endif]-->
		</div>
	</div>
</body>
</html>
