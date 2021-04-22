<template>
  <div id="app">
  
	<nav class="navbar navbar-expand-sm navbar-dark bg-dark">
		<a href="/" class="navbar-brand ml-3"><img id="logo" src="src/assets/bft_logo_relief.svg" alt="Body Fit Training logo"></a>
	</nav>
  
	<div class="container-fluid flex-grow-1 d-flex">
	
		<div class="row flex-fill flex-column flex-sm-row">
	
			<div class="col-sm-3 col-md-2 sidebar flex-shrink-1 bg-dark pt-3" id="Navbar">
				<ul class="nav flex-sm-column">
					<li class="active"><a class="nav-link" href="/">Users</a></li>
					<li><a class="nav-link" href="#">Orders</a></li>
					<li><a class="nav-link" href="#">Requests</a></li>
					<li><a class="nav-link" href="#">Notes</a></li>
				</ul>
			</div>
	  
			<div class="table-responsive col-sm-9 col-sm-offset-3 col-md-10 col-md-offset-2 flex-grow-1 py-3">
		
				<h1>USERS</h1>
		
				<table class="table table-striped table-sm">
					<thead>
						<tr>
							<th>ID</th>
							<th>Name</th>
							<th>Gender</th>
							<th>Company</th>
							<th>Email</th>
						</tr>
					</thead>
					<tbody>
						<tr v-for="user in users">
							<td>{{ user.index }}</td>
							<td>{{ user.name }}</td>
							<td>{{ user.gender }}</td>
							<td>{{ user.company }}</td>
							<td>{{ user.email }}</td>
						</tr>
					</tbody>
				</table>
			</div>
			
		</div>
		
	</div>
 
	<footer class="bg-dark shadow py-1">
		<span id="copyright"> {{ copyright }} </span>
		{{ footer_message }}
	</footer>
 
</div>
  
</template>

<script>

	import json from './data/users.json'
	
	export default {
		name: 'app',
		data() {
			return { 
				users: json,
				message: 'hey', 
				copyright: 'Copyright © 2021', 
				footer_message: 'Page loaded on ' + new Date().toLocaleString() 
			}
		}
	}

</script>

<style lang="scss">

	$white: #fff;
	$blue: #30AEDF;
	$aqua: #5CBECB;
	$teal: #88CEB8;
	$lightblue: #A1E9FF;
	$lightteal: #C2FCFF;
	
	body {
		font-family: Arial, sans-serif;
	}
	
	#logo {
		width: 247px;
	}
	
	.nav-link, .nav-link:active {
		color: $teal; 
	}
	.nav-link:hover {
		color: $blue;
	}
	#Navbar {
		padding-top: 0.8rem !important;
	}
	.sidebar {
		height: 88vh;
		font-variant: small-caps;
	}
	nav {
		border-bottom: solid 2px $lightteal;
	}
	
	.table-striped tbody tr:nth-of-type(2n+1) {
		background-color: $white;
	}
	table {
		background-image: linear-gradient($lightblue, $teal);
	}
	.table-striped thead tr th,
	.table-striped tbody tr td	{
		border-color: #343a40;
	}
	
	footer {
		text-align: center;
		font-size: 0.8em;
		color: $lightteal;
		border-top: solid 2px $lightteal;
	}
	#copyright {
		color: $white;
		display: block;
		margin-bottom: 4px;
	}

	@media only screen and (max-width: 560px) {
		th:nth-child(3), td:nth-child(3) {
			display: none;
		}
		nav a.navbar-brand {
			margin-left: 0 !important;
		}
		ul.nav li a.nav-link {
			padding-left: 0;
		}
		div#Navbar {
			padding-top: 0 !important;
		}
		.sidebar {
			height: 46px;
			border-bottom: solid 2px $lightteal;
		}
	}
	
	@media only screen and (max-width: 400px) {
		th:nth-child(1), td:nth-child(1) {
			display: none;
		}
		th:nth-child(4), td:nth-child(4) {
			display: none;
		}
		.sidebar {
			height: 46px;
			border-bottom: solid 2px $lightteal;
		}
	}
	
	@media only screen and (max-width: 300px) {
		th:nth-child(5), td:nth-child(5) {
			display: none;
		}		
		.sidebar {
			font-size: 0.8rem;
			height: 40px;
		}
	}

</style>
