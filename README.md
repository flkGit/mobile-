# 移动端开发小技巧


### HTML模板
<code>
	<html>
	<head>
		<title></title>
		<meta charset="utf-8" />
		<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no" />
	</head>
	<body>

		<script>
		document.documentElement.style.fontSize = document.documentElement.clientWidth / 7.5 + 'px';
		</script>
	</body>
	</html>
</code>