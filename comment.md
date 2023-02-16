<html>
<head>
	<title>Comments Page</title>
</head>
<body>
	<h1 style="color: #8B0000">Comments</h1>
	<form action="#" method="POST">
		<label for="name">Name:</label>
		<input type="text" id="name" name="name" required><br>
        <label for="email">Email:</label>
		<input type="email" id="email" name="email" required><br>
		<label for="comment">Comment:</label><br>
		<textarea id="comment" name="comment" required></textarea><br>
		<input type="submit" value="Submit">
	</form>
	<hr>
	<h2 style="color: #8B0000">Previous comments</h2>
	<div id="comments">
		<!-- Example comment -->
		<div class="comment">
			<h3 style="color: #8B0000">Saavan Gade</h3>
			<p>When life gives you lemons you squeeze them into someones eyes.</p>
			<span class="date" style="color:#D3D3D3">2023-02-15 14:30:00</span>
		</div>
	</div>
</body>
</html>
