<template>
	<div id="header-wrapper">
		<div id="header-text">
			<h1>Knowledge base doesn't have to be boring</h1>
			<h3>Everything you need to manage your messaging</h3>
			<div class="search-container">
				<form action="">
					<input type="text" placeholder="Search for answers" name="search">
					<button type="submit"><i class="fa fa-search" style="color:#fff;"></i></button>
				</form>
			</div>
		</div>


	</div>
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>
@import '../scss/_variables.scss';

#header-text {
	text-align: center;
	font-family: $font-family;
	color: $text-black;
	padding: 20px;

	h1 {
		font-style: normal;
		font-weight: bold;
		font-size: 34px;
		line-height: 41px;
	}

	h3 {
		font-style: normal;
		font-weight: normal;
		font-size: 20px;
		line-height: 24px;
	}
}

input {
	border: 1px solid #EEEEEE;
}

#header-text {
	text-align: center;
	font-family: $font-family;
	color: $text-black;
	padding: 20px;


	h1 {
		font-style: normal;
		font-weight: bold;

	}

	h3 {
		font-style: normal;
		font-weight: normal;
		font-size: 20px;
		line-height: 24px;
	}
}

* {
	box-sizing: border-box;
}

body {
	margin: 0;
	font-family: lato;
}

.topnav {
	overflow: hidden;
	background-color: #e9e9e9;
}

.topnav a {
	float: left;
	display: block;
	color: black;
	text-align: center;
	padding: 14px 16px;
	text-decoration: none;
	font-size: 17px;
}

.topnav a:hover {
	background-color: #ddd;
	color: black;
}

.topnav a.active {
	background-color: #2196F3;
	color: white;
}

.topnav .search-container {
	float: right;
}

.topnav input[type=text] {
	padding: 6px;
	margin-top: 8px;
	font-size: 17px;
	border: none;
}

.topnav .search-container button {
	float: right;
	padding: 6px 10px;
	margin-top: 8px;
	margin-right: 16px;
	background: #ddd;
	font-size: 17px;
	border: none;
	cursor: pointer;
}

.topnav .search-container button:hover {
	background: #ccc;
}

input {
	padding: 0.5%;
	width: 37%;
	;
}

input,
input::placeholder {
	font: 16px;
	line-height: 19.2px;
	color: #9C9AA6;
}

@media screen and (max-width: 600px) {
	.topnav .search-container {
		float: none;
	}

	.topnav a,
	.topnav input[type=text],
	.topnav .search-container button {
		float: none;
		display: block;
		text-align: left;
		width: 100%;
		margin: 0;
		padding: 14px;
	}

	.topnav input[type=text] {
		border: 1px solid #ccc;
	}
}

.search-container button {
	padding: .8% 1%;
	background-color: #03A84E;
	border: none;
}</style>