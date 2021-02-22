<script lang="ts">
	import { Router, Link, Route } from "svelte-routing";
	import Home from './home/Home.svelte';
import Navbar from "./home/Navbar.svelte";
	import Paintings from "./paintings/Paintings.svelte";
	export let url = "";
</script>


<Router url={url}>
	<Navbar>
		<Link to="/">Home</Link>
		<Link to="paintings">Paintings</Link>
	</Navbar>
	<div>		  
		<Route path="paintings"><Paintings /></Route>
		<Route path="/"><Home /></Route>
	</div>
</Router>

