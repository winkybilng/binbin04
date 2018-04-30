# binbin04
<!DOCTYPE html>
<html>
<head>
	<title>binbin 04</title>
<style type="text/css">
	ul li{
		width: 30px;
		height: 30px;
		list-style-type: none;
		background-color: red;
		border: 1px solid #999;
		float: left;
		color: white;
		margin: 5px;
		text-align: center;
	}
</style>
</head>
<body>
<input type="text" name="input" id="text">
<button id="left-in">左侧入</button>
<button id="left-out">左侧出</button>
<button id="right-in">右侧入</button>
<button id="right-out">右侧出</button>
<ul id="line">
	<li>10</li>
	<li>3</li>
	<li>7</li>
	<li>12</li>
	<li>11</li>
	<li>30</li>
</ul>
<script type="text/javascript">
	var a = document.getElementById("left-in");
	var b = document.getElementById("left-out");
	var c = document.getElementById("right-in");
	var d = document.getElementById("right-out");
	var e = document.getElementById("text");
	var f = document.getElementById("line");
	var ta = f.getElementsByTagName("li");
	var data = new Array;
	for (var i = 0; i < ta.length; i++) {
		data[i] = ta[i].innerHTML;
	}
  // 可以通过数组方式，但是每次显示相当于重新加载整个列表。
	function render(data) {
		f.innerHTML = "";
		for (var i = 0; i < data.length; i++) {
			var li = document.createElement("li");
			f.appendChild(li);
			li.innerHTML = data[i];
		}
	}
	c.onclick = function(){
		data.push(e.value);
		render(data);
	};
	a.onclick = function(){
		data.unshift(e.value);
		render(data);
	};
	b.onclick = function(){
		var item =data.shift();
		render(data);
		alert(item);
	};
	d.onclick = function(){
		var item =data.pop();
		render(data);
		alert(item);
	};
</script>
</body>
</html>
